#UIColor 颜色

### 适用于
  - **textColor** 文本颜色
  - **backgroundColor** 背景颜色 
  - **shadowColor** 阴影颜色
  - **barTinColor** 设置NavigationBar和NavigationItem的颜色
  - **TinColor** navigationItem里面的字体颜色
  - **borderColor** 边框颜色

### 系统颜色
  - **blackColor** 黑色   0.0 white
  - **darkGrayColor** 深灰色   0.333 white
  - **lightGrayColor** 浅灰色   0.667 white
  - **whiteColor** 白色   1.0 white
  - **grayColor** 灰色   0.5 white
  - **clearColor** 透明   0.0 white 0.0 alpha

### 随机颜色
```
    CGFloat r = arc4random()%256/255.0;
    CGFloat g = arc4random()%256/255.0;
    CGFloat b = arc4random()%256/255.0;
    UIColor *color = [UIColor colorWithRed:r green:g blue:b alpha:1];
```

### 快速创建方法
```
    [UIColor colorWithWhite:CGFloat alpha:CGFloat];
    [UIColor colorWithRed:CGFloat green:CGFloat blue:CGFloat alpha:CGFloat];
    [UIColor colorWithHue:(色调) saturation:(饱和度) brightness:(亮度) alpha:(透明度)];
```
- **redColor** 红色   1.0 , 0.0 , 0.0 RGB  
- **greenColor** 绿色   0.0 , 1.0 , 0.0 RGB  
- **blueColor** 蓝色   0.0 , 0.0 , 1.0 RGB  
- **cyanColor** 青色(红色与绿色之间)   0.0 , 1.0 , 1.0 RGB 
- **yellowColor** 黄色   1.0 , 1.0 , 0.0 RGB  
- **magentaColor** 洋红色(红色与蓝色之间)   1.0 , 0.0 , 1.0 RGB 
- **orangeColor** 橙色   1.0 , 0.5 , 0.0 RGB  
- **purpleColor** 紫色   0.5 , 0.0 , 0.5 RGB  
- **brownColor** 棕色   0.6 , 0.4 , 0.2 RGB
```