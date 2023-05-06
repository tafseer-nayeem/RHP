<br />
We also present a detailed analysis to provide more supportive evidence of our arguments. To this end, we randomly selected m examples for each class of reviews considering helpfulness votes. Then, we extract Top $K$ (where $K$ = $5$) $n$-grams from each class of reviews to identify the most relevant keywords or topics in reviews to assess what aspects are most talked about the items (e.g., hotels or restaurants). Detailed in the [EACL 2023 paper](https://aclanthology.org/2023.findings-eacl.125/)


<br />




|       Helpfulness Class      |   |   Unigram  |   |         Bigram        |
|:----------------------------:|---|:----------:|---|:---------------------:|
|       Class #1 Votes [1, 2)  |   |   'room'   |   |      'front desk'     |
|                              |   |   'staff'  |   |     'coffee maker'    |
|                              |   | 'location' |   |   'breakfast buffet'  |
|                              |   |   'time'   |   |       'sofa bed'      |
|                              |   |  'service' |   |      'swim pool'      |
|       Class #2 Votes [2, 4)  |   |   'room'   |   |      'front desk'     |
|                              |   |   'staff'  |   | 'shampoo conditioner' |
|                              |   |  'service' |   |   'customer service'  |
|                              |   | 'location' |   |      'resort fee'     |
|                              |   |   'time'   |   |      'pool area'      |
|       Class #3 Votes [4, 8)  |   |   'room'   |   |      'front desk'     |
|                              |   |   'staff'  |   |      'resort fee'     |
|                              |   |   'time'   |   |   'customer service'  |
|                              |   |  'service' |   |     'coffee maker'    |
|                              |   |   'view'   |   |      'city view'      |
|      Class #4 Votes [8, 16)  |   |   'room'   |   |      'front desk'     |
|                              |   |   'staff'  |   |      'resort fee'     |
|                              |   |  'service' |   |   'customer service'  |
|                              |   |   'time'   |   |     'minute walk'     |
|                              |   |   'pool'   |   |     'life jacket'     |
|     Class #5 Votes [16, inf) |   |   'room'   |   |      'front desk'     |
|                              |   |   'time'   |   |      'resort fee'     |
|                              |   |  'service' |   |       'bed bug'       |
|                              |   |   'staff'  |   |     'beach chair'     |
|                              |   |   'pool'   |   |      'cable car'      |