
# DashJs Streaming

Service using NodeJs and React to create a video stream using a fragmented video dealing with buffers, bitrate and resolution.

# Configuration
* Inside api/dash-js-react folder run 
  ```
   npm install
  ```
* After run npm run start inside of both
  * Player will be running on 3000
  * Backend will be running on 4000 (env)

## Routes

#### Uploading video

```http
  POST /store
```

| Body   | Type       | Description                           |
| :---------- | :--------- | :---------------------------------- |
| `file` | `file` | **Mandatory**. Your file with .mp4 extension

#### Returns a JSON containing the uploaded video ID
```
{
    "id": **id do video**
}
```
##
#### Converting the video into fragments
```http
  POST /manifest
```

| Body   | Type       | Description                                   |
| :---------- | :--------- | :------------------------------------------ |
| `id`      | `string` | **Mandatory**. The respective ID of the created video |


##

#### Get the MPD Xml (should be used in the player but it's possible to verify if the generated file is valid)
```
GET /{videoId}
```
| Parameter   | Type       | Description                                   |
| :---------- | :--------- | :------------------------------------------ |
| `videoId`      | `string` | **Mandatory**. The respective ID of the created video |



