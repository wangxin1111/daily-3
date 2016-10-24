# 2016-10-18日报

* ```
  点击事件的方法：
  * 一、匿名内部类
  * 二、内部类
  * 三、实现onclicklistener接口
  * 四、按钮onclick按钮
  ```

* res/layout/events_activity.xml

  * ```
    <?xml version="1.0" encoding="utf-8"?>
    <LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
        android:orientation="vertical" android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:gravity="center">
        <Button
            android:id="@+id/mybutton_btn"
            android:text="按钮一"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_margin="15dp"
            android:onClick="onClick" />

    </LinearLayout>
    ```

* 匿名内部类

* ```
  package com.feicuiedu.android.clickonevents;

  import android.os.Bundle;
  import android.support.v7.app.AppCompatActivity;
  import android.view.View;
  import android.widget.Button;
  import android.widget.Toast;

  /**
   * Created by Administrator on 2016/10/18.
   */

  public class Mainevents extends AppCompatActivity {

     private Button mybutton_btn = null;

   
     @Override
     protected void onCreate(Bundle savedInstanceState) {

        super.onCreate(savedInstanceState);
        setContentView(R.layout.events_activity);
        mybutton_btn = (Button) findViewById(R.id.mybutton_btn);

        
        //一、匿名内部类
        mybutton_btn.setOnClickListener(new View.OnClickListener() {
           @Override
           public void onClick(View v) {
              //Toast(this,"",Toast.LENGTH_LONG),其中可用getApplicationContext()替换this
              Toast.makeText(getApplicationContext(),"点击事件一",Toast.LENGTH_LONG).show();
           }
        });
  ```

* 内部类

  ```
  package com.feicuiedu.android.clickonevents;

  import android.os.Bundle;
  import android.support.v7.app.AppCompatActivity;
  import android.view.View;
  import android.widget.Button;
  import android.widget.Toast;

  /**
   * Created by Administrator on 2016/10/18.
   */

  public class Mainevents extends AppCompatActivity {

     private Button mybutton_btn = null;

     @Override
     protected void onCreate(Bundle savedInstanceState) {

        super.onCreate(savedInstanceState);
        setContentView(R.layout.events_activity);
        mybutton_btn = (Button) findViewById(R.id.mybutton_btn);
        mybutton_btn.setOnClickListener(listener);
     }
        View.OnClickListener listener = new View.OnClickListener() {
           @Override
           public void onClick(View v) {
              Toast.makeText(getApplicationContext(), "点击事件二", Toast.LENGTH_LONG).show();
           }
        };
     }

  ```



* 实现onclicklistener接口

  ```
  package com.feicuiedu.android.clickonevents;

  import android.os.Bundle;
  import android.support.v7.app.AppCompatActivity;
  import android.view.View;
  import android.widget.Button;
  import android.widget.Toast;

  /**
   * Created by Administrator on 2016/10/18.
   */

  public class Mainevents extends AppCompatActivity implements View.OnClickListener{
     private Button mybutton_btn = null;


     @Override
     protected void onCreate(Bundle savedInstanceState) {

        super.onCreate(savedInstanceState);
        setContentView(R.layout.events_activity);
        mybutton_btn = (Button) findViewById(R.id.mybutton_btn);
        mybutton_btn.setOnClickListener(this);

     }

     //三、实现onclicklistener接口
     @Override
     public void onClick(View v) {
        if(v == mybutton_btn){
           Toast.makeText(this,"点击事件三",Toast.LENGTH_LONG).show();
        }
     }



  ```

* 按钮onclick按钮

  ```
  package com.feicuiedu.android.clickonevents;

  import android.os.Bundle;
  import android.support.v7.app.AppCompatActivity;
  import android.view.View;
  import android.widget.Button;
  import android.widget.Toast;

  /**
   * Created by Administrator on 2016/10/18.
   */
  public class Mainevents extends AppCompatActivity {

     private Button mybutton_btn = null;



     @Override
     protected void onCreate(Bundle savedInstanceState) {

        super.onCreate(savedInstanceState);
        setContentView(R.layout.events_activity);
        mybutton_btn = (Button) findViewById(R.id.mybutton_btn);

     //四、按钮onclick按钮
     public void onClick2(View v){
        Toast.makeText(this,"点击按钮四",Toast.LENGTH_LONG).show();
     }
  }



  ```

* 控件