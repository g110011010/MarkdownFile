## Chapter2
### 2.1
1. 活动：活动是一种能够包含用户界面的组件，主要用于和用户进行交互。
### 2.2 手动创建一个活动
1. 配置布局文件
```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical" android:layout_width="match_parent"
    android:layout_height="match_parent">
    <!--定义一个按钮-->
    <!--第一行-->
    <!--@+id/id_name表示在xml中定义一个id-->
    <!--在xml中引用一个id使用@id/id_name-->
    <!--第二行-->
    <!--定义元素的宽度-->、
    <!--match_parent表示让此元素和父元素一样宽-->
    <!--第三行-->
    <!--定义高度-->
    <!--wrap_content表示高度只要能够刚好容下里面的内容就好-->
    <!--第四行定义了按钮里面显示的内容里面显示的-->
    <Button
        android:id="@+id/button"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Button1" />
</LinearLayout>
```
2. 在活动中加载布局
	```java
	
	import android.support.v7.app.AppCompatActivity;
	import android.os.Bundle;
	
	public class FirstActivity extends AppCompatActivity {
	
	    @Override
	    protected void onCreate(Bundle savedInstanceState) {
	        super.onCreate(savedInstanceState);
	//        调用setContentView方法给当前活动添加一个布局
	        setContentView(R.layout.first_layout);
	    }
	}
	
	```
3. 在AndroidManifest 文件中注册活动
```xml
<?xml version="1.0" encoding="utf-8"?>
<!--所有的活动都要在此文件下注册才能够生效-->
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.example.sf.activitytest">
<!--活动的注册声明要放在application标签内-->
    <application
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/AppTheme">
        <!--注册自己创建的活动，Android Stdio会自动帮忙注册生成-->
        <!--android.name属性指定了具体注册的是哪一个活动-->
        <!--.FirstActivity是com.example.sf.activitytest.FirstActivity的缩写，由于在最外层的manifest标签中已经通过
        package属性指明了程序的包名-->
        <!--android:label属性指明了活动中标题栏的内容-->
        <!--给主活动指定的label不仅会成为标题栏的内容，还会成为启动器中应用程序显示的名字-->
        <activity android:name=".FirstActivity"
            android:label="This is FirstActivity">
            <!--配置主活动-->
            <!--如果应用程序没有配置任何一个活动作为主活动，这个程序仍然是可以正常安装的，只是你无法再启动器中看到或者打开这个程序-->
            <intent-filter>
                <action android:name="android.intent.action.MAIN"/>
                <category android:name="android.intent.category.LAUNCHER"/>
            </intent-filter>
        </activity>
    </application>

</manifest
```
4. 使用Toast发送短小信息给用户
```java
package com.example.sf.activitytest;

import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.Toast;

public class FirstActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
//        调用setContentView方法给当前活动添加一个布局
        setContentView(R.layout.first_layout);
//        可以通过findViewById方法获取到在布局中定义的元素
//        findViewById()方法返回的是一个View对象，我们需要向下转型为将他向下转型为button对象
        View button1= findViewById(R.id.button1);
        if (button1 instanceof Button){
            Button button=(Button)button1;
//            使用setOnClickListener()方法为button对象注册一个监听器
//            按钮点击事件发生时，就会执行监听器中的onClick()方法
            button.setOnClickListener(new View.OnClickListener(){

                @Override
                public void onClick(View v) {
//Toast是Android系统中非常好用的提醒方式，在程序中可以使用它将一些短小的信息通知给用户
//                  静态方法makeTest()创建了一个Toast对象，其中有三个参数
//                    1. Context，也就是Toast要求的上下文
//                      2. Toast显示的文本内容
//                    3. Toast显示的时长
//                    调用show()方法将Toast方法显示出来
                    Toast.makeText(FirstActivity.this,"you have clicked button1",Toast.LENGTH_LONG).show();
                }
            });
        }
    }
}

```
#### 2.2.5 在活动中使用Menu
1. 在res目录下创建一个menu文件夹，然后在此文件夹下创建一个菜单文件，命名为main
```xml
<?xml version="1.0" encoding="utf-8"?>
<menu xmlns:android="http://schemas.android.com/apk/res/android">
<!--<item>标签用于创建某个具体的菜单项-->
    <!--通过android:id给菜单项指定一个唯一的标识符-->
    <!--通过android：title给这个菜单项指定一个唯一的标识符-->
    <item
        android:id="@+id/add_item"
        android:title="Add"/>
    <item
        android:id="@+id/remove_item"
        android:title="Remove"/>

</menu>
```
#### 2.2.6销毁当前对象
Activity类提供了finish方法用于销毁当前对象。
### 2.3
1. Intent：Intent是Android程序中各个组件之间进行交互的一种重要方式，它不仅可以指明当前组件想要执行的动作，还可以在不同的组件之间传递数据。Intent一般可以用于启动活动，启动服务，发送广播等任务场景。
2. Intent大致分为两种：显式Intent和隐式Intent
* **显式活动**：
```java
 /*
        * 点击按钮启动另外一个活动*/
        findViewById(R.id.button4).setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
//                创建一个Intent对象，其中第一个参数表适用于启动活动的上下文，第二个参数用于表示要启动的活动
                Intent intent=new Intent(FirstActivity.this,SecondActivity.class);
//                使用此方法启动另外一个活动
                startActivity(intent);
                //结束当前活动
                finish();
            }
        });
```
* **隐式活动**：隐式活动并不明确指出我们想要启动哪一个活动，而是指定了一系列更为抽象的action和category等信息，然后交由系统去分析这个Intent，并帮助我们找出合适的活动（能够响应我们这Intent的活动）去启动
```xml
 <activity android:name=".SecondActivity"
            android:label="this is second activity">
            <intent-filter>
                <!--指明了当前活动能够响应com.example.activitytest.ACTION_START这个action-->
                <action android:name="com.example.activitytest.ACTION_START"/>
                <!--更精确的指明了当前活动所能够响应的Intent还可能带有category.-->
                <!--只有<action><category>中的内容能够同时匹配上Intent中指定的action和category，这个活动才能够响应intent-->
                <!--这里指定的是一个默认的category，startActivity()会自动将这个category添加到intent中-->
                <category android:name="android.intent.category.DEFAULT"/>
            </intent-filter>
        </activity>
```

