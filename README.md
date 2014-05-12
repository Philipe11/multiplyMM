#import "XYZViewController.h"

@interface XYZViewController ()

@property (weak, nonatomic) IBOutlet UITextField *myNumber;

@property (weak, nonatomic) IBOutlet UILabel *myMultiplier;

@property (weak, nonatomic) IBOutlet UILabel *myAnswer;

@property (weak, nonatomic) IBOutlet UISlider *mySlider;


@end

@implementation XYZViewController

- (void)viewDidLoad

{
    [super viewDidLoad];


    self.mySlider.minimumValue = 0;

    self.mySlider.maximumValue = 100;

}

- (IBAction)changeMultiplier:(id)sender

{

    UISlider *slider = (UISlider *) sender;

    int val = slider.value;

    self.myMultiplier.text = [NSString stringWithFormat:@"%d", val];

}

- (IBAction)onCalculateButtonPressed:(id)sender

{

    int number1 = [self.myNumber.text integerValue];

    int number2 = [self.myMultiplier.text integerValue];
   
    NSInteger value = number1 * number2;

    if (value > 20)

    {

        self.view.backgroundColor = [UIColor greenColor];

    }


    else {

        self.view.backgroundColor = [UIColor whiteColor];

    }

    if (value % 3 == 0)

    {

        if (value % 5 == 0)

        {

            self.myAnswer.text = @"fizzbuzz";

        }

        else

        {

        self.myAnswer.text = @"fizz";

        }

    }
   
    else if (value % 5 == 0)
   
    {
   
        self.myAnswer.text = @"buzz";
   
    }

    else 
    
    {
   
        self.myAnswer.text = [NSString stringWithFormat:@"%d", value];

    }

}


- (void)didReceiveMemoryWarning

{

    [super didReceiveMemoryWarning];

}

@end
