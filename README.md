# Alex's-Bookstore-API
This is a developer guide for Alex's Bookstore API developed as a writing assignment for FIS Global. This is a fictional API. 

## Overview
This describes the operations that will allow you to implement the shopping cart for Alex's bookstore. The API is designed to allow customers to choose books, add or remove them from their shopping cart, and checkout when they are done. 

API Operation | Description
--- | ---
`.addBook()` | Adds an item to the cart. <br> Type: String
`.removeBook()` | Removes an item from the cart. <br> Type: String
`.checkout()` | Purchases the items in the cart. <br> Type: Array

## Programming Guidelines
**Getting Started**

A new user must be instantiated as a shopper for a shopping cart to be established for them.
```javascript
const User = new alexShopper();
```

**Adding a Book**

This operation adds a book to the shopping cart. The parameter is the title of the book being purchased. It returns the contents of the shopping cart as an array.
```javascript
User.addBook('BestSeller1');
=> ['BestSeller1'];
```
Currently `.addBook()` is only able to add one title at a time to the shopping cart. Use a new instance for each new item.

**Removing a Book**

This operation will remove a book from the cart. The parameter is the title of the book being removed.
```javascript
User.removeBook('BestSeller1'):
=> [];
```

**Checkout**

This operation will purchase all the books in the cart. Here is an example of a complete transaction:
```javascript
const User = new alexShopper();
User.addBook('BestSeller1');
=> ['BestSeller1']
User.addBook('BestSeller2');
=> ['BestSeller1', 'BestSeller2']
User.addBook('FantasyFic');
=> ['BestSeller1', 'BestSeller2', 'FantasyFic']
User.removeBook('Bestseller2');
=> ['BestSeller1', 'FantasyFic']
User.checkout();
```
## Error Handling
Exceptions can occur when `.removeBook()` is executed on a title that does not exist or when `.checkout()` is executed on an empty shopping cart. Use `try` and `catch` statements to guard against these errors. 

```javascript
try {
	const User = new alexShopper();
	alex.checkout(); // throws new Error('Empty cart')
	
	alex.addBook('BestSeller1');
	alex.addBook('FantasyFic');
} catch(err) {
	console.log(err);
}
```
## Sequence Diagram
