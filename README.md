# Push Server using NodeJs and simple client app
This project has two faces, server and client

## push server
server is a push server created using NodeJs where you can send push notifications

## client
client is a simple application to subscribe and unsubscribe push notifications

# Project installation needs

## client
use any static server to run client project

### My Favorite is http server
install - npm -i -g http-server
run - http-server -p 8081 (8081 is a port)

## server
1. Node
2. nodemon(optional to rerun the server whenever changes happen)
    npm i -g nodemon
3. webpush
    npm i -g --save web-push
4. urlsafe-base64
    npm i --save urlsafe-base64
5. node-storage
    npm i --save node-storage

### generate vapid keys 
#### generate vapid keys in json format and store it in vapid.json file
web-push generate-vapid-keys --json > server/vapid.json

#### using package.json
I have added the command in package.json So, simply run
npm run-script vapid

### to run nodemon server
nodemon server/

### to send push notification
#### localhost:3333 is my server, use yours when you run
curl -X POST -d "Hi, I am push notification" localhost:3333/push

#### if using powershell
Invoke-WebRequest -Method POST -Body "Hello World" -Uri http://localhost:3333/push