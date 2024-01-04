# Will the Customer Accept the Coupon?

## Context
Imagine driving through town and a coupon is delivered to your cell phone for a restaraunt near where you are driving. Would you accept that coupon and take a short detour to the restaraunt? Would you accept the coupon but use it on a sunbsequent trip? Would you ignore the coupon entirely? What if the coupon was for a bar instead of a restaraunt? What about a coffee house? Would you accept a bar coupon with a minor passenger in the car? What about if it was just you and your partner in the car? Would weather impact the rate of acceptance? What about the time of day?
Obviously, proximity to the business is a factor on whether the coupon is delivered to the driver or not, but what are the factors that determine whether a driver accepts the coupon once it is delivered to them? How would you determine whether a driver is likely to accept a coupon?

## Overview
The goal of this project is to use what you know about visualizations and probability distributions to distinguish between customers who accepted a driving coupon versus those that did not.

## Data
This data comes to us from the UCI Machine Learning repository and was collected via a survey on Amazon Mechanical Turk. The survey describes different driving scenarios including the destination, current time, weather, passenger, etc., and then ask the person whether he will accept the coupon if he is the driver. Answers that the user will drive there ‘right away’ or ‘later before the coupon expires’ are labeled as ‘Y = 1’ and answers ‘no, I do not want the coupon’ are labeled as ‘Y = 0’. There are five different types of coupons -- less expensive restaurants (under $20), coffee houses, carry out & take away, bar, and more expensive restaurants ($20 - $50).

## Dataset Information
The dataset consists of the following columns:

- **Categorical Variables:**
  - destination
  - passanger
  - weather
  - time
  - coupon
  - expiration
  - gender
  - age
  - maritalStatus
  - education
  - occupation
  - income
  - car
  - Bar
  - CoffeeHouse
  - CarryAway
  - RestaurantLessThan20
  - Restaurant20To50

- **Numeric Variables:**
  - temperature
  - has_children
  - toCoupon_GEQ5min
  - toCoupon_GEQ15min
  - toCoupon_GEQ25min
  - direction_same
  - direction_opp
  - Y

## Missing Values
Handling of missing values:
- The 'car' column has missing values, which have been updated to "Does not have car."
- Other missing values in different columns ('Bar', 'CoffeeHouse', 'CarryAway', 'RestaurantLessThan20', 'Restaurant20To50') are updated to 'Unknown'.

## Exploratory Data Analysis

### General Statistics
- Proportion of total observations accepting the coupon: 56.84%

### Visualizations

#### Coupon Acceptance Bar Plot
/images/DistributionOfCouponTypes.png
- The bar plot visualizes the acceptance and rejection distribution of coupons.

#### Temperature Histogram
/images/DistributionOfTemperature.png
- The histogram illustrates the distribution of temperatures in the dataset.


### Bar Coupons Analysis
- Created a new DataFrame 'bar_coupons_df' specifically for bar coupons.
- Proportion of accepted bar coupons: 41%
- Acceptance Rate for Customers who went to a bar 3 or fewer times: 53%
- Acceptance Rate for Customers who went to a bar more than 3 times: 77%

### Age and Bar Coupons Analysis
- Compared the acceptance rate between drivers over 25 and others.
- Identified differences in acceptance rates.
- Acceptance Rate for Customers who go to a bar more than once a month and are over 25: 69%
- Acceptance Rate for All Other Customers: 33%


## Hypotheses

- **Bar Coupons:**
  - Drivers who go to bars more than once a month are more likely to accept coupons.
  - Acceptance rates differ based on age, frequency of visits, and other factors.

- **Income Coupons:**
  - Hypothesized characteristics of customers accepting income-based coupons.

## Conclusion

- Frequency of Visiting Bars: Drivers who go to bars more frequently (more than once a month) are more likely to accept bar coupons.
- Demographic Factors: Acceptance rates may vary based on demographic factors such as age. Younger drivers (age below 30) going to bars more frequently may have a higher acceptance rate.
- Passenger Type: Drivers who have passengers other than kids are more likely to accept bar coupons.
- Marital Status: Drivers who are not widowed are more likely to accept bar coupons.
- Income and Restaurant Preferences: Drivers with lower income (less than 50K) who visit cheap restaurants more frequently are more likely to accept bar coupons.


## Requirements
- Python
- Libraries: pandas, numpy, seaborn, matplotlib

## Usage

1. Clone the repository:

```bash
git clone https://github.com/harpreetsohal1/coupon-acceptance-analysis.git
