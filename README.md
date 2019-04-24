# airswap-api-server Docker

## Prerequisite:
- docker: https://docs.docker.com/install/
- docker-compose: https://docs.docker.com/compose/install/

## Start environment:
- clone repository `git clone https://github.com/grandizzy/airswap-api-server.git`
- cd in `airswap-api-server` directory
- create `.env` file containing private key, e.g.  
`PRIVATE_KEY=0x00000000000000000000000000000000000000000000000000000000000000`
- run `./start.sh` to start Airswap `api-server` on port 5005 and Airswap `order-server` on port 5004

## Test:
- use API commands to query Airswap API server (see https://github.com/airswap/developers/tree/master/api-server#api) e.g.
```
curl -X POST \
   http://localhost:5005/getIntents \
   -H 'Content-Type: application/json' \
   -d '{
   "address": "0x6cc47be912a07fbe9cebe68c9e103fdf123b7269"
 }'
```

```
curl -X POST \
   http://localhost:5005/findIntents \
   -H 'Content-Type: application/json' \
   -d '{
   "makerTokens": ["0xcc1cbd4f67cceb7c001bd4adf98451237a193ff8"],
   "takerTokens": ["0x0000000000000000000000000000000000000000"]

 }'
```