# UISegmentedControl   分段控制器
***
### 属性
- ##### 创建
```
    NSArray *array = [[NSArray alloc]initWithObjects:@"1",@"2",@"3",nil];   //创建数组储存分段控制器标题
    UISegmentedControl *segment = [[UISegmentedControl alloc]initWithItems:array];   //创建UISegmentedControl,并赋予标题
    segment.frame = CGRectMake(20,20,30,30);   //设置UISegmentedControl的位置
```

- ##### BackgroundColor————背景颜色；
```
    segment.backgroundColor = [UIColor colorWithRed:1 green:1 blue:1 alpha:1];
```

- ##### tintColor————渲染色彩
```
    segment.tintColor = [UIColor redColor];
```

- ##### 片段的增删
```
    [segment insertSegmentWithTitle:@"First" atIndex:0 anitmated:NO];   //第0单元title为First
    UIImage *myImage = [UIImage imageNamed:@"1.png"];
    [segment inserSegmentWithImage:myImage atIndex:2 animated:NO];   //第2单元添加图片
    [segment removeSegmentAtIndex:1 animated:YES];   //删除单个片段
    [segment removeAllSegments];   //删除所有
    [segment setTitle:@"Third" forSegmentAtIndex:2];   //设置标题
    [NSString *myTitle = [segment titleForSegmentAtIndex:0];   //读取标题
     [segment setImage:[UIImage imageNamed:@""] forSegmentAtIndex:0];   //设置图像
     UIImage *myImage = [segment imageForSegmentAtIndex:3];   //读取图片
```

- ##### 设置片段的宽度
```
    [segment setWidth:64 forSegmentAtIndex:0];   //设置片段宽度
```

- ##### 瞬时单击
```
    segment.momentary = YES;   //按钮被按下后很快恢复,默认选中状态就一直保持 设置在点击后是否恢复原样
```

- ##### 初始化默认片段
```
    segment.selectedSegmentIndex = 0;   //初始指定第0格选中
```

- ##### 设置指定索引选项不可选
```
    [segment setEnabled:NO forSegmentAtIndex:4];
```

- ##### 判断指定索引选项是否可选
```
    BOOL endableFlag = [segment isEnabledForSegmentAtIndex:4];
    NSLog(@"endabledFlag = %d",endableFlag);
```

- ##### 设置边角
```
    segment.layer.cornerRadius = 5.0;
    segment.layer.masksToBounds = YES;
```

- ##### 响应事件
```
    [segment addTarget:self action:@selector(controlPressed:) forControlEvents:UIControlEventValueChanged];
-(void)controlPressed:(UISegmentedControl *)segment{
    NSInteger Index = segment.selectedSegmentIndex;
    switch(Index) {//switch循环语句
    }
}
```