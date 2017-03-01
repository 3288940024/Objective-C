###UILabel 标签
>UILable是iPhone界面最基本的控件，主要用来显示文本信息。

###属性
- ##### 创建

```
    CGRect rect = CGRectMake(100,200,50,50);
    UILabel *label = [[UILabel alloc]initWithFrame:rect];
```
- ##### text————设置和读取文本内容，默认nil
```
    label.text = @"文本信息";   //设置内容
    NSLog(@"%@",label.text);   //读取内容
```

- ##### backgroundColor————设置label背景颜色
```
    label.backgroundColor = [UIColor redColor];
```
- ##### textColor————设置文字颜色，默认为黑色
```
    label.textColor = [UIColor blackColor];
```
- ##### font————设置字体大小，默认17
```
    label.font = [UIFont systemFontOfSize:20];   //一般方法
    label.font = [UIFont boldSystemFontOfSize:20];   //加粗方法
    label.font = [UIFont fontWithName:@"Arial" size:16];   //指定字体的方法
```
**地址:**
http://blog.csdn.net/l_ch_g/article/details/8256485

- #####textAlignment————设置标签文本对齐方式
```
    label.textAlignment = NSTextAlignmentCenter;   //居中
```
> 
NSTextAlignmentLeft   居左
> 
NSTextAlignmentRight   居右

- #####numberOfLines————标签最多显示行数
```
    label.numberOfLines = 0;   //自动换行
```

- ##### ShadowColor————设置阴影颜色
```
    [label setShadowColor:[UIColor blackColor]];
    label.shadowColor = [UIColor blackColor];
```

- ##### ShadowOffset————设置阴影偏移量
```
    [label setShadowOffset:CGSizeMake(-1,-1)];
    label.shadowOffset = CGSizeMake(-1, -1);
```

- ##### enabled————是否激活
> 只是决定了Label的绘制方式，将它设置为NO将会使文本变暗，表示它没有激活，这时向它设置颜色值是无效的

```
    label.enabled = NO;
```