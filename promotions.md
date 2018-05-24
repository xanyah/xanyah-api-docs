# Promotions

Promotions can be attached to SaleVariants \(as SaleVariantPromotion\)  or Sales \(as SalePromotion\), during a sale creation. They allow the user to create discounts for a particular sale.

The promotion object contains 2 fields:

* Type: the type of promotion \(see below\)
* Amount: the amount of the promotion \(number, its value depends on the type of promotion\)

## Types of promotion

They are 2 types of promotions:

* `flat_discount` : Remove the amount from the price \(a 20€ article with a 2 flat discount will be at 18€\)
* `percent_discount` : Remove a percentage from the price \(a 20€ articles with a 10 discount will be at 18€\)



