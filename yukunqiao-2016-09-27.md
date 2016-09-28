# 2016-09-27工作日报
====================

1.已完成的工作内容

 * (1)正则表达式的作用：验证字符串是否与指定规则匹配
      
      本质：字符串规则，规则描述
      
   (2)常用正则表达式

  验证手机号
  
    import java.io.IOException;  

    import java.util.regex.Matcher;  

    import java.util.regex.Pattern;  

    publicclass ClassPathResource {  

    publicstaticboolean isMobileNO(String mobiles){  

      Pattern p = Pattern.compile("^((13[0-9])|(15[^4,\\D])|(18[0,5-9]))\\d{8}$");  

      Matcher m = p.matcher(mobiles);  

      System.out.println(m.matches()+"---");  

    return m.matches();  

      }  

    publicstaticvoid main(String[] args) throws IOException {  

      System.out.println(ClassPathResource.isMobileNO("12016155153"));  

      }  

      }  

    第二种方法：

    import java.util.regex.Matcher;  

    import java.util.regex.Pattern;  

      String value="手机号";  

      String regExp = "^[1]([3][0-9]{1}|59|58|88|89)[0-9]{8}$";  

      Pattern p = Pattern.compile(regExp);  

      Matcher m = p.matcher(value);  

    return m.find();//boolean
  
  验证邮箱
  
   String check = "^([a-z0-9A-Z]+[-|\\.]?)+[a-z0-9A-Z]@([a-z0-9A-Z]+(-[a-z0-9A-Z]+)?\\.)+[a-zA-Z]{2,}$";    
  
   Pattern regex = Pattern.compile(check);    
   
   Matcher matcher = regex.matcher("dffdfdf@qq.com");    
   
   boolean isMatched = matcher.matches();    
   
   System.out.println(isMatched);  
  
  验证身份证号
  
    简单的位数与数字校验

    
    var regex = /^(\d{15,15}|\d{18,18}|\d{17}(\d|X|x))$/;
    
    var regex = /^<span class="string">(/d{6})(18|19|20)?(/d{2})([01]/d)([0123]/d)(/d{3})(/d|X)?</span>$/;
    
    var regex = /(^/d{15}$/)|(^/d{17}(?:/d|x|X)$/);
    
    复杂的校验

    //这个可以验证15位和18位的身份证，并且包含生日和校验位的验证。     
    
    //如果有兴趣，还可以加上身份证所在地的验证，就是前6位有些数字合法有些数字不合法。   

    function isIdCardNo(num)   
    
    {     
    
    num = num.toUpperCase();    
    
    //身份证号码为15位或者18位，15位时全为数字，18位前17位为数字，最后一位是校验位，可能为数字或字符X。     
    
    if (!(/(^/d{15}$)|(^/d{17}([0-9]|X)$)/.test(num))){   
    
    alert('输入的身份证号长度不对，或者号码不符合规定！/n15位号码应全为数字，18位号码末位可以为数字或X。');   
    
    return false;   
    
    }   
    
    //校验位按照ISO 7064:1983.MOD 11-2的规定生成，X可以认为是数字10。   
    
    //下面分别分析出生日期和校验位   
    
    var len, re;   
    
    len = num.length;   
    
    if (len == 15){   
    
    re = new RegExp(/^(/d{6})(/d{2})(/d{2})(/d{2})(/d{3})$/);   
    
    var arrSplit = num.match(re);   

    
    //检查生日日期是否正确   
    
    var dtmBirth = new Date('19' + arrSplit[2] + '/' + arrSplit[3] + '/' + arrSplit[4]);   
    
    var bGoodDay;   
    
    bGoodDay = (dtmBirth.getYear() == Number(arrSplit[2])) &amp;&amp; ((dtmBirth.getMonth() + 1) == Number(arrSplit[3])) 
    
    &amp;&amp; (dtmBirth.getDate() == Number(arrSplit[4]));   
    
    if (!bGoodDay){   
    
    alert('输入的身份证号里出生日期不对！');     
    
    return false;   
    
    }
    else{   
    
    //将15位身份证转成18位   
    
    //校验位按照ISO 7064:1983.MOD 11-2的规定生成，X可以认为是数字10。   
    
    var arrInt = new Array(7, 9, 10, 5, 8, 4, 2, 1, 6, 3, 7, 9, 10, 5, 8, 4, 2);   
    
    var arrCh = new Array('1', '0', 'X', '9', '8', '7', '6', '5', '4', '3', '2');   
    
    var nTemp = 0, i;     
    
    num = num.substr(0, 6) + '19' + num.substr(6, num.length - 6);   
    
    for(i = 0; i &lt; 17; i ++){   
    
    nTemp += num.substr(i, 1) * arrInt[i];   
    
    }   
    
    num += arrCh[nTemp % 11];     
    
    return num;     
    
    }     
    
    }   
    
    if (len == 18){   
    
    re = new RegExp(/^(/d{6})(/d{4})(/d{2})(/d{2})(/d{3})([0-9]|X)$/);   
    
    var arrSplit = num.match(re);   

    
    //检查生日日期是否正确   
    
    var dtmBirth = new Date(arrSplit[2] + "/" + arrSplit[3] + "/" + arrSplit[4]);   
    
    var bGoodDay;   
    
    bGoodDay = (dtmBirth.getFullYear() == Number(arrSplit[2])) &amp;&amp; ((dtmBirth.getMonth() + 1) == Number(arrSplit[3])) &amp;&amp; (dtmBirth.getDate() == Number(arrSplit[4]));   
    
    if (!bGoodDay){   
    
    alert(dtmBirth.getYear());   
    
    alert(arrSplit[2]);   
    
    alert('输入的身份证号里出生日期不对！');   
    
    return false;   
    
    }else{   
    
    //检验18位身份证的校验码是否正确。   
    
    //校验位按照ISO 7064:1983.MOD 11-2的规定生成，X可以认为是数字10。   
    
    var valnum;   
    
    var arrInt = new Array(7, 9, 10, 5, 8, 4, 2, 1, 6, 3, 7, 9, 10, 5, 8, 4, 2);   
    
    var arrCh = new Array('1', '0', 'X', '9', '8', '7', '6', '5', '4', '3', '2');   
    
    var nTemp = 0, i;   
    
    for(i = 0; i &lt; 17; i ++){   
    
    nTemp += num.substr(i, 1) * arrInt[i];   
    
    }   
    
    valnum = arrCh[nTemp % 11];   
    
    if (valnum != num.substr(17, 1)){   
    
    alert('18位身份证的校验码不正确！应该为：' + valnum);   
    
    return false;   
    
    }   
    
    return num;   
    
    }   
    
    }   
    
    return false;   
    
    }     
    
    严格的校验方法


    var aCity={11:"北京",12:"天津",13:"河北",14:"山西",15:"内蒙古",21:"辽宁",22:"吉林",23:"黑龙江 ",
    
    31:"上海",32:"江苏",33:"浙江",34:"安徽",35:"福建",36:"江西",37:"山东",
    
    41:"河南",42:"湖北 ",43:"湖南",44:"广东",45:"广西",46:"海南",
    
    50:"重庆",51:"四川",52:"贵州",53:"云南",54:"西藏 ",
    
    61:"陕西",62:"甘肃",63:"青海",64:"宁夏",65:"新疆",
    
    71:"台湾",81:"香港",82:"澳门",91:"国外 "};
    
    function cidInfo(sId){   
    
    var iSum=0;
    
    var info="";   
    
    if(!/^d{17}(d|x)$/i.test(sId)){
    
    return false;
    
    }   
    
    sId=sId.replace(/x$/i,"a");   
    
    if(aCity[parseInt(sId.substr(0,2))]==null){ 
    
    return "Error:非法地区";
    
    }   
    
    sBirthday=sId.substr(6,4)+"-"+Number(sId.substr(10,2))+"-"+Number(sId.substr(12,2));   
    
    var d=new Date(sBirthday.replace(/-/g,"/"));
    
    if(sBirthday!=(d.getFullYear()+"-"+ (d.getMonth()+1) + "-" + d.getDate())){
    
    return "Error:非法生日";
    
    }   
    
    for(var i = 17;i&gt;=0;i --){
    
    iSum += (Math.pow(2,i) % 11) * parseInt(sId.charAt(17 - i),11);
    
    }
    
    if(iSum%11!=1)  return "Error:非法证号";  
    
    return aCity[parseInt(sId.substr(0,2))]+","+sBirthday+","+(sId.substr(16,1)%2?"男":"女")  
    
    }  
  
  验证银行卡号
  
  验证日期格式
  
  验证IP地址
  
      /**
    * 验证IP地址
    * 
    * @param 待验证的字符串
    
    * @return 如果是符合格式的字符串,返回 <b>true </b>,否则为 <b>false </b>
    
    */
    
    public static boolean isIP(String str) {
    
    String num = "(25[0-5]|2[0-4]\\d|[0-1]\\d{2}|[1-9]?\\d)";
    
    String regex = "^" + num + "\\." + num + "\\." + num + "\\." + num + "$";
    
    return match(regex, str);
    
    }

