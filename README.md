# pmg_connect

Sample tables

**Employees**

EmployeeID,Name,City,State<br/>
2030-2,Rebecca Aguirre,Springdale,AR<br/>
2030-1,Miguel Aguirre,Springdale,AR<br/>

**Specialties**

SpecialtyID,Specialty,SubSpecialty<br/>
7001,Accounting,<br/>
7002,Administrative Services,<br/>
7003,Adult Education,<br/>


**Languages**

languageID,language<br/>
401,Mandarin Chinese<br/>
402,Spanish<br/>
403,Hindi<br/>

**Lang_rel**

employeeID,languageID<br/>
6800-1,435<br/>
4950-2,434<br/>

## Cypher Snippets
// for creating associate speaks language relationship
LOAD CSV WITH HEADERS FROM 'https://raw.githubusercontent.com/johnmillstead/pmg_connect/main/langrel.csv' AS row
MATCH (a:Associate {associateID: row.employeeID}), (l:Language {languageID: row.languageID})
CREATE (a)-[:SPEAKS]->(l);
