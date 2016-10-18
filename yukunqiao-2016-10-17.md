# 2016-10-17日报

* 今天主要内容是daily日报(mvc模式<model,view,controller>)的讲解
* 日报共分为control,dao,db,entity,services,view六大部分
  * control:
    * DailyControl.java	涵盖了日报的增加，即writeDaily
    * UserControl.java   用户的登录(showLogin)和注册(showRegister)
  * dao
    * DailyDao.java	增加日报的sql语句(saveDaily)和查看日报列表的sql语句(getDailyByCondition)
    * UserDao.java        增加用户的sql语句(saveUser)和查看用户列表的sql语句(getUserByCondition)
  * db
    * DBUtils.java	新增，修改，删除的操作(modifyTable)和查询的操作(queryTable)
    * DBConn.java   数据库的连接
  * entity
    * Daily.java	日报表的列属性，以及属性的set，get方法
    * User.java        用户表的列属性，以及属性的set，get方法
  * services
    * DailyService.java	
    * UserService.java
  * view
    * main方法





* 注：程序在编程过程中难免会有异常出现，这时是要throws，还是要try/catch。绝大多数情况下，选择throws抛出异常，当程序在运行过程中需要对不合规范的操作进行提示时，此时选择try/catch

```
package com.feicuiedu.andori06.java.daily.db;

import java.io.IOException;
import java.sql.Connection;
import java.sql.ResultSet;
import java.sql.ResultSetMetaData;
import java.sql.SQLException;
import java.sql.Statement;
import java.util.ArrayList;
import java.util.LinkedHashMap;
import java.util.List;
import java.util.Map;

/**
 * Created by chenyan on 2016/10/10.
 */
public class DBUtils {

    // 新增，修改，删除的操作
    public static void modifyTable(String strSql) throws
            SQLException,
            IOException,
            ClassNotFoundException {
        Connection connection = null;

        connection = DBConn.getInstance().getConneciton();
        Statement st = null;
        st = connection.createStatement();
        st.executeUpdate(strSql);

    }

    // 查询的操作
    public static List<Map<String, Object>> queryTable(String strSql) {

        Connection connection = null;
        List<Map<String, Object>> lstResult = new ArrayList<Map<String, Object>>();
        try {
            connection = DBConn.getInstance()
                    .getConneciton();
            List<String> lstColumnNames = new ArrayList<String>();

            ResultSet rs = connection.createStatement()
                    .executeQuery(strSql);

            ResultSetMetaData rsm = rs.getMetaData();

            int colCount = rsm.getColumnCount();
            for (int i = 0; i < colCount; i++) {

                String columnName = rsm.getColumnName(i + 1);
                lstColumnNames.add(columnName.toLowerCase());
            }

            while (rs.next()) {

                LinkedHashMap<String, Object> resMap = new LinkedHashMap<String, Object>();
                for (String columnName : lstColumnNames) {
                    Object obj = rs.getObject(columnName);
                    resMap.put(columnName,
                            obj);
                }

                lstResult.add(resMap);
            }
        }
        catch (IOException e) {
            e.printStackTrace();
        }
        catch (ClassNotFoundException e) {
            e.printStackTrace();
        }
        catch (SQLException e) {
            e.printStackTrace();
        }


        return lstResult;
    }

}
```

```
package com.feicuiedu.andori06.java.daily.db;

import java.io.IOException;
import java.io.InputStream;
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.SQLException;
import java.sql.Statement;
import java.util.Properties;

/**
 * 数据库的连接
 * <p>
 * Created by chenyan on 2016/10/10.
 */
public class DBConn {

    private static DBConn dbConn;

    private DBConn() {

    }

    public static DBConn getInstance() {

        if (dbConn == null) {
            dbConn = new DBConn();
        }

        return dbConn;
    }


    public Connection getConneciton() throws
            IOException,
            ClassNotFoundException,
            SQLException {

        Properties properties = new Properties();

        InputStream inputStream = DBConn.class.getResourceAsStream("/config.properties");
        Connection connection = null;

        properties.load(inputStream);
        String driver = properties.getProperty("driver");
        String url = properties.getProperty("url");
        String userName = properties.getProperty("userName");
        String userPassword = properties.getProperty("userPassword");


        Statement st = null;
        ResultSet rs = null;

        // 注册驱动
        Class.forName(driver);

        // 根据驱动获得连接
        connection = DriverManager.getConnection(url,
                userName,
                userPassword);


        return connection;
    }
}
```

