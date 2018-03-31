# edx_nodejs_module4
Module 4 Assignment

Module 3 Assignment

Command line example usage:

`node server.js`

Working as expected, tests shown below.

I ran out of time to complete this assignment before this course finishes, so I referred to the sample answer.

Tests:

```
// Add 2 documents, then view results:
c# curl "http://localhost:3000/accounts" | json_pp
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100   151  100   151    0     0  15100      0 --:--:-- --:--:-- --:--:-- 15100
[
   {
      "name" : "savings",
      "_id" : "5abefb93d327fc0b0ad7394a",
      "balance" : 1000,
      "__v" : 0
   },
   {
      "__v" : 0,
      "_id" : "5abefb8dd327fc0b0ad73949",
      "name" : "savings",
      "balance" : 1000
   }
]


// Find single document
# curl "http://localhost:3000/accounts/5abefb8dd327fc0b0ad73949" | json_pp
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100    74  100    74    0     0   2960      0 --:--:-- --:--:-- --:--:--  2960
{
   "_id" : "5abefb8dd327fc0b0ad73949",
   "name" : "savings",
   "balance" : 1500,
   "__v" : 0
}


// Update

# curl -H "Content-Type: application/json" -X PUT -d '{"balance": "1500"}' "http://localhost:3000/accounts/5abefb8dd327fc0b0ad73949"
{"_id":"5abefb8dd327fc0b0ad73949","balance":1500,"name":"savings","__v":0}root@GreyMan:/home/mc#

# curl "http://localhost:3000/accounts" | json_pp
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100   151  100   151    0     0  16777      0 --:--:-- --:--:-- --:--:-- 18875
[
   {
      "__v" : 0,
      "name" : "savings",
      "balance" : 1000,
      "_id" : "5abefb93d327fc0b0ad7394a"
   },
   {
      "_id" : "5abefb8dd327fc0b0ad73949",
      "balance" : 1500,
      "name" : "savings",
      "__v" : 0
   }
]


// Delete

# curl -X DELETE "http://localhost:3000/accounts/5abefb8dd327fc0b0ad73949"
{"_id":"5abefb8dd327fc0b0ad73949","balance":1500,"name":"savings","__v":0}

# curl "http://localhost:3000/accounts" | json_pp
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100    76  100    76    0     0   8444      0 --:--:-- --:--:-- --:--:--  9500
[
   {
      "balance" : 1000,
      "_id" : "5abefb93d327fc0b0ad7394a",
      "__v" : 0,
      "name" : "savings"
   }
]

```
