# 2016-10-12日报

* Android Studio RelativeLayout

* manifests/AndroidManifest.xml

* ```
  <activity android:name=".MyMain">
      <intent-filter>
          <action android:name="android.intent.action.MAIN" />
          <category android:name="android.intent.category.LAUNCHER" />
      </intent-filter>
  </activity>
  ```

* java/(目录下第一个文件)

* ```
  public class MyMain extends AppCompatActivity {
      @Override
      protected void onCreate(@Nullable Bundle savedInstanceState) {
          super.onCreate(savedInstanceState);
          setContentView(R.layout.myactivity);
      }
  }
  ```

* res/layout/myactivity.xml

* ```
  <?xml version="1.0" encoding="utf-8"?>
  <RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
      android:layout_width="match_parent"
      android:layout_height="match_parent">

                  <TableLayout
                      android:id="@+id/table"
                      android:layout_gravity="center"
                      android:layout_width="match_parent"
                      android:layout_height="500px"
                      android:background="#ffffcc"
                      ></TableLayout>
                  <Button
                      android:layout_width="wrap_content"
                      android:layout_height="wrap_content"
                      android:text="CE"
                      android:id="@+id/CE"
                      android:layout_below="@id/table"/>
                  <Button
                      android:layout_width="wrap_content"
                      android:layout_height="wrap_content"
                      android:text="C"
                      android:id="@+id/C"
                      android:layout_toRightOf="@+id/CE"
                      android:layout_below="@id/table"/>
                  <Button
                      android:layout_width="wrap_content"
                      android:layout_height="wrap_content"
                      android:text="Esc"
                      android:id="@+id/Esc"
                      android:layout_toRightOf="@+id/C"
                      android:layout_below="@id/table"/>
                  <Button
                      android:layout_width="wrap_content"
                      android:layout_height="wrap_content"
                      android:text="/"
                      android:id="@+id/but1"
                      android:layout_toRightOf="@+id/Esc"
                      android:layout_below="@id/table"/>

                  <!--键盘第二行-->
                  <Button
                      android:layout_width="wrap_content"
                      android:layout_height="wrap_content"
                      android:text="7"
                      android:id="@+id/seven"
                      android:layout_below="@id/CE"/>
                  <Button
                      android:layout_width="wrap_content"
                      android:layout_height="wrap_content"
                      android:text="8"
                      android:id="@+id/eight"
                      android:layout_below="@id/CE"
                      android:layout_toRightOf="@id/seven"/>
                  <Button
                      android:layout_width="wrap_content"
                      android:layout_height="wrap_content"
                      android:text="9"
                      android:id="@+id/nine"
                      android:layout_below="@id/CE"
                      android:layout_toRightOf="@id/eight"/>
                  <Button
                      android:layout_width="wrap_content"
                      android:layout_height="wrap_content"
                      android:text="*"
                      android:id="@+id/but2"
                      android:layout_below="@id/CE"
                      android:layout_toRightOf="@id/nine"/>

                  <!--键盘第3行-->
                  <Button
                      android:layout_width="wrap_content"
                      android:layout_height="wrap_content"
                      android:text="4"
                      android:id="@+id/four"
                      android:layout_below="@id/seven"/>
                  <Button
                      android:layout_width="wrap_content"
                      android:layout_height="wrap_content"
                      android:text="5"
                      android:id="@+id/five"
                      android:layout_below="@id/eight"
                      android:layout_toRightOf="@id/four"/>
                  <Button
                      android:layout_width="wrap_content"
                      android:layout_height="wrap_content"
                      android:text="6"
                      android:id="@+id/six"
                      android:layout_below="@id/nine"
                      android:layout_toRightOf="@id/five"/>
                  <Button
                      android:layout_width="wrap_content"
                      android:layout_height="wrap_content"
                      android:text="-"
                      android:id="@+id/but3"
                      android:layout_below="@id/but2"
                      android:layout_toRightOf="@id/six"/>

                  <!--键盘第四行-->
                  <Button
                      android:layout_width="wrap_content"
                      android:layout_height="wrap_content"
                      android:text="1"
                      android:id="@+id/one"
                      android:layout_below="@id/four"/>
                  <Button
                      android:layout_width="wrap_content"
                      android:layout_height="wrap_content"
                      android:text="2"
                      android:id="@+id/two"
                      android:layout_below="@id/four"
                      android:layout_toRightOf="@id/one"/>
                  <Button
                      android:layout_width="wrap_content"
                      android:layout_height="wrap_content"
                      android:text="3"
                      android:id="@+id/three"
                      android:layout_below="@id/four"
                      android:layout_toRightOf="@id/two"/>
                  <Button
                      android:layout_width="wrap_content"
                      android:layout_height="wrap_content"
                      android:text="+"
                      android:id="@+id/but4"
                      android:layout_below="@id/four"
                      android:layout_toRightOf="@id/three"/>

                  <!--键盘第5行-->
                  <Button
                      android:layout_width="wrap_content"
                      android:layout_height="wrap_content"
                      android:text="()"
                      android:id="@+id/but5"
                      android:layout_below="@id/one" />
                  <Button
                      android:layout_width="wrap_content"
                      android:layout_height="wrap_content"
                      android:text="0"
                      android:id="@+id/zero"
                      android:layout_below="@id/one"
                      android:layout_toRightOf="@id/but5"/>
                  <Button
                      android:layout_width="wrap_content"
                      android:layout_height="wrap_content"
                      android:text="."
                      android:id="@+id/but6"
                      android:layout_below="@id/one"
                      android:layout_toRightOf="@id/zero"/>
                  <Button
                      android:layout_width="wrap_content"
                      android:layout_height="wrap_content"
                      android:text="="
                      android:id="@+id/but7"
                      android:layout_below="@id/one"
                      android:layout_toRightOf="@id/but6"/>


  </RelativeLayout>

  ```

