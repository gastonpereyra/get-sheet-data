# Get Sheet Data
Create APIs to get data from *Google Spread Sheet*

## Configuration

To use your *Google Spread Sheet* as an Database must follow these instructions:
* Share your document with this email: `json-api@proto-rescuefy.iam.gserviceaccount.com`
* First Row must be the key names
* The other rows are the values
* Sheet names is not allowed yet.

## API

Base URL: `https://get-sheet-data.vercel.app`

### Get Document Data

* Request:
    * `google-id`: Google Spread-Sheet ID. `String`: Alphanumeric

```
GET - api/document/[google-id]

example: api/document/2ABtD2ndfB82XM0twWM3uomdsveMxykcEjBn7dQUFuBO
```

* Response:
    * `object`:
        * keys: `String`, Sheet Names
        * values: `Array<object>`, Rows

```json
{
    "Sheet0": [
        { "name": "Tony", "lastname": "Stark" },
        { "name": "Bruce", "lastname": "Wayne" }
    ],
    "Sheet1": [
        { "name": "Natasha", "lastname": "Romanoff" },
        { "name": "Diana", "lastname": "Price" }
    ]
}
```

### Get Sheet in Document

* Request:
    * `google-id`: Google Spread-Sheet ID. `String`: Alphanumeric
    * `sheet-number`: Number of the Sheet (first is 0). `Number`: Positive

```
GET - api/document/[google-id]/sheet/[sheet-number]

example: api/document/2ABtD2ndfB82XM0twWM3uomdsveMxykcEjBn7dQUFuBO/sheet/0
```

* Response:
    * `object`:
        * values: `Array<object>`, Rows

```json
[
    { "name": "Tony", "lastname": "Stark" },
    { "name": "Bruce", "lastname": "Wayne" }
]
```