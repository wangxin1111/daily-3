# 20161021日报

* 今天的主要任务是继续将日报系统的界面设置跳转，代码如下：

* ```
  package com.feicuiedu.android.daily;

  import android.content.Intent;
  import android.os.Bundle;
  import android.support.annotation.Nullable;
  import android.support.v7.app.AppCompatActivity;
  import android.view.View;
  import android.widget.Button;

  /**
   * Created by Administrator on 2016/10/21.
   */

  public class WelcomeMain extends AppCompatActivity {

      private Button btn_Check;
      private Button btn_Increase;
      private Button btn_Exit;
      @Override
      protected void onCreate(@Nullable Bundle savedInstanceState) {
          super.onCreate(savedInstanceState);
          setContentView(R.layout.welcome_activity);

          btn_Check = (Button) findViewById(R.id.btn_Cheak);
          btn_Increase = (Button) findViewById(R.id.btn_Increase);
          btn_Exit = (Button) findViewById(R.id.btn_exit);

          btn_Check.setOnClickListener(checkDirectory);
          btn_Increase.setOnClickListener(increasedaily);
          btn_Exit.setOnClickListener(exit);
      }

      private View.OnClickListener checkDirectory = new View.OnClickListener(){

          @Override
          public void onClick(View v) {
              Intent intent = new Intent();
              intent.setClass(WelcomeMain.this,DirectoryMain.class);
              startActivityForResult(intent,97);
          }
      };
      private  View.OnClickListener increasedaily = new View.OnClickListener() {
          @Override
          public void onClick(View v) {
              Intent intent = new Intent();
              intent.setClass(WelcomeMain.this,IncreaseMain.class);
              startActivityForResult(intent,96);
          }
      };
      private  View.OnClickListener exit = new View.OnClickListener() {
          @Override
          public void onClick(View v) {
              Intent intent = new Intent();
              intent.setClass(WelcomeMain.this,LoginMain.class);
              startActivityForResult(intent,93);
          }
      };
  }
  ```

```
package com.feicuiedu.android.daily;

import android.content.Intent;
import android.os.Bundle;
import android.support.annotation.Nullable;
import android.support.v7.app.AppCompatActivity;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;

/**
 * Created by Administrator on 2016/10/20.
 */

public class CheckDailyMain extends AppCompatActivity {
    private TextView dailyName;
    private EditText shouldFinishedWork;
    private EditText havaFinishedWork;
    private EditText unfinishedReason;
    private EditText questionAndAnswer;
    private Button btn_serve;
    private Button btn_cancle;
    @Override
    protected void onCreate(@Nullable Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.checkdaily_activity);

        dailyName = (TextView) findViewById(R.id.dailyname);
        shouldFinishedWork = (EditText) findViewById(R.id.infinish);
        havaFinishedWork = (EditText) findViewById(R.id.infinished);
        unfinishedReason = (EditText) findViewById(R.id.inreason);
        questionAndAnswer = (EditText) findViewById(R.id.inquesion);
        btn_serve = (Button) findViewById(R.id.serve);
        btn_cancle = (Button) findViewById(R.id.returnd);

        btn_serve.setOnClickListener(serve);
        btn_cancle.setOnClickListener(cancle);
    }

    private View.OnClickListener serve = new View.OnClickListener() {

        @Override
        public void onClick(View v) {
            //显示跳转
            Intent intent = new Intent();
            intent.setClass(CheckDailyMain.this, WelcomeMain.class);
            startActivityForResult(intent, 95);

        }
    };
    private View.OnClickListener cancle = new View.OnClickListener() {

        @Override
        public void onClick(View v) {
            //显示跳转
            Intent intent = new Intent();
            intent.setClass(CheckDailyMain.this, DirectoryMain.class);
            startActivityForResult(intent, 92);

        }
    };
}
```

