A4 - Simulated Point of Sale (PoS) System (Java)

CostLessBites catering is coming to Concordia campuses to serve Concordia community (students and their family as well as employees) 
with healthy and budget sales throughout the year. Any member of the community can order meals using either their money or prepaid meal cards. 
In this assignment you will write code to simulate the Point of Sale (PoS) for CostLessBites catering which handles orders either as on-demand sales or prepaid card. 
To do so you will write Sales class, a PrePaiCard class, a PoS class and a driver: PoSDemo.

The catering restaurants offer the following:
▪ Five meal categories: junior, teen, medium, big and family size, for different diets and with flat rate price that includes taxes. 
▪ Meal’s menu from six diets: Carnivore, Halal, Kosher, Pescatarian, Vegetarian, Vigan.
▪ Yearly prepaid cards sold by type of diet.
Following is a description of the three classes you are required to implement and the methods that must be included.

Class Sales
Attributes: you want to keep track of the number of sales sold on-demand: junior ($5), teen ($10), medium ($12), big ($15) and family ($20). 
You should also have static constants for the values of each of these sales which you will need to use to evaluate how much fund you have in a till.

Methods:
− Constructors:
▪ Default constructor
▪ Constructor with 5 integer parameters to set the number of each meal category in the till.
▪ Copy constructor with one parameter of type Sales.
− Accessor and mutator methods for all attributes.
− addSales() method with 5 integer parameters which allows you to increase the number of each meal category by the indicated number.
− SalesTotal() method which returns an integer indicating the total value of the sales in the PoS. For example, 85 means the total payment value sums up to $85.
− toString() method which will return a string clearly indicating the count of each meal in the till. You decide on the format.
− equals() method which will return true if the two objects of type Sales being compared have the same breakdown of meal category and false otherwise.

Class PrePaiCard

Attributes: you want to keep track of the prepaid card type customers used (Carnivore, Halal, Kosher, Pescatarian Vegetarian, Vigan), 
the ID of the card holder (student id: for students and their family members, or employee ID for Concordia employe), 
and the expiry day as an integer, and month as an integer.

Methods:
-Constructors:
▪ Default constructor
▪ Constructor with 4 parameters to set the initial value of each attribute. If the day which is passed is not between 1 and 31, 
set it to 0 and if the month which is passed is not between 1 and 12, set it to 0.
▪ Copy constructor with one parameter of type PrePaiCard.
− Accessor methods for all attributes.
− Mutator methods for the due date and one for the due month. If the proposed day is not between 1 and 31, set it to 0, and 
if the proposed month is not between 1 and 12, set it to 0.
− toString() which will return a string indicating the type of the pre-paid card,the due date formatted as dd/mm. 
If the day number is less than 10, it must be preceded by a zero and if the month number is less than 10, it must be preceded by a zero. 
For example, a pre-paid card that expires on the seventh of January should show a due date of 07/01.
− equals() which will return true if the two objects of type PrePaiCard are identical in other words have exactly the same information and false otherwise.

Class PoS
Attributes: your PoS will contain Sales and PrePaiCards (typically more than one) which will be represented by an object of 
type Sales and an array of objects of type PrePaiCards.

Methods:
− Constructors:
▪ Default constructor
▪ Constructor with 2 parameters to set the initial value of each attribute. One attribute is of type Meals and the other is an array of type PrePaiCard.
(Warning: Be sure to set the attributes of PoS in such a way so as to avoid the risk of any privacy leaks). 
A PoS may contain no pre-paid cards in which case the reference to the array of PrePaiCard objects is set to null.
▪ There is no copy constructor.
− A method which will return true if the total $ value of sales of two PoS objects are equal, and false otherwise.
− A method which will return true if the number of each sales category of two PoS objects are equal, and false otherwise.
− A method which will return the total $ sales of a PoS. `
− A method which will return the number of prepaid cards in a PoS.
− A method which will add a new PrePaiCard to the PoS. You will need to account for a PoS not having any PrePaiCard before the addition.
(Reminder from COMP248 – how do you increase the number of elements in an array?). This method returns the number of the pre-paid cards of a PoS after the addition.
− A method which will remove a pre-paid card from the PoS. You will need to account for a PoS that has no prepaid 
cards. (Reminder from COMP248 – how do you reduce the number of elements in an array?). This method returns true if the removal of the card was successful and false if it was not.
− A method which will update the expiry day and month of a prepaid card.
− A method which will add meals sales to the PoS. This method should have 5 parameters, one for each meal category and returns the new total sales value payments of the PoS.
− equals() method which will return true if the total $ amount sales value and the number of pre-paid card of two PoS objects are equal, and false otherwise.
− toString() which will return a string clearly indicating the number of each meal sales category as well as the details of each pre-paid card of the PoS. 
It is possible for a PoS to have no pre-paid card, in which case “No pre-paid cards” should be indicated.
− A method which will return a string with just the breakdown of the sales.

Finally, to test these three classes, you are to write a driver: PoSDemo which behaves in the following way:
− Welcomes the user.
− Creates at least 5 PoS such that:
▪ 2 PoS have exactly the same sales categories distribution and the same number of prepaid cards.
▪ 1 PoS with the same total $ amount of sales of another PoS but with a different configuration of sales categories and this PoS should have at least 3 prepaid cards.
▪ The last 2 PoSs have the same breakdown of sales but different from the other 3 and both have no prepaid cards.
▪ You can hardcode the PoSs in your driver if you want; this way you won’t need to enter all of this information from the keyboard every time you test your program.

Brief explanation of each choice: (If the user enters an invalid choice, tell them and request a new choice).
1. Display the sales categories and prepaid cards of each PoS. Make sure all output is clearly labelled.
2. Ask the user which PoS they wish to see the content of and display the categories of the sales and the prepaid card(s) info for that PoS.
3. Compare all PoSs and display those pairs that have the same total $ amount of sales along with the $ amount. If you have displayed the pair 1 and 4, do not display the pair 4 and 1 as that is repetitive.
4. Compare all PoSs and display the pairs that have the same $ amount distribution. Similarly, as in option 3, if you have displayed the pair 1 and 4, do not display the pair 4 and 1 as that is repetitive.
5. List all PoSs pairs that are equal based on the definition of equal in the class PoS. Avoid repetitive displays.
6. Ask the user which PoS they want to add a prepaid card to, as well as the prepaid card information, create the new prepaid card and add it to the PoS in question.
7. Ask the user which PoS they want to remove a prepaid card from, as well as the prepaid card index, they want removed, and remove it from the PoS.
8. Ask the user which prepaid card from which PoS they want to update. Ask the user for the new expiry date and update the prepaid card.
9. Ask the user which PoS’s sales they want to add to and the number of each category sales they want to add. Then add these sales categories to the sales in the PoS.
When designing the driver use static methods to make the code easier to follow and to reduce repetitive code.
