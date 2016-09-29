# Widget Knex Schema
> Knex generated tables using JSON/Object schemas


### Example

```javascript
"use strict";

const migrate =  require('widget-knex-schema');
const knex =  require('knex')({config...});

const usersSchema =  {
  id: {type: 'increments', nullable: false, primary: true},
  name: {type: 'string', maxlength: 200, nullable: false},
  email: {type: 'string', maxlength: 254, nullable: false, unique: true},
  password: {type: 'string', maxlength: 254, nullable: false},
};

migrate.createTable(knex, 'users', usersSchema, true)
.then(function () {
  // success
})
.catch(function (error) {
  // error
});

```

### API
This module contains only one method `.createTable` which accepts 4 parameters:

  1. `knex` {Objetc} - A knex instance object (required)
  2. `tablename` {String} - name of the table to me created (required)
  3. `schema` {Object} - A JSON or JavaScript object schema (required)
  4. `timestamps` {Boolean} - if true adds `created_at` and `updated_at` columns (optional) - defaults to false.


License
-------

(MIT License)

Copyright (c) 2016 Qawelesizwe Mlilo <qawemlilo@gmail.com>

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the 'Software'), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
