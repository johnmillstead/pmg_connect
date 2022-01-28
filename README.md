# pmg_connect

Sample tables

**Employees**

EmployeeID,Name,City,State<br/>
2030-2,Rebecca Aguirre,Springdale,AR<br/>
2030-1,Miguel Aguirre,Springdale,AR<br/>

**Specialties**


**Languages**


**Lang_rel**

## Cypher for creating associate speaks language relationship
LOAD CSV WITH HEADERS FROM 'https://raw.githubusercontent.com/johnmillstead/pmg_connect/main/langrel.csv' AS row
MATCH (a:Associate {associateID: row.employeeID}), (l:Language {languageID: row.languageID})
CREATE (a)-[:SPEAKS]->(l);
