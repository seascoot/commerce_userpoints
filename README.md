# commerce_userpoints
Version of Drupal 7 Module Commerce Userpoints modified for cash credit use

## Introduction ##
This is a hack of the Drupal module called [Commerce Userpoints](http://https://www.drupal.org/project/commerce_userpoints), originally posted by liupascal.

I was looking for something simple to allow me to give store credits to account holders to offset purchases made through checkout.  I tried the 7.x-1.x-dev version posted 2013-Dec-23, but found that it was not usable for the purpose I required.

## Changes ##


- This version incorporates several patches posted by ankur_novatree :   
[https://www.drupal.org/node/2083403](https://www.drupal.org/node/2083403)
[https://www.drupal.org/node/2425537](https://www.drupal.org/node/2425537)
[https://www.drupal.org/node/2247775](https://www.drupal.org/node/2247775)
[https://www.drupal.org/node/2536780](https://www.drupal.org/node/2536780).


- Line item discount name has been changed from "Royalties" to "Credit Discount".


- Exchange rate line removed from the checkout pane since it is confusing for a simple credit discount.



- Made the default input for points to apply the same as the cart total or total available points if lower.



- Changed title of points text input box to "Amount of Credit to Apply". 

## Usage ##
Copy commerce_userpoints directory into your modules directory and enable the module.

Go to /admin/commerce/config/currency/userpoints
Add a points value currency.  This is how I set up mine to have credit show as whole dollars (no cents value).  Setting this as 0.01 exchange appeared too confusing to me for applying discounts.

![](http://www.clivewoodhouse.org/images/currency_settings.png)

Go to /admin/config/people/userpoints
Select the tab "Point Settings".
Here you can customize how the descriptions for your userpoints appear.  I set them thus since I'm using them as a credit system:

![](http://www.clivewoodhouse.org/images/points_value_settings.png)

Select the tab "Categorization" and make credit your default category:

![](http://www.clivewoodhouse.org/images/core_store_points_settings.png)

Go to /admin/commerce/config/commerce-userpoints/discount

Set the default to Credit.  You can limit use of the credit to certain components if needed.  That was not necessary for me, so I use "Base price".

![](http://www.clivewoodhouse.org/images/userpoint_discount_category.png)

To assign credits to account holders go to /admin/config/people/userpoints

From the first "Totals" tab you can see existing users with credits and also add credits to a user.

A test checkout page should have the option to use credit as a discount against an order like below: 

![](http://www.clivewoodhouse.org/images/store_credit_discount.png)
