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

##### addData(data): Promise   success function return index
```
indexDB.open()
       .then(() => indexDB.addData({ name: 'wilson', age: 25 }))
       .then(index => console.log(index))
```

##### getData(index): Promise  success function return data
```
indexDB.open()
       .then(() => indexDB.getData(1))
       .then(data => console.log(data))

```

##### putData(index, data): Promise   success function return index
```
indexDB.open()
       .then(() => indexDB.putData(1, { name: 'wang', age: 1 }))
       .then(index => console.log(index))
```

##### deleteData(index): Promise  success function return void
```
indexDB.open()
       .then(() => indexDB.delete(1))

```

##### forEachData(keyname, dir): Promise success   function return [{ key: '', data: '' }] || [];

```
// if (keyname) return item data;
// if (!keyname) return all data;
// dir can use 'next', 'prev', 'nextunique', 'prevunique', default 'next'

indexDB.open()
       .then(() => indexDB.forEachData())
       .then(result => console.log(result))
```

##### getIndexData(indexName, dataFieldset): Promise  success function return data
```
// when first open db use index, your can use the method
// use '===', not '=='

indexDB.open({ index: [ { name: 'name', unique: false } ] })
       .then(() => indexDB.getIndexData('name', 'wilson'))
       .then(result => console.log(result))
```

##### getOnlyIndexKey(indexName, indexKey, dir): Promise    success function return [{ key:'', data: '' }] || [];
```
// when first open db use index, your can use the method, like mySql groub By
// use '===', not '=='
// dir can use 'next', 'prev', 'nextunique', 'prevunique', default 'next'

indexDB.open({ index: [ { name: 'name', unique: false } ] })
       .then(() => indexDB.getOnlyIndexKey('name', 'wilson'))
       .then(result => console.log(result))

```

##### deleteDB(dbName): void
```
indexDB.deleteDB('test');

```






