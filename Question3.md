
## Question 3

a.)

For querying the customer database, the appropriate class construction would be:

Class: 'CustomerEntry'

Using a class works best here because this is a structured entity that has multiple attributes. Each of the mentioned five attributes will have distinct values. By defining 'CustomerEntry' class, instances can be created for each database entry.

Other options: Enums are not suitable because there is need to store many, differing entries.
Interface is not suitable because a concrete implemetation for storing data is needed.
Record could be used, but class has more flexibility and can be expanded later.

b.)

For filtering the list:

Interface: 'Predicate< Entry >'

Using an interface, especially 'Predicate' from Java's '.util.function' package, is appropriate as it allows for the definition of a filter method that is reusable. The method can be used wherever it is needed.

Other options: Class is too much overhead, interface is sufficient. Enum is not applicable because it does not encapsulate behavior. Record is inappropriate for representing behavior.

c.)

For modeling financial transactions:

Abstract Class: 'Transaction'
with subclasses: 'Deposit' & 'Withdrawal' & 'Transfer'.

Abstract class is appropriate as it defines the common traits / properties of all transactions. Subclasses specify details of different types of transactions.

Other options: Inteface is not sufficient because it doesn't hold state, as in amount, currency. Enum is not suitable for such complex behavior and state representation. A regular class would require duplicate code, being less manageable. Record is not suitable as it usually represents immutable data.

