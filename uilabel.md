###UILabel 标签
>UILable是iPhone界面最基本的控件，主要用来显示文本信息。


- ##### 创建

```
    CGRect rect = CGRectMake(100,200,50,50);
    UILabel *label = [[UILabel alloc]initWithFrame:rect];
```

```
    label.text = @"文本信息";   //设置内容
    NSLog(@"%@",label.text);   //读取内容
```

- ##### backgroundColor————设置label背景颜色
```
    label.backgroundColor = [UIColor redColor];
```

```
    label.textColor = [UIColor blackColor];
```

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


```
    label.numberOfLines = 0;   //自动换行
```


```
    [label setShadowColor:[UIColor blackColor]];
    label.shadowColor = [UIColor blackColor];
```


```
    [label setShadowOffset:CGSizeMake(-1,-1)];
    label.shadowOffset = CGSizeMake(-1, -1);
```


> 

```
    label.enabled = NO;
```