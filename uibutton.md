# UIButton 按钮
### 属性
- #####创建
```
    CGRect rect = CGRectMake(100,200,50,50);
    UIButton *button = [[UIButton alloc]initWithFrame: rect];
```
- #####buttonType————按键的风格
```
    UIButton *button = [UIButton buttonWithType:(buttonType)];
```
> 
    **UIButtonTypeCustom** 自定义风格
    **UIButtonTypeRoundedRect** 圆角矩形
    **UIButtonTypeDetailDisclosure** 蓝色小箭头
    **UIButtonTypeInfoLight** 亮色感叹号
>
    **UIButtonTypeInfoDark**   暗色感叹号
    **UIButtonTypeContactAdd** 十字加号按钮

- #####backgroundColor————button的背景颜色
```
    [button setBackgroundColor:[UIColor redColor]];
```

- #####state————forState:这个参数的作用是定义按钮的文字或图片在何种状态下才会显现
>     **UIControlStateNormal** = 0;   常规状态显现
    **UIControlStateHighlighted** = 1<<0;   高亮状态显现
    **UIControlStateDisabled** = 1<<1;   禁用的状态才会显现
    **UIControlStateSelected** = 1<<2;   选中状态
    **UIControlStateApplication** = 0x00FF0000;   当应用程序标志时
    **UIControlStateReserved** = 0xFF00000;   为内部框架预留

### 方法
 - **设置button标题和标题颜色**
```
    [button setTitle:@"" forState:UIControlStateNormal];
    [button setTitleColor:[UIColor redColor] forState:UIControlStateNormal];
```
 - **设置button的填充图片和背景图片**
```
    [button setImage:[UIImage imageNamed:@""] forState:UIControlStateNormal];
    [button setBackgroundImage:[UIImage imageNamed:@""] forState:UIControlStateNormal];
```
 - **设置按钮按下会发光**
```
    button.showsTouchWhenHighlighted = NO;
```
 - **添加或删除事件处理**
```
    [button addTarget:self action:@selector(click:) forControlEvents:UIControlEventTouchUpInside];   //添加
    [button removeTarget:nil action:nil forControlEvents:UIControlEventTouchUpInside];   //删除
```
> ###*forControlEvents*:
> 
**UIControlEventTouchDown**   单点触摸按下事件:用户点触屏幕,或者又有新手指落下的时候
**UIControlEventTouchDownRepeat**   多点触摸按下事件，点触计数大于1，用户按下第二,三,四根手指的时候
**UIControlEventTouchDragInside**   当一次触摸在控件窗口内拖动时
> 
**UIControlEventTouchDragEnter**   当一次触摸从控件窗口之外拖动到内部时
> 
**UIControlEventTouchDragExit**   当一次触摸从控件窗口之外拖动到外部时
> 
**UIControlEventTouchCancel**   所有触摸取消事件,即一次触摸因为放上了太多手指而被取消,或者被上锁或者电话呼叫打断
**UIControlEventTouchUpInside**   点击抬起时
**UIControlEventTouchOutside**   点击下去时
**UIControlEventValueChanged**   值改变
**UIControlEventEditingDidBegin**   当文本控件中的文本编辑时发送通知
> 
**UIControlEventEdingChanged**   当文本控件中的文本被改变发送通知
> 
**UIControlEventEditingDidEnd**   当文本控件中编辑结束时发送通知
> 
**UIControlEventEditingDidOnExit**   当文本控件内通过按下回车键结束编辑时发送通知
> 
**UIControlEventAlltouchEvents**   通知所有触摸事件
**UIControlEventAllEditingEvents**   通知所有关于文本编辑的事件
> 
**UIControlEventAllEvents**   通知所有事件

- #####定义按钮标题字体格式
```
    [button.titleLabell setFont:[UIFont systemFontOfSize:20]];
```

- #####设置按钮内部图片间距和标题间距
```
    UIEdgeInsets insets;
    insets.top = insets.bottom = insets.right = insets.left = 10;
    button.contentEdgeInsets = insets;
    button.titleEdgeInsets = insets;   //标题间距
```

- #####给button设置标签，用来辨别点击的是哪个button，常用在委托方法中
```
    button.tag = 0;
```

- #####设置圆角
```
    [button.layer setMasksTobounds:YES];   边缘是否剪切
    [button.layer setCornerRadius:10];   圆角
    [button.layer setBorderWidth:10];   边框宽度
    [button.layer setbBorderColor:[[UIColor redColor]CGColor]];   边框颜色
```