```java
     /*
        * 点击按钮启动另外一个活动*/
        findViewById(R.id.button4).setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
//                创建一个Intent对象，使用隐式intent启动一个启动一个活动
                Intent intent=new Intent("android.intent.category.DEFAULT");
                //                添加对应的category，此处的添加可以省略，因为添加的是默认的category
                intent.addCategory("android.intent.category.DEFAULT");
//                使用此方法启动另外一个活动
                startActivity(intent);
            }
        });
```
3. intent不仅可以启动自己程序内部的活动，还可以启动其它程序的活动，这使得Android系统中多个程序之间的功能共享成为了可能。
```java
//        点击按钮使用系统默认浏览器打开百度首页
        findViewById(R.id.baidu).setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
//                指定action为android系统内置的action
                Intent intent=new Intent(Intent.ACTION_VIEW);
//                setDate()用于指定当前Intent正在操作的数据
//                Uri.parse()将一个网址字符串解析为一个Uri对象
                intent.setData(Uri.parse("http://www.baidu.com"));
                startActivity(intent);
            }
        });

//        点击按钮拨打电话10086
        findViewById(R.id.activity31).setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Intent intent=new Intent(Intent.ACTION_DIAL);
                intent.setData(Uri.parse("tel:10086"));
                startActivity(intent);
            }
        });
```
设定自己的活动能够响应的隐式intent
```xml
 <activity android:name=".ThirdActivity">
        <!--在<intent-filter>标签中使用<data>标签可以更清楚的指明当前活动能够响应什么类型的数据-->
            <intent-filter>
                    <action android:name="android.intent.action.VIEW"/>
                    <category android:name="android.intent.category.DEFAULT"/>
                <!--android:scheme  用于指定数据的协议部分  
                android:host  用于指定数据的主机名部分如“www.baidu.com” 
                android:port  用于指定数据的端口部分
                android:path  用于指定主机名和端口之后的部分
                 android:mimeType 用于指定可以处理的数据类型，允许使用通配符的方式进行指定-->
                    <data android:scheme="http" />
             </intent-filter>
        </activity>
```

