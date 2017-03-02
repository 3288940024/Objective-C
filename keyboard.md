# KeyBoard 键盘
***
### keyboardType————键盘样式
```
text.keyboardType = UIKeyboardTypeDefault;
```
>     UIKeyboardTypeASCIICapable   支持ASCII的默认键盘
   >
 UIKeyboardTypeNumbersAndPunctuation   标准电话键盘,支持＋＊＃字符
   > 
 UIKeyboardTypeURL   URL键盘,支持.com按钮,只支持URL字符
   > 
 UIKeyboardTypeNumberPad   数字键盘
  > 
  UIKeyboardTypePhonePad   电话键盘
  > 
  UIKeyboardTypeNamePhonePad   电话键盘,也支持输入人名
   > 
 UIKeyboardTypeEmailAddress   用于输入电子邮件地址的键盘
 > 
   UIKeyboardTypeDecimalPad   数字键盘,有数字和小数点
  > 
  UIKeyboardTypeTwitter   优化的键盘,方便输入@,#字符

### returnKeyType————return键
```
    text.returnKeyTpe = UIReturnKeyDefault;   //默认灰色按钮,标有Return
```
>    **UIReturnKeyDone**   标有Done的蓝色按钮
> 
**UIReturnKeyGo**   标有Go的蓝色按钮
 > 
   **UIReturnKeyGoogle**   标有Google的蓝色按钮
 > 
   **UIReturnKeyJoin**   标有Join的蓝色按钮
  > 
  **UIReturnKeyNext**   标有Next的蓝色按钮
 > 
   **UIReturnKeyRoute**   标有Route的蓝色按钮
 > 
   **UIReturnKeySearch**   标有Search的蓝色按钮
  > 
  **UIReturnKeySend**   标有Send的蓝色按钮
 > 
   **UIReturnKeyYahoo**   标有Yahoo的蓝色按钮
 > 
   **UIReturnKeyEmergencyCall**   紧急呼叫按钮


### keyboardAppearance————键盘外观
```
    text.keyboardAppearance = UIKeyboardAppearanceDefault;   //默认外观,浅灰色
```
>     **UIKeyboardAppearanceAlert**   深灰,石墨色

### 回收键盘
- ##### 代理回收键盘
```
-(BOOL)textFieldShouldReturn:(UITextField *)textField{
    [text resignFirstResponder];
    return YES;
}
```

- ##### 手势回收键盘
```
    self.userInteractionEnabled = YES;
    UITapGestureRecognizer *singleTap = [[UITapGestureRecognizer alloc]initWithTarget:self action:@selector(FingerTapped:)];
    [self.view addGestureRecognizer:singleTap];
    -(void)fingerTapped:(UITapGestureRecognizer *)gestureRecognizer
    {[self.view endEditing:YES];}
```

- ##### button方法内回收键盘