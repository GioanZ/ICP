# Transferring data from a web2 database to web3 with api

This project was created to perform data transfers from a web2 database to web3 with api using Motoko.
Study how it was done in the project of: [Server krpeacock]([https://github.com/krpeacock/server]). Then for the installation phase follow their blueprint.

# Usage

The REST APIs can be called in any way, there is a GET call and a POST call. Here is an example of each through Postman's curls.

The POST inserts a single DB row:
```curl
curl --location 'http://127.0.0.1:4943/add_row?canisterId=ctiya-peaaa-aaaaa-qaaja-cai' \
--header 'Content-Type: application/json' \
--data '{
    "id": 23,
    "companyName": "Company_X",
    "cityDestination": "City_A",
    "supplier": "Company_Y",
    "cityOrigin": "City_B",
    "productType": "leather",
    "qty": 10
}'
```

The GET returns the entire DB (following the order of insertion, with relative insertion number):
```curl
curl --location 'http://127.0.0.1:4943/get_row_db?canisterId=ctiya-peaaa-aaaaa-qaaja-cai'
```

Output /get_row_db example in JSON:
```json
{
  "0": {
    "id": 23,
    "companyName": "Company_X",
    "cityDestination": "City_A",
    "supplier": "Company_Y",
    "cityOrigin": "City_B",
    "productType": "leather",
    "quantity": 10
  },
  "1": {
    "id": 7,
    "companyName": "Company_Z",
    "cityDestination": "City_C",
    "supplier": "Company_W",
    "cityOrigin": "City_D",
    "productType": "leather",
    "quantity": 100
  }
}
```

On ICP, in the backend part, you can see getDB() to get the DB as an array.
Output getDB() example in JSON:
```json
[{"id":"23","qty":"10","cityDestination":"City_A","supplier":"Company_Y","productType":"leather","companyName":"Company_X","cityOrigin":"City_B"},{"id":"7","qty":"100","cityDestination":"City_C","supplier":"Company_W","productType":"leather","companyName":"Company_Z","cityOrigin":"City_D"}]
```
"# fromweb2databasetoweb3" 
