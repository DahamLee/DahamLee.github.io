## Database

### Levels of data abstraction

* View level
	* application level
	* programs hide details of data types
	* views can also hide information
* Logical level
* Physical level

	
* A collection of tools for describing
	* data
	* data relationship
	* data sematics(의미론)
	* data constraints

	
* Data model type
	* relational model
	* network model
	* hierarchical model
	* object-based models
		* object-oriented and object-relational


### Relational Model

#### Keys
* super key: set of one or more attributes that, taken collectively, allow us to identify uniquely a tuple in the relation.
* candidate key: minimal superkeys 
* primary key: candidate key chosen by the database designer as the principal means

#### Terms
* Attribute, Field(Columns)
* Tuple, Record(Rows)

#### Relation Schema
* A1, A2, A3 ... An are attributes
* R = (A1, A2, .. An) is a relation schema

#### Relation
* Given sets D1, D2.. Dn, relation r is a subset of D1 x D2 x...Dn
* a set of n-tuples (a1, a2, .. an), where each a_i is included D_i

#### A relational instance
* A set of tuples all conforming to the same schema
* A relational schema describes the data that is contained in a relational instance

##### importanat

* ex) realtional schema: ID, name, dept_name, salary
* ex) relational instance: 2222, Einstein, Physics, 95000

* A relational database schema
	* A set of relational schema, one for each relation

* A relational database instance
	* a set of relational instances, one for each relation

##### SQL
* Data Definition Language (DDL)
* Data Manipulation Language (DML)

* DDL allows the specification of information about relations, including:
	* The schema for each relation
	* The type of values associated with each attribute
	* The Integrity constraints
	* The set of indices
	* The security and authorization

* DDL complier generates a set of table templates stored in a data dictionary

##### SQL2
* commands are case insensitive
	* select = SELECT
* values are not
	* Seattle =\= seattle
* use single quotes for constraints: ''-O, ""-X


##### ERD
* Three basic concepts
	* Entity sets
	* Relationship sets
	* Attributes

##### Logical optimization
* Find equivalent plans that are more efficient
* Minimize # of tuples at each step by changing the order of RA operators

##### Physical optimization
* Find algorithn with lowest IO cost to execute our plan
* calculate based