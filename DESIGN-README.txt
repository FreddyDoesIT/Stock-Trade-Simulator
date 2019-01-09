A How To Invest For Dummies Application

- Version 3

Compared with last version, we have made some big feature update in this one:

1. User can now choose either console-based user interface to use this application or choose GUI to interact. It is convenient. This can let user continuously track whether or not his/her portfolio is a wise choice.
2. The console-based UI can now 
	•save a portfolio to file
	•retrieve a portfolio from a file
	•save an investment strategy to file
	•retrieve an investment strategy from a file and apply it to a portfolio
   This is a big improvement compared with the last version. It can keep you on track as all you wish.
3. The newly added GUI version is not a newbie. It can do anything that a console-based one can.

*******************************************************************************************************************************
- Version 2
At this version, we have updated our application to make it more realistic and user-friendly.
Changes are as follows:

1. Users can input transaction fee for each of their transaction.
2. Transaction fee has been included into the buying cost which is more realistic.
3. Users can buy shares in fractional, not restricted to a whole number. This is more reasonable for users who want to invest
   with an amount which is not able to buy some stocks for whole number shares.
4. Users can invest periodically. This is a safer strategy for users who want more stability.
5. Users can invest directly with money with choice not to decide how many shares they want to buy in.
   This is more convenient for users who want to invest directly instead of calculating how many shares they want to purchase.
6. Related prompt information has become more user-friendly. Clarity and informativeness is our pursuit.

This is the new main menu.

Welcome! Enter the number in each line to start making bucks.
1. Please create your portfolio by giving it a name and choosing some stocks.
   Or you can add stocks into an existing portfolio.
2. Come on and buy shares of the stocks in your portfolio.
3. Find out the cost and value of your portfolio.
4. Have a look at what is the composition of your portfolio:
5. Invest a fixed amount into an existing portfolio, using a specified weight for each stock.
6. Dollar-cost averaging investment strategies.
7. Exit How-To-Invest-For-Dummies.

Like the previous version of our product, users enter the number in each line to start our program.

*******************************************************************************************************************************
- Version 1
-	Files included in this application:

The stock package: stock						
The controller package: controller		IController interface.		
Controller			    This is the implementation of controller. 		
IController			    This is the interface controller.IController.
PromptInformation		This is the class showing prompt information in the console.
The model package:model					
CheckingStock			This is a helper class to get some values about stock.
IModel				    This is the model.IModel interface.
IStock				    This is the model.IStock interface which requires some methods that its implementation should override.
MockModel			    The mock model to test if the controller works right.
Model				    This is the implementation of the model.IModel.
Stock				    This is the implementation of IStock implementation.
The view package:view					
IView				    This is the interface view.IView.
View				    This is the implementation of view.IView interface.
HowToInvestForDummies	This is function includes the main function.


This application selects the MVC architecture as the design pattern.

At this version of our application, we allow VIEW, CONTROLLER, and MODEL to assume their own responsibilities.

First and foremost, our model is always the heavy lifter. 
In this part, we have two interfaces IModel and IStock with their own implementation of Model and Stock respectively. There is also a MockModel to test if the controller works as expected, that is it is supposed to transmit correctly. Also there is a helper class to get some values about stock in CheckingStock. 
The model can create a porfolio or as many as they want, buy shares for any stock in user's portfolio, query the cost and value of the portfolio, test if the portfolio is existed or some stock is in some portfolio, and display what stocks are in one portfolio.


Next comes to our controller which serves as the bridge between the view and model.
This part has an interface mandates it should start running once there are inputs from console.
It takes in input from console and with the help of five private functions to run smoothly.
The controller will check whether the input is valid, and conduct relevent actions. It continuously interacts with user. Once all the input from console are valid, controller would throw the main logic work to the model to deal with, and then throw output to view to display.
For example: when the console displays (the view to display) "
Go ahead by entering the number in each line.
1. Please create your portfolio:
2. Do you want to add some stocks to your portfolio?
3. Find out the cost and value in your portfolio.
4. Have a look at what is the composition of your portfolio:
5. Exit How-To-Invest-For-Dummies.
"
The controller will tell if the input is 1 or 2 or 3 etc.If not, then controller will prompt information to user. 
Once the program enters to "
Go ahead by entering the number in each line.
1. Please create your portfolio:
2. Do you want to add some stocks to your portfolio?
3. Find out the cost and value in your portfolio.
4. Have a look at what is the composition of your portfolio:
5. Exit How-To-Invest-For-Dummies.
1
Please create a name for your portfolio.
 Press Enter to continue, and Q or q back to the main menu.
"
The further logic would be dealt with by model.

What at last is our view, it handles the output at this version of our application.
