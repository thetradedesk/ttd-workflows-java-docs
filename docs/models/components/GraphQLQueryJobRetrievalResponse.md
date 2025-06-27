# GraphQLQueryJobRetrievalResponse

This is the top level class returned to a user when they retrieve a query job


## Fields

| Field                                                                    | Type                                                                     | Required                                                                 | Description                                                              |
| ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ |
| `job`                                                                    | [Optional\<GraphQlQueryJob>](../../models/components/GraphQlQueryJob.md) | :heavy_minus_sign:                                                       | This is the response model that mirrors the GQL bulkjob                  |
| `errors`                                                                 | *JsonNullable\<String>*                                                  | :heavy_minus_sign:                                                       | N/A                                                                      |