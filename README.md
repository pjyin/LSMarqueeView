# LSMarqueeView
A fast-integrated marquee(跑马灯)

## How to use
add the head file to your project

```objc
// >>>>>> dataSorce >>>>>
NSMutableArray *tempArr = @[].mutableCopy;
UILabel *labelOne = [UILabel new];
labelOne.font = [UIFont systemFontOfSize:14];
labelOne.text = @"☺ 这是一个广告标题1~";
labelOne.textColor = [UIColor blackColor];
    
UILabel *labelTwo = [UILabel new];
labelTwo.font = [UIFont systemFontOfSize:14];
labelTwo.text = @"☺ 这是一个广告标题2~~";
labelTwo.textColor = [UIColor blackColor];
    
UILabel *labelThree = [UILabel new];
labelThree.font = [UIFont systemFontOfSize:14];
labelThree.text = @"☺ 这是一个广告标题3~~~";
labelThree.textColor = [UIColor blackColor];
    
[tempArr addObject:labelOne];
[tempArr addObject:labelTwo];
[tempArr addObject:labelThree];
// >>>>>> dataSorce >>>>>
    
self.marqueeView = [[LSMarqueeView alloc] initWithFrame:CGRectMake(10, 100, 354, 60) andLableArr:tempArr];
[self.view addSubview:self.marqueeView];
    
self.marqueeView.clickBlock = ^(id sender){
   NSLog(@"sender %@", sender);
};
```

Turn on or off rotation
    
```objc
#pragma mark - self Life cycle

- (void)viewDidAppear:(BOOL)animated{
    [self.marqueeView  startCountdown];
}

- (void)viewWillDisappear:(BOOL)animated{
    dispatch_source_cancel(self.marqueeView.timer);
}
```

## Example
![example](example.gif)

## See More
[一个尴尬的轮子之跑马灯](https://www.lsrain.com/2017/07/19/iOS/一个尴尬的轮子之_跑马灯/)

