2) All the companies that have more than 5000 employees. 
Limit the search to 20 companies and sort them by number of employees.

        db.companies.find({ number_of_employees: {$gt: 5000}}).sort({ number_of_employees: 1}).limit(20)

3) All the companies founded between 2000 and 2005, both years included. 
Retrieve only the name and founded_year fields.

      db.companies.find({$and: [{founded_year: {$gte: 2000}}, {founded_year: {$lte: 2005}}]},{name:1,founded_year:1})
        
       