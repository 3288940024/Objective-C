# UITextView   标签视图
***
### 属性
- #####创建
```
    UITextView *textView = [[UITextView alloc] initWithFrame:CGRectMake(20, 20, 400, 500)];
```

- ##### text————内容
```
    textView.text = @"";
```

- ##### textColor————字体颜色
```
    textView.textColor = [UIColor redColor];
```

- ##### font————字体大小
```
    textView.font = [UIFont systemFontOfSize:20];
```

- ##### backgroundColor————背景颜色
```
    textView.backgroundColor = [UIColor whiteColor];
```

- ##### returnKeytype————返回键类型
```
    textView.returnKeyType = UIReturnKeyDefault;
```

- ##### keyboardtype————键盘类型
```
    textView.keyboardType = UIKeyboardTypeDefault;
```

- ##### autoresizingMask————自适应高度
```
    textView.autoresizingMask = UIViewAutoresizingFlexibleHeight;
```

- ##### scrollEnabled————是否可以拖动
```
    textView.scrollEnabled = YES;
```

- ##### editable————是否可以编辑
```
    textView.editable = YES;
```

- ##### dataDetectortypes————显示数据类型连接模式；
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