2.工作成果

 *Pattern , Matcher 类的使用

* 套路用法
   import java.util.regex.Matcher;
   
   import java.util.regex.Pattern;
   
   public class Test5 {
    
    public static void main(String[] args) {
    
       // 定义一个正则表达式字符串
    
       String expression = "(abc)*";
        
       // 定义一个需要验证的字符串
       
       String str = "";
        
       
       // 套路用法
       
       Pattern p = Pattern.compile(expression);
       
       Matcher m = p.matcher(str);
        
       
       // 请问 str符合 expression的规则吗？
       
       boolean bln = m.matches();
        
       
       // matches()方法返回true的话，那么就表示str负责expression的规则
       
       // 反之则不符合
       
       System.out.println(bln);
     
     }
    
    }
* public class Test5 {

   public static void main(String[] args) {

    // 定义一个正则表达式字符串
    
    String expression = "-?\\d{3}";
      
    // 定义一个需要验证的字符串
    
    String str = "-a222222";
      
       // 套路用法
    
    Pattern p = Pattern.compile(expression);
    
    Matcher m = p.matcher(str);
      
       // 请问 str符合 expression的规则吗？
      
       // 表示str中的字符串必须完全匹配expression
    
    boolean bln1 = m.matches();
      
       // 表示str中从开始位置字符到找到能匹配expression的字符串或者子字符串就可以了
    
    boolean bln2 =  m.lookingAt();
      
       // 表示匹配expression成功一次后，是否还有下一个组字符串与expression匹配
    
    boolean bln3 =  m.find();
      
       // matches()方法返回true的话，那么就表示str负责expression的规则
    
    // 反之则不符合
    
    System.out.println("bln1="+bln1);
    
    System.out.println("bln2="+bln2);
    
    System.out.println("bln3="+bln3);
   
   }

  }

