# AdGroup
(*adGroup()*)

## Overview

### Available Operations

* [createAdGroup](#createadgroup) - Create a new ad group with required fields
* [updateAdGroup](#updateadgroup) - Update an ad group with specified fields
* [archiveAdGroups](#archiveadgroups) - Archive multiple ad groups
* [createAdGroupsJob](#createadgroupsjob) - Create multiple new ad groups with required fields
* [updateAdGroupsJob](#updateadgroupsjob) - Update multiple ad groups with specified fields

## createAdGroup

Create a new ad group with required fields

### Example Usage

```java
package hello.world;

import com.thetradedesk.workflows.TtdWorkflows;
import com.thetradedesk.workflows.models.components.*;
import com.thetradedesk.workflows.models.errors.ProblemDetailsException;
import com.thetradedesk.workflows.models.operations.CreateAdGroupResponse;
import java.lang.Exception;
import java.util.List;
import java.util.Optional;
import org.openapitools.jackson.nullable.JsonNullable;

public class Application {

    public static void main(String[] args) throws ProblemDetailsException, Exception {

        TtdWorkflows sdk = TtdWorkflows.builder()
                .ttdAuth("<YOUR_API_KEY_HERE>")
            .build();

        AdGroupCreateWorkflowInputWithValidation req = AdGroupCreateWorkflowInputWithValidation.builder()
                .primaryInput(AdGroupCreateWorkflowPrimaryInput.builder()
                    .name("<value>")
                    .channel(AdGroupChannel.DISPLAY)
                    .funnelLocation(AdGroupFunnelLocation.CONSIDERATION)
                    .isEnabled(false)
                    .description("twine from gosh poor safely editor astride vice lost and")
                    .budget(AdGroupWorkflowBudgetInput.builder()
                        .allocationType(AllocationType.MAXIMUM)
                        .budgetInAdvertiserCurrency(3786.02)
                        .budgetInImpressions(783190L)
                        .dailyTargetInAdvertiserCurrency(9747.02)
                        .dailyTargetInImpressions(985999L)
                        .build())
                    .baseBidCPMInAdvertiserCurrency(3785.04)
                    .maxBidCPMInAdvertiserCurrency(7447.3)
                    .audienceTargeting(AdGroupWorkflowAudienceTargetingInput.builder()
                        .audienceId("<id>")
                        .audienceAcceleratorExclusionsEnabled(true)
                        .audienceBoosterEnabled(true)
                        .audienceExcluderEnabled(true)
                        .audiencePredictorEnabled(false)
                        .crossDeviceVendorListForAudience(List.of(
                            107263))
                        .recencyExclusionWindowInMinutes(90062)
                        .targetTrackableUsersEnabled(true)
                        .useMcIdAsPrimary(true)
                        .build())
                    .roiGoal(AdGroupWorkflowROIGoalInput.builder()
                        .maximizeReach(true)
                        .maximizeLtvIncrementalReach(false)
                        .cpcInAdvertiserCurrency(2280.31)
                        .ctrInPercent(JsonNullable.of(null))
                        .nielsenOTPInPercent(5175.21)
                        .cpaInAdvertiserCurrency(2544.37)
                        .returnOnAdSpendPercent(8201.47)
                        .vcrInPercent(4846.08)
                        .viewabilityInPercent(JsonNullable.of(null))
                        .vcpmInAdvertiserCurrency(4649.53)
                        .cpcvInAdvertiserCurrency(313.95)
                        .miaozhenOTPInPercent(4704.1)
                        .build())
                    .creativeIds(JsonNullable.of(null))
                    .associatedBidLists(List.of(
                        AdGroupWorkflowAssociateBidListInput.builder()
                            .bidListId("<id>")
                            .isEnabled(false)
                            .isDefaultForDimension(true)
                            .build()))
                    .programmaticGuaranteedPrivateContractId("<id>")
                    .build())
                .campaignId("<id>")
                .advancedInput(AdGroupWorkflowAdvancedInput.builder()
                    .koaOptimizationSettings(AdGroupWorkflowKoaOptimizationSettingsInput.builder()
                        .areFutureKoaFeaturesEnabled(false)
                        .predictiveClearingEnabled(false)
                        .build())
                    .comscoreSettings(AdGroupWorkflowComscoreSettingsInput.builder()
                        .isEnabled(false)
                        .populationId(JsonNullable.of(null))
                        .demographicMemberIds(List.of(
                            959580,
                            236376))
                        .mobileDemographicMemberIds(List.of(
                            664689,
                            827980,
                            21321))
                        .build())
                    .contractTargeting(AdGroupWorkflowContractTargetingInput.builder()
                        .allowOpenMarketBiddingWhenTargetingContracts(true)
                        .build())
                    .dimensionalBiddingAutoOptimizationSettings(List.of(
                        List.of(),
                        List.of()))
                    .isUseClicksAsConversionsEnabled(false)
                    .isUseSecondaryConversionsEnabled(false)
                    .nielsenTrackingAttributes(AdGroupWorkflowNielsenTrackingAttributesInput.builder()
                        .gender(TargetingGender.MALE)
                        .startAge(TargetingStartAge.TWENTY_FIVE)
                        .endAge(TargetingEndAge.SEVENTEEN)
                        .countries(List.of(
                            "<value 1>",
                            "<value 2>",
                            "<value 3>"))
                        .enhancedReportingOption(EnhancedNielsenReportingOptions.SITE)
                        .build())
                    .newFrequencyConfigs(List.of(
                        AdGroupWorkflowNewFrequencyConfigInput.builder()
                            .counterName(Optional.empty())
                            .frequencyCap(375286)
                            .frequencyGoal(534735)
                            .resetIntervalInMinutes(788122)
                            .build()))
                    .flights(List.of(
                        AdGroupWorkflowFlightInput.builder()
                            .campaignFlightId(874887L)
                            .allocationType(AllocationType.MAXIMUM)
                            .budgetInAdvertiserCurrency(4070.96)
                            .budgetInImpressions(901477L)
                            .dailyTargetInAdvertiserCurrency(5847.35)
                            .dailyTargetInImpressions(257517L)
                            .build()))
                    .build())
                .validateInputOnly(true)
                .build();

        CreateAdGroupResponse res = sdk.adGroup().createAdGroup()
                .request(req)
                .call();

        if (res.adGroupPayload().isPresent()) {
            // handle response
        }
    }
}
```

### Parameters

| Parameter                                                                                                   | Type                                                                                                        | Required                                                                                                    | Description                                                                                                 |
| ----------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                   | [AdGroupCreateWorkflowInputWithValidation](../../models/shared/AdGroupCreateWorkflowInputWithValidation.md) | :heavy_check_mark:                                                                                          | The request object to use for the request.                                                                  |

### Response

**[CreateAdGroupResponse](../../models/operations/CreateAdGroupResponse.md)**

### Errors

| Error Type                            | Status Code                           | Content Type                          |
| ------------------------------------- | ------------------------------------- | ------------------------------------- |
| models/errors/ProblemDetailsException | 400, 403                              | application/json                      |
| models/errors/APIException            | 4XX, 5XX                              | \*/\*                                 |

## updateAdGroup

Only the fields provided in the request payload will be updated.

### Example Usage

```java
package hello.world;

import com.thetradedesk.workflows.TtdWorkflows;
import com.thetradedesk.workflows.models.components.*;
import com.thetradedesk.workflows.models.errors.ProblemDetailsException;
import com.thetradedesk.workflows.models.operations.UpdateAdGroupResponse;
import java.lang.Exception;
import java.util.List;
import org.openapitools.jackson.nullable.JsonNullable;

public class Application {

    public static void main(String[] args) throws ProblemDetailsException, Exception {

        TtdWorkflows sdk = TtdWorkflows.builder()
                .ttdAuth("<YOUR_API_KEY_HERE>")
            .build();

        AdGroupUpdateWorkflowInputWithValidation req = AdGroupUpdateWorkflowInputWithValidation.builder()
                .id("<id>")
                .primaryInput(AdGroupUpdateWorkflowPrimaryInput.builder()
                    .isEnabled(JsonNullable.of(null))
                    .description("likely upliftingly league that finally after owlishly when furthermore brush")
                    .budget(AdGroupWorkflowBudgetInput.builder()
                        .allocationType(AllocationType.MAXIMUM)
                        .budgetInAdvertiserCurrency(2166.43)
                        .budgetInImpressions(508947L)
                        .dailyTargetInAdvertiserCurrency(5830.53)
                        .dailyTargetInImpressions(377823L)
                        .build())
                    .baseBidCPMInAdvertiserCurrency(1710.9)
                    .maxBidCPMInAdvertiserCurrency(1926.83)
                    .audienceTargeting(AdGroupWorkflowAudienceTargetingInput.builder()
                        .audienceId("<id>")
                        .audienceAcceleratorExclusionsEnabled(false)
                        .audienceBoosterEnabled(true)
                        .audienceExcluderEnabled(true)
                        .audiencePredictorEnabled(true)
                        .crossDeviceVendorListForAudience(List.of(
                            774064,
                            165155,
                            542528))
                        .recencyExclusionWindowInMinutes(740341)
                        .targetTrackableUsersEnabled(false)
                        .useMcIdAsPrimary(true)
                        .build())
                    .roiGoal(AdGroupWorkflowROIGoalInput.builder()
                        .maximizeReach(false)
                        .maximizeLtvIncrementalReach(false)
                        .cpcInAdvertiserCurrency(1146.61)
                        .ctrInPercent(3063.1)
                        .nielsenOTPInPercent(411.57)
                        .cpaInAdvertiserCurrency(JsonNullable.of(null))
                        .returnOnAdSpendPercent(7161.01)
                        .vcrInPercent(5983.85)
                        .viewabilityInPercent(9094.92)
                        .vcpmInAdvertiserCurrency(1135.94)
                        .cpcvInAdvertiserCurrency(6372.45)
                        .miaozhenOTPInPercent(8405.28)
                        .build())
                    .creativeIds(List.of(
                        "<value 1>",
                        "<value 2>",
                        "<value 3>"))
                    .associatedBidLists(List.of(
                        AdGroupWorkflowAssociateBidListInput.builder()
                            .bidListId("<id>")
                            .isEnabled(true)
                            .isDefaultForDimension(true)
                            .build()))
                    .name("<value>")
                    .channel(AdGroupChannel.NATIVE)
                    .funnelLocation(AdGroupFunnelLocation.CONVERSION)
                    .build())
                .advancedInput(AdGroupWorkflowAdvancedInput.builder()
                    .koaOptimizationSettings(AdGroupWorkflowKoaOptimizationSettingsInput.builder()
                        .areFutureKoaFeaturesEnabled(false)
                        .predictiveClearingEnabled(true)
                        .build())
                    .comscoreSettings(AdGroupWorkflowComscoreSettingsInput.builder()
                        .isEnabled(false)
                        .populationId(935670)
                        .demographicMemberIds(List.of(
                            873274,
                            940674,
                            350994))
                        .mobileDemographicMemberIds(List.of(
                            572403,
                            872508,
                            141651))
                        .build())
                    .contractTargeting(AdGroupWorkflowContractTargetingInput.builder()
                        .allowOpenMarketBiddingWhenTargetingContracts(true)
                        .build())
                    .dimensionalBiddingAutoOptimizationSettings(List.of(
                        List.of(
                            DimensionalBiddingDimensions.HAS_CONTENT_LIVESTREAM)))
                    .isUseClicksAsConversionsEnabled(false)
                    .isUseSecondaryConversionsEnabled(false)
                    .nielsenTrackingAttributes(AdGroupWorkflowNielsenTrackingAttributesInput.builder()
                        .gender(TargetingGender.FEMALE)
                        .startAge(TargetingStartAge.FIFTY_FIVE)
                        .endAge(TargetingEndAge.SIXTY_FOUR_PLUS)
                        .countries(List.of(
                            "<value 1>",
                            "<value 2>"))
                        .enhancedReportingOption(EnhancedNielsenReportingOptions.NONE)
                        .build())
                    .newFrequencyConfigs(List.of(
                        AdGroupWorkflowNewFrequencyConfigInput.builder()
                            .counterName("<value>")
                            .frequencyCap(685969)
                            .frequencyGoal(448470)
                            .resetIntervalInMinutes(577492)
                            .build()))
                    .flights(List.of(
                        AdGroupWorkflowFlightInput.builder()
                            .campaignFlightId(528311L)
                            .allocationType(AllocationType.MINIMUM)
                            .budgetInAdvertiserCurrency(5325.23)
                            .budgetInImpressions(876101L)
                            .dailyTargetInAdvertiserCurrency(44.58)
                            .dailyTargetInImpressions(815686L)
                            .build()))
                    .build())
                .validateInputOnly(false)
                .build();

        UpdateAdGroupResponse res = sdk.adGroup().updateAdGroup()
                .request(req)
                .call();

        if (res.adGroupPayload().isPresent()) {
            // handle response
        }
    }
}
```

### Parameters

| Parameter                                                                                                   | Type                                                                                                        | Required                                                                                                    | Description                                                                                                 |
| ----------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                   | [AdGroupUpdateWorkflowInputWithValidation](../../models/shared/AdGroupUpdateWorkflowInputWithValidation.md) | :heavy_check_mark:                                                                                          | The request object to use for the request.                                                                  |

### Response

**[UpdateAdGroupResponse](../../models/operations/UpdateAdGroupResponse.md)**

### Errors

| Error Type                            | Status Code                           | Content Type                          |
| ------------------------------------- | ------------------------------------- | ------------------------------------- |
| models/errors/ProblemDetailsException | 400, 403                              | application/json                      |
| models/errors/APIException            | 4XX, 5XX                              | \*/\*                                 |

## archiveAdGroups

**NOTE**: Once archived, ad groups cannot be un-archived.

### Example Usage

```java
package hello.world;

import com.thetradedesk.workflows.TtdWorkflows;
import com.thetradedesk.workflows.models.errors.ProblemDetailsException;
import com.thetradedesk.workflows.models.operations.ArchiveAdGroupsResponse;
import java.lang.Exception;
import java.util.List;

public class Application {

    public static void main(String[] args) throws ProblemDetailsException, Exception {

        TtdWorkflows sdk = TtdWorkflows.builder()
                .ttdAuth("<YOUR_API_KEY_HERE>")
            .build();

        ArchiveAdGroupsResponse res = sdk.adGroup().archiveAdGroups()
                .forceArchive(false)
                .requestBody(List.of(
                    "<value 1>",
                    "<value 2>"))
                .call();

        if (res.strings().isPresent()) {
            // handle response
        }
    }
}
```

### Parameters

| Parameter            | Type                 | Required             | Description          |
| -------------------- | -------------------- | -------------------- | -------------------- |
| `forceArchive`       | *Optional\<Boolean>* | :heavy_minus_sign:   | N/A                  |
| `requestBody`        | List\<*String*>      | :heavy_minus_sign:   | N/A                  |

### Response

**[ArchiveAdGroupsResponse](../../models/operations/ArchiveAdGroupsResponse.md)**

### Errors

| Error Type                            | Status Code                           | Content Type                          |
| ------------------------------------- | ------------------------------------- | ------------------------------------- |
| models/errors/ProblemDetailsException | 400, 403                              | application/json                      |
| models/errors/APIException            | 4XX, 5XX                              | \*/\*                                 |

## createAdGroupsJob

Create multiple new ad groups with required fields

### Example Usage

```java
package hello.world;

import com.thetradedesk.workflows.TtdWorkflows;
import com.thetradedesk.workflows.models.components.AdGroupBulkCreateWorkflowInputWithValidation;
import com.thetradedesk.workflows.models.components.WorkflowCallbackInput;
import com.thetradedesk.workflows.models.errors.ProblemDetailsException;
import com.thetradedesk.workflows.models.operations.CreateAdGroupsJobResponse;
import java.lang.Exception;
import java.util.List;
import java.util.Map;

public class Application {

    public static void main(String[] args) throws ProblemDetailsException, Exception {

        TtdWorkflows sdk = TtdWorkflows.builder()
                .ttdAuth("<YOUR_API_KEY_HERE>")
            .build();

        AdGroupBulkCreateWorkflowInputWithValidation req = AdGroupBulkCreateWorkflowInputWithValidation.builder()
                .input(List.of())
                .validateInputOnly(false)
                .callbackInput(WorkflowCallbackInput.builder()
                    .callbackUrl("https://fantastic-daughter.biz/")
                    .callbackHeaders(Map.ofEntries(
                        Map.entry("key", "<value>"),
                        Map.entry("key1", "<value>"),
                        Map.entry("key2", "<value>")))
                    .build())
                .build();

        CreateAdGroupsJobResponse res = sdk.adGroup().createAdGroupsJob()
                .request(req)
                .call();

        if (res.standardJobSubmitResponse().isPresent()) {
            // handle response
        }
    }
}
```

### Parameters

| Parameter                                                                                                           | Type                                                                                                                | Required                                                                                                            | Description                                                                                                         |
| ------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                           | [AdGroupBulkCreateWorkflowInputWithValidation](../../models/shared/AdGroupBulkCreateWorkflowInputWithValidation.md) | :heavy_check_mark:                                                                                                  | The request object to use for the request.                                                                          |

### Response

**[CreateAdGroupsJobResponse](../../models/operations/CreateAdGroupsJobResponse.md)**

### Errors

| Error Type                            | Status Code                           | Content Type                          |
| ------------------------------------- | ------------------------------------- | ------------------------------------- |
| models/errors/ProblemDetailsException | 400, 403                              | application/json                      |
| models/errors/APIException            | 4XX, 5XX                              | \*/\*                                 |

## updateAdGroupsJob

Only the fields provided in the request payload for each specific ad group will be updated.

### Example Usage

```java
package hello.world;

import com.thetradedesk.workflows.TtdWorkflows;
import com.thetradedesk.workflows.models.components.*;
import com.thetradedesk.workflows.models.errors.ProblemDetailsException;
import com.thetradedesk.workflows.models.operations.UpdateAdGroupsJobResponse;
import java.lang.Exception;
import java.util.List;
import org.openapitools.jackson.nullable.JsonNullable;

public class Application {

    public static void main(String[] args) throws ProblemDetailsException, Exception {

        TtdWorkflows sdk = TtdWorkflows.builder()
                .ttdAuth("<YOUR_API_KEY_HERE>")
            .build();

        AdGroupBulkUpdateWorkflowInputWithValidation req = AdGroupBulkUpdateWorkflowInputWithValidation.builder()
                .input(List.of(
                    AdGroupUpdateWorkflowInput.builder()
                        .id("<id>")
                        .primaryInput(AdGroupUpdateWorkflowPrimaryInput.builder()
                            .isEnabled(false)
                            .description("stealthily miserable imaginary er since athwart er blah marten")
                            .budget(AdGroupWorkflowBudgetInput.builder()
                                .allocationType(AllocationType.MINIMUM)
                                .budgetInAdvertiserCurrency(5440.47)
                                .budgetInImpressions(JsonNullable.of(null))
                                .dailyTargetInAdvertiserCurrency(6251.13)
                                .dailyTargetInImpressions(931411L)
                                .build())
                            .baseBidCPMInAdvertiserCurrency(188.02)
                            .maxBidCPMInAdvertiserCurrency(6077.98)
                            .audienceTargeting(AdGroupWorkflowAudienceTargetingInput.builder()
                                .audienceId("<id>")
                                .audienceAcceleratorExclusionsEnabled(true)
                                .audienceBoosterEnabled(true)
                                .audienceExcluderEnabled(false)
                                .audiencePredictorEnabled(false)
                                .crossDeviceVendorListForAudience(List.of(
                                    27262))
                                .recencyExclusionWindowInMinutes(676417)
                                .targetTrackableUsersEnabled(true)
                                .useMcIdAsPrimary(true)
                                .build())
                            .roiGoal(AdGroupWorkflowROIGoalInput.builder()
                                .maximizeReach(false)
                                .maximizeLtvIncrementalReach(true)
                                .cpcInAdvertiserCurrency(JsonNullable.of(null))
                                .ctrInPercent(2972.79)
                                .nielsenOTPInPercent(4206.38)
                                .cpaInAdvertiserCurrency(JsonNullable.of(null))
                                .returnOnAdSpendPercent(842.94)
                                .vcrInPercent(6307.13)
                                .viewabilityInPercent(9286.78)
                                .vcpmInAdvertiserCurrency(8251.2)
                                .cpcvInAdvertiserCurrency(4502.77)
                                .miaozhenOTPInPercent(2362.43)
                                .build())
                            .creativeIds(List.of(
                                "<value 1>"))
                            .associatedBidLists(List.of(
                                AdGroupWorkflowAssociateBidListInput.builder()
                                    .bidListId("<id>")
                                    .isEnabled(true)
                                    .isDefaultForDimension(true)
                                    .build()))
                            .name("<value>")
                            .channel(AdGroupChannel.TV)
                            .funnelLocation(AdGroupFunnelLocation.NONE)
                            .build())
                        .advancedInput(AdGroupWorkflowAdvancedInput.builder()
                            .koaOptimizationSettings(AdGroupWorkflowKoaOptimizationSettingsInput.builder()
                                .areFutureKoaFeaturesEnabled(true)
                                .predictiveClearingEnabled(false)
                                .build())
                            .comscoreSettings(AdGroupWorkflowComscoreSettingsInput.builder()
                                .isEnabled(true)
                                .populationId(907569)
                                .demographicMemberIds(JsonNullable.of(null))
                                .mobileDemographicMemberIds(List.of(
                                    169306,
                                    568551))
                                .build())
                            .contractTargeting(AdGroupWorkflowContractTargetingInput.builder()
                                .allowOpenMarketBiddingWhenTargetingContracts(true)
                                .build())
                            .dimensionalBiddingAutoOptimizationSettings(List.of(
                                List.of(
                                    DimensionalBiddingDimensions.HAS_FREQUENCY_ADJUSTMENT_ID)))
                            .isUseClicksAsConversionsEnabled(true)
                            .isUseSecondaryConversionsEnabled(true)
                            .nielsenTrackingAttributes(AdGroupWorkflowNielsenTrackingAttributesInput.builder()
                                .gender(TargetingGender.FEMALE)
                                .startAge(TargetingStartAge.FORTY_FIVE)
                                .endAge(TargetingEndAge.THIRTY_FOUR)
                                .countries(List.of(
                                    "<value 1>",
                                    "<value 2>"))
                                .enhancedReportingOption(EnhancedNielsenReportingOptions.AUDIENCE)
                                .build())
                            .newFrequencyConfigs(List.of(
                                AdGroupWorkflowNewFrequencyConfigInput.builder()
                                    .counterName("<value>")
                                    .frequencyCap(25438)
                                    .frequencyGoal(637221)
                                    .resetIntervalInMinutes(375296)
                                    .build()))
                            .flights(JsonNullable.of(null))
                            .build())
                        .build()))
                .validateInputOnly(true)
                .callbackInput(WorkflowCallbackInput.builder()
                    .callbackUrl("https://winged-bathhouse.net")
                    .callbackHeaders(JsonNullable.of(null))
                    .build())
                .build();

        UpdateAdGroupsJobResponse res = sdk.adGroup().updateAdGroupsJob()
                .request(req)
                .call();

        if (res.standardJobSubmitResponse().isPresent()) {
            // handle response
        }
    }
}
```

### Parameters

| Parameter                                                                                                           | Type                                                                                                                | Required                                                                                                            | Description                                                                                                         |
| ------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                           | [AdGroupBulkUpdateWorkflowInputWithValidation](../../models/shared/AdGroupBulkUpdateWorkflowInputWithValidation.md) | :heavy_check_mark:                                                                                                  | The request object to use for the request.                                                                          |

### Response

**[UpdateAdGroupsJobResponse](../../models/operations/UpdateAdGroupsJobResponse.md)**

### Errors

| Error Type                            | Status Code                           | Content Type                          |
| ------------------------------------- | ------------------------------------- | ------------------------------------- |
| models/errors/ProblemDetailsException | 400, 403                              | application/json                      |
| models/errors/APIException            | 4XX, 5XX                              | \*/\*                                 |