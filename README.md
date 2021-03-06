# elepay-java-sdk

elepay API リファレンス

- API version: 1.1.4

elepay APIはRESTをベースに構成された決済APIです。支払い処理、返金処理など、決済に関わる運用における様々なことができます。

  For more information, please visit [https://elepay.io](https://elepay.io)

*Automatically generated by the [OpenAPI Generator](https://openapi-generator.tech)*

## Requirements

Building the API client library requires:

1. Java 1.8+
2. Maven/Gradle

## Installation

To install the API client library to your local Maven repository, simply execute:

```shell
mvn clean install
```

To deploy it to a remote Maven repository instead, configure the settings of the repository and execute:

```shell
mvn clean deploy
```

Refer to the [OSSRH Guide](http://central.sonatype.org/pages/ossrh-guide.html) for more information.

### Maven users

Add this dependency to your project's POM:

```xml
<dependency>
  <groupId>io.elepay</groupId>
  <artifactId>elepay-java-sdk</artifactId>
  <version>1.1.4</version>
  <scope>compile</scope>
</dependency>
```

### Gradle users

Add this dependency to your project's build file:

```groovy
compile "io.elepay:elepay-java-sdk:1.1.4"
```

### Others

At first generate the JAR by executing:

```shell
mvn clean package
```

Then manually install the following JARs:

- `target/elepay-java-sdk-1.1.4.jar`
- `target/lib/*.jar`

## Getting Started

Please follow the [installation](#installation) instruction and execute the following Java code:

```java

import io.elepay.client.charge.*;
import io.elepay.client.charge.auth.*;
import io.elepay.client.charge.pojo.*;
import io.elepay.client.charge.api.ChargeApi;

public class ChargeApiExample {

    public static void main(String[] args) {
        ChargeApi apiInstance = new ChargeApi();
        apiInstance.getApiClient().setUsername("elepay secret key");

        ChargeReq chargeReq = new ChargeReq(); // ChargeReq | 支払リクエスト
        chargeReq.setAmount(100);
        chargeReq.setPaymentMethod(PaymentMethodType.CREDITCARD);
        chargeReq.setResource(ResourceType.WEB);
        chargeReq.setOrderNo("ORD0000000001");
        try {
            ChargeDto result = apiInstance.createCharge(chargeReq);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling ChargeApi#createCharge");
            System.err.println("Status code: " + e.getCode());
            System.err.println("Reason: " + e.getResponseBody());
            System.err.println("Response headers: " + e.getResponseHeaders());
            e.printStackTrace();
        }
    }
}

```

## Documentation for API Endpoints

All URIs are relative to *https://api.elepay.io*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*ChargeApi* | [**createCharge**](docs/ChargeApi.md#createCharge) | **POST** /charges | Create charge
*ChargeApi* | [**listCharges**](docs/ChargeApi.md#listCharges) | **GET** /charges | List charges
*ChargeApi* | [**retrieveCharge**](docs/ChargeApi.md#retrieveCharge) | **GET** /charges/{id} | Retrieve charge
*CustomerApi* | [**createCustomer**](docs/CustomerApi.md#createCustomer) | **POST** /customers | Create customer
*CustomerApi* | [**createSource**](docs/CustomerApi.md#createSource) | **POST** /customers/{customerId}/sources | Create source
*CustomerApi* | [**deleteCustomer**](docs/CustomerApi.md#deleteCustomer) | **DELETE** /customers/{customerId} | Delete customer
*CustomerApi* | [**deleteSource**](docs/CustomerApi.md#deleteSource) | **DELETE** /customers/{customerId}/sources/{sourceId} | Delete source
*CustomerApi* | [**listCustomers**](docs/CustomerApi.md#listCustomers) | **GET** /customers | List customers
*CustomerApi* | [**listSources**](docs/CustomerApi.md#listSources) | **GET** /customers/{customerId}/sources | List sources by customer ID
*CustomerApi* | [**retrieveCustomer**](docs/CustomerApi.md#retrieveCustomer) | **GET** /customers/{customerId} | Retrieve customer
*CustomerApi* | [**retrieveSource**](docs/CustomerApi.md#retrieveSource) | **GET** /customers/{customerId}/sources/{sourceId} | Retrieve source
*PaymentMethodApi* | [**listPaymentMethods**](docs/PaymentMethodApi.md#listPaymentMethods) | **GET** /payment-methods | List supported payment methods
*RefundApi* | [**createRefund**](docs/RefundApi.md#createRefund) | **POST** /charges/{id}/refunds | Create refund
*RefundApi* | [**listChargesRefunds**](docs/RefundApi.md#listChargesRefunds) | **GET** /charges/{id}/refunds | List refunds
*RefundApi* | [**retrieveChargeRefund**](docs/RefundApi.md#retrieveChargeRefund) | **GET** /charges/{id}/refunds/{refundId} | Retrieve refund


## Documentation for Models

 - [ChargeDateTimeType](docs/ChargeDateTimeType.md)
 - [ChargeDto](docs/ChargeDto.md)
 - [ChargeReq](docs/ChargeReq.md)
 - [ChargeStatusType](docs/ChargeStatusType.md)
 - [ChargesResponse](docs/ChargesResponse.md)
 - [CustomerDto](docs/CustomerDto.md)
 - [CustomerReq](docs/CustomerReq.md)
 - [CustomerResponse](docs/CustomerResponse.md)
 - [PaymentMethodDto](docs/PaymentMethodDto.md)
 - [PaymentMethodResponse](docs/PaymentMethodResponse.md)
 - [PaymentMethodType](docs/PaymentMethodType.md)
 - [RefundDto](docs/RefundDto.md)
 - [RefundReq](docs/RefundReq.md)
 - [RefundStatusType](docs/RefundStatusType.md)
 - [RefundsDto](docs/RefundsDto.md)
 - [RefundsResponse](docs/RefundsResponse.md)
 - [ResourceType](docs/ResourceType.md)
 - [SortOrderType](docs/SortOrderType.md)
 - [SourceDto](docs/SourceDto.md)
 - [SourceReq](docs/SourceReq.md)
 - [SourceResponse](docs/SourceResponse.md)
 - [SourceStatusType](docs/SourceStatusType.md)


## Documentation for Authorization

Authentication schemes defined for the API:
### basicAuth


- **Type**: HTTP basic authentication


## Recommendation

It's recommended to create an instance of `ApiClient` per thread in a multithreaded environment to avoid any potential issues.

## Author

support@elestyle.jp