4. 使用Intent向下一个活动传递数据
```java
//向下一个活动传递数据
        /*
        * 点击按钮启动另外一个活动*/
        findViewById(R.id.button4).setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
//                创建一个Intent对象，使用隐式intent启动一个启动一个活动
                Intent intent=new Intent("android.intent.category.DEFAULT");
//                添加对应的category，此处的添加可以省略，因为添加的是默认的category
                intent.addCategory("android.intent.category.DEFAULT");
//                向下一个action传递数据，第一个参数是键，用于从后面Intent中取值，第二个参数时真正要传递的数据
                intent.putExtra("extra_data","here is the message to next action");
//                使用此方法启动另外一个活动

                startActivity(intent);
            }
        });
```
```java
//从上一个活动接受数据
protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        //                获取用于启动本action的intent
        Intent getString=getIntent();
//                获取传入的数据
        String message=getString.getStringExtra("extra_data");
//                输出获取的数据到日志
        Log.d("SecondActivity", message);
        setContentView(R.layout.activity_second);
        findViewById(R.id.button3).setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Toast.makeText(SecondActivity.this, "this is second activity", Toast.LENGTH_SHORT).show();
            }
        });
        findViewById(R.id.back_activity1).setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                finish();
            }
        });
//        点击按钮使用系统默认浏览器打开百度首页
        findViewById(R.id.baidu).setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {

//                指定action为android系统内置的action
                Intent intent=new Intent(Intent.ACTION_VIEW);
//                setDate()用于指定当前Intent正在操作的数据
//                Uri.parse()将一个网址字符串解析为一个Uri对象
                intent.setData(Uri.parse("http://www.baidu.com"));
                startActivity(intent);
            }
        });
    }
}
```
5. 返回数据给上一个活动，使用startActivityForResult()
```java
        /*
        * 点击按钮启动另外一个活动*/
        findViewById(R.id.button4).setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
//                创建一个Intent对象，使用隐式intent启动一个启动一个活动
                Intent intent=new Intent("android.intent.category.DEFAULT");
//                添加对应的category，此处的添加可以省略，因为添加的是默认的category
                intent.addCategory("android.intent.category.DEFAULT");
//                向下一个action传递数据，第一个参数是键，用于从后面Intent中取值，第二个参数时真正要传递的数据
                intent.putExtra("extra_data","here is the message to next action");
//                使用此方法启动另外一个活动

                //第二个参数是请求码可以自定义，只要唯一就好，用于之后的回调中判断数据的来源
//                使用此方法启动一个活动，在启动的活动被销毁的时候会调用本活动的onActivityResult()来接受反悔的数据
                startActivityForResult(intent,1);
            }
        });

  /*
    * 使用startActivityForResult()方法启动新活动，在新活动销毁的时候自动调用此方法，用于获取新活动返回的数据
    * @param requestCode 启动活动时传入的请求码
    * @param resultCode 返回数据时传入的处理结果
    * @param data 带有返回数据的Intent对象*/
    @Override
    protected void onActivityResult(int requestCode,int resultCode,Intent data){
        switch (requestCode){
            case 1:
                if(resultCode==RESULT_OK){
                    String returnMessage=data.getStringExtra("data_return");
                    Log.d("FirstActivity", returnMessage);
                }
                break;
            default:
        }
    }
```

