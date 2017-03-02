# UISearchBar 搜索条
***
### 属性
- ##### 创建
```
UISearchBar *searchBar = [[UISearchBar alloc] initWithFrame:CGRectMake(0, 50, 100, 60)]; 
```

- ##### barStyle————控件的样式
```
    searchBar.barStyle = UISearchBarStyleDefault;
```
> **UISearchBarStyleProminent** 用我的邮件、消息和联系人
> 
**UISearchBarStyleMinimal** 使用的日历,笔记和音乐


- ##### Prompt————显示在顶部的单行文字，通常作为一个提示行
```
    searchBar.prompt = @"提示";
```

- ##### text————显示在顶部的单行文字，通常作为一个提示行
```
    searchBar.prompt = @"提示";
```

- ##### Prompt————显示在顶部的单行文字，通常作为一个提示行
```
    searchBar.prompt = @"提示";
```

- ##### placeholder————半透明的提示文字，输入搜索内容消失
```
    searchBar.placeholder = @"请输入";
```

- ##### showsBookmarkButton————是否在控件的右端显示一个书的按钮(没有文字的时候)
```
    searchBar.showsBookmarkButton = YES;
```

- ##### showsCancelButton————是否显示cancel按钮
```
    searchBar.showsCancelButton = YES;
```

- ##### showsSearchResultsButton————是否在控件的右端显示搜索结果按钮(没有文字的时候)
```
    searchBar.showsSearchResultsButton = YES;
```

- ##### searchResultsButtonSelected————搜索结果按钮是否被选中
```
    searchBar.searchResultsButtonSelected = YES;
```

- ##### tintColor————bar的颜色(具有渐变效果)
```
    searchBar.tintColor = [UIColor redColor];
```
- ##### translucent————指定控件是否会有透视效果
```
    searchBar.translucent = YES;
```

- ##### showsScopeBar————控制搜索栏下部的选择栏是否显示出来
```
    searchBar.showsScopeBar = YES;
```

- ##### selectedScopeButtonIndex————搜索栏下部的选择栏按钮的个数
```
    searchBar.selectedScopeButtonIndex = 1;
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

- ##### autocorrectionType————是否纠错
```
    textfield.autocorrectionType = UITextAutocorrectionTypeDefault;
```
>     UITextAutocorrectionTypeNo    不自动纠错
>
    UITextAutocorrectionTypeYes   自动纠错

- ##### backgroundImage————设置控件背景图片
```
    searchBar.backgroundImage = [UIImage imageNamed:@"1.png"];
```

- ##### scopeBarBackgroundImage————设置搜索栏下部背景图片
```
    searchBar.scopeBarBackgroundImage = [UIImage imageNamed:@"2.png"];
```

***
### 代理
- ##### UISearchBar得到焦点并开始编辑时，执行该方法
```
-(BOOL)searchBarShouldBeginEditing:(UISearchBar *)searchBar;           // return NO to not become first responder
```

- ##### 开始编辑时调用
```
-(void)searchBarTextDidBeginEditing:(UISearchBar *)searchBar{          // called when text starts editing
          [searchBar setShowsCancelButton:YES animated:YES];   //  动画显示取消按钮
}
```

- ##### 将要结束编辑时调用
```
-(BOOL)searchBarShouldEndEditing:(UISearchBar *)searchBar;       // return NO to not resign first responder
```

- ##### 结束编辑时调用
```
-(void)searchBarTextDidEndEditing:(UISearchBar *)searchBar;            // called when text ends editing
```

- ##### 内容发生改变时调用
```
-(void)searchBar:(UISearchBar *)searchBar textDidChange:(NSString *)searchText{   // called when text changes (including clear)
```

***
### 按钮点击方法
- ##### 点击搜索按钮时调用
```
-(void)searchBarSearchButtonClicked:(UISearchBar *)searchBar;     // called when keyboard search button pressed
```

- ##### 点击书按钮时调用
```
-(void)searchBarBookmarkButtonClicked:(UISearchBar *)searchBar;        // called when bookmark button pressed
```

- ##### 点击取消按钮时调用
```
-(void)searchBarCancelButtonClicked:(UISearchBar *) searchBar{           // called when cancel button pressed
    [searchBar setShowsCancelButton:NO animated:NO];    // 取消按钮回收
    [searchBar resignFirstResponder];                                // 取消第一响应值,键盘回收,搜索结束
}
```

- ##### 点击搜索结果按钮时调用
```
-(void)searchBarResultsListButtonClicked:(UISearchBar *)searchBarNS_AVAILABLE_IOS(3_2);// called when search results button pressed
```

- ##### 点击下面搜索栏按钮时调用
```
-(void)searchBar:(UISearchBar *)searchBar selectedScopeButtonIndexDidChange:(NSInteger)selectedScopeNS_AVAILABLE_IOS(3_0);
```