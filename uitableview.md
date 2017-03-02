# UITableView 表视图
***
### 属性
- ##### 创建
```
    UITableView *tableView = [[UITableView alloc] initWithFrame:self.view.bounds style:UITableViewStylePlain];
```
>     UITableViewStylePlain   基本类型
> 
 UITableViewStyleGrouped   分组类型

- ##### separatorStyle————分割线类型
```
    tableView.separatorStyle = UITableViewCellSeparatorStyleNone;//这种分离器风格是目前只支持分组样式表视图
```
>     UITableViewCellSeparatorStyleNone
> 
    UITableViewCellSeparatorStyleSingleLine
 > 
   UITableViewCellSeparatorStyleSingleLineEtched

- ##### separatorInset————分割线的位置
```
    tableView.separatorInset = UIEdgeInsetsMake(0, 20, 0, 20);
```
- ##### separatorColor————分割线的颜色
```
    tableView.separatorColor = [UIColor blackColor];
```

- ##### selectionStyle————选中颜色
```
        cell.selectionStyle = UITableViewCellSelectionStyleNone;
```
>     UITableViewCellSelectionStyleBlue   蓝色
> 
    UITableViewCellSelectionStyleGray   灰色
>
    UITableViewCellSelectionStyleDefault   默认

- ##### accessoryType————cell右边格式
```
        cell.accessoryType = UITableViewCellAccessoryNone;
```
> **UITableViewCellAccessoryDisclosureIndicator**   cell的右边有一个小箭头，距离右边有十几像素
> 
**UITableViewCellAccessoryDetailDisclosureButton**   cell右边有一个蓝色的圆形button
> 
**UITableViewCellAccessoryCheckmark**   cell右边的形状是对号

***
### 代理Delegate & 数据源DataSouce
- ##### 区数
```
-(NSInteger)numberOfSectionsInTableView:(UITableView *)tableView {
    return 100;
}
```

- ##### 更新数据
```
    [tableView reloadData];
```

- ##### 行数
```
-(NSInteger)tableView:(UITableView *)tableView numberOfRowsInSection:(NSInteger)section {
    return 100;
}
```

- ##### 显示内容
```
-(UITableViewCell*)tableView:(UITableView *)tableView cellForRowAtIndexPath:(NSIndexPath *)indexPath {
    static NSString *reuse = @"reuseID";//复用,static-只执行一次
    UITableViewCell *cell = [tableView dequeueReusableCellWithIdentifier:reuse];
    if (!cell) {//如果为空,则重新创建,不为空从缓存池中获取
        cell = [[UITableViewCell alloc] initWithStyle:UITableViewCellStyleDefault reuseIdentifier:reuse];
    }
    return cell;
}
```
>     **UITableViewCellStyleValue1**   左对齐标签和蓝色标签左对齐和右对齐文本(用于设置)
> 
    **UITableViewCellStyleValue2**   右对齐标签剩下蓝色文本和左对齐标签(用于手机/联系人)
> 
    **UITableViewCellStyleSubtitle**   左对齐标签顶部和左对齐标签底部灰色文本(用于iPod)

- ##### 行高
```
-(CGFloat)tableView:(UITableView *)tableView heightForRowAtIndexPath:(NSIndexPath *)indexPath {
    return 100;
}
```

- ##### 表头高
```
-(CGFloat)tableView:(UITableView *)tableView heightForHeaderInSection:(NSInteger)section {
    return 100;
}
```

- ##### 表尾高
```
-(CGFloat)tableView:(UITableView *)tableView heightForFooterInSection:(NSInteger)section {
    return 100;
}
```

- ##### 估计行高
```
-(CGFloat)tableView:(UITableView *)tableView estimatedHeightForRowAtIndexPath:(NSIndexPath *)indexPath {
    return 100;
}
```

- ##### 估计表头高
```
-(CGFloat)tableView:(UITableView *)tableView estimatedHeightForHeaderInSection:(NSInteger)section {
    return 100;
}
```

- ##### 估计表尾高
```
-(CGFloat)tableView:(UITableView *)tableView estimatedHeightForFooterInSection:(NSInteger)section {
    return 100;
}
```

- ##### 标题名称
```
-(NSString *)tableView:(UITableView *)tableView titleForHeaderInSection:(NSInteger)section{  
    HeroGroup *hg = _heroAry[section];  
    return hg.header;  
}  
```

- ##### 表头视图
```
-(UIView*)tableView:(UITableView *)tableView viewForHeaderInSection:(NSInteger)section {
    return nil;
}
```

- ##### 尾部说明
```
-(NSString *)tableView:(UITableView *)tableView titleForFooterInSection:(NSInteger)section{  
    HeroGroup *hg = _heroAry[section];  
    return hg.footer;  
}
```

- ##### 表尾视图
```
-(UIView*)tableView:(UITableView *)tableView viewForFooterInSection:(NSInteger)section {
    return nil;
}
```

- ##### 标题索引
```
-(NSArray *)sectionIndexTitlesForTableView:(UITableView *)tableView {
    return indexs;  
}  
```

- ##### 点击事件
```
-(void)tableView:(UITableView *)tableView didSelectRowAtIndexPath:(NSIndexPath *)indexPath {
}
```

- ##### 删除和插入实现的方法  
```
-(void)tableView:(UITableView *)tableView commitEditingStyle:(UITableViewCellEditingStyle)editingStyle forRowAtIndexPath:(NSIndexPath *)indexPath;  
```

- ##### 移动实现的方法  
```
-(void)tableView:(UITableView *)tableView moveRowAtIndexPath:(NSIndexPath *)sourceIndexPath toIndexPath:(NSIndexPath *)destinationIndexPath; 
```

- ##### 设置编辑的样式  
```
-(UITableViewCellEditingStyle)tableView:(UITableView *)tableView editingStyleForRowAtIndexPath:(NSIndexPath *)indexPath;
```
  
- ##### 移动or排序  
```
-(NSIndexPath *)tableView:(UITableView *)tableView targetIndexPathForMoveFromRowAtIndexPath:(NSIndexPath *)sourceIndexPath toProposedIndexPath:(NSIndexPath *)proposedDestinationIndexPath;
```

- ##### 哪些row可以被编辑  
```
-(BOOL)tableView:(UITableView *)tableView canEditRowAtIndexPath:(NSIndexPath *)indexPath;  
 ``` 

- ##### 哪些row可以被移动  
```
-(BOOL)tableView:(UITableView *)tableView canMoveRowAtIndexPath:(NSIndexPath *)indexPath; 
``` 