* daily界面

* ```
  <?xml version="1.0" encoding="utf-8"?>
  <RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
      android:layout_width="match_parent"
      android:layout_height="match_parent">

      <TableLayout
          android:id="@+id/draw1"
          android:layout_width="match_parent"
          android:layout_height="500px"
          android:background="@drawable/dailytitle">
      </TableLayout>
      <TextView
          android:id="@+id/name"
          android:layout_width="200px"
          android:layout_height="150px"
          android:text="用户名:"
          android:gravity="center"
          android:textSize="50px"
          android:layout_below="@id/draw1"/>
      <EditText
          android:id="@+id/username"
          android:layout_width="match_parent"
          android:layout_height="150px"
          android:textSize="50px"
          android:layout_below="@id/draw1"
          android:layout_toRightOf="@id/name"/>
      <TextView
          android:id="@+id/password"
          android:layout_width="200px"
          android:layout_height="150px"
          android:text="密   码:"
          android:gravity="center"
          android:textSize="50px"
          android:layout_below="@id/name"/>
      <EditText
          android:id="@+id/userpassword"
          android:layout_width="match_parent"
          android:layout_height="150px"
          android:textSize="50px"
          android:layout_below="@id/username"
          android:layout_toRightOf="@id/password"/>
      <CheckBox
          android:id="@+id/checkbox1"
          android:layout_width="wrap_content"
          android:layout_height="wrap_content"
          android:layout_below="@id/password"/>
      <TextView
          android:id="@+id/remember"
          android:layout_width="wrap_content"
          android:layout_height="100px"
          android:text="记住密码"
          android:textSize="50px"
          android:layout_below="@id/password"
          android:layout_toRightOf="@id/checkbox1"/>
      <TextView
          android:id="@+id/forget"
          android:layout_width="wrap_content"
          android:layout_height="100px"
          android:text="记住密码?   "
          android:textSize="50px"
          android:textStyle="italic"
          android:layout_below="@id/userpassword"
          android:layout_alignParentRight="true"/>
      <Button
          android:id="@+id/login"
          android:layout_width="400px"
          android:layout_height="150px"
          android:text="登录"
          android:textSize="50px"
          android:layout_below="@id/remember"/>
      <Button
          android:id="@+id/logup"
          android:layout_width="400px"
          android:layout_height="150px"
          android:text="注册"
          android:textSize="50px"
          android:layout_below="@id/forget"
          android:layout_toRightOf="@id/login"
          android:layout_alignParentRight="true"/>


  </RelativeLayout>
  ```