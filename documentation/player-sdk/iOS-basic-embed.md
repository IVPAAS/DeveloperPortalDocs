---
layout: page
title: iOS Player SDK Basic embedding  
---


# Using Kaltura player

## Import KPViewController to main project

```
#import <KALTURAPlayerSDK/KPViewController.h>
```

## Create KPViewController instance:

```
@property (retain, nonatomic) KPViewController *player;
```

## To Initialize PlayerViewController for Fullscreen:

``` objc 
- (KPViewController *)player {
    if (!_player) {
        // Account Params
        KPPlayerConfig *config = [[KPPlayerConfig alloc] initWithServer:@"http://cdnapi.kaltura.com"
                                                         uiConfID:@"26698911"
                                                         partnerId:@"1831271"];
        
        
        // Video Entry
        config.entryId =  @"1_o426d3i4";
        
        // Setting this property will cache the html pages in the limit size
        config.cacheSize = 0.8;
        _player = [[KPViewController alloc] initWithConfiguration:config];
    }
    return _player;
}

- (void)viewDidAppear:(BOOL)animated {
    [super viewDidAppear:animated];
    [self presentViewController:self.player animated:YES completion:nil];
}
```
![iOS-fullscreen](./images/iOS-fullscreen-embed.png)


## To Initialize PlayerViewController for Inline

[Inline player](Fullscreen-inline-iOS.md)
