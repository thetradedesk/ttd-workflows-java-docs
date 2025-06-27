# GraphQlQueryJobInput

Required fields for executing a GraphQL query job


## Fields

| Field                                                                                    | Type                                                                                     | Required                                                                                 | Description                                                                              |
| ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| `query`                                                                                  | *String*                                                                                 | :heavy_check_mark:                                                                       | The GraphQL query to execute                                                             |
| `callbackInput`                                                                          | [Optional\<GraphQlJobCallbackInput>](../../models/components/GraphQlJobCallbackInput.md) | :heavy_minus_sign:                                                                       | Input class for providing a callback's url and any headers needed for the callback.      |