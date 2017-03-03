# UISlider 滑块
***
### 属性
- ##### 创建
```
UISlider *slider = [[UISlider alloc]initWithFrame:CGRectMake(0,400,320,200)];
```

- ##### 访问UISlider的值
```
    slider.value = 3;   //设置slider的值
    float value = slider.value;   //得到slider的值
    [slider setValue:3 animated:YES];   //设置slider的值，并浮附有动画效果
```

- ##### min，max————设置最大,最小值
```
    slider.minimumValue = 0;   //设置滑轮所能滚到的最小值
    slider.maximumValue = 1;   //值滑轮所能滚到的最大值
```

- ##### UISlider的行为
```
    [slider addTarget:self action:@selector(change) forControlEvents:UIControlEventValueChanged];   //为slider添加方法当slider的值改变时就会触发change方法
    slider.continuous = YES;   //默认值为YES设置为YES只要滑轮滚动就会触发change方法设置为NO只有当滑轮停止移动时才会触发change方法
```

- ##### UISlider的外观
 - **minimumValueImage** 最小值图片
 - **maximumValueImage** 最大值图片
 - **setMinimumTrackImage** 滑轮左边图片
 - **setMaximumTrackImage** 滑轮右边图片
 - **currentMinimumTrackImage** 得到当前滑轮左边图片
 - **currentMaximumTrackImage** 得到当前滑轮右边图片
 - **minimumTrackTintColor** 滑轮左边颜色
 - **maximumTrackTintColor** 滑轮右边颜色
 - **setThumbImage** 滑轮样式图片
 - **thumbTintColor** 滑轮颜色
```
    slider.minimumValueImage = [UIImage imageNamed:@""];
    slider.maximumValueImage = [UIImage imageNamed:@""];   //设置了会减少滚动区域的宽度,但整个slider的宽度不变
    [slider setMinimumTrackImage:[UIImage imageNamed:@""] forState:UIControlStateNormal];   //设置滑轮左边的图片,最好宽度和slider一样
    [slider currentMinimumTrackImage];   //得到当前滑轮左边的图片
    [slider setMaximumTrackImage:[UIImage imageNamed:@""] forState:UIControlStateNormal];   //设置滑轮右边的图片,最好宽度和slider一样
    [slider currentMaximumTrackImage];   //得到当前滑轮右边的图片
    slider.minimumTrackTintColor = [UIColor redColor];   //滑轮左边颜色，如果设置颜色;图片将不显示
    slider.maximumTrackTintColor = [UIColor redColor];   //滑轮右边颜色,如果设置颜色,图片将不显示
    [slider thumbImageForState:UIControlStateNormal];
    [slider setThumbImage:[UIImage imageNamed:@""] forState:UIControlStateHighlighted];   //设置滑轮样子图片,设置普通状态和高亮状态的滑轮样式
    slider.thumbTintColor = [UIColor redColor];   //设置滑轮的颜色如果设置后图片将不会显示
```

### 仅供参考,错误勿怪！