# Simple Search Engine
This is program is simple implementation of a search engine designed to implement the following tasks:

1. Index the contents of the cran collection 
2. Extract all the queries from the cranqry document 
3. Query the index using the extracted queries 
4. Obtain a ranked list of relevancy scores
5. Calculate the MAP and recall scores for the search engine. 

Documents used for this project 
The full contents of the cran.all.1400 collection was separated into individual document objects. 
Each document contained five fields and each was identified using a .X tag; Document ID (.I), Title (.T), Abstract (.A), Bibliography (.B) and Document Text (.W).
The program identified if and what tag was in a line and stored that information an an array. 
When all five fields in the array were filled an IndexWrite was used to create and store each document to an “in memory” directory 

Queries
The cran.qry file was parsed in the same way as the cran.all.1400 using the query ID (.I) and query contents (.W) tags. 
The contents of each query were separated into an array. 
Each query was executed on the full directory of documents by looping through the the contents of each element in the query array and using that contents as the input to QueryParser and the Query. 
The QueryParser used the specified analyzer on the query.
QueryParserDefined which feild the search should take place on. 
During the Query process, all punctuation was removed from each individual query. 
The result of the the query process is set of ranked relevent documents as a text file. 
