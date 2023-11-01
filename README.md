# Social Media Data as Graph Network
### Tools used is Neo4j

### Description of use case
We create a Social Media data and store as graph data. The nodes are the social media users connected by links or edges.

#### Graph data view in Neo4j
![alt text](https://github.com/KarlRetumban/Samptest/blob/main/Graphdata.PNG)


### Codes for creating the Social Media graph data
~~~cypher
// Create nodes and links 
CREATE (alice:Person:Photographer {name: "Alice Peterson", age:25, gender:"female", username: "alice234"}),
 (john:Person:Traveller {name: "John Black", age:36, gender:"Male", username: "traveljohn213"}),
 (dan:Person:Hiker {name: "Dan Henderson", age:42, gender:"Male", username: "hikerdan5454"}),
 (migs:Person {name: "Migs Laurey", age:21, gender:"Male", username: "migslaurey522"}),
 (peter:Person {name: "Peter Mclooney", age:31, gender:"Male", username: "petermclooney555"}),
 (joe:Person {name: "Joe Bryant", age:25, gender:"Male", username: "imnotkobe868"}),
 (dianna:Person:Foodie {name: "Dianna Delarey", age:24, gender:"Female", username: "migslaurey522"}),
 (drake:Person:Athlete {name: "Drake Justin", age:23, gender:"Male", username: "drakej878"}),
 (mica:Person {name: "Mica Malooney", age:19, gender:"Female", username: "molooneymica8568"}),
 (joseph:Person:Cyclist {name: "Joseph Richardson", age:34, gender:"Male", username: "josephscyclist951"}),
 (donald:Person:Swimmer {name: "Donald Riley", age:18, gender:"Male", username: "swimdonald247"}),
 (ralph:Person {name: "Ralph Davis", age:29, gender:"Male", username: "ralphd683"}),
 
 (alice)-[:FRIENDS]->(john),
 (john)-[:FRIENDS]->(alice),
 (alice)-[:FRIENDS]->(dianna), 
 (dianna)-[:FRIENDS]->(alice),
 (peter)-[:FRIENDS]->(dan),
 (dan)-[:FRIENDS]->(peter), 
 (peter)-[:FRIENDS]->(joseph),
 (joseph)-[:FRIENDS]->(peter), 
 (drake)-[:FRIENDS]->(joe),
 (joe)-[:FRIENDS]->(drake), 
 (drake)-[:FRIENDS]->(donald), 
 (donald)-[:FRIENDS]->(drake),
 
 (alice)-[:LIKES{type:"like", contenttype:"post", content:"image", image_url:"http://dummyimage.com/120x100.png/ff"}]->(dan),
 (alice)-[:LIKES{type:"heart", contenttype:"post", content:"image", image_url:"http://dummyimage.com/150x100.jpg/sw"}]->(joe),
 (peter)-[:LIKES{type:"smiley", contenttype:"post", content:"text", text:"I love this view!"}]->(drake), 
 (drake)-[:LIKES{type:"like", contenttype:"post", content:"text", text:"Stunning place, love it!"}]->(ralph),
 (joe)-[:LIKES{type:"like", contenttype:"post", content:"text", text:"Will definitely try this walk again"}]->(drake),
 
 (alice)-[:COMMENTS{comment: "Nice photo, i love it!", contenttype:"post", content:"image", 
image_url:"http://dummyimage.com/1150x100/kk.jpg/sw"}]->(migs),
 (dan)-[:COMMENT{comment: "I wish I was there!", contenttype:"post", content:"image", 
image_url:"http://dummyimage.com/1250x100.png/fg"}]->(dianna), 
 (joe)-[:COMMENT{comment: "I wish I was there!", contenttype:"post", content:"text", text:"Great walking experience!"}]->(alice),
 
 (alice)-[:FOLLOWS]->(peter),
 (dan)-[:FOLLOWS]->(peter),
 (dan)-[:FOLLOWS]->(mica),
 (dan)-[:FOLLOWS]->(alice),
 (peter)-[:FOLLOWS]->(alice);
~~~
