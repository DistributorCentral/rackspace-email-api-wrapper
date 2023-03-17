# Rackspace Email API Wrapper

Rackspace Email API Wrapper is a wrapper for making calls to Rackspace's Email API

[Rackspace Documentation](http://api-wiki.apps.rackspace.com/api-wiki/index.php?title=Main_Page)

## Installation

`yarn add 'rackspace-email-api-wrapper@https://github.com/DistributorCentral/rackspace-email-api-wrapper'`

## Getting Started

```javascript
import rackspace from "rackspace-email-api-wrapper";

// OR

const rackspace = require("rackspace-email-api-wrapper");

rackspace.init(YOUR_USER_KEY, YOUR_SECRET_KEY);

const getCustomer = async () => {
  const response = await rackspace.api("GET", `/customers?startswith=UserName`);

  console.log(response);

  // OR

  rackspace.api("GET", `/customers?startswith=UserName`).then((response) => {
    console.log(repsonse);
  });
};

const createCustomer = async () => {
  const response = await rackspace.api("POST", "/customers", {
    name: "UserName",
  });

  console.log(response);

  // OR

  rackspace
    .api("POST", "/customers", {
      name: "UserName",
    })
    .then((response) => {
      console.log(repsonse);
    });
};
```

## API

**init** - init(key, secret)

The init method sets the key and secret used for authenticating the API calls

**api** - api(method, url, payload)

The api method creates a signed request and parses the response. It returns a promise that can be awaited if you are using asycn / await
