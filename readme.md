# zSoftworks | AI Api Docs
## Info
This REST Api is Developed by zSoftworks for private use cases. https://zsoftworks.org

## Content
1. License
2. Get An API key
2. Routes
2. Status
2. Prompt To Image Generation
2. Image To Image Generation
3. Predictions API
2. Error Messages


## 1. License
## YOU NEED TO AGREE TO http://api.zsoftworks.org/License

## 2. Get An API Key
1. Message blatan.t on discord

## 3. Routes
POST:
```
    /status/  <Use: Allows You to get the current status of this API>
    /api/v1/

```
GET:
```
    /status/  <Use: Allows You to get the current status of this API>
    / <Use: Litterally Nothing, Just Displays a static site>
    /api/verify/ <Use: Allows You to verify your API key>
```
## 4. Status

`POST` /status

This Retruns the Current Status of this server. *Do Not Need To Post Any Info*

Example Response:

```json
{"status":"operational","message":"Welcome to the zSoftworks API!","version":"0.01A","warning":"We Are Currently Experincing Slowed Requests"}
```
`GET` /status
This Retruns the Current Status of this server.

Example Response:

```json
{"status":"operational","message":"Welcome to the zSoftworks API!","version":"0.01A","warning":"We Are Currently Experincing Slowed Requests"}
```
## 5. Prompt To Image

`POST` /api/v1/images/generate

This endpoint is for you to request a image generation, then your image will be added to our queue then it will generate and give you your image using our cdn. please do mind that we Clear out our stored images from time to time.


Example cURL request:

```bash
curl -X POST "http://nova-jump.bnr.la:3000/api/v1/images/generate" -H "Authorization: _zsauth.example.example" -H "Content-Type: application/json" -d "{\"prompt\": \"a cute monkey\"}"

```

In this case, Authorization is your zAI Api key. Then prompt is your text prompt. We have two different api key types, a watermarked and non watermarked key. most users have the watermarked key meaning a small watermark will be added

Lets say That you Included a bad prompt for example NSFW content, then you will get a error message like this:

```json
{"code":100,"message":"Promt Flagged"}
```
Example Response:

```json
{"Prompt":"a cute monkey","timestamp":1698399412832,"islogged":true,"watermark":0,"ztrace":"_ztrace_458146ab298da3d80bb3ca98295e204d","Images":["http://nova-jump.bnr.la:3000/cdn/1ef020ed04b4bc/0.png"]}
```

## 8. Code Table


| Code  |  Reason |   
|---|---|
| 100  | Promt Flagged  |
|  104 |  Error Processing Request |
| 101  |  No token provided.  |
|102|Unauthorized request. Token provided was invalid.|
|103|Credit Too Low |
|105| Error Making image|
|106| Unkown Error|
|107| Missing Entry|
|108| Invalid Entry|
|109| User Created|
|110| Sucess|
## 9. How Credits Work
> Each image Generated is 1 Credit, and each credit is $0.009. You can buyGet credits by asking blatant
