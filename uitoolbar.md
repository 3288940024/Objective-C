# UIToolbar 工具栏
***
### 属性

```
    UIToolbar *toolbar = [[UIToolbar alloc] initWithFrame:CGRectMake(0,460,320,44)];
    toolbar.barStyle = UIBarButtonItemStylePlain;   //设置工具栏的风格
```

```
    UIBarButtonItem *addItem = [[UIBarButtonItem alloc] initWithBarButtonSystemItem:UIBarButtonSystemItemAdd target:self action:nil];   //初始化UIBarButtonItem
    NSArray *items = [NSArray arrayWithObjects:addItem,nil];   //把Items放进数组
    [self setToolbarItems:items];  //向UIToolBar添加UIBarButtonItem
```