###UILabel 标签
>UILable是iPhone界面最基本的控件，主要用来显示文本信息。

***
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

- #####numberOfLines————标签最多显示行数
```
    label.numberOfLines = 0;   //自动换行
```
>     NSTextAlignmentLeft 居左
>
    NSTextAlignmentRight 居右

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

- #####highlighted———— 是否高亮显示
label.highlighted = YES；label.highlighted.TextColor = [UIColor orangeColor]；   设置高亮时文本颜色

- #####baselineAdjustment————控制文本基线的行为
> 如果**adjustsFontSizeToFitWidth**属性设置为YES;
**UIBaselineAdjustmentNone**   文本最低端与label中线对齐
**UIBaselineAdjustmentAlignCenters**   文本中线与label中线对齐
> 
**UIBaselineAdjustmentAlignBaselines** = 0   默认,文本最上端与中线对齐

- ##### adjustsLetterSpacingToFitWidth————改变字母之间的间距来适应Label 大小
```
    label.adjustsLetterSpacingToFitWidth = NO;
```

- #####lineBreakMode————设置文字过长的显示格式
```
label.lineBreakMode = NSLineBreakByCharWrapping; //以字符为显示单位，后面部分省略不显示
```
> 
**NSLineBreakByClipping**   剪切与文本宽度相同的内容长度，后部分被删除
> 
**NSLineBreakByTruncatingHead**   前面部分文字……方式省略，显示尾部文字内容
> **NSLineBreakByTruncatingMiddle**   中间的内容以……方式省略，显示头尾的文字内容
> 
**NSLineBreakByTruncatingTail**   结尾部分的内容以……方式省略，显示头的文字内容
> 
**NSLineBreakByWordWrapping**   以单词为显示单位，后面部分省略不显示

- ##### adjustsFontSizeToFitWidth————设置字体大小适应label宽度
```
    label.adjustsFontSizeToFitWidth = YES;
```

***
### 扩展
- ##### \n————换行符
```
    label.text = @"请\n竖\n直\n方\n向\n排\n列";
    label.numberOfLines = [label.text length];
```

- #####添加边框
```
    label.layer.borderWidth = 1; //设置边框宽度(默认黑色)
    label.layer.borderColor = [[UIColor redColor] CGColor]; //自定义边框颜色
    //改变边框颜色：
    CGColorSpaceRef colorSpace = CGColorSpaceCreateDeviceRGB(); //设置颜色空间
    CGColorRef colorref = CGColorCreate(colorSpace,(CGFloat[]){0,0,0,1}); //设置自定义颜色
    label.layer.borderColor = colorref;
```

- #####字体样式
```
    label.attributedText = [[NSAttributedString alloc]initWithString:@"123" attributes:dict];   //设置文本内容并加入自定义字体字典
```
 - 空心字体，实心字体
```
    NSDictionary *dict = @{NSFontAttributeName:[UIFont systemFontOfSize:50],NSForegroundColorAttributeName:[UIColor redColor],NSStrokeWidthAttributeName:@3,NSStrokeColorAttributeName:[UIColor greenColor]};
```
> **NSFontAttributeName** 文本字体大小
> 
**NSForegroundColorAttributeName** 文本里面字体颜色 ***@3*** 空心, ***@-3*** 实心
> 
**NSStrokeColorAttributeName** 文本外缘字体颜色 
 - **NSStrikethroughStyleAttributeName**   删除线
```
    NSDictionary *dict = @{NSStrikethroughStyleAttributeName:[NSNumber numberWithInteger:NSUnderlineStyleSingle]};
    [NSNumber numberWithInteger:NSUnderlineStyleSingle] = @(NSUnderlineStyleSingle);
    NSStrikethroughColorAttributeName   //删除线颜色
```
 - **NSUnderlinetyleAttributeName**   下划线
```
  NSDictionary *dict = @{NSUnderlineStyleAttributeName:[NSNumber numberWithInteger:NSUnderlineStyleSingle]};
    NSUnderlineColorAttributeName   //下划线颜色
```
 - **NSShadowAttributeName**   阴影

 - **NSVerticalGlyphFormAttributeName**   横屏排版
> ***@(0)***该属性所对应的值是一个NSNumber对象（整数）。**0**表示横排文本。**1**表示竖排文本。在IOS中，总是使用横排文本，0以外的值都未定义
 - **NSObliquenessAttributeName**   设置字体倾斜 @1,
 - **NSExpansionAttributeName**   设置文本扁平化 @1,

- **CAGradientLayer**————渐变字体
```
    CAGradientLayer *gradientlayer = [CAGradientLayer layer];
```
 - 创建渐变层
```
    gradientlayer.startPoint = CGPointMake(0,0.5);
    gradientlayer.endPoint = CGPointMake(1,0.5);   //横屏
    gradientlayer.frame = label.frame;
    gradientlayer.colors = @[(id)[self randomColor].CGColor,(id[self randomColor].CGColor,(id)[self randomColor].CGColor];    ///设置渐变层的颜色，随机颜色渐变
    gradientlayer.mask = label.layer;
```
> **mask**层工作原理：按照透明度裁剪，只保留非透明部分，文字就是非透明的，因此除了文字，其他都被裁剪掉，这样就只会显示文字下面渐变层的内容，相当于留了文字的区域，让渐变层去填充文字的颜色
```
    label.frame = gradientlayer.bounds;
```

- 计算UILabel随字体多行后的高度
```
    CGRect bounds = CGRectMake(0,0,200,300);
    heightLabel = [label textTextForBounds:bounds limitedToNumberOfLines:20];   //计算20行后Label的Frame
    NSLog(@%f,heightLabel.size.height);
```

- 根据内容多少改变label的高度
```
    NSDictionary *attribute = @{NSFontAttributeName:[UIFont systemFontOfSize:20]};
    CGSize size = [label.text boundingRectWithSize:CGSizeMake(200,100) options:(NSStringDrawingUsesFontLeading | NSStringDrawingTruncatesLastVisibleLine | NSStringDrawingUsesLineFragmentOrigin)attributes:attribute context:nil].size;
```