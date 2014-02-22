![image](https://github.com/JackTeam/PathCover/raw/master/Screenshots/PathCover.gif)
![image](https://github.com/JackTeam/PathCover/raw/master/Screenshots/PathCoverZooming.gif)

=========

PathCover is pull down refresh and a parallax/zooming top view with real time blur effect to any UITableView, inspired by Path for iOS.        

Completely created using UIKit/QuartzCore/Accelerate framework, AudioToolbox framework to play sound to refreshing.    

Easy to drop into your project.      

You can add this feature to your own project, `PathCover` is easy-to-use.        

## Requirements ##

PathCover requires Xcode 5, targeting either iOS 5.0 and above, ARC-enabled.      

## Profile

[CocosPods](http://cocosPods.org) is the recommended methods of installation XHPathCover, just add the following line to `Profile`:

```
pod 'XHPathCover', '~> 0.1.0'
```

## How to use ##
```objc
zooimg effect property to user, but if you user zooimg effect, will be dissmiss parallax effect.      

#import "XHPathCover.h"    

@property (nonatomic, strong) XHPathCover *pathCover;       

_pathCover = [[XHPathCover alloc] initWithFrame:CGRectMake(0, 0, CGRectGetWidth(self.view.bounds), 250)];
[_pathCover setBackgroundImage:[UIImage imageNamed:@"MenuBackground"]];
[_pathCover setAvatarImage:[UIImage imageNamed:@"meicon.png"]];
[_pathCover setInfo:[NSDictionary dictionaryWithObjectsAndKeys:@"Jack", XHUserNameKey, @"1990-10-19", XHBirthdayKey, nil]];
self.tableView.tableHeaderView = self.pathCover;
    
[_pathCover setHandleRefreshEvent:^{
    // refresh your data sources
}];
    
#pragma mark - scroll delegate

- (void)scrollViewDidScroll:(UIScrollView *)scrollView {
    [_pathCover scrollViewDidScroll:scrollView];
}

- (void)scrollViewDidEndDecelerating:(UIScrollView *)scrollView {
    [_pathCover scrollViewDidEndDecelerating:scrollView];
}

- (void)scrollViewDidEndDragging:(UIScrollView *)scrollView willDecelerate:(BOOL)decelerate {
    [_pathCover scrollViewDidEndDragging:scrollView willDecelerate:decelerate];
}

- (void)scrollViewWillBeginDragging:(UIScrollView *)scrollView {
    [_pathCover scrollViewWillBeginDragging:scrollView];
}

```
## Lincense ##

`PathCover` is available under the MIT license. See the LICENSE file for more info.
