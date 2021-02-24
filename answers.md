2.  All the companies that have more than 5000 employees.
    Limit the search to 20 companies and sort them by number of employees.

            db.companies.find({ number_of_employees: {$gt: 5000}}).sort({ number_of_employees: 1}).limit(20)

3.  All the companies founded between 2000 and 2005, both years included.
    Retrieve only the name and founded_year fields.

          db.companies.find({$and: [{founded_year: {$gte: 2000}}, {founded_year: {$lte: 2005}}]},{name:1,founded_year:1})


4.  All the companies that had a Valuation Amount of more than 100.000.000
    and have been founded before 2010.
    Retrieve only the name and ipo fields.

            db.companies.find({"ipo.valuation_amount": {$gte: 100000000}, "founded_year": {$lt: 2010}}, {"ipo.valuation_amount": 1, "name": 1, "founded_year": 1}, {$sort: {"founded_year": -1}}  )

5.  All the companies that have less than 1000 employees and have been founded before 2005.
    Order them by the number of employees and limit the search to 10 companies.

            db.companies.find({"number_of_employees": {$lt: 1000}, "founded_year": {$lt: 2005}}, {}, $sort: {"number_of_employees": -1}, $limit: 10)

6.  All the companies that don't include the partners field.

7.  All the companies that have a null type of value on the category_code field.

8.  All the companies that have at least 100 employees but less than 1000.
    Retrieve only the name and number of employees fields.

9.  Order all the companies by their IPO price in descending order.

10. Retrieve the ten companies with most employees, order by the number of employees

11. All the companies founded in the second semester of the year.
    Limit your search to 1000 companies.

12. All the companies founded before 2000 that have an acquisition amount of more than 10.000.000

13. All the companies that have been acquired after 2010,
    order by the a