```
package com.feicuiedu.android.daily;

import android.content.Intent;
import android.os.Bundle;
import android.support.annotation.Nullable;
import android.support.v7.app.AppCompatActivity;
import android.view.View;
import android.view.ViewGroup;
import android.widget.AdapterView;
import android.widget.BaseAdapter;
import android.widget.Button;
import android.widget.ListView;
import android.widget.TextView;
import android.widget.Toast;

import java.util.ArrayList;
import java.util.HashMap;
import java.util.List;
import java.util.Map;

/**
 * Created by Administrator on 2016/10/20.
 */

public class DirectoryMain extends AppCompatActivity {

    private ListView listView1;
    private List<Map<String,String>> list;

    @Override
    protected void onCreate(@Nullable Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.directory_activity);

        listView1 = (ListView) findViewById(R.id.listView1);
        list = getData();

        // 绑定适配器
        listView1.setAdapter(baseAdapter);

        // 监听事件
        listView1.setOnItemClickListener(oicl);
        //listView1.setOnClickListener(detail);
    }

    private AdapterView.OnItemClickListener oicl = new AdapterView.OnItemClickListener() {
        @Override
        public void onItemClick(AdapterView<?> parent, View view, int position, long id) {
            Toast.makeText(DirectoryMain.this,"position="+position+",id="+id,Toast.LENGTH_LONG).show();
        }
    };

    private List<Map<String,String>> getData() {

        List<Map<String,String>> tmp = new ArrayList<Map<String,String>>();

        for (int i = 0; i < 20; i++) {
            Map<String,String> map = new HashMap<String,String>();
            map.put("id",i+"");
            map.put("createDate","2016-10-"+i);
            map.put("name","2016-10-"+i+"日报");
            tmp.add(map);
        }

        return tmp;
    }

    private BaseAdapter baseAdapter = new BaseAdapter() {

        // 定义数据的个数
        @Override
        public int getCount() {
            return list.size();
        }

        // 定义每行数据的对象
        @Override
        public Map<String,String> getItem(int position) {
            return list.get(position);
        }

        // 定义每行的id值
        @Override
        public long getItemId(int position) {
            return position;
        }

        // 定义每行都 是什么样的布局,如何展示数据
        @Override
        public View getView(int position, View convertView, ViewGroup parent) {
            Map<String,String> tmpMap = getItem(position);

            String id = tmpMap.get("id");
            String createDate = tmpMap.get("createDate");
            String name = tmpMap.get("name");


            View view = getLayoutInflater().inflate(R.layout.listview_items_activity,null);

            TextView tvId = (TextView) view.findViewById(R.id.tvId);
            TextView tvName= (TextView) view.findViewById(R.id.tvName);
            TextView tvDate = (TextView) view.findViewById(R.id.tvDate);

            tvId.setText(id);
            tvDate.setText(createDate);
            tvName.setText(name);

            return view;
        }
    };


    /*private View.OnClickListener detail = new View.OnClickListener(){

        @Override
        public void onClick(View v) {
            Intent intent = new Intent();
            intent.setClass(DirectoryMain.this,CheckDailyMain.class);
            startActivityForResult(intent,90);
        }
    };*/
}

```

```
package com.feicuiedu.android.daily;

import android.content.Intent;
import android.os.Bundle;
import android.support.annotation.Nullable;
import android.support.v7.app.AppCompatActivity;
import android.view.View;
import android.widget.Button;
import android.widget.DatePicker;
import android.widget.EditText;
import android.widget.RadioButton;
import android.widget.RadioGroup;
import android.widget.TableLayout;
import android.widget.TextView;

/**
 * Created by Administrator on 2016/10/20.
 */

public class LogupMain extends AppCompatActivity {
    private EditText importName;
    private DatePicker calendar;
    private EditText importPassword;
    private EditText importconfirmPassword;
    private Button btn_Serve;
    private Button btn_Cancle;

    @Override
    protected void onCreate(@Nullable Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.logup_activity);

        importName = (EditText) findViewById(R.id.Uname);
        calendar = (DatePicker) findViewById(R.id.date);
        importPassword = (EditText) findViewById(R.id.Upassword);
        importconfirmPassword = (EditText) findViewById(R.id.Uconpass);
        btn_Serve = (Button) findViewById(R.id.serve);
        btn_Cancle = (Button) findViewById(R.id.cancle);

        btn_Serve.setOnClickListener(operate);
        btn_Cancle.setOnClickListener(login);
    }

    private View.OnClickListener operate = new View.OnClickListener(){

        @Override
        public void onClick(View v) {
            Intent intent = new Intent();
            intent.setClass(LogupMain.this,WelcomeMain.class);
            startActivityForResult(intent,100);
        }
    };
    private View.OnClickListener login = new View.OnClickListener(){

        @Override
        public void onClick(View v) {
            Intent intent = new Intent();
            intent.setClass(LogupMain.this,LoginMain.class);
            startActivityForResult(intent,94);
        }
    };


}
```

