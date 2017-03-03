# UICollectionView 表格视图
> 继承**UIScrollView**
***
### 属性
- ##### 创建
```
	UICollectionViewFlowLayout *flowLayout=[[UICollectionViewFlowLayout alloc] init];
	self.collectionView=[[UICollectionView alloc] initWithFrame:CGRectMake(0, 64, 320, 200) collectionViewLayout:flowLayout];
    flowLayout.scrollDirection = UICollectionViewScrollDirectionHorizontal;
// 通过xib注册
  [self.collectionView registerNib:[UINib nibWithNibName:NSStringFromClass([CYXNormalCell class]) bundle:nil] forCellWithReuseIdentifier:reuseIdentifier];
```
>  **UICollectionViewScrollDirectionVertical**   垂直方向
> 
  **UICollectionViewScrollDirectionHorizontal**   水平方向

- ##### backgroundColor————背景颜色
```
    collectionView.backgroundColor = [UIColor redColor];
```

- ##### minimumLineSpacing————设置横向item距离
```
    flowLayout.minimumLineSpacing = 0;
```

- ##### minimumInteritemSpacing————设置纵向item距离
```
    flowLayout.minimumInteritemSpacing = 0;
```

- ##### reloadData————刷新
```
    [collectionView reloadData];
```

*** 
###方法，代理，数据源
- ##### 区块数
```
-(NSInteger)numberOfSectionsInCollectionView:(UICollectionView *)collectionView {
    return 100;
}
```

- ##### item个数
```
-(NSInteger)collectionView:(UICollectionView *)collectionView numberOfItemsInSection:(NSInteger)section {
    return 100;
}
```

- ##### 展示内容
```
-(__kindof UICollectionViewCell *)collectionView:(UICollectionView *)collectionView cellForItemAtIndexPath:(NSIndexPath *)indexPath {
    UICollectionView *cell = [collectionView dequeueReusableCellWithReuseIdentifier:@"cell" forIndexPath:indexPath];
    return cell;
}
```

- ##### item尺寸
```
-(CGSize)collectionView:(UICollectionView *)collectionView layout:(UICollectionViewLayout *)collectionViewLayout sizeForItemAtIndexPath:(NSIndexPath *)indexPath {
    return CGSizeMake(0, 0);
}
```

- ##### 表头尺寸
```
-(CGSize)collectionView:(UICollectionView *)collectionView layout:(UICollectionViewLayout *)collectionViewLayout referenceSizeForHeaderInSection:(NSInteger)section {
    return CGSizeMake(0, 0);
}
```

- ##### 表尾尺寸
```
-(CGSize)collectionView:(UICollectionView *)collectionView layout:(UICollectionViewLayout *)collectionViewLayout referenceSizeForFooterInSection:(NSInteger)section {
    return CGSizeMake(0, 0);
}
```

- ##### 表头表尾内容
```
-(UICollectionReusableView*)collectionView:(UICollectionView *)collectionView viewForSupplementaryElementOfKind:(NSString *)kind atIndexPath:(NSIndexPath *)indexPath {
    return nil;
}
```

- ##### item边缘间隙
```
-(UIEdgeInsets)collectionView:(UICollectionView *)collectionView layout:(UICollectionViewLayout *)collectionViewLayout insetForSectionAtIndex:(NSInteger)section {
    return UIEdgeInsetsMake(0, 0, 0, 0);
}
```
- ##### 点击事件
```
-(void)collectionView:(UICollectionView *)collectionView didSelectItemAtIndexPath:(NSIndexPath *)indexPath {
}
```

- ##### 是否可以被选择
```
-(BOOL)collectionView:(UICollectionView *)collectionView shouldSelectItemAtIndexPath:(NSIndexPath *)indexPath {
	return YES;
}
```

### 仅供参考,错误勿怪！