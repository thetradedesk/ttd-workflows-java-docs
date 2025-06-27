# Campaign
(*campaign()*)

## Overview

### Available Operations

* [create](#create) - Create a new campaign with required fields
* [updateCampaign](#updatecampaign) - Update a campaign with specified fields
* [createCampaignsJob](#createcampaignsjob) - Create multiple new campaigns with required fields
* [updateCampaignsJob](#updatecampaignsjob) - Update multiple campaigns with specified fields
* [archiveCampaigns](#archivecampaigns) - Archive multiple campaigns
* [getVersion](#getversion) - Get a campaign's version

## create

Create a new campaign with required fields

### Example Usage

```java
package hello.world;

import com.thetradedesk.workflows.TtdWorkflows;
import com.thetradedesk.workflows.models.components.*;
import com.thetradedesk.workflows.models.errors.ProblemDetailsException;
import com.thetradedesk.workflows.models.operations.CreateCampaignResponse;
import java.lang.Exception;
import java.time.OffsetDateTime;
import java.util.List;
import org.openapitools.jackson.nullable.JsonNullable;

public class Application {

    public static void main(String[] args) throws ProblemDetailsException, Exception {

        TtdWorkflows sdk = TtdWorkflows.builder()
                .ttdAuth("<YOUR_API_KEY_HERE>")
            .build();

        CampaignCreateWorkflowInputWithValidation req = CampaignCreateWorkflowInputWithValidation.builder()
                .primaryInput(CampaignCreateWorkflowPrimaryInput.builder()
                    .advertiserId("<id>")
                    .name("<value>")
                    .primaryChannel(CampaignChannelType.DOOH)
                    .primaryGoal(CampaignWorkflowROIGoalInput.builder()
                        .maximizeReach(false)
                        .maximizeLtvIncrementalReach(JsonNullable.of(null))
                        .cpcInAdvertiserCurrency(6678.34)
                        .ctrInPercent(5357.4)
                        .nielsenOTPInPercent(2741.6)
                        .cpaInAdvertiserCurrency(4220.63)
                        .returnOnAdSpendPercent(8572.83)
                        .vcrInPercent(8294.92)
                        .viewabilityInPercent(8592.21)
                        .vcpmInAdvertiserCurrency(8388.8)
                        .cpcvInAdvertiserCurrency(JsonNullable.of(null))
                        .miaozhenOTPInPercent(3033.14)
                        .build())
                    .description("woot furthermore mentor")
                    .timeZone("Europe/Ulyanovsk")
                    .customCPAClickWeight(2561.01)
                    .customCPAViewthroughWeight(5604.35)
                    .customCPAType(CustomCPAType.CLICK_VIEWTHROUGH_WEIGHTING)
                    .impressionsOnlyBudgetingCpm(1502.33)
                    .budget(CampaignWorkflowBudgetInput.builder()
                        .pacingMode(CampaignPacingMode.PACE_AS_SOON_AS_POSSIBLE)
                        .budgetInAdvertiserCurrency(6363.35)
                        .budgetInImpressions(836518L)
                        .dailyTargetInAdvertiserCurrency(7814.79)
                        .dailyTargetInImpressions(784985L)
                        .build())
                    .endDateInUtc(JsonNullable.of(null))
                    .seedId(JsonNullable.of(null))
                    .campaignConversionReportingColumns(List.of(
                        CampaignWorkflowCampaignConversionReportingColumnInput.builder()
                            .trackingTagId("<id>")
                            .includeInCustomCPA(false)
                            .reportingColumnId(888649)
                            .roasConfig(CustomROASConfig.builder()
                                .includeInCustomROAS(false)
                                .customROASWeight(4766.9)
                                .customROASClickWeight(3310.24)
                                .customROASViewthroughWeight(2919.37)
                                .build())
                            .weight(5369.43)
                            .crossDeviceAttributionModelId("<id>")
                            .build()))
                    .startDateInUtc(JsonNullable.of(null))
                    .build())
                .advancedInput(CampaignWorkflowAdvancedInput.builder()
                    .flights(List.of(
                        CampaignWorkflowFlightInput.builder()
                            .startDateInclusiveUTC(OffsetDateTime.parse("2024-07-08T10:52:56.944Z"))
                            .budgetInAdvertiserCurrency(5904.11)
                            .endDateExclusiveUTC(OffsetDateTime.parse("2023-05-12T16:41:56.386Z"))
                            .budgetInImpressions(JsonNullable.of(null))
                            .dailyTargetInAdvertiserCurrency(6112.24)
                            .dailyTargetInImpressions(333131L)
                            .build()))
                    .purchaseOrderNumber(JsonNullable.of(null))
                    .build())
                .adGroups(List.of(
                    CampaignCreateWorkflowAdGroupInput.builder()
                        .primaryInput(AdGroupCreateWorkflowPrimaryInput.builder()
                            .name("<value>")
                            .channel(AdGroupChannel.NATIVE_VIDEO)
                            .funnelLocation(AdGroupFunnelLocation.NONE)
                            .isEnabled(false)
                            .description("quash lightly rot bashfully slope")
                            .budget(AdGroupWorkflowBudgetInput.builder()
                                .allocationType(AllocationType.MINIMUM)
                                .budgetInAdvertiserCurrency(4043.98)
                                .budgetInImpressions(907414L)
                                .dailyTargetInAdvertiserCurrency(49.95)
                                .dailyTargetInImpressions(62363L)
                                .build())
                            .baseBidCPMInAdvertiserCurrency(1136.89)
                            .maxBidCPMInAdvertiserCurrency(6950.27)
                            .audienceTargeting(AdGroupWorkflowAudienceTargetingInput.builder()
                                .audienceId("<id>")
                                .audienceAcceleratorExclusionsEnabled(false)
                                .audienceBoosterEnabled(true)
                                .audienceExcluderEnabled(false)
                                .audiencePredictorEnabled(true)
                                .crossDeviceVendorListForAudience(List.of(
                                    458524,
                                    284141))
                                .recencyExclusionWindowInMinutes(982426)
                                .targetTrackableUsersEnabled(false)
                                .useMcIdAsPrimary(true)
                                .build())
                            .roiGoal(AdGroupWorkflowROIGoalInput.builder()
                                .maximizeReach(JsonNullable.of(null))
                                .maximizeLtvIncrementalReach(true)
                                .cpcInAdvertiserCurrency(8782.74)
                                .ctrInPercent(JsonNullable.of(null))
                                .nielsenOTPInPercent(7930.85)
                                .cpaInAdvertiserCurrency(4606.89)
                                .returnOnAdSpendPercent(2522.83)
                                .vcrInPercent(5828.49)
                                .viewabilityInPercent(6824.44)
                                .vcpmInAdvertiserCurrency(7123.95)
                                .cpcvInAdvertiserCurrency(6233.72)
                                .miaozhenOTPInPercent(8437.22)
                                .build())
                            .creativeIds(List.of(
                                "<value 1>"))
                            .associatedBidLists(List.of(
                                AdGroupWorkflowAssociateBidListInput.builder()
                                    .bidListId("<id>")
                                    .isEnabled(true)
                                    .isDefaultForDimension(false)
                                    .build()))
                            .programmaticGuaranteedPrivateContractId("<id>")
                            .build())
                        .advancedInput(CampaignCreateWorkflowAdGroupAdvancedInput.builder()
                            .koaOptimizationSettings(AdGroupWorkflowKoaOptimizationSettingsInput.builder()
                                .areFutureKoaFeaturesEnabled(true)
                                .predictiveClearingEnabled(true)
                                .build())
                            .comscoreSettings(AdGroupWorkflowComscoreSettingsInput.builder()
                                .isEnabled(false)
                                .populationId(523753)
                                .demographicMemberIds(JsonNullable.of(null))
                                .mobileDemographicMemberIds(JsonNullable.of(null))
                                .build())
                            .contractTargeting(AdGroupWorkflowContractTargetingInput.builder()
                                .allowOpenMarketBiddingWhenTargetingContracts(true)
                                .build())
                            .dimensionalBiddingAutoOptimizationSettings(List.of(
                                List.of(
                                    DimensionalBiddingDimensions.HAS_FULL_REFERRER_URL),
                                List.of(
                                    DimensionalBiddingDimensions.HAS_PUBLISHER_ID)))
                            .isUseClicksAsConversionsEnabled(JsonNullable.of(null))
                            .isUseSecondaryConversionsEnabled(true)
                            .nielsenTrackingAttributes(AdGroupWorkflowNielsenTrackingAttributesInput.builder()
                                .gender(TargetingGender.FEMALE)
                                .startAge(TargetingStartAge.THIRTY_FIVE)
                                .endAge(TargetingEndAge.FORTY_NINE)
                                .countries(List.of())
                                .enhancedReportingOption(EnhancedNielsenReportingOptions.SITE)
                                .build())
                            .newFrequencyConfigs(List.of(
                                AdGroupWorkflowNewFrequencyConfigInput.builder()
                                    .counterName("<value>")
                                    .frequencyCap(391231)
                                    .frequencyGoal(499235)
                                    .resetIntervalInMinutes(587736)
                                    .build()))
                            .flights(List.of(
                                CampaignCreateWorkflowAdGroupFlightInput.builder()
                                    .allocationType(AllocationType.FIXED)
                                    .budgetInAdvertiserCurrency(5340.32)
                                    .budgetInImpressions(492382L)
                                    .dailyTargetInAdvertiserCurrency(5622.5)
                                    .dailyTargetInImpressions(398919L)
                                    .build()))
                            .build())
                        .build()))
                .validateInputOnly(false)
                .build();

        CreateCampaignResponse res = sdk.campaign().create()
                .request(req)
                .call();

        if (res.campaignPayload().isPresent()) {
            // handle response
        }
    }
}
```

### Parameters

| Parameter                                                                                                     | Type                                                                                                          | Required                                                                                                      | Description                                                                                                   |
| ------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                     | [CampaignCreateWorkflowInputWithValidation](../../models/shared/CampaignCreateWorkflowInputWithValidation.md) | :heavy_check_mark:                                                                                            | The request object to use for the request.                                                                    |

### Response

**[CreateCampaignResponse](../../models/operations/CreateCampaignResponse.md)**

### Errors

| Error Type                            | Status Code                           | Content Type                          |
| ------------------------------------- | ------------------------------------- | ------------------------------------- |
| models/errors/ProblemDetailsException | 400, 403                              | application/json                      |
| models/errors/APIException            | 4XX, 5XX                              | \*/\*                                 |

## updateCampaign

Only the fields provided in the request payload will be updated.

### Example Usage

```java
package hello.world;

import com.thetradedesk.workflows.TtdWorkflows;
import com.thetradedesk.workflows.models.components.*;
import com.thetradedesk.workflows.models.errors.ProblemDetailsException;
import com.thetradedesk.workflows.models.operations.UpdateCampaignResponse;
import java.lang.Exception;
import java.time.OffsetDateTime;
import java.util.List;
import org.openapitools.jackson.nullable.JsonNullable;

public class Application {

    public static void main(String[] args) throws ProblemDetailsException, Exception {

        TtdWorkflows sdk = TtdWorkflows.builder()
                .ttdAuth("<YOUR_API_KEY_HERE>")
            .build();

        CampaignUpdateWorkflowInputWithValidation req = CampaignUpdateWorkflowInputWithValidation.builder()
                .id("<id>")
                .primaryInput(CampaignUpdateWorkflowPrimaryInput.builder()
                    .description("yahoo whether frail but into form sway neck notwithstanding")
                    .timeZone("Asia/Amman")
                    .customCPAClickWeight(1380.93)
                    .customCPAViewthroughWeight(3991.98)
                    .customCPAType(CustomCPAType.CLICK_VIEWTHROUGH_WEIGHTING)
                    .impressionsOnlyBudgetingCpm(126.57)
                    .budget(CampaignWorkflowBudgetInput.builder()
                        .pacingMode(CampaignPacingMode.PACE_AS_SOON_AS_POSSIBLE)
                        .budgetInAdvertiserCurrency(6974.82)
                        .budgetInImpressions(834352L)
                        .dailyTargetInAdvertiserCurrency(8583.49)
                        .dailyTargetInImpressions(746941L)
                        .build())
                    .endDateInUtc(OffsetDateTime.parse("2024-07-09T17:14:23.542Z"))
                    .seedId("<id>")
                    .campaignConversionReportingColumns(List.of(
                        CampaignWorkflowCampaignConversionReportingColumnInput.builder()
                            .trackingTagId("<id>")
                            .includeInCustomCPA(false)
                            .reportingColumnId(716444)
                            .roasConfig(CustomROASConfig.builder()
                                .includeInCustomROAS(true)
                                .customROASWeight(8307.9)
                                .customROASClickWeight(129.65)
                                .customROASViewthroughWeight(2890.82)
                                .build())
                            .weight(5187.48)
                            .crossDeviceAttributionModelId(JsonNullable.of(null))
                            .build()))
                    .name("<value>")
                    .primaryChannel(CampaignChannelType.DISPLAY)
                    .primaryGoal(CampaignWorkflowROIGoalInput.builder()
                        .maximizeReach(false)
                        .maximizeLtvIncrementalReach(true)
                        .cpcInAdvertiserCurrency(8835.54)
                        .ctrInPercent(4975.78)
                        .nielsenOTPInPercent(6033.78)
                        .cpaInAdvertiserCurrency(JsonNullable.of(null))
                        .returnOnAdSpendPercent(5696.08)
                        .vcrInPercent(8315.31)
                        .viewabilityInPercent(1059.68)
                        .vcpmInAdvertiserCurrency(4588.07)
                        .cpcvInAdvertiserCurrency(2202.71)
                        .miaozhenOTPInPercent(2682.12)
                        .build())
                    .startDateInUtc(OffsetDateTime.parse("2024-02-29T10:31:50.069Z"))
                    .build())
                .advancedInput(CampaignWorkflowAdvancedInput.builder()
                    .flights(List.of(
                        CampaignWorkflowFlightInput.builder()
                            .startDateInclusiveUTC(OffsetDateTime.parse("2025-11-09T04:11:39.432Z"))
                            .budgetInAdvertiserCurrency(6534.57)
                            .endDateExclusiveUTC(OffsetDateTime.parse("2025-09-10T20:38:51.701Z"))
                            .budgetInImpressions(865481L)
                            .dailyTargetInAdvertiserCurrency(1033.72)
                            .dailyTargetInImpressions(JsonNullable.of(null))
                            .build()))
                    .purchaseOrderNumber("<value>")
                    .build())
                .validateInputOnly(true)
                .build();

        UpdateCampaignResponse res = sdk.campaign().updateCampaign()
                .request(req)
                .call();

        if (res.campaignPayload().isPresent()) {
            // handle response
        }
    }
}
```

### Parameters

| Parameter                                                                                                     | Type                                                                                                          | Required                                                                                                      | Description                                                                                                   |
| ------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                     | [CampaignUpdateWorkflowInputWithValidation](../../models/shared/CampaignUpdateWorkflowInputWithValidation.md) | :heavy_check_mark:                                                                                            | The request object to use for the request.                                                                    |

### Response

**[UpdateCampaignResponse](../../models/operations/UpdateCampaignResponse.md)**

### Errors

| Error Type                            | Status Code                           | Content Type                          |
| ------------------------------------- | ------------------------------------- | ------------------------------------- |
| models/errors/ProblemDetailsException | 400                                   | application/json                      |
| models/errors/APIException            | 4XX, 5XX                              | \*/\*                                 |

## createCampaignsJob

Create multiple new campaigns with required fields

### Example Usage

```java
package hello.world;

import com.thetradedesk.workflows.TtdWorkflows;
import com.thetradedesk.workflows.models.components.*;
import com.thetradedesk.workflows.models.errors.ProblemDetailsException;
import com.thetradedesk.workflows.models.operations.CreateCampaignsJobResponse;
import java.lang.Exception;
import java.time.OffsetDateTime;
import java.util.List;
import java.util.Map;
import org.openapitools.jackson.nullable.JsonNullable;

public class Application {

    public static void main(String[] args) throws ProblemDetailsException, Exception {

        TtdWorkflows sdk = TtdWorkflows.builder()
                .ttdAuth("<YOUR_API_KEY_HERE>")
            .build();

        CampaignBulkCreateWorkflowInputWithValidation req = CampaignBulkCreateWorkflowInputWithValidation.builder()
                .input(List.of(
                    CampaignCreateWorkflowInput.builder()
                        .primaryInput(CampaignCreateWorkflowPrimaryInput.builder()
                            .advertiserId("<id>")
                            .name("<value>")
                            .primaryChannel(CampaignChannelType.NATIVE_VIDEO)
                            .primaryGoal(CampaignWorkflowROIGoalInput.builder()
                                .maximizeReach(false)
                                .maximizeLtvIncrementalReach(false)
                                .cpcInAdvertiserCurrency(25.32)
                                .ctrInPercent(4889.32)
                                .nielsenOTPInPercent(5258.8)
                                .cpaInAdvertiserCurrency(2553.01)
                                .returnOnAdSpendPercent(1142.91)
                                .vcrInPercent(1152.77)
                                .viewabilityInPercent(6711.38)
                                .vcpmInAdvertiserCurrency(4528.37)
                                .cpcvInAdvertiserCurrency(9833.69)
                                .miaozhenOTPInPercent(1951.58)
                                .build())
                            .description(JsonNullable.of(null))
                            .timeZone("America/North_Dakota/Center")
                            .customCPAClickWeight(9662.9)
                            .customCPAViewthroughWeight(3558.78)
                            .customCPAType(CustomCPAType.CLICK_VIEWTHROUGH_WEIGHTING)
                            .impressionsOnlyBudgetingCpm(4427.56)
                            .budget(CampaignWorkflowBudgetInput.builder()
                                .pacingMode(CampaignPacingMode.PACE_AHEAD)
                                .budgetInAdvertiserCurrency(5501.96)
                                .budgetInImpressions(629784L)
                                .dailyTargetInAdvertiserCurrency(2524.41)
                                .dailyTargetInImpressions(726807L)
                                .build())
                            .endDateInUtc(OffsetDateTime.parse("2023-12-21T01:12:20.772Z"))
                            .seedId("<id>")
                            .campaignConversionReportingColumns(List.of(
                                CampaignWorkflowCampaignConversionReportingColumnInput.builder()
                                    .trackingTagId("<id>")
                                    .includeInCustomCPA(false)
                                    .reportingColumnId(356532)
                                    .roasConfig(CustomROASConfig.builder()
                                        .includeInCustomROAS(false)
                                        .customROASWeight(1483.03)
                                        .customROASClickWeight(5286.76)
                                        .customROASViewthroughWeight(8906.82)
                                        .build())
                                    .weight(JsonNullable.of(null))
                                    .crossDeviceAttributionModelId("<id>")
                                    .build()))
                            .startDateInUtc(OffsetDateTime.parse("2025-09-26T21:06:42.946Z"))
                            .build())
                        .advancedInput(CampaignWorkflowAdvancedInput.builder()
                            .flights(List.of(
                                CampaignWorkflowFlightInput.builder()
                                    .startDateInclusiveUTC(OffsetDateTime.parse("2024-09-20T06:04:19.345Z"))
                                    .budgetInAdvertiserCurrency(8219.9)
                                    .endDateExclusiveUTC(OffsetDateTime.parse("2024-01-18T07:43:56.299Z"))
                                    .budgetInImpressions(76925L)
                                    .dailyTargetInAdvertiserCurrency(9309.03)
                                    .dailyTargetInImpressions(152838L)
                                    .build()))
                            .purchaseOrderNumber("<value>")
                            .build())
                        .adGroups(List.of(
                            CampaignCreateWorkflowAdGroupInput.builder()
                                .primaryInput(AdGroupCreateWorkflowPrimaryInput.builder()
                                    .name("<value>")
                                    .channel(AdGroupChannel.DISPLAY)
                                    .funnelLocation(AdGroupFunnelLocation.AWARENESS)
                                    .isEnabled(true)
                                    .description("scenario dish gracefully through tame yahoo pension husband as atop")
                                    .budget(AdGroupWorkflowBudgetInput.builder()
                                        .allocationType(AllocationType.MAXIMUM)
                                        .budgetInAdvertiserCurrency(2283.06)
                                        .budgetInImpressions(301691L)
                                        .dailyTargetInAdvertiserCurrency(9268.18)
                                        .dailyTargetInImpressions(851470L)
                                        .build())
                                    .baseBidCPMInAdvertiserCurrency(694.78)
                                    .maxBidCPMInAdvertiserCurrency(6084.4)
                                    .audienceTargeting(AdGroupWorkflowAudienceTargetingInput.builder()
                                        .audienceId("<id>")
                                        .audienceAcceleratorExclusionsEnabled(true)
                                        .audienceBoosterEnabled(false)
                                        .audienceExcluderEnabled(true)
                                        .audiencePredictorEnabled(false)
                                        .crossDeviceVendorListForAudience(List.of(
                                            497890,
                                            566253))
                                        .recencyExclusionWindowInMinutes(742665)
                                        .targetTrackableUsersEnabled(true)
                                        .useMcIdAsPrimary(true)
                                        .build())
                                    .roiGoal(AdGroupWorkflowROIGoalInput.builder()
                                        .maximizeReach(false)
                                        .maximizeLtvIncrementalReach(true)
                                        .cpcInAdvertiserCurrency(9062.02)
                                        .ctrInPercent(7192.99)
                                        .nielsenOTPInPercent(2823.22)
                                        .cpaInAdvertiserCurrency(3140.25)
                                        .returnOnAdSpendPercent(6857.21)
                                        .vcrInPercent(2704.73)
                                        .viewabilityInPercent(2247.4)
                                        .vcpmInAdvertiserCurrency(8383.69)
                                        .cpcvInAdvertiserCurrency(4755.8)
                                        .miaozhenOTPInPercent(4575.86)
                                        .build())
                                    .creativeIds(List.of(
                                        "<value 1>",
                                        "<value 2>"))
                                    .associatedBidLists(List.of(
                                        AdGroupWorkflowAssociateBidListInput.builder()
                                            .bidListId("<id>")
                                            .isEnabled(true)
                                            .isDefaultForDimension(false)
                                            .build()))
                                    .programmaticGuaranteedPrivateContractId("<id>")
                                    .build())
                                .advancedInput(CampaignCreateWorkflowAdGroupAdvancedInput.builder()
                                    .koaOptimizationSettings(AdGroupWorkflowKoaOptimizationSettingsInput.builder()
                                        .areFutureKoaFeaturesEnabled(true)
                                        .predictiveClearingEnabled(false)
                                        .build())
                                    .comscoreSettings(AdGroupWorkflowComscoreSettingsInput.builder()
                                        .isEnabled(false)
                                        .populationId(559587)
                                        .demographicMemberIds(List.of(
                                            139340,
                                            129935))
                                        .mobileDemographicMemberIds(JsonNullable.of(null))
                                        .build())
                                    .contractTargeting(AdGroupWorkflowContractTargetingInput.builder()
                                        .allowOpenMarketBiddingWhenTargetingContracts(true)
                                        .build())
                                    .dimensionalBiddingAutoOptimizationSettings(List.of(
                                        List.of(
                                            DimensionalBiddingDimensions.HAS_AUDIENCE_REACH_PERCENTAGE_TIER_ID),
                                        List.of()))
                                    .isUseClicksAsConversionsEnabled(false)
                                    .isUseSecondaryConversionsEnabled(true)
                                    .nielsenTrackingAttributes(AdGroupWorkflowNielsenTrackingAttributesInput.builder()
                                        .gender(TargetingGender.FEMALE)
                                        .startAge(TargetingStartAge.THIRTY_FIVE)
                                        .endAge(TargetingEndAge.TWENTY_FOUR)
                                        .countries(List.of(
                                            "<value 1>",
                                            "<value 2>"))
                                        .enhancedReportingOption(EnhancedNielsenReportingOptions.NONE)
                                        .build())
                                    .newFrequencyConfigs(JsonNullable.of(null))
                                    .flights(List.of(
                                        CampaignCreateWorkflowAdGroupFlightInput.builder()
                                            .allocationType(AllocationType.MAXIMUM)
                                            .budgetInAdvertiserCurrency(4838.47)
                                            .budgetInImpressions(420224L)
                                            .dailyTargetInAdvertiserCurrency(1513.78)
                                            .dailyTargetInImpressions(735500L)
                                            .build()))
                                    .build())
                                .build()))
                        .build()))
                .validateInputOnly(true)
                .callbackInput(WorkflowCallbackInput.builder()
                    .callbackUrl("https://impeccable-pick.com/")
                    .callbackHeaders(Map.ofEntries(
                        Map.entry("key", "<value>")))
                    .build())
                .build();

        CreateCampaignsJobResponse res = sdk.campaign().createCampaignsJob()
                .request(req)
                .call();

        if (res.typeBasedJobSubmitResponse().isPresent()) {
            // handle response
        }
    }
}
```

### Parameters

| Parameter                                                                                                             | Type                                                                                                                  | Required                                                                                                              | Description                                                                                                           |
| --------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                             | [CampaignBulkCreateWorkflowInputWithValidation](../../models/shared/CampaignBulkCreateWorkflowInputWithValidation.md) | :heavy_check_mark:                                                                                                    | The request object to use for the request.                                                                            |

### Response

**[CreateCampaignsJobResponse](../../models/operations/CreateCampaignsJobResponse.md)**

### Errors

| Error Type                            | Status Code                           | Content Type                          |
| ------------------------------------- | ------------------------------------- | ------------------------------------- |
| models/errors/ProblemDetailsException | 400, 403                              | application/json                      |
| models/errors/APIException            | 4XX, 5XX                              | \*/\*                                 |

## updateCampaignsJob

Only the fields provided in the request payload for each specific campaign will be updated.

### Example Usage

```java
package hello.world;

import com.thetradedesk.workflows.TtdWorkflows;
import com.thetradedesk.workflows.models.components.*;
import com.thetradedesk.workflows.models.errors.ProblemDetailsException;
import com.thetradedesk.workflows.models.operations.UpdateCampaignsJobResponse;
import java.lang.Exception;
import java.time.OffsetDateTime;
import java.util.List;
import java.util.Map;
import org.openapitools.jackson.nullable.JsonNullable;

public class Application {

    public static void main(String[] args) throws ProblemDetailsException, Exception {

        TtdWorkflows sdk = TtdWorkflows.builder()
                .ttdAuth("<YOUR_API_KEY_HERE>")
            .build();

        CampaignBulkUpdateWorkflowInputWithValidation req = CampaignBulkUpdateWorkflowInputWithValidation.builder()
                .input(List.of(
                    CampaignUpdateWorkflowInput.builder()
                        .id("<id>")
                        .primaryInput(CampaignUpdateWorkflowPrimaryInput.builder()
                            .description("hmph energetically yet surprisingly swift knight swear multicolored absent")
                            .timeZone("America/Argentina/San_Juan")
                            .customCPAClickWeight(JsonNullable.of(null))
                            .customCPAViewthroughWeight(8361.84)
                            .customCPAType(CustomCPAType.PIXEL_WEIGHTING)
                            .impressionsOnlyBudgetingCpm(2706.4)
                            .budget(CampaignWorkflowBudgetInput.builder()
                                .pacingMode(CampaignPacingMode.PACE_AS_SOON_AS_POSSIBLE)
                                .budgetInAdvertiserCurrency(2564.89)
                                .budgetInImpressions(659726L)
                                .dailyTargetInAdvertiserCurrency(6514.48)
                                .dailyTargetInImpressions(892097L)
                                .build())
                            .endDateInUtc(OffsetDateTime.parse("2023-11-11T21:39:56.025Z"))
                            .seedId("<id>")
                            .campaignConversionReportingColumns(List.of(
                                CampaignWorkflowCampaignConversionReportingColumnInput.builder()
                                    .trackingTagId("<id>")
                                    .includeInCustomCPA(true)
                                    .reportingColumnId(809247)
                                    .roasConfig(CustomROASConfig.builder()
                                        .includeInCustomROAS(false)
                                        .customROASWeight(JsonNullable.of(null))
                                        .customROASClickWeight(JsonNullable.of(null))
                                        .customROASViewthroughWeight(6784.9)
                                        .build())
                                    .weight(2260.69)
                                    .crossDeviceAttributionModelId("<id>")
                                    .build()))
                            .name("<value>")
                            .primaryChannel(CampaignChannelType.NONE)
                            .primaryGoal(CampaignWorkflowROIGoalInput.builder()
                                .maximizeReach(true)
                                .maximizeLtvIncrementalReach(false)
                                .cpcInAdvertiserCurrency(3354.68)
                                .ctrInPercent(7716.49)
                                .nielsenOTPInPercent(JsonNullable.of(null))
                                .cpaInAdvertiserCurrency(381.7)
                                .returnOnAdSpendPercent(8461.44)
                                .vcrInPercent(4170.61)
                                .viewabilityInPercent(5364.85)
                                .vcpmInAdvertiserCurrency(1107.08)
                                .cpcvInAdvertiserCurrency(JsonNullable.of(null))
                                .miaozhenOTPInPercent(4584.96)
                                .build())
                            .startDateInUtc(OffsetDateTime.parse("2023-01-13T23:06:05.083Z"))
                            .build())
                        .advancedInput(CampaignWorkflowAdvancedInput.builder()
                            .flights(List.of(
                                CampaignWorkflowFlightInput.builder()
                                    .startDateInclusiveUTC(OffsetDateTime.parse("2023-08-14T13:47:31.198Z"))
                                    .budgetInAdvertiserCurrency(1874.95)
                                    .endDateExclusiveUTC(OffsetDateTime.parse("2024-07-07T14:46:57.378Z"))
                                    .budgetInImpressions(207094L)
                                    .dailyTargetInAdvertiserCurrency(7255.71)
                                    .dailyTargetInImpressions(760981L)
                                    .build()))
                            .purchaseOrderNumber("<value>")
                            .build())
                        .build()))
                .validateInputOnly(true)
                .callbackInput(WorkflowCallbackInput.builder()
                    .callbackUrl("https://soggy-apparatus.org/")
                    .callbackHeaders(Map.ofEntries(
                        Map.entry("key", "<value>"),
                        Map.entry("key1", "<value>"),
                        Map.entry("key2", "<value>")))
                    .build())
                .build();

        UpdateCampaignsJobResponse res = sdk.campaign().updateCampaignsJob()
                .request(req)
                .call();

        if (res.typeBasedJobSubmitResponse().isPresent()) {
            // handle response
        }
    }
}
```

### Parameters

| Parameter                                                                                                             | Type                                                                                                                  | Required                                                                                                              | Description                                                                                                           |
| --------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                             | [CampaignBulkUpdateWorkflowInputWithValidation](../../models/shared/CampaignBulkUpdateWorkflowInputWithValidation.md) | :heavy_check_mark:                                                                                                    | The request object to use for the request.                                                                            |

### Response

**[UpdateCampaignsJobResponse](../../models/operations/UpdateCampaignsJobResponse.md)**

### Errors

| Error Type                            | Status Code                           | Content Type                          |
| ------------------------------------- | ------------------------------------- | ------------------------------------- |
| models/errors/ProblemDetailsException | 400, 403                              | application/json                      |
| models/errors/APIException            | 4XX, 5XX                              | \*/\*                                 |

## archiveCampaigns

**NOTE**: Once archived, campaigns cannot be un-archived.

### Example Usage

```java
package hello.world;

import com.thetradedesk.workflows.TtdWorkflows;
import com.thetradedesk.workflows.models.errors.ProblemDetailsException;
import com.thetradedesk.workflows.models.operations.ArchiveCampaignsResponse;
import java.lang.Exception;
import java.util.List;

public class Application {

    public static void main(String[] args) throws ProblemDetailsException, Exception {

        TtdWorkflows sdk = TtdWorkflows.builder()
                .ttdAuth("<YOUR_API_KEY_HERE>")
            .build();

        ArchiveCampaignsResponse res = sdk.campaign().archiveCampaigns()
                .forceArchive(false)
                .requestBody(List.of(
                    "<value 1>",
                    "<value 2>",
                    "<value 3>"))
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

**[ArchiveCampaignsResponse](../../models/operations/ArchiveCampaignsResponse.md)**

### Errors

| Error Type                            | Status Code                           | Content Type                          |
| ------------------------------------- | ------------------------------------- | ------------------------------------- |
| models/errors/ProblemDetailsException | 400, 403                              | application/json                      |
| models/errors/APIException            | 4XX, 5XX                              | \*/\*                                 |

## getVersion

Get a campaign's version

### Example Usage

```java
package hello.world;

import com.thetradedesk.workflows.TtdWorkflows;
import com.thetradedesk.workflows.models.errors.ProblemDetailsException;
import com.thetradedesk.workflows.models.operations.GetCampaignVersionResponse;
import java.lang.Exception;

public class Application {

    public static void main(String[] args) throws ProblemDetailsException, Exception {

        TtdWorkflows sdk = TtdWorkflows.builder()
                .ttdAuth("<YOUR_API_KEY_HERE>")
            .build();

        GetCampaignVersionResponse res = sdk.campaign().getVersion()
                .id("<id>")
                .call();

        if (res.campaignVersionWorkflow().isPresent()) {
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

**[GetCampaignVersionResponse](../../models/operations/GetCampaignVersionResponse.md)**

### Errors

| Error Type                            | Status Code                           | Content Type                          |
| ------------------------------------- | ------------------------------------- | ------------------------------------- |
| models/errors/ProblemDetailsException | 400, 401, 403, 404                    | application/json                      |
| models/errors/APIException            | 4XX, 5XX                              | \*/\*                                 |