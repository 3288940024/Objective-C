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

- ##### textColor————字体颜色
```
    textfield.textColor = [UIColor redColor];
```

- ##### clearButtonMode————输入框中的叉；
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

- ##### 每输入一个字符就变成点 用于密码输入
```
    textfield.secureTextEntry = YES;
```

- ##### autocorrectionType————是否纠错
```
    textfield.autocorrectionType = UITextAutocorrectionTypeDefault;
```
>     UITextAutocorrectionTypeNo    不自动纠错
>
    UITextAutocorrectionTypeYes   自动纠错

- ##### clearsOnBeginEditing————编辑清空
```
    textfield.clearsOnBeginEditing = YES;
```

- ##### textAlignment————内容对齐方式
```
    textfield.textAlignment = UITextAlignmentLeft;
```
>     UITextAlignmentRight   右对齐
> 
UITextAlignmentCenter   中对齐

- ##### contentVerticalAlignment————内容垂直对齐方式
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

### 代理方法
- ##### 返回一个BOOl值，指定是否循序文本字段开始编辑，返回NO时不能唤起键盘进行编辑
```
-(BOOL)textFieldShouldBeginEditing:(UITextField *)textField {
    return YES;
}
```

- ##### 开始编辑时触发,文本字段将成为first responder
```
-(void)textFieldDidBeginEditing:(UITextField *)textField{}  
```

- ##### 返回BOOL值，指定是否允许文本字段结束编辑，当编辑结束，文本字段会让出first responder。要想在用户结束编辑时阻止文本字段消失，可以返回NO。这对一些文本字段必须始终保持活跃状态的程序很有用，比如即时消息。
```
-(BOOL)textFieldShouldEndEditing:(UITextField *)textField{
    return NO;   //一直处于编辑阶段
}
```

- ##### 当用户自动更正功能，把输入的文字修改为推荐的文字时，就会调用这个方法。这对于加入撤销选项的应用程序特别有用。可以跟踪字段内所做的最后一次修改，也可以对所有编辑做日志记录，用作审计用途。要防止文字被改变可以返回NO。这个方法的参数中有个NSRange对象，指明了被改变文字的位置，建议修改的文字也在其中
```
-(BOOL)textField:(UITextField *)textField shouldChangeCharactersInRange:(NSRange)range replacementString:(NSString *)string{
    return YES;
}
```  

- ##### 返回一个BOOL值指明是否允许根据用户请求清除内容。可以设置在特定条件下才允许清除内容
```
-(BOOL)textFieldShouldClear:(UITextField *)textField{
    return YES;   //返回YES,输入内容后点击右边的清除按钮可以清除,返回NO,则不可以
}
```
 
- ##### 返回一个BOOL值，指明是否允许在按下回车键时结束编辑。如果允许要调用resignFirstResponder方法，这会导致结束编辑，而键盘会被收起
```
-(BOOL)textFieldShouldReturn:(UITextField *)textField{
    return YES;
}
``` 

***
### 拓展
- #####限定特定字符输入
```
-(BOOL)textField:(UITextField *)textField shouldChangeCharactersInRange:(NSRange)range replacementString:(NSString *)string{
    //可以在文件顶部定义:
    //#define NUMBERD @"0123456789n"(这个代表可以输入数字和换行，这个n，如果不写，Done按键将不会触发)
    NSCharacterSet *cs = [[NSCharacterSet characterSetWithCharactersInString:NUMBERD] invertedSet];   //inverted方法是去反字符，把所有的除了NUMBERS里的字符都找出来(包含去空格功能)
    NSString *filtered = [string componentsSeparatedByString:NUMBERD];   //按cs分离出数组,数组按@""分离出字符串
    //componentsJoinedByString用于根据一个字符串来将数组连接成一个新的字符串
    BOOL canChange = [string isEqualToString:filtered];
    return canChange;   //这样写了后,输入非数字时不能输入
}
```

- #####限制只能输入一定长度的字符
```
-(BOOL)textField:(UITextField *)textField shouldChangeCharactersInRange:(NSRange)range replacementString:(NSString *)string{
    if ([string isEqualToString:@""]) /*按回车可以改变(这里写什么就只能输入什么)*/ {
        return YES;   //string就是此时输入的那个字符 textField就是此时正在输入的那个输入框 返回YES就是可以改变输入框的值 NO相反
        NSString *toBeString = [textField.text stringByReplacingCharactersInRange:range withString:string];   //得到输入框的内容
        if (self.myTextField == textField) /*判断是否是我们要限定的那个输入框*/{
            if ([toBeString length] > 20) {
                textField.text = [toBeString substringFromIndex:20];   //最多只能输入20个字符
            }
        }
    }
}
```
