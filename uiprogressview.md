# UIProgressView 进度条
***
### 属性
- ##### 创建
```
    UIProgressView *progressView = [[UIProgressView alloc]initWithProgressViewStyle:UIProgressViewStyleDefault];    //设置风格
    progressView.frame = CGRectMake(30,100,200,50);    //设置位置
```

- ##### trackTintColor————设置进度条颜色
```
    progressView.trackTintColor = [UIColor blackColor];
```

- ##### progressTintColor————设置进度条上的颜色
```
    progressView.trackTintColor = [UIColor blackColor];
```

- ##### trackImage————设置进度条的背景图片
```
    progressView.trackImage = [UIImage imageNamed:@""];
```

- ##### progressImage————设置进度条上的背景图片
```
    progressView.progressImage = [UIImage imageNamed:@""];
```

- ##### 赋值
```
    progressView.progress = 0.7;   //普通赋值
    [progressView setProgress:0.7 animated:YES];   //赋值并有动画效果
```

### 仅供参考,错误勿怪！