# New Parameters

## GET classifications job file list

`GET https://analytics.adobe.io/api/{GLOBAL_COMPANY_ID}/classifications/job/export/file/{JOB_ID}/list`

### Request and Response Examples

Click the **Request** tab in the following example to see a cURL request for this endpoint. Click the **Response** tab to see a successful JSON response for the request.

<CodeBlock slots="heading, code" repeat="2" languages="CURL,JSON"/>

#### Request Example

```sh
curl -X GET "https://analytics.adobe.io/api/{GLOBAL_COMPANY_ID}/classifications/job/export/file/{JOB_ID}/list" \
     -H "x-api-key: {CLIENT_ID}" \
     -H "Content-Type: application/json" \
     -H "Authorization: Bearer {ACCESS_TOKEN}"
```

#### Response Example

```json
{
    "count": 6,
    "files": [
        "part1.tsv",
        "part2.tsv",
        "part3.tsv",
        "part4.tsv",
        "part5.tsv",
        "part6.tsv"
    ]
}
```

#### Request example details

The example above requests the list of file *PARTS* for the specified `JOB_ID`.

#### Response example details

The example above returns the `count` of file *PARTS* alongside the *`FILE_NAME`* of each *PART*.

### Request Parameters

| Name | Required | Type | Description |
| --- | --- | --- | --- |
| `job_id` | required | string | The job ID |

### Response Parameters

| Name | Type | Description |
| --- | --- | --- |
| `count` | integer | The number of files returned |
| `files` | container | An array containing the list of files |

## GET classification export job file part

`GET https://analytics.adobe.io/api/{GLOBAL_COMPANY_ID}/classifications/job/export/file/{JOB_ID}/{FILE_NAME}`

### Request and Response Examples

Click the **Request** tab in the following example to see a cURL request for this endpoint. Click the **Response** tab to see a successful JSON response for the request.

<CodeBlock slots="heading, code" repeat="2" languages="CURL,JSON"/>

#### Request Example

```sh
curl -X GET "https://analytics.adobe.io/api/{GLOBAL_COMPANY_ID}/classifications/job/export/file/{JOB_ID}/{FILE_NAME}" \
     -H "x-api-key: {CLIENT_ID}" \
     -H "Content-Type: application/json" \
     -H "Authorization: Bearer {ACCESS_TOKEN}"
```

#### Response Example

```json

```

#### Request example details

The example above requests the file *PART* *`FILE_NAME`*.

#### Response example details

### Request Parameters

| Name | Required | Type | Description |
| --- | --- | --- | --- |
| `job_id` | required | string | The job ID |
| `file_name` | required | string | The name of the file to be retrieved |

### Response Parameters

| Name | Type | Description |
| --- | --- | --- |
| `` |  |  |