```
package com.feicuiedu.android.daily;

import android.content.Intent;
import android.os.Bundle;
import android.support.annotation.Nullable;
import android.support.v7.app.AppCompatActivity;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;

/**
 * Created by Administrator on 2016/10/20.
 */

public class IncreaseMain extends AppCompatActivity {
    private EditText dailyName;
    private EditText shouldFinishedWork;
    private EditText havaFinishedWork;
    private EditText unfinishedReason;
    private EditText questionAndAnswer;
    private Button btn_serve;
    private Button btn_cancle;
    @Override
    protected void onCreate(@Nullable Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.increase_activity);

        dailyName = (EditText) findViewById(R.id.indailyname);
        shouldFinishedWork = (EditText) findViewById(R.id.infinish);
        havaFinishedWork = (EditText) findViewById(R.id.infinished);
        unfinishedReason = (EditText) findViewById(R.id.inreason);
        questionAndAnswer = (EditText) findViewById(R.id.inquesion);
        btn_serve = (Button) findViewById(R.id.serve);
        btn_cancle = (Button) findViewById(R.id.returnd);

        btn_serve.setOnClickListener(serve);
        btn_cancle.setOnClickListener(cancle);
    }

    private View.OnClickListener serve = new View.OnClickListener() {

        @Override
        public void onClick(View v) {
            //显示跳转
            Intent intent = new Intent();
            intent.setClass(IncreaseMain.this, DirectoryMain.class);
            startActivityForResult(intent, 95);

        }
    };
    private View.OnClickListener cancle = new View.OnClickListener() {

        @Override
        public void onClick(View v) {
            //显示跳转
            Intent intent = new Intent();
            intent.setClass(IncreaseMain.this, WelcomeMain.class);
            startActivityForResult(intent, 92);

        }
    };
}
```

```
package com.feicuiedu.android.daily;

import android.content.Intent;
import android.os.Bundle;
import android.support.annotation.Nullable;
import android.support.v7.app.AppCompatActivity;
import android.view.View;
import android.widget.Button;
import android.widget.CheckBox;
import android.widget.EditText;
import android.widget.TableLayout;
import android.widget.TextView;

/**
 * Created by Administrator on 2016/10/20.
 */

public class LoginMain extends AppCompatActivity {

    private EditText importName;
    private EditText importPassword;
    private TextView forgetPassword;
    private Button btn_Login;
    private Button btn_Logup;


    @Override
    protected void onCreate(@Nullable Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.login_activity);
        importName = (EditText) findViewById(R.id.importName);
        importPassword = (EditText) findViewById(R.id.importPassword);
        forgetPassword = (TextView) findViewById(R.id.forget);
        btn_Login = (Button) findViewById(R.id.btn_login);
        btn_Logup = (Button) findViewById(R.id.btn_logup);

        btn_Logup.setOnClickListener(register);
        btn_Login.setOnClickListener(operate);
    }

    private View.OnClickListener register = new View.OnClickListener(){

        @Override
        public void onClick(View v) {
            //显示跳转
            Intent intent = new Intent();
            intent.setClass(LoginMain.this,LogupMain.class);
            startActivityForResult(intent,99);

        }
    };
    private View.OnClickListener operate = new View.OnClickListener(){

        @Override
        public void onClick(View v) {
            Intent intent = new Intent();
            intent.setClass(LoginMain.this,WelcomeMain.class);
            startActivityForResult(intent,98);
        }
    };


}
```

* 问题：
* 一个控件可以设置两个监听事件吗？
* 如何点击一个日报名，调转到详细的日报？增加一个日报，在列表中增添一笔记录？