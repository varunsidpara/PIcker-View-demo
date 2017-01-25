//
//  ViewController.m
//  PickerViewDemo
//
//  Created by ci yosemite 2 on 19/01/17.
//  Copyright (c) 2017 ci yosemite 2. All rights reserved.
//

#import "ViewController.h"

@interface ViewController ()

@end

@implementation ViewController
{

    NSArray *pickerContent;

}

- (void)viewDidLoad {
    [super viewDidLoad];

    teamArray   = [[NSArray alloc]initWithObjects:@"Chess",
                   @"Cricket",@"Football",@"Tennis",@"Volleyball", nil];
    
    photoArray   = [[NSArray alloc]initWithObjects:@"Sachin-Tendulkar.jpg",@"Shahid-Afridi.jpg",@"shoaib-akhtar.jpg",@"MS-Dhoni.jpg",@"wasim-akram.jpg",@"Brian-Lara.jpg",@"Chris-Gayle.jpg",@"Lasith-Malinga.jpg",@"Muttiah-Muralidharan.jpg",@"brett-lee.jpg", nil];
    
    nameArray = [[NSArray alloc]initWithObjects:@"Sachin Tendulkar",@"Shahid Afridi",@"Shoaib Akhtar",@"M S Dhoni",@"Wasim Akram",@"Barin Lara",@"Chris Gayle",@"Lasith Malinga",@"Muttiah Murlidharan",@"Brett Lee", nil];

    pickerContent = [[NSArray alloc]initWithObjects:[UIImage imageNamed:@"Sachin-Tendulkar.jpg"],
                     [UIImage imageNamed:@"Shahid-Afridi.jpg"],
                     [UIImage imageNamed:@"shoaib-akhtar.jpg"],
                     [UIImage imageNamed:@"MS-Dhoni.jpg"],
                     [UIImage imageNamed:@"wasim-akram.jpg"],
                     [UIImage imageNamed:@"Brian-Lara.jpg"],
                     [UIImage imageNamed:@"Chris-Gayle.jpg"],
                     [UIImage imageNamed:@"Lasith-Malinga.jpg"],
                     [UIImage imageNamed:@"Muttiah-Muralidharan.jpg"],
                     [UIImage imageNamed:@"brett-lee.jpg"],nil];
    

}

- (void)didReceiveMemoryWarning {
    [super didReceiveMemoryWarning];
    // Dispose of any resources that can be recreated.
}

#pragma mark - Picker View Data source
- (NSInteger)numberOfComponentsInPickerView:(UIPickerView *)pickerView
{
    //Two columns
    return 3;
}
- (NSInteger)pickerView:(UIPickerView *)pickerView numberOfRowsInComponent:(NSInteger)component{
    //set number of rows
    if(component== 0)
    {
        return photoArray.count;
    }
    else if(component== 1)
    {
        return [teamArray count];
    }
    else if(component == 2)
    {
        return [nameArray count];
    }
    return 0;
}
- (NSString *)pickerView:(UIPickerView *)pickerView titleForRow:(NSInteger)row forComponent:(NSInteger)component{
    
    if(component == 0)    {
        return [photoArray objectAtIndex:row];
    }
    else if(component == 1)
    {
        return [teamArray objectAtIndex:row];
    }
    else if(component == 2)
    {
        return [nameArray objectAtIndex:row];
        
    }
    
    return @"";
}

#pragma mark- Picker View Delegate
-(void)pickerView:(UIPickerView *)pickerView didSelectRow:(NSInteger)row inComponent:(NSInteger)component{
    
    if (component==0)
        [imageView setImage:[UIImage imageNamed:[photoArray objectAtIndex:row]]];
    else if (component==1)
        [teamTextField setText:[teamArray objectAtIndex:row]];
    else if (component==2)
        [nameTextField setText:[nameArray objectAtIndex:row]];
}

@end
