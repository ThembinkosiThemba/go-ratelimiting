# Ratelimiter

- limits  on users [based on the number of times the APIs are called to protect against DOS]

## 3 different approaches
1. Token Bucket: when bucket is full, it starts dropping requests. [all requests are collected in a bucket]

2. Per Client Rate Limiting
We dont want to limit the entire application because that will make it difficult for all users to access the APIs.
- Only problematic users need to be kept out.
- User IP address when limiting requests.

3. Toolbooth
- Scalable library, already exists.
- implements multiple types of ratelimit behind the scene so you dont have to write any logic.

## Usage
You can test each method but running each method and calling the api using the following commands

```bash
cd project-directory
go run main.go

```

### API singular call:
```bash
curl -i http://localhost:8080/ping
```

### API multiple calls:
```bash
for i in {1..6}; do curl http://localhost:8080/ping; done
```