# Exemples en Gherkin

```gherkin
Feature: Explaining Cucumber  
	In order to gain an understanding of the Cucumber testing system  
	As a non-programmer  
	I want to have an overview of Cucumber that is understandable by non-geeks  
  
Scenario: A worker seeks an overview of Cucumber  
	Given I have a coworker who knows a lot about Cucumber  
	When I ask my coworker to give an overview of how Cucumber works  
	And I listen to their explanation  
	Then I should have a basic understanding of Cucumber
```


```gherkin
Feature: Subscribers see different articles based on their subscription level  
  
Scenario: Free subscribers see only the free articles  
	Given users with a free subscription can access "FreeArticle1" but not "PaidArticle1"  
	When I type "freeFrieda@example.com" in the email field  
	And I type "validPassword123" in the password field  
	And I press the "Submit" button  
	Then I see "FreeArticle1" on the home page  
	And I do not see "PaidArticle1" on the home page  
  
Scenario: Subscriber with a paid subscription can access "FreeArticle1" and "PaidArticle1"  
	Given I am on the login page  
	When I type "paidPattya@example.com" in the email field  
	And I type "validPassword123" in the password field  
	And I press the "Submit" button  
	Then I see "FreeArticle1" and "PaidArticle1" on the home page
```


```gherkin
Feature: Adding a product to the cart
  As a user of the online store
  I want to be able to add products to my cart
  In order to complete my purchase

Scenario: Adding a single product to the cart
	Given the following product data:
	| name | price |
	| product1 | $10 |
	| product2 | $20 |
	When I add "product1" to my cart
	Then the cart total should be "$10"
	And the number of items in the cart should be "1"
```