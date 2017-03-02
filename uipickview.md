#UIPickView 选择框
***
### 属性
- ###### 创建
```
    UIPickerView *pickerView = [[UIPickerView alloc] initWithFrame:CGRectMake(0, 100, 320, 216)];  
```

- ###### showsSelectionIndicator————该属性控制是否显示UIPickerView中的选中标记（以高亮背景作为选中标记）
```
    pickerView.showsSelectionIndicator = YES;
```

***
### 方法
- ##### numberOfComponents————获取UIPickerView指定列中包含的列表项的数量。该属性是一个只读属性
```
-(NSInteger)numberOfRowsInComponent:(NSInteger)component;
```

- ##### numberOfRowsInComponent————获取UIPickerView包含的列数量
```
-(NSInteger)numberOfComponentsInPickerView:(UIPickerView *)pickerView;
```

- ##### rowSizeForComponent————获取UIPickerView包含的指定列中列表项的大小。该方法返回一个CGSize对象
```
-(CGSize)rowSizeForComponent:(NSInteger)component;
```

- ##### 设置选中该UIPickerView中指定列的特定列表项。最后一个参数控制是否使用动画
```
-(void)selectRow:(NSInteger)row inComponent:(NSInteger)component animated:(BOOL)animated;  // scrolls the specified row to center.
```

- ##### selectedRowInComponent————该方法返回该UIPickerView指定列中被选中的列表项
```
-(NSInteger)selectedRowInComponent:(NSInteger)component;                                   // returns selected row. -1 if nothing selected
```

- ##### 返回该UIPickerView指定列的列表项所使用的UIView控件
```
-(UIView *)viewForRow:(NSInteger)row forComponent:(NSInteger)component;
```

- ##### numberOfComponentsInPickerView————该UIPickerView将通过该方法来判断应该包含多少列
```
-(NSInteger)numberOfComponentsInPickerView:(UIPickerView *)pickerView;
```

- ##### 该UIPickerView将通过该方法判断指定列应该包含多少个列表项
```
-(NSInteger)pickerView:(UIPickerView *)pickerView numberOfRowsInComponent:(NSInteger)component;
```

- ##### 返回的CGFloat值将作为该UIPickerView控件中指定列中列表项的高度
```
- (CGFloat)pickerView:(UIPickerView *)pickerView rowHeightForComponent:(NSInteger)component __TVOS_PROHIBITED;
```
- ##### 返回的CGFloat值将作为该UIPickerView控件中指定列的宽度
```
-(CGFloat)pickerView:(UIPickerView *)pickerView widthForComponent:(NSInteger)component __TVOS_PROHIBITED;
```

- ##### 返回的NSString值将作为该UIPickerView控件中指定列的列表项的文本标题
```
-(nullable NSString *)pickerView:(UIPickerView *)pickerView titleForRow:(NSInteger)row forComponent:(NSInteger)component __TVOS_PROHIBITED;
```

- ##### 返回的UIView控件将直接作为该UIPickerView控件中指定列的指定列表项
```
-(UIView *)pickerView:(UIPickerView *)pickerView viewForRow:(NSInteger)row forComponent:(NSInteger)component reusingView:(nullable UIView *)view __TVOS_PROHIBITED;
```

- ##### 当用户单击选中该UIPickerView控件的指定列的指定列表项时将会激发该方法
```
-(void)pickerView:(UIPickerView *)pickerView didSelectRow:(NSInteger)row inComponent:(NSInteger)component __TVOS_PROHIBITED;
```
