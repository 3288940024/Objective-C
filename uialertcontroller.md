# UIAlertController 提示框
***
### 属性
- ##### 创建
```
    UIAlertController *alert = [UIAlertController alertControllerWithTitle:@"提示" message:@"主题" preferredStyle:UIAlertControllerStyleAlert];
```
>     **UIAlertControllerStyleAlert**   显示在中间
> 
    **UIAlertControllerStyleActionSheet**   显示在底部

- ##### 添加按钮
```
    UIAlertAction *a = [UIAlertAction actionWithTitle:@"" style:UIAlertActionStyleDefault handler:^(UIAlertAction * _Nonnull action) {
        NSLog(@"点击");
    }];
```
> 
    **UIAlertActionStyleCancel**   关闭
 >
   **UIAlertActionStyleDefault**   默认
 >
   **UIAlertActionStyleDestructive**   警告

- ##### 添加指示框
```
[alertaddTextFieldWithConfigurationHandler:^(UITextField*textField) { textField.textColor= [UIColorredColor];
textField.text=@"iOS8";
[textFieldaddTarget:selfaction:@selector(usernameDidChange:)forControlEvents:UIControlEventEditingChanged];
}];
```


### 仅供参考,错误勿怪！