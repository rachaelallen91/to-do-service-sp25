---
layout: page
---

# Update user by ID

Updates a [`user`](user.md) record specified by the `userId` path parameter. The request must include the full user object. Any fields omitted from the request will be removed from the updated user.

## URL

```shell
{server_url}/users/{userId}
```

## Parameters

| Parameter name | Type   | Description                         |
|----------------|--------|-------------------------------------|
| `userId`       | number | The ID of the user to update        |

## Request headers

| Header name     | Value              | Description                   |
|------------------|--------------------|-------------------------------|
| `Content-Type`   | `application/json` | Indicates the request body format is JSON |

## Request body

The request body must contain the complete user object. Any missing properties will be removed from the stored record.

```json
{
  "id": 1,
  "name": "Ferdinand Smith",
  "email": "f.smith@example.com"
}
```

## Example using cURL

```bash
curl -X PUT http://localhost:3000/users/1 \
  -H "Content-Type: application/json" \
  -d '{
    "id": 1,
    "name": "Ferdinand Smith",
    "email": "f.smith@example.com"
  }'
```

## Return body

If the update is successful, the response includes the updated user object.

```json
{
  "id": 1,
  "name": "Ferdinand Smith",
  "email": "f.smith@example.com"
}
```