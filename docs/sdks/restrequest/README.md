# RESTRequest
(*restRequest()*)

## Overview

### Available Operations

* [submitRestRequest](#submitrestrequest) - Submit a valid REST request

## submitRestRequest

This generic operation can be used to execute any valid REST request.
To explore the available REST operations, see the [REST API Reference](https://partner.thetradedesk.com/v3/portal/api/doc/ApiReferencePlatform).

### Example Usage

```java
package hello.world;

import com.thetradedesk.workflows.TtdWorkflows;
import com.thetradedesk.workflows.models.components.CallRestApiWorkflowInput;
import com.thetradedesk.workflows.models.components.RestApiMethodType;
import com.thetradedesk.workflows.models.errors.ProblemDetailsException;
import com.thetradedesk.workflows.models.operations.SubmitRestRequestResponse;
import java.lang.Exception;

public class Application {

    public static void main(String[] args) throws ProblemDetailsException, Exception {

        TtdWorkflows sdk = TtdWorkflows.builder()
                .ttdAuth("<YOUR_API_KEY_HERE>")
            .build();

        CallRestApiWorkflowInput req = CallRestApiWorkflowInput.builder()
                .methodType(RestApiMethodType.GET)
                .endpoint("<value>")
                .dataBody("<value>")
                .build();

        SubmitRestRequestResponse res = sdk.restRequest().submitRestRequest()
                .request(req)
                .call();

        if (res.object().isPresent()) {
            // handle response
        }
    }
}
```

### Parameters

| Parameter                                                                   | Type                                                                        | Required                                                                    | Description                                                                 |
| --------------------------------------------------------------------------- | --------------------------------------------------------------------------- | --------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| `request`                                                                   | [CallRestApiWorkflowInput](../../models/shared/CallRestApiWorkflowInput.md) | :heavy_check_mark:                                                          | The request object to use for the request.                                  |

### Response

**[SubmitRestRequestResponse](../../models/operations/SubmitRestRequestResponse.md)**

### Errors

| Error Type                            | Status Code                           | Content Type                          |
| ------------------------------------- | ------------------------------------- | ------------------------------------- |
| models/errors/ProblemDetailsException | 400, 401, 403, 404                    | application/json                      |
| models/errors/APIException            | 4XX, 5XX                              | \*/\*                                 |