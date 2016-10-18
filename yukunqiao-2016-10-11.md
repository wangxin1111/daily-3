# 2016-10-11日报

* daily界面

* Android Studio LinearLayout

* ```
  <?xml version="1.0" encoding="utf-8"?>
  <LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
      android:orientation="vertical"
      android:layout_width="match_parent"
      android:layout_height="match_parent">

      <LinearLayout
          android:layout_width="match_parent"
          android:layout_height="400px"
          android:orientation="horizontal"
          android:background="@drawable/dailyinages">
      </LinearLayout>
      <LinearLayout
          android:layout_width="match_parent"
          android:layout_height="100px"
          android:orientation="horizontal">
          <TextView
              android:layout_width="200px"
              android:layout_height="match_parent"
              android:text="用户名:"
              android:gravity="center"
              android:textSize="50px"/>
          <EditText
              android:layout_width="match_parent"
              android:layout_height="match_parent"
              android:textSize="50px"/>/>
      </LinearLayout>
      <LinearLayout
          android:layout_width="match_parent"
          android:layout_height="100px"
          android:orientation="horizontal">
          <TextView
              android:layout_width="200px"
              android:layout_height="match_parent"
              android:text="密   码:"
              android:gravity="center"
              android:textSize="50px"/>
          <EditText
              android:layout_width="match_parent"
              android:layout_height="match_parent"
              android:textSize="50px"/>
      </LinearLayout>
      <LinearLayout
          android:layout_width="match_parent"
          android:layout_height="200px"
          android:orientation="horizontal">
          <CheckBox
              android:layout_width="wrap_content"
              android:layout_height="wrap_content"
              android:layout_gravity="center_vertical"/>
          <TextView
              android:layout_width="wrap_content"
              android:layout_height="match_parent"
              android:text="记住密码"
              android:gravity="center"
              android:textSize="50px"
              android:layout_weight="1"/>
          <TextView
              android:layout_width="wrap_content"
              android:layout_height="match_parent"
              android:text="忘记密码 ?"
              android:gravity="center"
              android:textSize="50px"
              android:layout_weight="5"
              android:textStyle="italic" />
      </LinearLayout>
      <LinearLayout
          android:layout_width="match_parent"
          android:layout_height="match_parent"
          android:orientation="horizontal">
          <Button
              android:layout_width="250px"
              android:layout_height="wrap_content"
              android:layout_gravity="center"
              android:layout_weight="1"
              android:text="登录" />
          <Button
              android:layout_width="250px"
              android:layout_height="wrap_content"
              android:layout_gravity="center"
              android:layout_weight="1"
              android:text="注册" />
      </LinearLayout>

  </LinearLayout>
  ```

* ```
  <?xml version="1.0" encoding="utf-8"?>
  <RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
      android:layout_width="match_parent"
      android:layout_height="match_parent">

      <!--注册用户页面-->
      <TableLayout
          android:id="@+id/draw1"
          android:layout_width="match_parent"
          android:layout_height="100dp"
          android:background="@drawable/dailytitle">
      </TableLayout>
      <TextView
          android:id="@+id/name"
          android:layout_width="wrap_content"
          android:layout_height="60dp"
          android:text="姓      名："
          android:textSize="30dp"
          android:gravity="bottom"
          android:layout_below="@id/draw1"/>
      <EditText
          android:id="@+id/Uname"
          android:layout_width="match_parent"
          android:layout_height="60dp"
          android:textSize="30dp"
          android:gravity="bottom"
          android:layout_below="@id/draw1"
          android:layout_toRightOf="@id/name" />
      <TextView
          android:id="@+id/sex"
          android:layout_width="wrap_content"
          android:layout_height="60dp"
          android:text="性       别："
          android:textSize="30dp"
          android:gravity="bottom"
          android:layout_below="@id/name"/>
      <RadioGroup
          android:id="@+id/Rgroup"
          android:layout_width="match_parent"
          android:layout_height="60dp"
          android:orientation="horizontal"
          android:layout_below="@id/Uname"
          android:layout_toRightOf="@id/sex">
          <RadioButton
              android:id="@+id/woman"
              android:layout_width="100dp"
              android:layout_height="60dp"
              android:text="女"
              android:textSize="30dp"
              android:layout_below="@id/Uname"
              android:layout_toRightOf="@id/sex"
              android:gravity="bottom"/>

          <RadioButton
              android:id="@+id/man"
              android:layout_width="100dp"
              android:layout_height="60dp"
              android:text="男"
              android:textSize="30dp"
              android:layout_below="@id/Uname"
              android:layout_toRightOf="@id/woman"
              android:gravity="bottom"/>
      </RadioGroup>


      <TextView
          android:id="@+id/birthday"
          android:layout_width="wrap_content"
          android:layout_height="60dp"
          android:text="出生日期:"
          android:textSize="30dp"
          android:gravity="bottom"
          android:layout_below="@id/sex" />
      <DatePicker
          android:id="@+id/date"
          android:layout_width="match_parent"
          android:layout_height="60dp"
          android:layout_gravity="center_horizontal"
          android:textSize="30dp"
          android:layout_below="@id/sex"
          android:layout_toRightOf="@id/birthday"
          />

      <TextView
          android:id="@+id/password"
          android:layout_width="wrap_content"
          android:layout_height="60dp"
          android:text="密     码："
          android:textSize="30dp"
          android:gravity="bottom"
          android:layout_below="@id/birthday"/>
      <EditText
          android:id="@+id/Upassword"
          android:layout_width="match_parent"
          android:layout_height="60dp"
          android:textSize="30dp"
          android:gravity="bottom"
          android:layout_below="@id/birthday"
          android:layout_toRightOf="@id/password" />
      <TextView
          android:id="@+id/conpass"
          android:layout_width="wrap_content"
          android:layout_height="60dp"
          android:text="确认密码："
          android:textSize="30dp"
          android:gravity="bottom"
          android:layout_below="@id/password"/>
      <EditText
          android:id="@+id/Uconpass"
          android:layout_width="match_parent"
          android:layout_height="60dp"
          android:textSize="30dp"
          android:gravity="bottom"
          android:layout_below="@id/password"
          android:layout_toRightOf="@id/conpass" />
      <Button
          android:id="@+id/serve"
          android:layout_width="200dp"
          android:layout_height="60dp"
          android:text="保存"
          android:textSize="30dp"
          android:layout_below="@id/conpass" />
      <Button
          android:id="@+id/cancle"
          android:layout_width="200dp"
          android:layout_height="60dp"
          android:text="取消"
          android:textSize="30dp"
          android:layout_below="@id/conpass"
          android:layout_toRightOf="@id/serve"/>

  </RelativeLayout>
  ```