* group()方法的使用
  
  import java.util.regex.Matcher;
  
  import java.util.regex.Pattern;
  
  /**
  
  - Created by chenyan on 2016/9/27.
  
  */
  
  public class Test6 {
  
  
  public static void main(String[] args) {
  
  String expression = "A(B(C))D";
  
  Pattern p = Pattern.compile(expression);
  
  Matcher m = p.matcher("ABCD");
  
  System.out.println("matches:" + m.matches());
  
  System.out.println("groupCount:" + m.groupCount());
  
  System.out.println("group():" + m.group());
  
  System.out.println("group(1):" + m.group(1));
  
  System.out.println("group(2):" + m.group(2));
  
  }
  
  }

* list

 * ArrayList  可变数组
 
    import java.util.ArrayList;
    
    import java.util.Iterator;
    
    import java.util.List;
    
    /**
    - Created by chenyan on 2016/9/27.
       */
       
      public class ListDemo {
      
      public static void main(String[] args) {
      
          // 创建
          
          List<String> list = new ArrayList<String>();
          
          
          // 添加
          
          list.add("毛泽东");
          
          list.add("周恩来");
          
          list.add("刘少奇");
          
          list.add(2,"朱德");
          
          // list.add("林彪");
          
          //  修改
          
          // list.set(0,"林彪");

    			// 删除
          
    			// list.remove(0);
          
    			list.remove("毛泽东");
    
    			// 查询遍历
          
    			for(int index = 0;index< list.size();index ++) {
          
    				String name = list.get(index);
            
    				System.out.println(name);
            
    			}
    
    			System.out.println("*******************************");
          
    			for (String name : list) {
          
    				System.out.println(name);
            
    			}
    
    			System.out.println("*******************************");
          
    			Iterator<String> it = list.iterator();
          
    			while(it.hasNext()) {
          
    				String name = it.next();
            
    				System.out.println(name);
            
    			}
          
    		}
        
    	}
      

    * LinkedList 链表

    	* 在集合任何位置（头部、中间、尾部）添加、获取

    	* 插入、删除操作频繁时，可使用LinkedList来提高效率

    	* LinkedList还额外提供对头部和尾部元素进行添加和删除操作的方法 

    	import java.util.ArrayList;
      
    	import java.util.Iterator;
      
    	import java.util.LinkedList;
      
    	import java.util.List;
    
    	/**
    	 * Created by chenyan on 2016/9/27.
    	 */
       
    	public class LinkedListDemo {
    
    		public static void main(String[] args) {

    			// 创建
          
    			LinkedList<String> list = new LinkedList<>();
    
    			// 添加
          
    			list.add("毛泽东");
    
    			list.add("周恩来");
    
    			list.add("刘少奇");
    
    			list.add(2,"朱德");
    
    			// list.add("林彪");
    
    			//  修改
          
    			// list.set(0,"林彪");

    			// 删除
          
    			// list.remove(0);
          
    			list.remove("毛泽东");
    
    			list.addFirst("陈独秀");
          
    			list.addLast("华国锋");
          
    			// 查询遍历
          
    			for(int index = 0;index< list.size();index ++) {
          
    				String name = list.get(index);
            
    				System.out.println(name);
            
    			}
    
    			System.out.println("*******************************");
          
    			for (String name : list) {
          
    				System.out.println(name);
            
    			}
    
    			System.out.println("*******************************");
          
    			Iterator<String> it = list.iterator();
          
    			while(it.hasNext()) {
          
    				String name = it.next();
            
    				System.out.println(name);
            
    			}
          
    		}
        
    	}

