
# Uploading a File

Handles upload and downloading of files
Make sure the directory :: `~/rust-iot/temp` exists

## Build & Run
`cargo build --features "full"`
`cargo run --features "full"`
`docker build .`

* Note docker will be building full, you can change it to do a different version.

## Ports

HTTP: 3001

## Health Check
`http GET http://localhost:3001/api/healthz`

## File Upload
`http -f POST localhost:3001/api/upload name='46320EEA-9D7A-4E10-895C-8264ED780791' file@~/Downloads/videos/image-13.05.2020_05.09.47.jpg`
`http -f POST localhost:3001/api/upload device_id='46320EEA-9D7A-4E10-895C-8264ED780795' file@~/Downloads/videos/video-13.05.2020_05.09.51.mp4`
`http POST localhost:3001/api/upload`
`http POST localhost:3001/api/health`
- Uploading a file to the server

## Download File
`http GET localhost:3001/api/download/2343`

```
curl \
  -F "userid=1" \
  -F "filecomment=This is an image file" \
  -F "image=@test/note.txt" \
  localhost:3001/upload
```

### Example Queries
`http -f POST localhost:3001/api/upload/46320EEA-9D7A-4E10-895C-8264ED780792 file@~/Downloads/videos/image-13.05.2020_05.09.47.jpg`

`http -f POST localhost:3001/api/upload/46320EEA-9D7A-4E10-895C-8264ED780793 file@~/Downloads/videos/video-13.05.2020_05.09.51.mp4`

This is using HTTPie for running.

