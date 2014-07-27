# LBHamburgerButton #

Bang Nguyen

@luongbang152

http://luongbang.me

## Overview ##

LBHamburgerButton is an iOS control that displays 3 lines (hamburger) and other icon (back, close...) without using image. It has a beautiful, clean and smooth transition between 2 state like Google Material Design or "close button" of Paper app.

## Requirement ##

LBHamburgerButton use QuartzCore framework, so dont forget to add this framework. ARC (iOS 5+) is also required.

## How to use ##

First, you need to copy 2 files LBHamburgerButton.h/.m to your project. Then, import them to your class

```objc
#import "LBHamburgerButton.h"
```

This is a sub-class of UIButton. So you can init a simple button and call set-up method:

```objc
buttonHamburger = [[LBHamburgerButton alloc] initWithFrame:CGRectMake(0, 0, 100, 100)];
[buttonHamburger setUpHamburgerWithType:LBHamburgerButtonTypeCloseButton
                              lineWidth:50
                             lineHeight:50/6
                            lineSpacing:5
                             lineCenter:CGPointMake(50, 50)
                                  color:[UIColor whiteColor]];
```

or use full contructor like this:

```objc
buttonHamburger = [[LBHamburgerButton alloc] initWithFrame:CGRectMake(0, 0, 100, 100)
                                         withHamburgerType:LBHamburgerButtonTypeCloseButton
                                                 lineWidth:50
                                                lineHeight:50/6
                                               lineSpacing:5
                                                lineCenter:CGPointMake(50, 50)
                                                     color:[UIColor whiteColor]];
```

Set other propertises, add target add it to view like UIButton.

```objc
[buttonHamburger setCenter:CGPointMake(120, 120)];
[buttonHamburger setBackgroundColor:[UIColor blackColor]];
[buttonHamburger addTarget:self action:@selector(buttonPressed:) forControlEvents:UIControlEventTouchUpInside];

[self.view addSubview:buttonHamburger];
```

When you want to switch state, just call `switchState`.

```objc
- (void)buttonPressed:(id)sender {
    LBHamburgerButton* btn = (LBHamburgerButton*)sender;
    [btn switchState];
}
```

## Release notes

Version 1.0

Initial release
Two type
- Back (<-)
- Close (x)

## MIT License
Copyright (c) 2014 Bang Nguyen

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.