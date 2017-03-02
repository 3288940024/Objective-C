# UIScrollView 滚动视图
***
### 属性
- ##### 创建
```
    UIScrollView *scrollView = [[UIScrollView alloc] initWithFrame:CGRectMake(0, 0, 320, 460)];
```

- ##### backgroundColor————背景颜色
```
    scrollView.backgroundColor = [UIColor redColor];
```

- ##### contentSize————设置内容的大小
```
    scrollView.contentSize = CGSizeMake(320, 400);
```

- ##### bounces————是否反弹
```
    scrollView.bounces = NO;
```

- ##### pagingEnabled————是否分页
```
    scrollView.pagingEnabled = YES;
```

- ##### scrollEnabled————是否滚动
```
    scrollView.scrollEnabled = NO;
```

- ##### showsVerticalScrollIndicator————是否显示竖直滚动条
```
    scrollView.showsVerticalScrollIndicator = NO;
```

- ##### showsHorizontalScrollIndicator————是否显示水平滚动条
```
    scrollView.showsHorizontalScrollIndicator = NO;
```

- ##### indicator————指示器风格
```
    scrollView.indicatorStyle = UIScrollViewIndicatorStyleWhite;
```

- ##### contentInset————设置内容的边缘
```
    scrollView.contentInset = UIEdgeInsetsMake(0, 50, 50, 0);
```

- ##### scrollIndicatorInsets————设置指示器的边缘
```
    scrollView.scrollIndicatorInsets = UIEdgeInsetsMake(0, 50, 0, 0);
```

- ##### flashScrollIndicators————提示用户指标闪光
```
    [scrollView flashScrollIndicators];
```
- ##### directionalLockEnabled————是否同时运动
```
    scrollView.directionalLockEnabled = YES;
```

***
### 方法及代理
- ##### 返回一个放大或者缩小的视图
```
-(UIView *)viewForZoomingInScrollView:(UIScrollView *)scrollView{}
```

- ##### 开始放大或者缩小
```
-(void)scrollViewWillBeginZooming:(UIScrollView *)scrollView withView:
(UIView *)view{}
```

- ##### 缩放结束时
```
-(void)scrollViewDidEndZooming:(UIScrollView *)scrollView withView:(UIView *)view atScale:(float)scale{}
```

- ##### 视图已经放大或缩小
```
-(void)scrollViewDidZoom:(UIScrollView *)scrollView{
      NSLog(@"scrollViewDidScrollToTop");
}
```

- ##### 是否支持滑动至顶部
```
-(BOOL)scrollViewShouldScrollToTop:(UIScrollView *)scrollView{
    return YES;
}
```

- ##### 滑动到顶部时调用该方法
```
-(void)scrollViewDidScrollToTop:(UIScrollView *)scrollView{
    NSLog(@"scrollViewDidScrollToTop");
}
```

- ##### 滑动时调用
```
-(void)scrollViewDidScroll:(UIScrollView *)scrollView{
    NSLog(@"scrollViewDidScroll");
}
```

- ##### 拖动时调用
```
-(void)scrollViewWillBeginDragging:(UIScrollView *)scrollView{
    NSLog(@"scrollViewWillBeginDragging");
}
```

- ##### 结束拖动时调用
```
-(void)scrollViewDidEndDragging:(UIScrollView *)scrollView willDecelerate:(BOOL)decelerate{
    NSLog(@"scrollViewDidEndDragging");
}
```

- ###### 开始减速时调用（以下两个方法注意与以上两个方法加以区别）
```
- (void)scrollViewWillBeginDecelerating:(UIScrollView *)scrollView{
    NSLog(@"scrollViewWillBeginDecelerating");
}
```

- ##### 减速停止时调用
```
-(void)scrollViewDidEndDecelerating:(UIScrollView *)scrollView{
   NSLog(@"scrollViewDidEndDecelerating"); 
}
```