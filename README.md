# challenge_15
## Project Overview
Combine AWS skills with existing Python to create a bot that will recommend an investment portfolio for a retirement plan.
---

## Technologies

The application is using Lex and AWS Lamda. Lamda code is provided in a separate file in gitHub. Also I have inculded a video of the Lex bot to show the functionality.


# Imports


The operating system used in creating the application is Windows 10 64 bit. 

Sample Python code from Lamda:

```python

    output = ""
    if age >= 25 and age <=65:
        output = "You're in the right age range."
    else: 
        output = "Please enter your age between 25 and 65 and a minimum of $5000 investment."
    return output


def validate_data(age, investment_amount, intent_request):
    """
    Validates the data provided by the user.
    """

    # Validate that the user age is between 25 and 65 years old    
    if age is not None:
        age = parse_int(age)
        if age not in range (25,65):      
            return build_validation_result(
                False,
                "age",
                "You should be at least 25 years to open an account.",
            )
        
    # Validate the investment amount, it should be >= 5,000
    if investment_amount is not None:
        investment_amount = parse_int(
            investment_amount
        )  # Since parameters are strings it's important to cast values
        if investment_amount < 5000:
            return build_validation_result(
                False,
                "investmentAmount",
                "Your investment amount should be equal to or greater than $5,000."
            )

    # A True results is returned if age or investment amount are valid
    return build_validation_result(True, None, None)

```

---

## Installation Guide

1. Open Gitbash or terminal and go in to the folder where you want to place the files.
2. Click on the blue "code" button which will allow you to clone.![<Code button in Github>]()
3. Then click on SSH or HTTPS as a clone method depending on if you have the SSH key setup. You will copy the link. You will then type "git clone" in Gitbask or Terminal. Then paste the ssh or https information and press enter.
4. Next type "git pull" command in Terminal or GitBash to pull the repository from the remote Github repository to a local directory on your computer.
5. You have access to the application. 

---

## Usage

The project accomplishes the following main tasks:

Configure the initial robo advisor: Define an Amazon Lex bot with a single intent that establishes a conversation about requirements to suggest an investment portfolio for retirement.

Build and test the robo advisor: Make sure that your bot works and accurately responds during the conversation with the user.

Enhance the robo advisor with an Amazon Lambda function: Create an Amazon Lambda function that validates the user's input and returns the investment portfolio recommendation. This includes testing the Amazon Lambda function and integrating it with the bot.

---

## Contributors

This application was provided by the instrutor of Columbia University and addtional code was added by Khatija Azeem to complete the project.

---

## License

For this application, I used Github to uplaod the file into a repository. Since this is a public file, there will be no restriction on usage of this code. 
