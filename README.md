# pmg_connect

## Cypher for creating associate speaks language relationship
LOAD CSV WITH HEADERS FROM 'https://raw.githubusercontent.com/johnmillstead/pmg_connect/main/langrel.csv' AS row
MATCH (a:Associate {associateID: row.employeeID}), (l:Language {languageID: row.languageID})
CREATE (a)-[:SPEAKS]->(l);
