# Dmp
(*dmp()*)

## Overview

### Available Operations

* [getFirstPartyDataJob](#getfirstpartydatajob) - Submit a job for first-party data retrieval for an advertiser
* [getThirdPartyDataJob](#getthirdpartydatajob) - Submit a job for third-party data retrieval for a partner

## getFirstPartyDataJob

When a first-party data query is submitted, a job ID is returned.
This job ID can be used to poll for the job's status using the associated operation under "Job Status".

### Example Usage

```java
package hello.world;

import com.thetradedesk.workflows.TtdWorkflows;
import com.thetradedesk.workflows.models.components.FirstPartyDataInput;
import com.thetradedesk.workflows.models.components.WorkflowCallbackInput;
import com.thetradedesk.workflows.models.errors.ProblemDetailsException;
import com.thetradedesk.workflows.models.operations.GetFirstPartyDataJobResponse;
import java.lang.Exception;
import java.util.Map;

public class Application {

    public static void main(String[] args) throws ProblemDetailsException, Exception {

        TtdWorkflows sdk = TtdWorkflows.builder()
                .ttdAuth("<YOUR_API_KEY_HERE>")
            .build();

        FirstPartyDataInput req = FirstPartyDataInput.builder()
                .advertiserId("<id>")
                .nameFilter("<value>")
                .queryShape("<value>")
                .callbackInput(WorkflowCallbackInput.builder()
                    .callbackUrl("https://difficult-pocket-watch.com")
                    .callbackHeaders(Map.ofEntries(
                        Map.entry("key", "<value>"),
                        Map.entry("key1", "<value>"),
                        Map.entry("key2", "<value>")))
                    .build())
                .build();

        GetFirstPartyDataJobResponse res = sdk.dmp().getFirstPartyDataJob()
                .request(req)
                .call();

        if (res.typeBasedJobSubmitResponse().isPresent()) {
            // handle response
        }
    }
}
```

### Parameters

| Parameter                                                         | Type                                                              | Required                                                          | Description                                                       |
| ----------------------------------------------------------------- | ----------------------------------------------------------------- | ----------------------------------------------------------------- | ----------------------------------------------------------------- |
| `request`                                                         | [FirstPartyDataInput](../../models/shared/FirstPartyDataInput.md) | :heavy_check_mark:                                                | The request object to use for the request.                        |

### Response

**[GetFirstPartyDataJobResponse](../../models/operations/GetFirstPartyDataJobResponse.md)**

### Errors

| Error Type                            | Status Code                           | Content Type                          |
| ------------------------------------- | ------------------------------------- | ------------------------------------- |
| models/errors/ProblemDetailsException | 400, 401, 403, 404                    | application/json                      |
| models/errors/APIException            | 4XX, 5XX                              | \*/\*                                 |

## getThirdPartyDataJob

When a third-party data query is submitted, a job ID is returned.
This job ID can be used to poll for the job's status, and when complete, the results download link,
using the associated operation under "Job Status".

### Example Usage

```java
package hello.world;

import com.thetradedesk.workflows.TtdWorkflows;
import com.thetradedesk.workflows.models.components.ThirdPartyDataInput;
import com.thetradedesk.workflows.models.components.WorkflowCallbackInput;
import com.thetradedesk.workflows.models.errors.ProblemDetailsException;
import com.thetradedesk.workflows.models.operations.GetThirdPartyDataJobResponse;
import java.lang.Exception;
import java.util.Map;

public class Application {

    public static void main(String[] args) throws ProblemDetailsException, Exception {

        TtdWorkflows sdk = TtdWorkflows.builder()
                .ttdAuth("<YOUR_API_KEY_HERE>")
            .build();

        ThirdPartyDataInput req = ThirdPartyDataInput.builder()
                .partnerId("<id>")
                .queryShape("<value>")
                .callbackInput(WorkflowCallbackInput.builder()
                    .callbackUrl("https://extroverted-intent.net")
                    .callbackHeaders(Map.ofEntries(
                        Map.entry("key", "<value>"),
                        Map.entry("key1", "<value>")))
                    .build())
                .build();

        GetThirdPartyDataJobResponse res = sdk.dmp().getThirdPartyDataJob()
                .request(req)
                .call();

        if (res.typeBasedJobSubmitResponse().isPresent()) {
            // handle response
        }
    }
}
```

### Parameters

| Parameter                                                         | Type                                                              | Required                                                          | Description                                                       |
| ----------------------------------------------------------------- | ----------------------------------------------------------------- | ----------------------------------------------------------------- | ----------------------------------------------------------------- |
| `request`                                                         | [ThirdPartyDataInput](../../models/shared/ThirdPartyDataInput.md) | :heavy_check_mark:                                                | The request object to use for the request.                        |

### Response

**[GetThirdPartyDataJobResponse](../../models/operations/GetThirdPartyDataJobResponse.md)**

### Errors

| Error Type                            | Status Code                           | Content Type                          |
| ------------------------------------- | ------------------------------------- | ------------------------------------- |
| models/errors/ProblemDetailsException | 400, 401, 403, 404                    | application/json                      |
| models/errors/APIException            | 4XX, 5XX                              | \*/\*                                 |