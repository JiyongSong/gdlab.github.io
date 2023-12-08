---
layout: post
date: 2023-12-08 KST
author: Jiyong Song
---

# Lecture#03 Database storage 1

This is based on the *disk-oriented* DBMS architecture.



## Storage

* Volatile - random access, byte-addressable
* Non-volatile - sequential access, block-addressable

| Storage           | Characteristic    | Component | &uarr; &darr; |
|---                |---                |---        |---            |
| CPU registers     | Volatile          | CPU       | &uarr; Faster, smaller, expensive |
| CPU caches        | Volatile          | CPU       |               |
| DRAM              | Volatile          | Memory    |               |
| SSD               | Non-volatile      | Disk      |               |
| HDD               | Non-volatile      | Disk      |               |
| Network storage   | Non-volatile      | Disk      | &darr; Slower, larger, cheaper    |

<!--
| Volatile          | Non-volatile      |
|---                |---                |
| Random access     | Sequential access |
| Byte-addressable  | Block-addressable |
-->

| Storage           | Access time       | Same ratio    |
|---                |---:               |---            |
| L1 cache ref      | 1 ns              | 1 sec         |
| L2 cache ref      | 4 ns              | 4 sec         |
| DRAM              | 100 ns            | 100 sec       |
| SSD               | 16,000 ns         | 4.4 hours     |
| HDD               | 2,000,000 ns      | 3.3 weeks     |
| Network storage   | ~50,000,000 ns    | 1.5 years     |
| Tape archives     | 1,000,000,000 ns  | 31.7 years    |



## Disk-oriented DBMS overview



## DBMS vs. OS



## File storage



## Database pages

* A **page** is a fixed-size block of data.
* How DBMSs manage pages in files on disk?
  - Heap file organization
  - Tree file organization
  - Sqeuantial / sorted file organization (ISAM)
  - Hashing file organization


## Database heap

* Heap file: unordered collection of pages with random ordered tuples



## Page layout

How to organize the data inside of the page?
Assume that row-oriented storage model.

* Page header: meta-data about the page's contents.
  - Page size, checksum, version, ...

* Tuple-oriented storage
  - Slotted page: header + slot array + tuples
    - Slot -> tuple's starting position offset.
  - Unique **record id** for a logical tuple
    - Physical location: file id, page id, slot #
    - It is interal, hidden, NO means to apps.



## Tuple layout

* Tuple: header + attributes
* Tuple header: meta-data
  - Visibility info, bit map for null values
* Denormalize: pre-join
  - Store related tuples in the same page.
  - Pros: potentially reduces the amount of I/O.
  - Cons: can make updates more expensive.
