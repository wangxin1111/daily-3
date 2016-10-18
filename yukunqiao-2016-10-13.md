# 2016-10-13日报

* IP地址

  * 网络中设备的标识
  * 不易记忆，可用主机名
  * 本地回环地址：127.0.0.1 主机名：localhost

* 端口号

  * 用于标识进程的逻辑地址，不同进程的标识
  * 有效端口：0~65535，其中0~1024系统使用或保留端口

* 传输协议

  * 通讯的规则
  * 常见协议：TCP，UDP

* InetAddress类用来封装我们前面讨论的数字式的IP地址和该地址的域名。

* UDP

  * 将数据及源和目的封装成数据包中，不需要建立连接
  * 每个数据报的大小在限制在64k内
  * 因无连接，是不可靠协议
  * 不需要建立连接，速度快

* TCP

  * 建立连接，形成传输数据的通道。
  * 在连接中进行大数据量传输
  * 通过三次握手完成连接，是可靠协议
  * 必须建立连接，效率会稍低

* URL类有多种形式的构造函数：

  * URL ( String url)　//url代表一个绝对地址，URL对象直接指向这个资源
  * URL ( URL baseURL , String relativeURL)　//其中，baseURL代表绝对地址，relativeURL代表相对地址。　　
  * URL ( String protocol , String host , String file)　　//其中，protocol代表通信协议，host代表主机名，file代表文件名。
  * URL ( String protocol , String host , int port , String file)

* 利用HttpURLConnection来服务器交互的基本过程：

  * 将访问路径封装成URL对象，通过URL对象获取到HttpURLConnection。
  * 设置连接参数。
  * 连接到服务器。
  * 向服务器写数据(可选)。
  * 读取服务器返回的数据。

* 设置输入/输出流

  * connection.setDoOutput(true);
  * connection.setDoInput(true);

* 设置请求的方式为Get或者Post

  * connection.setRequestMethod(“GET”);
  * connection.setRequestMethod(“POST”);

* build.gradle 添加

  * ```
    compile 'org.json:json:20160810'
    ```

* ```
  import org.json.JSONArray;
  import org.json.JSONObject;

  import java.io.ByteArrayOutputStream;
  import java.io.IOException;
  import java.io.InputStream;
  import java.io.OutputStream;
  import java.net.HttpURLConnection;
  import java.net.MalformedURLException;
  import java.net.URL;
  import java.util.ArrayList;
  import java.util.HashMap;
  import java.util.List;
  import java.util.Map;

  /**
   * Created by chenyan on 2016/10/12.
   */
  public class NetTest {

      public static void main(String[] args) {

          try {

              String url = "http://118.244.212.82:9092/newsClient/news_list";
              //url代表一个绝对地址
              String params = "ver=1&subid=1&dir=1&nid=1&stamp=20140321&cnt=20";

              /*利用HttpURLConnection来服务器交互的基本过程：
              将访问路径封装成URL对象，通过URL对象获取到HttpURLConnection。
              设置连接参数。
              连接到服务器。
              向服务器写数据(可选)。
              读取服务器返回的数据。*/

              /*URLConnection与HttpURLConnection都是抽象类，无法直接实例化对象。
              其对象主要通过URL的openConnection()方法获得*/
              URL strUrl = new URL(url);
              //URL对象直接指向这个资源
              HttpURLConnection httpURLConnection = (HttpURLConnection) strUrl.openConnection();

              httpURLConnection.setConnectTimeout(5000);
              //设置输入/输出流
              httpURLConnection.setDoOutput(true);
              httpURLConnection.setDoInput(true);
              //设置请求的方式为Get或者Post(字母全部大写，Post为常用)
              httpURLConnection.setRequestMethod("POST");
              // httpURLConnection.setRequestMethod("POST");

              // 获取输出流
              OutputStream out = httpURLConnection.getOutputStream();
              out.write(params.getBytes());
              out.flush();

              if (httpURLConnection.getResponseCode() == 200) {

                  InputStream is = httpURLConnection.getInputStream();

                  byte[] data = read(is);
                  String str = new String(data, "UTF-8");
                  //System.out.println("str="+str);

                  JSONObject jsonObject = new JSONObject(str);

                  Map<String,Object> map = new HashMap<String,Object>();

                  map.put("message",jsonObject.get("message"));
                  map.put("status",jsonObject.get("status"));

                  JSONArray jsonArray = jsonObject.getJSONArray("data");
                  List<Map<String,Object>> tmpList = new ArrayList<Map<String,Object>>();

                  for (int i = 0; i <jsonArray.length() ; i++) {
                      JSONObject tmpObject = jsonArray.getJSONObject(i);

                      Map<String,Object> tmpMap = new HashMap<String,Object>();
                      tmpMap.put("summary",tmpObject.get("summary"));
                      tmpMap.put("icon",tmpObject.get("icon"));
                      tmpMap.put("stamp",tmpObject.get("stamp"));
                      tmpMap.put("title",tmpObject.get("title"));
                      tmpMap.put("nid",tmpObject.get("nid"));
                      tmpMap.put("link",tmpObject.get("link"));
                      tmpMap.put("type",tmpObject.get("type"));

                      tmpList.add(tmpMap);
                  }

                  map.put("data",tmpList);

                  System.out.println(map);
              }
              else {
                  System.out.println("连接失败");
              }

          }
          catch (MalformedURLException e) {
              e.printStackTrace();
          }
          catch (IOException e) {
              e.printStackTrace();
          }
          catch (Exception e) {
              e.printStackTrace();
          }
      }

      // 从流中读取数据
      public static byte[] read(InputStream inStream) throws Exception {
          ByteArrayOutputStream outStream = new ByteArrayOutputStream();
          byte[] buffer = new byte[1024];
          int len = 0;
          while ((len = inStream.read(buffer)) != -1) {
              outStream.write(buffer, 0, len);
          }
          inStream.close();
          return outStream.toByteArray();
      }
  }
  ```