```java
//点击按钮注销活动，并返回数据给启动者
      findViewById(R.id.back_activity1).setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Intent intent=new Intent();
                intent.putExtra("data_return","Hello,this is the message to the up action");
//               是专门用于向上一个方法返回数据的，第一个参数用于向上一个活动返回处理结果，第二个参数返回带有返回数据的intent对象
                setResult(RESULT_OK,intent);
                finish();
            }
        });
```
### 

	* [Chapter2](#chapter2)
		* [2.1](#21)
		* [2.2 手动创建一个活动](#22-手动创建一个活动)
			* [2.2.5 在活动中使用Menu](#225-在活动中使用menu)
			* [2.2.6销毁当前对象](#226销毁当前对象)
		* [2.3](#23)
		* [2.4](#24)

2.4
1. android是通过任务来管理活动的。一个任务就是一组存储在栈中的活动的集合，这个栈也被称作返回栈。
2. 启动一个新活动是将活动入栈的过程，按返回键是将栈顶活动销毁的过程。
3. 每个活动在其生命周期都会有最多四种状态：


状态|描述
--|---|--
运行状态|当一个活动位于返回栈的栈顶时，这个活动就处于运行状态。系统最不愿意回收的就是出于运行状态的活动，因为这会带来很严重的用户体验。
暂停状态|当一个活动不再处于栈顶位置，但是仍然可见时，这个活动就进入了暂停状态。（处于运行状态的活动不沾满屏幕时，下层活动就是可见的），只有在内存极低的情况下，系统才会去考虑回收这种状态的活动
停止状态|当一个活动不再处于栈顶，并完全处于不可见状态的时候，活动就进入了停止状态。系统仍然会为这个活动保存相应的状态和成员变量。，但这并不是完全可靠的。，当其他地方需要内存的时候，处于停止状态的活动可能被系统回收。
销毁状态|当一个活动从返回栈中移除之后这个活动就变成了销毁状态。系统会倾向于回收处于这种状态的活动，从而保证内存的充足。
4. 活动的生命期：Activity类提供了七种回调方法，覆盖了活动生命周期的每一个环节。


方法|描述
--|---|--
onCreate()|活动第一次被创建时调用。你应该这种方法中完成活动的初始化操作。
onStart()|这个方法在活动由不可见变为可见时调用。
onResume（）|这个方法在活动准备好和用户进行交互时使用。此时的活动一定位于返回栈的栈顶，并且处于运行状态。
onPause（）|这个方法在系统准备去启动或者恢复另一个活动的时候调用
onStop（）|这个方法在活动完全不可见的时候调用。
onDestory()|这个方法在活动被销毁之前调用，之后方法将会变成销毁状态
onRestart()|这个方法使活动由停止状态变为运行状态之前调用
5. 模拟各个回调函数执行过程
活动设置：主活动x1、对话框式活动x1(子活动)、普通活动x1(子活动）
主活动中有两个按钮，分别点击可进入每个子活动
模拟过程一：启动程序->点击按钮进入普通活动->按返回键返回主活动

MainActivity|NormalActivity|comment
--|---|--
onStart()|**-**|进入主活动
onResume()|**-**|
onPause()|**-**|点击进入normalActivity
**-**|onStart()|
**-**|onResume()|
onStop()|**-**|
**-**|onPause()|点击返回键
onRestart()|**-**|
onStart()|**-**|
onResume()|**-**|
**-**|onStop()|
**-**|onDestory()|
模拟过程二：启动程序->点击按钮进入对话框式活动->按返回键返回主活动

MainActivity|DialogActivity|comment
--|---|--
onStart()|**-**|进入主活动
onResume()|**-**|
onPause()|**-**|点击进入DialogActivity
**-**|onStart()|
**-**|onResume()|点击返回键
onResume()|**-**|
**-**|onStop()|
**-**|onDestory()|
>当子活动没有完全覆盖住父活动时（父活动仍然可见），父活动的onStop（）方法不会被执行，如上。

6. 当活动进入停止状态（执行onStop()之后），活动是有可能被系统回收的，此时如果子活动要返回到这个已经被系统回收的活动，那么将会首先调用onCreate()方法。
7. 活动一旦被系统回收，其中所有的临时数据均将会消失。这样会严重影响用户体验，为了解决这一问题，可以应用回调方法onSaveInstanceState(),该方法能保证活动在被系统回收之前一定会被调用。因此我们可以在这个方法中的Boundle参数对临时数据进行保存。
```java
//存入数据
  @Override
    protected void onSaveInstanceState(Bundle outState){
        super.onSaveInstanceState(outState);
        String s="String you want to save";
        outState.putString("data_key",s);
    }
```

```java
//读取数据

 @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        if(savedInstanceState !=null){//判断是否已经有数据存入
            String data=savedInstanceState.getString("data_key");
            Log.d(TAG, "onCreate: "+data);
        }
        }
```

## Chapter 2 UI开发

### 3.2 常用控件的使用方法
#### 3.2.1TextView
