# Animations
一些动画的飞机稿，都是一些单独分离出来的用于测试的子动画，现在统一归类一下。

##1.AnimatedCurveDemo

![](curverAnim_2.gif)

###Usage:

```objc

   KYPullToCurveVeiw *headerView = [[KYPullToCurveVeiw alloc]initWithAssociatedScrollView:self.tableView];

    __weak KYPullToCurveVeiw *weakHeaderView = headerView;

    [headerView addRefreshingBlock:^{
        
        //具体的操作
        //...
    
        double delayInSeconds = 2.0;
        dispatch_time_t popTime = dispatch_time(DISPATCH_TIME_NOW, delayInSeconds * NSEC_PER_SEC);
        dispatch_after(popTime, dispatch_get_main_queue(), ^(void){
        
            [weakHeaderView stopRefreshing];
            
        });

    }];


```
