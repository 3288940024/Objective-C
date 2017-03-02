# UITextField 输入框
***
### 属性
- ##### 创建
```
    UITextField *textfield = [[UITextField alloc]initWithFrame:CGRectMake(20,20,130,30)];
```

- ##### BorderStyle————边框样式
>     UITextBorderStyleNone   无样式
   > 
 UITextBorderStyleLine   
    > 
UITextBorderStyleBezel   
   > 
 UITextBorderStyleRoundedRect   圆角

- ##### backgroundColor————输入框背景颜色
```
    textfield.backgroundColor = [UIColor whiteColor];
```

- ##### background,disableBackground————添加背景图片
```
    textfield.background = [UIImage imageNamed:@""];
    textfield.disabledBackground = [UIImage imageNamed:@""];   //设置enable为NO时的背景图片
```

- ##### placeholder————输入框没有内容时水印提示 
```
    textfield.placeholder = @"";
```

- ##### font————设置输入框内容的字体样式和大小
```
    textfield.font = [UIFont fontWithName:@"" size:20];
```

- #####textColor————字体颜色
```
    textfield.textColor = [UIColor redColor];
```

- #####clearButtonMode————输入框中的叉；
```
    text.clearButtonMode = UITextFieldViewModeAlways;
    text.rightViewMode = UITextFieldViewModeAlways;
```
>     **UITextFieldViewModeNever**   从不出现
>
    **UITextFieldViewModeWhileEditing**   编辑时出现
>
    **UITextFieldViewModeUnlessEditing**   除了编辑外都出现
 >
   **UITextFieldViewModeAlways**   一直出现

  - **最右侧加图片:<左侧类似>**
```
   UIImageView *image = [[UIImageView alloc]initWithImage:[UIImage imageNamed:@""]];
    textfield.tightView = image;
```

- ##### 输入框中一开始就有的文字
```
    textfield.text = @"";
```

- #####每输入一个字符就变成点 用于密码输入
```
    textfield.secureTextEntry = YES;
```

- #####autocorrectionType————是否纠错
```
    textfield.autocorrectionType = UITextAutocorrectionTypeDefault;
```
>     UITextAutocorrectionTypeNo    不自动纠错
>
    UITextAutocorrectionTypeYes   自动纠错

- #####clearsOnBeginEditing————编辑清空
```
    textfield.clearsOnBeginEditing = YES;
```

- #####textAlignment————内容对齐方式
```
    textfield.textAlignment = UITextAlignmentLeft;
```
>     UITextAlignmentRight   右对齐
> 
UITextAlignmentCenter   中对齐

- #####contentVerticalAlignment————内容垂直对齐方式
```
    textfield.contentVerticalAlignment = UIControlContentVerticalAlignmentCenter;
```
>     UIControlContentVerticalAlignmentTop   对齐顶端
>
    UIControlContentVerticalAlignmentBottom   对齐底部
>
    UIControlContentVerticalAlignmentFill   充满

- ##### contentHorizontalAlignment————内容水平对齐方式
```
    textfield.contentHorizontalAlignment = UIControlContentHorizontalAlignmentLeft;
```
>     UIControlContentHorizontalAlignmentLeft   对齐左边
 >
   UIControlContentHorizontalAlignmentCenter   对齐中间
  >
  UIControlContentHorizontalAlignmentRight   对齐右边
 >
   UIControlContentHorizontalAlignmentFill   充满

- ##### adjustsFontSizeToFitWidth————自动收缩字体适应文本窗口
```
    textfield.adjustsFontSizeToFitWidth = YES;
    textfield.minimumFontSize = 20;   //最小缩小字体
```

- ##### autocapitalizationType————首字母是否大写
```
    textfield.autocapitalizationType = UITextAutocapitalizationTypeNone;   //不自动大写
```
>     UITextAutocapitalizationTypeWords   单词首字母大写
>
    UITextAutocapitalizationTypeSentences   句子的首字母大写
> 
   UITextAutocapitalizationTypeAllCharacters   所有字母都大写