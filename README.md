
#测试git远程仓库修改 
#原git链接 https://github.com/liuxinixn/LXCalendar
# LXCalendar

一个简单的日历控件，会一步步完善。


![image](https://github.com/liuxinixn/LXCalendar/blob/master/calendar.gif)

```
typedef void (^SelectBlock) (NSInteger year ,NSInteger month ,NSInteger day);
@interface LXCalendarView : UIView
/*
 * 当前月的title颜色
 */
@property(nonatomic,strong)UIColor *currentMonthTitleColor;
/*
 * 上月的title颜色
 */
@property(nonatomic,strong)UIColor *lastMonthTitleColor;
/*
 * 下月的title颜色
 */
@property(nonatomic,strong)UIColor *nextMonthTitleColor;

/*
 * 选中的背景颜色
 */
@property(nonatomic,strong)UIColor *selectBackColor;

/*
 * 今日的title颜色
 */
@property(nonatomic,strong)UIColor *todayTitleColor;

/*
 * 选中的是否动画效果
 */
@property(nonatomic,assign)BOOL     isHaveAnimation;



/*
 * 是否禁止手势滚动
 */
@property(nonatomic,assign)BOOL     isCanScroll;

/*
 * 是否显示上月，下月的按钮
 */
@property(nonatomic,assign)BOOL     isShowLastAndNextBtn;

/*
 * 是否显示上月，下月的的数据
 */
@property(nonatomic,assign)BOOL     isShowLastAndNextDate;

/*
 * 在配置好上面的属性之后执行
 */
-(void)dealData;

//选中的回调
@property(nonatomic,copy)SelectBlock selectBlock;
```

使用方法：
```

 self.calenderView =[[LXCalendarView alloc]initWithFrame:CGRectMake(20, 80, Device_Width - 40, 0)];
    
    self.calenderView.currentMonthTitleColor =[UIColor hexStringToColor:@"2c2c2c"];
    self.calenderView.lastMonthTitleColor =[UIColor hexStringToColor:@"8a8a8a"];
    self.calenderView.nextMonthTitleColor =[UIColor hexStringToColor:@"8a8a8a"];
    
    self.calenderView.isHaveAnimation = NO;
    
    self.calenderView.isCanScroll = YES;
    self.calenderView.isShowLastAndNextBtn = NO;
    
    self.calenderView.isShowLastAndNextDate = YES;

    self.calenderView.todayTitleColor =[UIColor redColor];
    
    self.calenderView.selectBackColor =[UIColor greenColor];
    
    [self.calenderView dealData];
    
    self.calenderView.backgroundColor =[UIColor whiteColor];
    [self.view addSubview:self.calenderView];
    
    self.calenderView.selectBlock = ^(NSInteger year, NSInteger month, NSInteger day) {
        NSLog(@"%ld年 - %ld月 - %ld日",year,month,day);
    };
```
