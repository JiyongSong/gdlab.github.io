---
layout: post
date: 2023-11-28 KST
author: Jiyong Song
---

# Lecture#01 Relational model & algebra



## Databases

* Database vs database management system (DBMS)



## Flat file strawman

* Comma-separated value (CSV) file



## Database management system

* data model
    > ex) relational, NoSQL, array/matrix/vectors

* schema



## Relational model

* relation = table

* tuple
    > set of attrivute values

* n-ary relation
    > relation with n attributes



## Data manipulation languages (DMLs)



## Relational algebra


### Select

* Syntax: $$\sigma_{predicate}(R)$$

* Example: $$\sigma_{a\_id='a2'}(R)$$

* SQL: `SELECT * FROM R WHERE a\_id = 'a2'`


### Projection

* Syntax: $$\pi_{A1, A2, ..., An}(R)$$

* Example: $$\pi_{b\_id-100, a\_id}(\sigma_{a\_id='a2'}(R))$$

* SQL: `SELECT b_id-100, a_id FROM R WHERE a_id = 'a2'`


### Union, intersection, difference, product, join. ...



## Data models
