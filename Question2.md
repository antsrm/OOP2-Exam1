
## Question 2

a.) 

In the scenario, inheritance and polymorphism are manifested in the exception handling:

## Inheritance

'AIException' is an abstract base class that extends 'Exception'. It is the superclass common to all AI-related exceptions. 'DataProcessingError' and 'ModelTrainingError' both extends the 'AIException', thus inheriting it's properties & methods. These two concrete subclasses represent specific error types that can occur in AI pipeline.

## Polymorphism

'AIPipeline' class has method 'run' that throws 'DataProcessingError' or 'ModelTrainingError'. Based on the random condition it either throws one or the other of these two.

'AIPipeline2' class has method 'run' that throws the general 'AIException'. In this case, any subclass of 'AIException' can be thrown, including 'DataProcessingError' and 'ModelTrainingError'.

## Exception handling

The 'main' method is demonstrative of polymorphic behavior.

The catch block 'DataProcessingError' cathces exceptions thrown by either 'pipeline1.run()' or by 'pipeline2.run()'.

The catch block of 'ModelTrainingError' catches expections thrown by either 'pipeline1.run()' or 'pipeline2.run()'.

The catch block of 'AIException' catches any other 'AIException' that doesn't match the previously mentioned specific exceptions. Those two specific exceptions are handled already by their specific blocks. This block will only be executed for potential future 'AIException' subclasses.

b.)

Currency converter code works in following way:

CurrencyConverter Class: The 'convert' method uses switch statement to convert an amount based on currency provided. It returns an 'Object' of any type. In this case, it always returns 'double'.

SpecificCurrencyConverter Class: Subclass that overrides 'convert' method, provides it's own implementation that returns a 'double' directly. It does not use the currency parameter. It simply returns amount times 1.2.

## Advantages

It is possible to add new currency converters by making new subclasses of 'CurrencyConverter', so the program is extendable.

There is flexibility in the implementation as 'convert' method can be called on instance of 'CurrencyConverter' or any subclass. Also, 'SpecificCurrencyConverter' can be used to provide specific convert logic, diffrent from the base class. These features exemplify polymorphism.

## Disadvantages

The return type of 'Object' in the base class can be hazardous. For type safety it would be better to return specific type, like 'Double'.

In 'SpecificCurrencyConverter' the 'currency' parameter is ignored and same conversion rate is always applied. This is not very intuitive, reducing the usefulness of this subclass.

Also, hardcoded conversion rates in the subclasses mean code duplication. So, if there is need to update conversion rates, changes in multiple places are needed.

