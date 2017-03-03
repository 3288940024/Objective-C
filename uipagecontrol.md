# UIPageControl 分页控制器
***
### 属性
- ##### 创建
```
    UIPageControl * page = [[UIPageControl alloc]initWithFrame:CGRectMake(100, 100, 100, 100)];
```

- ##### numberOfPages————设置控制器页数（默认为0）
```
    page.numberOfPages = 3;   //三页
```

- ##### currentPage————设置当前所在页码
```
    page.currentPage = 1;   //当前在第一页
```

- ##### hidesForSinglePage ————设置当总页数为1时，是否自动隐藏控制器
```
    page.hidesForSinglePage = YES;
```

- ##### defersCurrentPageDisplay————设置是否延迟自动更新控制器的当前页码（默认为NO）
```
    page.defersCurrentPageDisplay = YES;
```

- ##### pageIndicatorTintColor————设置控制器页码点得颜色
```
    page.pageIndicatorTintColor = [UIColor redColor];
```

- ##### currentPageIndicatorTintColor————设置控制器当前所在页码点的颜色
```
    page.currentPageIndicatorTintColor = [UIColor blackColor];
```

***
### 方法
- ##### - (void)updateCurrentPageDisplay;————更新控制器当前页码
>注意：这个属性如果设置为YES，点击时并不会改变控制器显示的当前页码点，必须手动调用这个方法，才会更新。

- ##### - (CGSize)sizeForNumberOfPages:(NSInteger)pageCount; ————通过页数得到控制器大小
>这个属性用于页数会变化的情况下进行大小动态处理


### 仅供参考,错误勿怪！