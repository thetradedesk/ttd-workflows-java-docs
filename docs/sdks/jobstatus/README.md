# JobStatus
(*jobStatus()*)

## Overview

### Available Operations

* [getGraphQlQueryJobStatus](#getgraphqlqueryjobstatus) - Get the status of a previously submitted GraphQL query job.
* [getJobStatus](#getjobstatus) - Get the status of a previously submitted job

## getGraphQlQueryJobStatus

Use this operation to get a previously submitted GraphQL query job's status and completion percentage.
Once a job is complete, this operation will return the URL from which to download the job results.

### Example Usage

```java
package hello.world;

import com.thetradedesk.workflows.TtdWorkflows;
import com.thetradedesk.workflows.models.errors.ProblemDetailsException;
import com.thetradedesk.workflows.models.operations.GetGraphQlQueryJobStatusResponse;
import java.lang.Exception;

public class Application {

    public static void main(String[] args) throws ProblemDetailsException, Exception {

        TtdWorkflows sdk = TtdWorkflows.builder()
                .ttdAuth("<YOUR_API_KEY_HERE>")
            .build();

        GetGraphQlQueryJobStatusResponse res = sdk.jobStatus().getGraphQlQueryJobStatus()
                .id("<id>")
                .call();

        if (res.graphQLQueryJobRetrievalResponse().isPresent()) {
            // handle response
        }
    }
}
```

### Parameters

| Parameter          | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `id`               | *String*           | :heavy_check_mark: | N/A                |

### Response

**[GetGraphQlQueryJobStatusResponse](../../models/operations/GetGraphQlQueryJobStatusResponse.md)**

### Errors

| Error Type                            | Status Code                           | Content Type                          |
| ------------------------------------- | ------------------------------------- | ------------------------------------- |
| models/errors/ProblemDetailsException | 400, 401, 403, 404                    | application/json                      |
| models/errors/APIException            | 4XX, 5XX                              | \*/\*                                 |

## getJobStatus

Use this operation to get a previously submitted job's status and completion percentage.
Once a job is complete, this operation will return the URL from which to download the job results.
            
Job results expire after 24 hours, at which point you will need to submit a new job.

### Example Usage

```java
package hello.world;

import com.thetradedesk.workflows.TtdWorkflows;
import com.thetradedesk.workflows.models.errors.ProblemDetailsException;
import com.thetradedesk.workflows.models.operations.GetJobStatusResponse;
import java.lang.Exception;

public class Application {

    public static void main(String[] args) throws ProblemDetailsException, Exception {

        TtdWorkflows sdk = TtdWorkflows.builder()
                .ttdAuth("<YOUR_API_KEY_HERE>")
            .build();

        GetJobStatusResponse res = sdk.jobStatus().getJobStatus()
                .id(412651L)
                .call();

        if (res.typeBasedJobStatusResponse().isPresent()) {
            // handle response
        }
    }
}
```

### Parameters

| Parameter          | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `id`               | *long*             | :heavy_check_mark: | N/A                |

### Response

**[GetJobStatusResponse](../../models/operations/GetJobStatusResponse.md)**

### Errors

| Error Type                            | Status Code                           | Content Type                          |
| ------------------------------------- | ------------------------------------- | ------------------------------------- |
| models/errors/ProblemDetailsException | 400, 401, 403, 404                    | application/json                      |
| models/errors/APIException            | 4XX, 5XX                              | \*/\*                                 |