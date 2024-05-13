# Cordra API Introduction

For the work with the typeregistry, the use of API's is an important feature to handle larger datasets or if you just have no need for the user interface. To begin, an account is necessary for most operations. Once you have an account, you can generate an access token using the following command:

```
curl --request POST \
  --url 'http://typeregistry.lab.pidconsortium.net/auth/token' \
  --header 'Content-Type: application/json' \
  --data '{
  "grant_type": "password",
  "username": "",
  "password": ""
}'
```
Enter your username and password in the designated fields. The token can be retrieved from the `access_token` field in the response. This token will stay active during your session and can be used for multiple requests.

The retrieve command is one of the simplest ones and just requires the URL of the object you want to retrieve. Note that a `#` in front of `objects` in the URL would direct you to the UI version of the type.

```
curl --request GET \
  --url 'http://typeregistry.lab.pidconsortium.net/objects/21.T11969/a41d30cdc6206b5a6fdd' \
  --header 'Content-Type: application/json' 
```

Some types are only visible for authorized users. For those types we will use the generated token to authenticate ourselves. This will be done in an `'Authorization'` Header field, where `TOKEN` is the access token you generated for your account.

```
curl --request GET \
  --url 'http://typeregistry.lab.pidconsortium.net/objects/21.T11969/0ea269895eceaf41f7d2' \
  --header 'Content-Type: application/json' \
  --header 'Authorization: Bearer TOKEN'
```

Another important use of the API involves the creation of types via the API. This is helpful for larger batches of data or if you do not wish to work via the UI. Since Cordra stores types as JSON objects, we have to create JSON Objects based on the schemas provided. For more information on the schemas please refer to the respective sections in the documentations or view them directly under `Types` in the navigation bar. If you create a type via the API ist must be valid for the desired schema. An example for a type that is a valid `BasicInfoType` can be for example the following. Note that no field for `id` is given in the JSON object. This will be automatically filled and is part of the response.
```
{
    "name": "TestType",
    "provenance": {
      "contributors": [
        {
          "Name": "Type Typerman"
        }
      ],
      "creationDate": "",
      "lastModificationDate": ""
    },
    "ExpectedUse": "Will demonstrate API",
    "Aliases": [
      "TestFile"
    ],
    "MeasuredUnits": [
      "21.T11969/a41d30cdc6206b5a6fdd"
    ],
    "Schema": {
      "Type": "String",
      "Properties": [
        {
          "Property": "minLength",
          "Value": 0
        },
        {
          "Property": "maxLength",
          "Value": 10
        }
      ]
    }
  }
```
Consider this object saved on your disk as `testType.json`. To now create a type with that content consider the following command:

```
curl --request POST \
  --url 'http://typeregistry.lab.pidconsortium.net/objects/?type=BasicInfoType' \
  --header 'Content-Type: application/json' \
  --header 'Authorization: Bearer TOKEN' \
  --data @"testType.json"
```

Note that we need to authenticate the same way as before. The JSON object representing the type is simply passed as the content of the `POST` request. Of course it would also be possible to copy the actual JSON into the `--data` field, but referencing the file is a simpler way. For more information on the Cordra API refer to the links in the `Documentation` tab.