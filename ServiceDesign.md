# Amazon Services

## Media content delivery

### Elastic Transcoder
- Media transcoding
  - converting media to one format to another
  - jobs
    - do the transcoding
  - pipelines
    - queues to manage jobs
  - presets
    - settings to convert media
  - notifications
    - SNS
- Transcoded files placed in OG bucket with different file name

### Translate
- machine learning category
- can integrate for localization
  - supporting multiple languages
- on demand
- encoder
  - reads source text
- decoder
  - outputs

### Elemental MediaStore
- video origination and storage services
  - containers, folders, endpoint, object, and policy
- live video streams
  - good for Elemental MediaStore, origination endpoint
- storage-based video
  - good for S3 buckets

### Transcribe
- speed to text
  - audio and video files
  - video can generate closed captions
- based on machine learning

### Rekognition
- image and video analysis
  - people, speech, objects
- can be run against S3
  - allows enhanced search based on results

## Desktop and app streaming

### WorkSpaces
- Virtual desktops in AWS
  - Linux, Windows 7 with/without Office, Windows 10
- Persistent storage, virtual D: drive
- backed up periodically

### AppStream 2.0
- virtual applications
- common for custom apps

### ElastiCache
- in memory caching for DBs
  - Memcached, very simple
  - Redis, HIPPA or PCI compliant
  
