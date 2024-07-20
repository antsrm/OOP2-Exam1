
## Question 4

Object oriented principles are suitable for modeling this problem.

For this design, the following classes should be defined:

'EnergyCostCalculator' is the main class for handling user input and making the calculations. The output is the energy cost per month.

'Appliance' class is representative of a household appliance, with energy consumption and average use rates.

'CostRate' class is about cost per kilowatt hour at different times.

Specifications:

## 'EnergyCostCalculator'
Attributes:

- 'List< Appliance > appliances': This is list of the applicances used in the household.

- 'Map< String, CostRate > monthlyRates' : Cost rates per month, based on month names or numbers.

Methods:

- 'void addAppliance(Appliance appliance)' : Add household appliance to list.

- 'void setMonthlyRates(String month, CostRate costRate)': Setting the cost rate of a given month.

- 'double calcMonthlyCost(String month)' : Calculates total monthly energy cost for given month.

## Appliance
Attributes:

- 'String name': Appliance name.
- 'int count': Number of these appliances.
- double consumptionRate': Energy consumption in kilowatt hours per hour.
- 'double peakHours': Average use time in peak hours per month.
- 'double normalHours': Average use in normal hours per month.
- 'double offPeakHours': Aveage use time in off peak hours per month.

Methods:

- 'Appliance(String name, int count, double consumptionRate, double peakHours, double normalHours, double offPeakHours) : constructor for appliance.

## 'CostRate'
Attributes:

- 'double peakKwh' : Cost of kwh during peak hours
- 'double normalKwh' : Cost of kwh during normal hours.
- 'double offPeakKwh': Cost of kwh during off peak hours.

Methods:
- costRate(double peakKwh, double normalKwh, double offPeakKwh): Constructor for cost rates.

## Special cases:

For seasonal variation, it is possible to input diffrent 'CostRate' values for every month. The use patterns of the applicances can be altered for each month.

Users can specify hours for peak, normal, off-peak for every appliance separately.

