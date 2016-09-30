# 2016-09-29工作日报
======================

* IO流

  * 流是一组有顺序的，有起点和终点的字节集合，是对数据传输的总称或抽象。
  * 所谓的IO就是指流的读(input输入)与写(output输出)操作的简称。 
  * Java对数据的操作是通过流的方式，IO流用来处理设备之间的数据传输。

* 流的分类

  * 根据数据流向不同分为：
    * 输入流（intput）： 输入流只能进行读操作
    * 输出流（output）：输出流只能进行写操作
  * 根据处理数据类型的不同分为：
    * 字节流：InputStream是所有字节输入流的祖先，而OutputStream是所有字节输出流的祖先。
    * 字符流：Reader是所有读取字符串输入流的祖先，而writer是所有输出字符串的祖先。

* File类

  | 方法                    | 说明                           |
  | :-------------------- | :--------------------------- |
  | boolean exists()      | 文件或目录是否存在                    |
  | boolean isFile()      | 是否是文件                        |
  | boolean isDirectory() | 是否是目录                        |
  | String  getName()     | 获取文件或目录的名字                   |
  | long  lastModified()  | 获取最后的修改日期的long值              |
  | long  length()        | 获取文件大小，字节为单位                 |
  | String[] list()       | 如果对象是目录，则返回目录下所有文件和目录名字的列表   |
  | mkdir()               | 创建File中的目录                   |
  | mkdirs()              | 创建File中的目录，如果父目录不存在，还会创建父目录  |
  | renameTo(File f)      | 修改文件的名称，会删除原文件               |
  | createNewFile()       | 如果File代表文件，则创建一个空文件          |
  | boolean delete()      | 删除文件或目录(如果目录下包含子目录或文件，则不能删除) |

  * 创建文件夹

    ```
    import java.io.File;

    /**
     * Created by Administrator on 2016/9/29.
     */
    public class Test {
        public static void main(String[] args){

            //创建一个File对象
            File file = new File("E:\\workspace\\IdeaProjects\\流");
            
            //判断文件夹是否存在
            if(!file.exists()){
                //不存在，创建文件夹
                file.mkdirs();
            }

        }
    }
    ```

  * 创建文件

    * 方法一：(只适用于Windows系统)

    ```
    import java.io.File;
    import java.io.IOException;

    /**
     * Created by Administrator on 2016/9/29.
     */
    public class Test {
        public static void main(String[] args){

            //根据文件所在文件夹对象，创建文件
            File fileDoc = new File("E:\\workspace\\IdeaProjects\\流","IO流.doc");

            //创建文件
            try {
                fileDoc.createNewFile();
            } catch (IOException e) {
                e.printStackTrace();
            }
        }

    }
    ```

    * 方法二：(适用于任何系统)

    ```
    import java.io.File;
    import java.io.IOException;

    /**
     * Created by Administrator on 2016/9/29.
     */
    public class Test {
        public static void main(String[] args){

            //根据文件所在文件夹对象，创建文件
            File fileDoc = new File("E:"+File.separator+"workspace"+File.separator+"IdeaProjects"+File.separator+"流"+File.separator+"IO流.doc");
            //File fileDoc = new File("E:\\workspace\\IdeaProjects\\流","IO流.doc");

            //创建文件
            try {
                fileDoc.createNewFile();
            } catch (IOException e) {
                e.printStackTrace();
            }
        }

    }
    ```

  * 删除文件

    ```
    import java.io.File;
    import java.io.IOException;

    /**
     * Created by Administrator on 2016/9/29.
     */
    public class Test {
        public static void main(String[] args){

            //要删除文件所在的位置及名称
            File fileDoc = new File("E:\\workspace\\IdeaProjects\\流","IO流.doc");
            //判断要删除的文件是否存在
            if(fileDoc.exists()){
                //存在，删除文件
                fileDoc.delete();
            }
            //不存在，创建新的文件
            try {
                fileDoc.createNewFile();
            } catch (IOException e) {
                e.printStackTrace();
            }
            
        }

    }
    ```

  * 判断类型

    ```
    import java.io.File;


    /**
     * Created by Administrator on 2016/9/29.
     */
    public class Test {
        public static void main(String[] args){

            //文件路径
            File file1 = new File("E:\\workspace\\IdeaProjects\\流\\IO流.doc");
            //文件夹路径
            File file2 = new File("E:\\workspace\\IdeaProjects\\流1");
            //判断file1是否是文件
            System.out.println(file1.isFile());
            //判断file2是否是路径
            System.out.println(file2.isDirectory());
            //获取文件的大小，单位为字节
            System.out.println("文件大小："+ file1.length());
            //获取文件的路径，两种方法对于文件夹与文件均可以
            System.out.println("文件路径："+ file2.getPath());
            System.out.println("文件路径："+file1);
    		System.out.println("文件的（绝对）路径:" + file1.getAbsolutePath());

        }

    }
    ```

  * 获取文件或目录的名字

    ```
    import java.io.File;

    /**
     * Created by Administrator on 2016/9/29.
     */
    public class Test {
        public static void main(String[] args){

            //文件路径
            File file1 = new File("E:\\workspace\\IdeaProjects\\流\\IO流.doc");
            //文件夹路径
            File file2 = new File("E:\\workspace\\IdeaProjects\\流1");
            //获取文件或目录名字
            System.out.println("文件名字："+ file1.getName());
            System.out.println("目录名字："+ file2.getName());
            
        }

    }
    ```

  * 获取最后的修改日期

    ```
    import java.io.File;

    /**
     * Created by Administrator on 2016/9/29.
     */
    public class Test {
        public static void main(String[] args){

            //文件路径
            File file1 = new File("E:\\workspace\\IdeaProjects\\流\\IO流.doc");
            //文件夹路径
            File file2 = new File("E:\\workspace\\IdeaProjects\\流1");
            //获取最后的修改日期
            System.out.println("文件最后的修改日期："+ file1.lastModified());
            System.out.println("目录最后的修改日期："+ file2.lastModified());

        }

    }
    ```

  * 给文件重命名

    ```
    import java.io.File;

    /**
     * Created by Administrator on 2016/9/29.
     */
    public class Test {
        public static void main(String[] args){

            File file = new File("E:\\workspace\\IdeaProjects\\流\\IO流.doc");
            //所谓的修改文件的名称，实际上是先把源文件内容复制一个新名称的新文件中，然后把源文件删除
            file.renameTo(new File("E:\\workspace\\IdeaProjects\\流\\","IO流_copy.doc"));

        }

    }
    ```

  * 列出指定文件夹下的所有文件和文件夹(包括子文件夹)

    ​