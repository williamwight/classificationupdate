# New Parameters

## GET classifications job file partition list

Use this endpoint to retrieve a list of file parts partitioned from a complete Classifications file belonging to an existing job.

`GET https://analytics.adobe.io/api/{GLOBAL_COMPANY_ID}/classifications/job/export/file/{JOB_ID}/list`

### Request and Response Examples

Click the **Request** tab in the following example to see a cURL request for this endpoint. Click the **Response** tab to see a successful JSON response for the request.

<CodeBlock slots="heading, code" repeat="2" languages="CURL,JSON"/>

#### Request Example

```sh
curl -X GET "https://analytics.adobe.io/api/{GLOBAL_COMPANY_ID}/classifications/job/export/file/16e38fbc-fc82-4fdf-88de-ec33e63489d5/list" \
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

The example above requests the list of Classifications data file parts for the `16e38fbc-fc82-4fdf-88de-ec33e63489d5` job ID.

#### Response example details

The example above returns the `count` of total Classifications data file parts alongside the file name of each part.

### Request Parameters

| Name | Required | Type | Description |
| --- | --- | --- | --- |
| `job_id` | required | string | The job ID |

### Response Parameters

| Name | Type | Description |
| --- | --- | --- |
| `count` | integer | The number of files returned |
| `files` | container | An array containing the list of file part names |

## GET classification export job file part

Use this endpoint to retrieve a part of a complete Classifications data file. The GET classifications job file partition list endpoint may be used to retrieve the file names required for this endpoint. For more information on classification data, see [Classification data files](https://experienceleague.adobe.com/en/docs/analytics/components/classifications/classifications-importer/c-saint-data-files).

`GET https://analytics.adobe.io/api/{GLOBAL_COMPANY_ID}/classifications/job/export/file/{JOB_ID}/{FILE_NAME}`

### Request and Response Examples

Click the **Request** tab in the following example to see a cURL request for this endpoint. Click the **Response** tab to see a successful JSON response for the request.

<CodeBlock slots="heading, code" repeat="2" languages="CURL,JSON"/>

#### Request Example

```sh
curl -X GET "https://analytics.adobe.io/api/{GLOBAL_COMPANY_ID}/classifications/job/export/file/16e38fbc-fc82-4fdf-88de-ec33e63489d5/part1.tsv" \
     -H "x-api-key: {CLIENT_ID}" \
     -H "Content-Type: application/json" \
     -H "Authorization: Bearer {ACCESS_TOKEN}"
```

#### Response Example

```tsv
## SC   SiteCatalyst saint Import File  v:2.1
## SC   '## SC' indicates a SiteCatalyst pre-process header. Please do not remove these lines.
## SC   D:YYYY-07-31 18:00:11  A:xxxxxx:xx
 
Key File Name   File Option Directory
KeyYYYY0522-1   File Name-1 Option-1    Directory-1
KeyYYYY0522-2   File Name-2 Option-2    Directory-2
KeyYYYY0522-3   File Name-3 Option-3    Directory-3
```

#### Request example details

The example above requests the Classifications data file part named `part1.tsv` belonging to the job `16e38fbc-fc82-4fdf-88de-ec33e63489d5`.

#### Response example details

The example above responds with the data of the file part specified in the request.

### Request Parameters

| Name | Required | Type | Description |
| --- | --- | --- | --- |
| `job_id` | required | string | The job ID |
| `file_name` | required | string | The name of the file to be retrieved |

### Response Parameters

The response includes the classification data in the format specified with the export job request. No other response parameters are returned.