* ```
  <?xml version="1.0" encoding="utf-8"?>
  <RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
      android:layout_width="match_parent"
      android:layout_height="match_parent">

      <!--增加日报界面-->
      <DatePicker
          android:id="@+id/cal"
          android:layout_width="match_parent"
          android:layout_height="60dp">
      </DatePicker>
      <TextView
          android:id="@+id/finish"
          android:layout_width="match_parent"
          android:layout_height="50dp"
          android:text="应完成工作："
          android:textSize="30dp"
          android:gravity="center_vertical"
          android:layout_below="@id/cal"/>
      <EditText
          android:id="@+id/infinish"
          android:layout_width="match_parent"
          android:layout_height="50dp"
          android:textSize="30dp"
          android:inputType="textMultiLine"
          android:layout_below="@id/finish"/>
      <TextView
      android:id="@+id/finished"
      android:layout_width="match_parent"
      android:layout_height="50dp"
      android:text="已完成工作："
      android:textSize="30dp"
      android:gravity="center_vertical"
      android:layout_below="@id/infinish"/>
      <EditText
          android:id="@+id/infinished"
          android:layout_width="match_parent"
          android:layout_height="50dp"
          android:textSize="30dp"
          android:inputType="textMultiLine"
          android:layout_below="@id/finished"/>
      <TextView
          android:id="@+id/reason"
          android:layout_width="match_parent"
          android:layout_height="50dp"
          android:text="未完成原因："
          android:textSize="30dp"
          android:gravity="center_vertical"
          android:layout_below="@id/infinished"/>
      <EditText
          android:id="@+id/inreason"
          android:layout_width="match_parent"
          android:layout_height="50dp"
          android:textSize="30dp"
          android:inputType="textMultiLine"
          android:layout_below="@id/reason"/>
      <TextView
          android:id="@+id/quesion"
          android:layout_width="match_parent"
          android:layout_height="50dp"
          android:text="遇到的问题及解决方法："
          android:textSize="30dp"
          android:gravity="center_vertical"
          android:layout_below="@id/inreason"/>
      <EditText
          android:id="@+id/inquesion"
          android:layout_width="match_parent"
          android:layout_height="50dp"
          android:textSize="30dp"
          android:inputType="textMultiLine"
          android:layout_below="@id/quesion"/>
      <Button
          android:id="@+id/serve"
          android:layout_width="133dp"
          android:layout_height="60dp"
          android:text="保存"
          android:textSize="30dp"
          android:layout_below="@id/inquesion" />
      <Button
          android:id="@+id/increase"
          android:layout_width="133dp"
          android:layout_height="60dp"
          android:text="新增"
          android:textSize="30dp"
          android:layout_below="@id/inquesion"
          android:layout_toRightOf="@id/serve"/>
      <Button
          android:id="@+id/returnd"
          android:layout_width="133dp"
          android:layout_height="60dp"
          android:text="返回"
          android:textSize="30dp"
          android:layout_below="@id/inquesion"
          android:layout_toRightOf="@id/increase"/>

  </RelativeLayout>
  ```

