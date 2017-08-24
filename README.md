# SuperOptionItemView

常用选项条目布局控件 里面添加了一些常用的组件，也是借鉴以为大神的做法，这里表示非常感谢，学到了很多东西
+
+有１．OptionItemView 常用的选项条目布局控件
+ ２．封装的RecyclerView和Adapter
+ ３. ImagePicker
+  4 . nineGridImageView
+  5 . videoRecordView
+  6 . Emoji仿扣扣聊天功能表情选择输入
+  7 . 及在normal-libs中其他的一些常用view组件
+  8.GPSManager定位,ComparessHelper压缩图片，文件工具
+  9.SearchView搜索
+  10.videoPlayer播放
+  11.ClockView自定义闹钟
   12.自定义chartView，饼状图，柱状图，曲线图等
+
+具体可以下载了解一下
+
+　具体使用，很简单，方法一： 你可以通过添加依赖 在项目的build.gradle
+
+   allprojects {
+      repositories {
+          jcenter()
+         //添加这一行
+          maven { url 'https://jitpack.io' }
+      }
+  }
+
+//在module里面build.gradle添加依赖
+
+dependencies {
+    ...
+	compile 'com.github.SingalLine:OptionItemView:-SNAPSHOT'
+}
+
+方法二：https://github.com/SingalLine/OptionItemView
+选择直接下载将module直接填加到自己项目中
+
+比如：OptionItemView的用法 在layout布局文件中使用
+
+  <com.singal.zy.library.OptionItemView
+        android:id="@+id/option_item_view"
+        android:layout_width="match_parent"
+        android:layout_height="50dp"
+        app:left_image_margin_left="15dp"
+        app:left_src="@mipmap/ic_launcher"
+        app:left_text="左边"
+        app:left_text_color="#f00"
+        app:left_text_size="15sp"
+        app:right_src="@mipmap/ic_launcher"
+        app:right_text="右边"
+        app:splite_mode="true"
+        app:title="中间"/>
+
+    <!--app:splite_mode="true" 如果为false为整体点击，不拆分-->
+
+在activity中设置对应的事件
+
+    OptionItemView optionItemView = (OptionItemView) findViewById(R.id.option_item_view);
+
+    optionItemView.setOnOptionItemClickListener(new OptionItemView.OnOptionItemClickListener() {
+        @Override
+        public void leftOnClick() {
+            Toast.makeText(MainActivity.this, "点击了左边", Toast.LENGTH_SHORT).show();
+        }
+
+        @Override
+        public void centerOnClick() {
+            Toast.makeText(MainActivity.this, "点击了中间", Toast.LENGTH_SHORT).show();
+        }
+
+        @Override
+        public void rightOnClick() {
+            Toast.makeText(MainActivity.this, "点击了右边", Toast.LENGTH_SHORT).show();
+        }
+    });
+
+    optionItemView.setOnClickListener(new View.OnClickListener() {
+        @Override
+        public void onClick(View view) {
+            Toast.makeText(MainActivity.this, "点击了整体", Toast.LENGTH_SHORT).show();
+        }
+    });
+
+也可以自己在上面进行修改，变成自己想要的样式
