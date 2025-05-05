# Kobra gRPC interface

Kobra gRPC module is a basic request/response wrapper for interfacing with [Kobrad](https://github.com/kobradag/kobrad)

## Installing kobra-grpc

```
npm install -g @kobradag/grpc
```

## Cloning kobra-grpc

```
git clone https://github.com/kobradag/koda-grpc
cd kobra-grpc
npm install
```

## Example

```js
const { Client } = require('@kobradag/grpc');

const client = new Client({
    host:"127.0.0.1:44448"
});
client.connect();
client.verbose = true;

try {
    let response = await client.call('getMempoolEntriesRequest', { });
    console.log(response);
} catch(ex) {
    ...
}

client.call('getVirtualSelectedParentBlueScoreRequest', { }).then((response)=>{
    console.log(response);
}).catch((err)=>{
    console.log('error:',err);
})
```
