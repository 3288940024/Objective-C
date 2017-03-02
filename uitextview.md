# UITextView   标签视图
***
### 属性

```
    UITextView *textView = [[UITextView alloc] initWithFrame:CGRectMake(20, 20, 400, 500)];
```


```
    textView.text = @"";
```


```
    textView.textColor = [UIColor redColor];
```


```
    textView.font = [UIFont systemFontOfSize:20];
```


```
    textView.backgroundColor = [UIColor whiteColor];
```


```
    textView.returnKeyType = UIReturnKeyDefault;
```


```
    textView.keyboardType = UIKeyboardTypeDefault;
```


```
    textView.autoresizingMask = UIViewAutoresizingFlexibleHeight;
```


```
    textView.scrollEnabled = YES;
```


```
    textView.editable = YES;
```


```
    textView.dataDetectorTypes = UIDataDetectorTypeAll;
```

***
### delegate————代理
- ##### - (BOOL)textViewShouldBeginEditing:(UITextView *)textView;   //将要开始编辑
- ##### - (BOOL)textViewShouldBeginEditing:(UITextView *)textView;   //将要开始编辑
- ##### - (BOOL)textViewShouldEndEditing:(UITextView *)textView;   ///将要结束编辑
- ##### - (void)textViewDidBeginEditing:(UITextView *)textView;   //开始编辑
- ##### - (void)textViewDidEndEditing:(UITextView *)textView;   //结束编辑
- ##### - (BOOL)textView:(UITextView *)textView shouldChangeTextInRange:(NSRange)range replacementText:(NSString *)text;   //内容将要发生改变编辑

- ##### - (void)textViewDidChange:(UITextView *)textView;   //内容发生编辑
- ##### - (void)textViewDidChangeSelection:(UITextView *)textView;   //焦点发生改变

***
### 拓展
- ##### 回车键推出键盘
```
-(BOOL)textView:(UITextView *)textView shouldChangeTextInRange:(NSRange)range replacementText:(NSString *)text {
    if ([text isEqualToString:@""]) {
        [textView resignFirstResponder];
    }
}
```

- ##### UITextView自定义选择文字后的菜单
```
    UIMenuItem *menuItem = [[UIMenuItem alloc]initWithTitle:@"分享" action:@selector(changeColor:)];
    UIMenuController *menu = [UIMenuController sharedMenuController];
    [menu setMenuItems:[NSArray arrayWithObject:menuItem]];
-(BOOL)canPerformAction:(SEL)action withSender:(id)sender {
    if (action == @selector(changeColor:)) {
        if (textView.selectedRange.length > 0) {
            return YES;
        }
        return NO;
    }
}
```