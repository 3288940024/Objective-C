# UIImageView,UIImage 图片
***
### 属性
- #####创建
```
    UIImageView *imageView = [[UIImageView alloc]init];
```

- #####添加图片
 - **用类方法创建UIImage**（png格式可以省略后缀）
```
    UIImage *image = [UIImage imageNamed:@""];
```

 - **用路径来获得图片**
```
    NSString *path = @"";   //这是路径地址
    UIImage *image2 = [UIImage imageWithContentsOfFile:path];
```

 - **根据网址来获得图片**
```
    NSString *url = @"";   //这是网址
    UIImage *image = [UIImage imageWithData:[NSData dataWithContentsOfURL:[NSURL URLWithString:url]]];
```

 - **获取UIImage的size**
```
    CGFloat width = imageView.frame.size.width;   //宽度
    CGFloat height = imageView.frame.size.height;   //高度
```

 - **NSData和UIImage之间的转换**
```
    NSData转换成UIImage:
    NSData *imagedata = [NSData dataWIthContentsOfFile:path];
    UIImage *image = [UIImage imageWithData:imagedata];
    UIImage转换成NSData
    NSData *imagedata1 = [NSData dataWithContentsOfFile:path];
```

- ##### 设置圆角
```
    imageView.layer.masksToBounds = YES;   //对本身周围裁剪
    imageView.layer.cornerRadius = 10;   //设置半径
```

- ##### 设置边框颜色和大小
```
    imageView.layer.borderColor = [UIColor orangeColor].CGColor;
    imageView.layer.borderWidth = 2;
```

- #####contentMode————填充方式
>     UIViewContentModeScaleToFill   全部填充
 >
   UIViewContentModeScaleAspectFit   按比例填充
 >
   UIViewContentModeScaleAspectFill   按比例填充,自动对周围裁剪
> 
UIViewContentModeRedraw   范围变化重绘(调用setneedsdisplay)    
> 
UIViewContentModeCenter   按中心填充    
> 
UIViewContentModeTop   按顶部填充
 > 
   UIViewContentModeBottom   按底部填充
 > 
   UIViewContentModeLeft   按左边填充
> 
UIViewContentModeRight   按右边填充    
> 
UIViewContentModeTopLeft   按左上方填充
 > 
   UIViewContentModeTopRight   按右上方填充
 > 
   UIViewContentModeBottomLeft   按左下方填充
  > 
  UIViewContentModeBottomRight   按右下方填充

- #####透明度 
```
    imageView.alpha = 0.5;
    imageView.hidden = YES;
    imageView.highlightedImage = (UIImage *)hightlighedImage;   //设置高亮时显示的图片
```

***
### 扩展
- #####播放一系列图片
```
    NSArray *array = @[@""];   //创建一个数组存储图片
    imageView.animationImages = array;   //轮流播放数组内图片
    imageView.animationDuration = [array count];   //设置播放完用时
    imageView.animationRepeatCount = 0;   //设置播放次数
    [imageView startAnimating];   //开始播放
```

- #####    为图片添加单击事件——————一定先将userInteractionEnabled设置为YES，这样才能响应
```
    imageView.userInteractionEnabled = YES;
    UITapGestureRecognizer *singleTap = [[UITapGestureRecognizer alloc]initWithTarget:self action:@selector(click:)];
    [imageView addGestureRecognizer:singleTap];
```

### 仅供参考,错误勿怪！