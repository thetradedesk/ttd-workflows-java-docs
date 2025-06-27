# GraphQLRequest
(*graphQLRequest()*)

## Overview

### Available Operations

* [submitGraphQlRequest](#submitgraphqlrequest) - Submit a valid GraphQL query or mutation
* [submitGraphQlQueryJob](#submitgraphqlqueryjob) - Submit a valid bulk GraphQL query

## submitGraphQlRequest

This generic operation can be used to execute any valid GraphQL request.
To explore the available GraphQL operations, see the [GraphQL Schema Explorer](https://partner.thetradedesk.com/v3/portal/api/graphql-schema).

### Example Usage

```java
package hello.world;

import com.thetradedesk.workflows.TtdWorkflows;
import com.thetradedesk.workflows.models.components.GraphQLRequestInput;
import com.thetradedesk.workflows.models.components.Variables;
import com.thetradedesk.workflows.models.errors.ProblemDetailsException;
import com.thetradedesk.workflows.models.operations.SubmitGraphQlRequestResponse;
import java.lang.Exception;

public class Application {

    public static void main(String[] args) throws ProblemDetailsException, Exception {

        TtdWorkflows sdk = TtdWorkflows.builder()
                .ttdAuth("<YOUR_API_KEY_HERE>")
            .build();

        GraphQLRequestInput req = GraphQLRequestInput.builder()
                .request("<value>")
                .variables(Variables.builder()
                    .build())
                .build();

        SubmitGraphQlRequestResponse res = sdk.graphQLRequest().submitGraphQlRequest()
                .request(req)
                .call();

        if (res.object().isPresent()) {
            // handle response
        }
    }
}
```

### Parameters

| Parameter                                                         | Type                                                              | Required                                                          | Description                                                       |
| ----------------------------------------------------------------- | ----------------------------------------------------------------- | ----------------------------------------------------------------- | ----------------------------------------------------------------- |
| `request`                                                         | [GraphQLRequestInput](../../models/shared/GraphQLRequestInput.md) | :heavy_check_mark:                                                | The request object to use for the request.                        |

### Response

**[SubmitGraphQlRequestResponse](../../models/operations/SubmitGraphQlRequestResponse.md)**

### Errors

| Error Type                            | Status Code                           | Content Type                          |
| ------------------------------------- | ------------------------------------- | ------------------------------------- |
| models/errors/ProblemDetailsException | 400, 401, 403, 404                    | application/json                      |
| models/errors/APIException            | 4XX, 5XX                              | \*/\*                                 |

## submitGraphQlQueryJob

This generic operation can be used to execute any valid bulk GraphQL query.
For information on bulk GraphQL query syntax, see [GraphQL API Bulk Operations](https://partner.thetradedesk.com/v3/portal/api/doc/GqlBulkOperations).

### Example Usage

```java
package hello.world;

import com.thetradedesk.workflows.TtdWorkflows;
import com.thetradedesk.workflows.models.components.*;
import com.thetradedesk.workflows.models.errors.ProblemDetailsException;
import com.thetradedesk.workflows.models.operations.SubmitGraphQlQueryJobResponse;
import java.lang.Exception;
import java.util.List;

public class Application {

    public static void main(String[] args) throws ProblemDetailsException, Exception {

        TtdWorkflows sdk = TtdWorkflows.builder()
                .ttdAuth("<YOUR_API_KEY_HERE>")
            .build();

        GraphQlQueryJobInput req = GraphQlQueryJobInput.builder()
                .query("<value>")
                .callbackInput(GraphQlJobCallbackInput.builder()
                    .callbackUrl("https://wilted-cork.net/")
                    .callbackHeaders(List.of(
                        KeyValuePairOfStringAndStringInput.builder()
                            .key("<key>")
                            .value("<value>")
                            .build()))
                    .build())
                .build();

        SubmitGraphQlQueryJobResponse res = sdk.graphQLRequest().submitGraphQlQueryJob()
                .request(req)
                .call();

        if (res.graphQlQueryJobResponse().isPresent()) {
            // handle response
        }
    }
}
```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `request`                                                           | [GraphQlQueryJobInput](../../models/shared/GraphQlQueryJobInput.md) | :heavy_check_mark:                                                  | The request object to use for the request.                          |

### Response

**[SubmitGraphQlQueryJobResponse](../../models/operations/SubmitGraphQlQueryJobResponse.md)**

### Errors

| Error Type                            | Status Code                           | Content Type                          |
| ------------------------------------- | ------------------------------------- | ------------------------------------- |
| models/errors/ProblemDetailsException | 400, 401, 403, 404                    | application/json                      |
| models/errors/APIException            | 4XX, 5XX                              | \*/\*                                 |