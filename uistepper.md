# UIStepper 步进控件
***
### 属性
- ##### 创建
```
UIStepper * step = [[UIStepper alloc]initWithFrame:CGRectMake(100, 100, 100, 100)];
```

- ##### continuous————设置控制器值是否连续触发变化
>若设置为YES，则长按会连续触发变化，若设置为NO，只有在按击结束后，才会触发。
```
    step.continuous = YES;
```

- ##### autorepeat————设置长按是否一直触发变化
>若设置为YES，则长按值会一直改变，若设置为NO，则一次点击只会改变一次值
```
    step.autorepeat = YES;
```

- ##### wraps————设置控制器的值是否循环(到达边界后，重头开始，默认为NO)
```
    step.wraps = YES;
```

- ##### value————设置控制器的值
```
    step.value = 3;
    step.minimumValue = 1;   //最小值(默认为0)
    step.maximumValue = 5;   //最大值(默认为100)
```

***
### 方法
- ##### 设置控制器背景图片
```
-(void)setBackgroundImage:(UIImage*)image forState:(UIControlState)state;
```

- ##### 获取背景图片
```
-(UIImage*)backgroundImageForState:(UIControlState)state;
```

- ##### 通过左右按钮的状态设置分割线的图片
```
-(void)setDividerImage:(UIImage*)image forLeftSegmentState:(UIControlState)leftState rightSegmentState:(UIControlState)rightState;
```

- ##### 获取分割线图片
```
-(UIImage*)dividerImageForLeftSegmentState:(UIControlState)state rightSegmentState:(UIControlState)state;
```

- ##### 设置和获取加号按钮的图片
```
-(void)setIncrementImage:(UIImage *)image forState:(UIControlState)state;
-(UIImage *)incrementImageForState:(UIControlState)state;
```

- ##### 设置和获取减号按钮的图片
```
-(void)setDecrementImage:(UIImage *)image forState:(UIControlState)state;
-(UIImage *)decrementImageForState:(UIControlState)state;
```