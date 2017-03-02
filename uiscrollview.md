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

