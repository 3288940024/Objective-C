# UISwitch 开关
***
### 属性
- ##### 创建
```
UISwitch *switchView = [[UISwitch alloc]initWithFrame:CGRectMake(54.0f,16.0f,100.0f,28.0f)];
```

- ##### 设置UISwitch的初始化状态
```
    switchView.on = YES;   //设置初始为ON的一边
    [switchView setOn:YES];
```

- ##### UISwitch事件的响应
```
     [switchView addTarget:self action:@selector(switchAction:) forControlEvents:UIControlEventValueChanged];
-(void)switchAction:(id)sender {
    BOOL isButtonOn = [switchButton isOn];
    if (isButtonOn) {
        showSwitchValue.text = @"是";
    }else {
        showSwitchValue.text = @"否";
    }
}
```

- ##### 控件大小不能设置frame,只能用缩放比例
```
    switchView.transform = CGAffineTransformMakeScale(0.75,0.75);
```

- ##### UISwitch的颜色
```
    switchView.onTintColor = [UIColor colorWithRed:0.984 green:0.478 blue:0.224 alpha:1.000];
    switchView.onTintColor = [UIColor colorWithRed:99/255.f green:155/255.f blue:0 alpha:1.0];
```