* set

  * Set接口也是Collection接口的子接口，但是与Collection或List接口不同的是，Set接口中不能加入重复的元素。
  
  * Set接口的定义： public interface Set<E> extends Collection<E>
  
  * Set接口的主要方法与Collection是一致的 
  
  * Set接口的实例无法像List接口那样进行双向输出
  
  * Set接口的常用子类 
  
    * HashSet (散列的存放) :
    
      HashSet是Set接口的一个实现类，
      
      主要的特点是：
      
      里面不能存放重复元素，
      
      采用散列的存储方式，所以是没有顺序(插入顺序)的。 
      
    import java.util.HashSet;
    
    import java.util.Iterator;
    
    import java.util.LinkedList;
    
    /**
    * Created by chenyan on 2016/9/27.
       */
       
      public class HashSetDemo {
      
      public static void main(String[] args) {
      

    			// 创建
          
    			HashSet<String> list = new HashSet<String>();
          
    
    			// 添加
          
    			list.add("毛泽东");
    
    			list.add("周恩来");
    
    			list.add("刘少奇");
    
    			// list.add("林彪");
    
    			//  修改
          
    			// list.set(0,"林彪");
    
    			// 删除
          
    			// list.remove(0);
          
    			// list.remove("毛泽东");

    			// 查询遍历

    			for (String name : list) {
          
    				System.out.println(name);
            
    			}
    
    			System.out.println("*******************************");
          
    			Iterator<String> it = list.iterator();
          
    			while(it.hasNext()) {
          
    				String name = it.next();
            
    				System.out.println(name);
            
    			}
          
    		}
        
    	}
    	
    	* TreeSet (有序的存放) :
    	
    		输入的数据进行有序排列
    
    		import java.util.Iterator;
        
    		import java.util.TreeSet;
    
    		/**
    		 * Created by chenyan on 2016/9/27.
    		 */
         
    		public class TreeSetDemo {
    
    			public static void main(String[] args) {

    				// 创建
            
    				TreeSet<String> list = new TreeSet<String>();
    
    				// 添加
            
    				list.add("b毛泽东");
    
    				list.add("a周恩来");
    
    				list.add("c刘少奇");
    
    				// list.add("林彪");
    
    				//  修改
            
    				// list.set(0,"林彪");
    
    				// 删除
            
    				// list.remove(0);
            
    				// list.remove("毛泽东");

    				// 查询遍历

    				for (String name : list) {
            
    					System.out.println(name);
    				}
    
    				System.out.println("*******************************");
            
    				Iterator<String> it = list.iterator();
    				while(it.hasNext()) {
            
    					String name = it.next();
              
    					System.out.println(name);
              
    				}
            
    			}
          
    		}




  
3.未完成的工作

 *
  
4.未完成的原因

 *
  
5.遇到的问题及解决方法

 * 