* ```
  <?xml version="1.0" encoding="utf-8"?>
  <RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
      android:layout_width="match_parent"
      android:layout_height="match_parent">

      <!--日报详细内容查看-->
      <TextView
          android:id="@+id/name"
          android:layout_width="match_parent"
          android:layout_height="60dp"
          android:text="于坤巧-2016-10-10日报"
          android:textSize="30dp">
      </TextView>
      <TextView
          android:id="@+id/finish"
          android:layout_width="match_parent"
          android:layout_height="50dp"
          android:text="应完成工作："
          android:textSize="30dp"
          android:gravity="center_vertical"
          android:layout_below="@id/name"/>
      <EditText
          android:id="@+id/infinish"
          android:layout_width="match_parent"
          android:layout_height="50dp"
          android:text="应完成工作"
          android:textSize="25dp"
          android:inputType="textMultiLine"
          android:layout_below="@id/finish"/>
      <TextView
          android:id="@+id/finished"
          android:layout_width="match_parent"
          android:layout_height="50dp"
          android:text="已完成工作："
          android:textSize="30dp"
          android:gravity="center_vertical"
          android:layout_below="@id/infinish"/>
      <EditText
          android:id="@+id/infinished"
          android:layout_width="match_parent"
          android:layout_height="50dp"
          android:text="已完成……"
          android:textSize="25dp"
          android:inputType="textMultiLine"
          android:layout_below="@id/finished"/>
      <TextView
          android:id="@+id/reason"
          android:layout_width="match_parent"
          android:layout_height="50dp"
          android:text="未完成原因："
          android:textSize="30dp"
          android:gravity="center_vertical"
          android:layout_below="@id/infinished"/>
      <EditText
          android:id="@+id/inreason"
          android:layout_width="match_parent"
          android:layout_height="50dp"
          android:text="原因"
          android:textSize="25dp"
          android:inputType="textMultiLine"
          android:layout_below="@id/reason"/>
      <TextView
          android:id="@+id/quesion"
          android:layout_width="match_parent"
          android:layout_height="50dp"
          android:text="遇到的问题及解决方法："
          android:textSize="30dp"
          android:gravity="center_vertical"
          android:layout_below="@id/inreason"/>
      <EditText
          android:id="@+id/inquesion"
          android:layout_width="match_parent"
          android:layout_height="50dp"
          android:text="方法"
          android:textSize="25dp"
          android:inputType="textMultiLine"
          android:layout_below="@id/quesion"/>
      <Button
          android:id="@+id/serve"
          android:layout_width="133dp"
          android:layout_height="60dp"
          android:text="保存"
          android:textSize="30dp"
          android:layout_below="@id/inquesion" />

      <Button
          android:id="@+id/returnd"
          android:layout_width="133dp"
          android:layout_height="60dp"
          android:text="返回"
          android:textSize="30dp"
          android:layout_below="@id/inquesion"
          android:layout_alignParentRight="true"/>
  </RelativeLayout>

  ```

* ```
  <?xml version="1.0" encoding="utf-8"?>
  <RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
      android:layout_width="match_parent"
      android:layout_height="match_parent"
      xmlns:tools="http://schemas.android.com/tools">

      <!--登陆后查看日报 目录-->
      <TextView
          android:id="@+id/date"
          android:layout_width="100dp"
          android:layout_height="60dp"
          android:text="日期"
          android:textSize="30dp"/>
      <TextView
          android:id="@+id/name"
          android:layout_width="300dp"
          android:layout_height="60dp"
          android:text="内容"
          android:textSize="30dp"
          android:layout_toRightOf="@id/date"/>
      <TextView
          android:id="@+id/date1"
          android:layout_width="100dp"
          android:layout_height="60dp"
          android:text="2016-10-10"
          android:textSize="20dp"
          android:layout_below="@id/date"/>
      <TextView
          android:id="@+id/name1"
          android:layout_width="300dp"
          android:layout_height="60dp"
          android:text="于坤巧-2016-10-10"
          android:textSize="20dp"
          android:layout_below="@id/name"
          android:layout_toRightOf="@id/date1"
          />
      <TextView
          android:id="@+id/date2"
          android:layout_width="100dp"
          android:layout_height="60dp"
          android:text="2016-10-10"
          android:textSize="20dp"
          android:layout_below="@id/date1"/>
      <TextView
          android:id="@+id/name2"
          android:layout_width="300dp"
          android:layout_height="60dp"
          android:text="于坤巧-2016-10-10"
          android:textSize="20dp"
          android:layout_below="@id/name1"
          android:layout_toRightOf="@id/date1"
          />

  </RelativeLayout>
  ```