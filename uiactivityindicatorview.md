# UIActivityIndicatorView 活动指示器
***
### 属性
- ##### 创建
```
    UIActivityIndicatorView *activithIndicatorView = [[UIActivityIndicatorView alloc] initWithFrame:CGRectMake(0, 0, 30, 30)];
```

- ##### UIActivityIndicatorViewStyle————指示器风格
```
   activithIndicatorView.activityIndicatorViewStyle = UIActivityIndicatorViewStyleWhite;
```
>     UIActivityIndicatorViewStyleWhiteLarge 更大的
> 
    UIActivityIndicatorViewStyleWhite 白色
> 
    UIActivityIndicatorViewStyleGray 灰色

- ##### hidesWhenStopped————停止时是否隐藏
```
    activithIndicatorView.hidesWhenStopped = YES;
```

- ##### color—————指示器颜色
```
    activithIndicatorView.color = [UIColor redColor];
```

***
### 方法
- ##### 开始动画
```
-(void)startAnimating;
```

- ##### 停止动画
```
-(void)startAnimating;
```

- ##### 指定进度中心点
```
    [activity setCenter:CGPointMake(160, 140)];//指定进度轮中心点
```