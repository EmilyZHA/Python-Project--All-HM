Homework 01 - Currency Converter
Consider money that you need to convert into another currency.

We will ask you to code a converter function by asking the user to give an input value and specify the conversion he or she wants to make (from the source currency to the target currency).

Step one
Let's assume you are a user who wants to convert money from EUR to YEN (Japanese currency).

Please take the currency value to be 1 EUR = 157.58 YEN

Write a code that:

(1) Asks from the user for an input
This value will be considered to be in EUR.
(2) Call your converter fCheck the value and raise an error if it is not a numerical or positive value.
All your error messages must start with "Error: "
On error, the function returns -1.unction with this value.
(3)
(4) Then calculates the value in YEN.
(5) Return the result.
def currency_converter(value):
    
    error_message = 'Error: your value should be a positive number'
    ### (3) your code here
  
    try:
        if float(value)<=0:# if user input is negative or zero, raise an error
            print(error_message)
            return -1
    except:
        print(error_message)# if there is any error occur,raise an error
        return -1
    else:
        conversion=float(value)*157.58
         
    ### (5) 
        return conversion
prompt = 'Enter a value in EUR to be converted to YEN:'
​
### (1) your code here
user_input = input(prompt)
​
output=currency_converter(user_input)###2
​
print(f"Your input is equal to {output} YEN.")
​
Enter a value in EUR to be converted to YEN:10
Your input is equal to 1575.8000000000002 YEN.
Step two
Let's now consider multiple options of conversion from one currency to another one.

Create a function that takes two inputs:

the value (in EUR) to be converted.
the final currency for which you need to know the value.
For this exercise, you will consider the following currencies: YEN / USD / CAD / GBP / INR

The conversion rates are:

1 EUR = 157.58 YEN
1 EUR = 0.99 USD
1 EUR = 1.35 CAD
1 EUR = 0.86 GBP
1 EUR = 81.90 INR
When asking for inputs from the user, please stick to upper case letters

def currency_converter2(value, currency):
​
    error_message = 'Error: your value should be a positive number'
    error_message2 = 'Error: select one of the given currencies (YEN / USD / CAD / GBP / INR)'
​
    ### your code here
    currency_list=['YEN','USD','CAD','GBP','INR']
    exchange_list={'YEN':157.58,'USD':0.99,'CAD':1.35,'GBP':0.86,'INR':81.90}# all currency and change rate 
    try:
        if float(value)<=0 or str(value).isalpha ==True: # if input is negative or alpha, raise an error
            print(error_message)
            return -1
        if currency not in currency_list: 
            print(error_message2)
            return -1 
    except:# if any error occurs, raise an error
            print(error_message)
    else:
        conversion = float(value)*exchange_list[currency]
        return conversion
euro_amount = input('Please enter a value in EUR:')
currency_choice = input('Please enter the currency converted to(YEN / USD / CAD / GBP / INR)').upper()
output = currency_converter2(euro_amount, currency_choice)
currency=currency_choice
​
​
print(f"Your input is equal to {output} {currency}.")
Please enter a value in EUR:10
Please enter the currency converted to(YEN / USD / CAD / GBP / INR)USD
Your input is equal to 9.9 USD.
More tests:

input1 = 12
input2 = 'GBP'
currency_converter2(input1, input2)
input1 = 30.45
input2 = 'INR'
currency_converter2(input1, input2)
Step three
In this last step, you will extend the programme you're programming once again!

Now you will not only consider one input currency, but any input currency.

This means that the user will have to specify which currency the input is in, and he or she will also have to specify the output currency.

So here is what you need to do:

Add another input from the user specifying the input or initial currency.
Take time before coding to consider all the ways of converting from one currency to another.

Concerning the conversion rates, use the ones given in step 2.

def currency_converter3(value, currency1, currency2):
​
    error_message = 'Error: your value should be a positive number'
    error_message2 = 'Error: select one of the given currencies (YEN / USD / CAD / GBP / INR)'
​
    ### your code here
    currency_list=['YEN','USD','CAD','GBP','INR','EUR']
    exchange_list={('EUR','YEN'):157.58,
                   ('EUR','USD'):0.99,
                   ('EUR','CAD'):1.35,
                   ('EUR','GBP'):0.86,
                   ('EUR','INR'):81.9,
                   ('YEN','EUR'):0.006,
                   ('YEN','USD'):0.006,
                   ('YEN','CAD'):0.009,
                   ('YEN','GBP'):0.005,
                   ('YEN','INR'):0.52,
                   ('USD','EUR'):1.01,
                   ('USD','YEN'):159.17,
                   ('USD','CAD'):1.36,
                   ('USD','GBP'):0.87,
                   ('USD','INR'):82.73,
                   ('CAD','EUR'):0.74,
                   ('CAD','YEN'):116.73,
                   ('CAD','USD'):0.73,
                   ('CAD','GBP'):0.64,
                   ('CAD','INR'):60.67,
                   ('GBP','EUR'):1.16,
                   ('GBP','YEN'):183.23,
                   ('GBP','USD'):1.15,
                   ('GBP','CAD'):1.57,
                   ('GBP','INR'):95.23,
                   ('INR','EUR'):0.01,
                   ('INR','YEN'):1.924,
                   ('INR','USD'):0.012,
                   ('INR','CAD'):0.016,
                   ('INR','GBP'):0.011
                  }
  
    try:
        if float(value)<=0 or str(value).isalpha ==True: # if input is negative or alpha, raise error
            print(error_message)
            return -1
        if currency1 not in currency_list or currency2 not in currency_list:
            print(error_message2)
            return -1 
    except:
            print(error_message)
    else:
        conversion = float(value)*exchange_list[currency1,currency2]
        return conversion
​
currency_converter1=input('Please enter the converted currency(YEN / USD / CAD / GBP / INR / EUR):').upper()
currency_converter2=input('Please enter the currency which convert to  (YEN / USD / CAD / GBP / INR / EUR):').upper()
euro_amount=input('Please enter convert amount:')
output=currency_converter3(euro_amount, currency_converter1,currency_converter2)
​
​
​
print(f"Your input in {currency_converter1}, is equal to {output} {currency_converter2}.")
    
    
​
Please enter the converted currency(YEN / USD / CAD / GBP / INR / EUR):EUR
Please enter the currency which convert to  (YEN / USD / CAD / GBP / INR / EUR)USD
Please enter convert amount:10
Your input in EUR, is equal to 9.9 USD.
