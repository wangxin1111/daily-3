# 2016-09-30 工作日报
=====================

* JDBC
  * build.gradle 文件 在dependencies下增加 compile 'mysql:mysql-connector-java:5.1.39'
  * 查询

```
import java.sql.*;

import static java.lang.Class.forName;

/**
 * Created by Administrator on 2016/9/30.
 */
public class JDBCTest {
    public static void main(String[] args) {
    	//固定格式
        String driver = "com.mysql.jdbc.Driver";
        String url = "jdbc:mysql://localhost:3306/yukunqiao_db?useUnicode=true&characterEncoding=utf-8&useSSL=false";
        String username = "root";
        String password = "ykq92";
        try {
            forName(driver);
            Connection connection = DriverManager.getConnection(url, username, password);
            

            StringBuffer sb = new StringBuffer();
            //注意空格
            sb.append("SELECT                       ");
            sb.append("id,name,sex,birthday,password ");
            sb.append("FROM                         ");
            sb.append("user_                        ");
//            sb.append("WHERE                        ");
//            sb.append("name = '于坤巧';             ");
//            System.out.println(sb.toString());
            Statement st = connection.createStatement();
            ResultSet rs = st.executeQuery(sb.toString());

			//循环输出
            while (rs.next()) {
                int id = rs.getInt("id");
                String name = rs.getString("name");
                System.out.println(id + ";" + name);
            }


        } catch (ClassNotFoundException e) {
            e.printStackTrace();
        } catch (SQLException e) {
            e.printStackTrace();
        }

    }

}
```