### ng-IndexDB

- this is a angular 1.x module

#### api

##### canUse (): boolean
```
indexDB.canUse() // true or false
```

##### open (config): Promise
```
  config = {
    name: 'test'      // db name , default is 'test',
    version: 1,       // db version, default is 1,
    database: 'table' // table name, default is 'table',
    mainKey: {        // extras fieldset , default use autoIncrement 
      keypath: ''   
    },
    index: [          // extras fieldset, this is used first open indexDB;
      {               //                  this can use more index;
        name: '',     // index name,
        unique: true
      } 
    }
  }
``` 

##### 