# 最火Android开源项目MaterialDialog使用
---
开源地址：[https://github.com/open-android/RoundedImageView](https://github.com/open-android/RoundedImageView "开源项目地址")

# 运行效果

![](http://i.imgur.com/BpRjAuO.png)


## 使用步骤

### 1. 在project的build.gradle添加如下代码(如下图)

	allprojects {
	    repositories {
	        ...
	        maven { url "https://jitpack.io" }
	    }
	}

![](http://oi5nqn6ce.bkt.clouddn.com/itheima/booster/code/jitpack.png)


### 2. 在Module的build.gradle添加依赖

    compile 'com.github.open-android:RoundedImageView:v1.0.0'


### 3. 复制如下代码到xml

		<com.itheima.roundedimageview.RoundedImageView
	        android:layout_width="wrap_content"
	        android:layout_height="wrap_content"
	        android:src="@mipmap/icon_33"
	        android:scaleType="fitCenter"
	        app:riv_corner_radius="10dip"
	        app:riv_border_width="1dip"
	        app:riv_border_color="#333333"
	        app:riv_oval="false" />

		<!--
		    关键属性解释：
		
		    app:riv_corner_radius ： 四周角度
		    app:riv_border_width ：  描边宽度
		    app:riv_border_color ： 描边颜色
		    app:riv_oval="false"  ： 是否是原型 ， 若为true， 则上面的radius可不用设置。-->

### 细节

*  当然也可以使用代码来控制 

		RoundedImageView riv = new RoundedImageView(context);
		riv.setScaleType(ScaleType.CENTER_CROP); //缩放居中
		riv.setCornerRadius((float) 10); // 四周角度
		riv.setBorderWidth((float) 2); //描边大小
		riv.setBorderColor(Color.DKGRAY); //描边颜色
		riv.setImageDrawable(drawable); //图片设置
		riv.setBackground(backgroundDrawable); //背景设置
		riv.setOval(true); //是否为椭圆

* 当然也可以配合Picasso来对图片进行艺术处理 （黑白照）

		Transformation transformation = new RoundedTransformationBuilder()
          .borderColor(Color.BLACK)
          .borderWidthDp(3)
          .cornerRadiusDp(30)
          .oval(false)
          .build();
		
		Picasso.with(context)
		    .load(url)
		    .fit()
		    .transform(transformation)
		    .into(imageView);


欢迎关注微信公众号

![](http://oi5nqn6ce.bkt.clouddn.com/itheima/booster/code/qrcode.png)
