# API Specification for 2eat
--------------------------

Crowd-sourced restaurant menus.

# API

## /v1/restaurants/

### List all restaurants

```
>> GET /v1/restaurants/
>> Accepts: application/json

<< 200 OK
<< Content-Type: application/json
<<
<< {
<<   pages: 5,
<<   pageSize:1,
<<   items: [{
<<     id: "c2c7d8cc-8265-4bfb-8010-fc143802fa2b",
<<     idSlug: "jalla-jalla-bergsatan-16-malmo",
<<     name: "Jalla Jalla",
<<     rating: 5,
<<     keywords: ["arabic", "kebab", "falafel"],
<<     adress: {
<<       line: "Bergsgatan 16"
<<       zip: 21154,
<<       city: "Malmö",
<<       country: "Sweden",
<<       phone: "+46 40 30 39 20",
<<     },
<<     position: {
<<       latitude: 34.647995,
<<       longitude: -86.738549
<<     },
<<     open: [{
<<       weekdays: ["monday"],
<<       from: 10,
<<       to: 4
<<     }],
<<     menus: [{
<<       id: "d10e0efc-0d84-474b-9052-5615368dbe76",
<<       idSlug: "lunch",
<<       type: "lunch",
<<       url: "http://img.2eat.com/restaurants/jalla-jalla/menu.png",
<<       valid: {
<<         from: 10,
<<         to: 15
<<       }
<<     }]
<<   }]
<< }
```

### List restaurants given a certain lat/lng position

```
>> GET /v1/restaurants/?latitude=34.647995&longitude=-86.738549&range=5km
>> Accepts: application/json

<< (same as /v1/restaurants/)
```

### Retrieve a single restaurant

```
>> GET /v1/restaurant/c2c7d8cc-8265-4bfb-8010-fc143802fa2b/
>> Accepts: application/json

<< 200 OK
<< Content-Type: application/json
<<
<< {
<<   id: "c2c7d8cc-8265-4bfb-8010-fc143802fa2b",
<<   idSlug: "jalla-jalla-bergsatan-16-malmo",
<<   name: "Jalla Jalla",
<<   rating: 5,
<<   keywords: ["arabic", "kebab", "falafel"],
<<   adress: {
<<     line: "Bergsgatan 16"
<<     zip: 21154,
<<     city: "Malmö",
<<     country: "Sweden",
<<     phone: "+46 40 30 39 20",
<<   },
<<   position: {
<<     latitude: 34.647995,
<<     longitude: -86.738549
<<   },
<<   open: [{
<<     weekdays: ["monday"],
<<     from: 10,
<<     to: 4
<<   }],
<<   menus: [{
<<     url: "http://img.2eat.com/restaurants/jalla-jalla/menu.png"
<<   }]
<< }
```

# TODO

* [ ] Add user authentication.
* [ ] Add restaurant menu image upload.
