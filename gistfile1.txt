//
//  ViewController.h
//  PickerViewDemo
//
//  Created by ci yosemite 2 on 19/01/17.
//  Copyright (c) 2017 ci yosemite 2. All rights reserved.
//

#import <UIKit/UIKit.h>

@interface ViewController : UIViewController<UIPickerViewDataSource,UIPickerViewDelegate,UITextFieldDelegate>
{
    
    IBOutlet UIImageView *imageView;
    IBOutlet UIPickerView *myPickerView;
    IBOutlet UITextField *nameTextField;
    IBOutlet UITextField *teamTextField;
    
    NSArray *photoArray;
    NSArray *teamArray;
    NSArray *nameArray;

}
@end

