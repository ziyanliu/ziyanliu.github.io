---
layout: post
title:  "侧滑返回使用FDFullscreenPopGesture遇到的问题"
tags:  "iOS"
date:   2017-01-05 17:19:56 +0800
categories: 总结
---
最近做项目需要侧滑返回在使用FDFullscreenPopGesture遇到个问题。我这里①是隐藏导航栏的，②是显示导航栏的。这样就会出BUG了。当从②左侧边缘往右滑动时，如果只是稍微动一下，而没有返回到①（就是露出一点①页面之后，赶紧往往左滑，确保还停留在②页面）这时就出问题了，②页面的导航栏没了。要是正常侧滑返回不会出现这个问题，这个bug着实让我头痛了一天。

解决办法：

、、、

在viewWillAppear:方法里面添加对是否隐藏NavigationBar的判断

dispatch_after(dispatch_time(DISPATCH_TIME_NOW, (int64_t)(CGFLOAT_MIN * NSEC_PER_SEC)), dispatch_get_main_queue(), ^{
    UIViewController *vc = [self.navigationController.viewControllers lastObject];
    if (vc.fd_prefersNavigationBarHidden) {
        [self.navigationController setNavigationBarHidden:YES animated:NO];
    } else {
        [self.navigationController setNavigationBarHidden:NO animated:NO];
    }
});

、、、

