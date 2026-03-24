---
title: Test page 23
deprecated: false
hidden: false
metadata:
  robots: index
---
## get_warrant_filter Warrant Filter

`value QuoteClient::get_warrant_filter(const utility::string_t symbol, int page, int page_size, utility::string_t sort_field_name, utility::string_t sort_dir, value filter_params)`

**Description**

Get warrants and CBBCs (Callable Bull/Bear Contracts) quote list data, supporting sorting by different fields and filtering warrants.

**Parameters**

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| symbol | utility::string_t | Yes | Underlying stock symbol |
| page | int | No | Page number, starting from 0, default 0 |
| page_size | int | No | Items per page, default 50 |
| sort_field_name | utility::string_t | No | Sort field, default expireDate (refer to fields in the return object) |
| sort_dir | utility::string_t | No | Sort order, U("ASC") or U("DESC"), default ASC |
| filter_params | value | No | Filter parameters JSON object, default value::null() |

**filter_params Filter Parameters**

| Field | Type | Description |
| --- | --- | --- |
| issuer_name | string | Issuer (refer to issuerName field in bounds of the return), default all |
| expire_ym | string | Expiry date, format yyyy-MM |
| state | int | Status: 0 All, 1 Normal, 2 Terminated, 3 Waiting to be listed, default 0 |
| warrant_type | array\[int\] | Type (1: Call, 2: Put, 3: Bull, 4: Bear, 0: All), default all |
| in_out_price | array\[int\] | 1: In-the-money (including at-the-money), -1: Out-of-the-money |
| lot_size | array\[int\] | Shares per lot |
| entitlement_ratio | array\[double\] | Entitlement ratio |
| strike_min | double | Minimum strike price |
| strike_max | double | Maximum strike price |
| effective_leverage_min | double | Minimum effective leverage |
| effective_leverage_max | double | Maximum effective leverage |
| leverage_ratio_min | double | Minimum leverage ratio |
| leverage_ratio_max | double | Maximum leverage ratio |
| call_price_min | double | Minimum call price |
| call_price_max | double | Maximum call price |
| volume_min | int | Minimum volume |
| volume_max | int | Maximum volume |
| premium_min | double | Minimum premium |
| premium_max | double | Maximum premium |
| outstanding_ratio_min | double | Minimum outstanding ratio |
| outstanding_ratio_max | double | Maximum outstanding ratio |
| implied_volatility_min | double | Minimum implied volatility |
| implied_volatility_max | double | Maximum implied volatility |

**Return**

`web::json::value` JSON object

Return field descriptions:

| Name | Type | Description |
| --- | --- | --- |
| page | int | Page number |
| totalPage | int | Total pages |
| totalCount | int | Total data count |
| bounds | object | Available filter conditions for the request, see below |
| items | array | Warrant data list, fields described below |

bounds object structure:

| Name | Type | Description |
| --- | --- | --- |
| issuer_name | array\[string\] | Issuer names |
| expire_date | array\[string\] | Expiry dates |
| lot_size | array\[int\] | Shares per lot |
| entitlement_ratio | array\[double\] | Entitlement ratios |
| leverage_ratio | object | Leverage ratio range |
| strike | object | Strike price range |
| premium | object | Premium range |
| outstanding_ratio | object | Outstanding ratio range |
| implied_volatility | object | Implied volatility range |
| effective_leverage | object | Effective leverage range |
| call_price | object | Call price range |

items array element field descriptions:

| Name | Type | Description |
| --- | --- | --- |
| symbol | string | Symbol code |
| name | string | Name |
| type | int | Type: 1 Call, 2 Put, 3 Bull, 4 Bear |
| sec_type | string | Security type, warrant: war / CBBC: iopt |
| market | string | Market, hk |
| entitlement_ratio | double | Entitlement ratio |
| entitlement_price | double | Entitlement price |
| premium | double | Premium |
| breakeven_point | double | Breakeven point at expiry |
| call_price | double | Call price (CBBCs only) |
| before_call_level | double | Distance to call price (percentage, e.g., 0.196875 means 19.6875%) |
| expire_date | string | Expiry date |
| last_trading_date | string | Last trading date |
| state | int | Status: 1 Normal, 2 Terminated, 3 Waiting to be listed |
| change_rate | double | Change rate |
| change | double | Price change |
| latest_price | double | Latest price |
| volume | long | Volume |
| outstanding_ratio | double | Outstanding ratio |
| lot_size | int | Shares per lot |
| strike | double | Strike price |
| in_out_price | double | In-the-money (`>0`) / Out-of-the-money (`<0`) |
| delta | double | Delta |
| leverage_ratio | double | Leverage ratio |
| effective_leverage | double | Effective leverage |
| implied_volatility | double | Implied volatility |

**Example**

```cpp
#include "tigerapi/quote_client.h"
#include "tigerapi/client_config.h"

using namespace TIGER_API;

ClientConfig config(false, U("/path/to/your/properties/"));
QuoteClient quote_client(config);

// Build filter parameters
value filter_params = value::object();
filter_params[U("issuer_name")] = value::string(U("ML"));
filter_params[U("expire_ym")] = value::string(U("2024-06"));
// 0 All, 1 Normal, 2 Terminate Trades, 3 Waiting to be listed
filter_params[U("state")] = value::number(1);

value lot_size_arr = value::array();
lot_size_arr[0] = value::number(1000);
lot_size_arr[1] = value::number(5000);
filter_params[U("lot_size")] = lot_size_arr;

// -1: out the money, 1: in the money
value in_out_price_arr = value::array();
in_out_price_arr[0] = value::number(1);
in_out_price_arr[1] = value::number(-1);
filter_params[U("in_out_price")] = in_out_price_arr;

// 1: Call, 2: Put, 3: Bull, 4: Bear, 0: All
value warrant_type_arr = value::array();
warrant_type_arr[0] = value::number(2);
warrant_type_arr[1] = value::number(4);
filter_params[U("warrant_type")] = warrant_type_arr;

filter_params[U("premium_min")] = value::number(0.0);
filter_params[U("premium_max")] = value::number(1.0);
filter_params[U("strike_min")] = value::number(100.0);
filter_params[U("strike_max")] = value::number(500.0);
filter_params[U("implied_volatility_min")] = value::number(1.0);
filter_params[U("implied_volatility_max")] = value::number(100.0);

value result = quote_client.get_warrant_filter(
    U("00700"), 0, 10,
    U("implied_volatility"), U("DESC"),
    filter_params);
ucout << result.serialize() << std::endl;
```

***

## get_warrant_briefs Get Warrant Quotes

`value QuoteClient::get_warrant_briefs(const value &symbols)`

**Description**

Get real-time warrant and CBBC quotes

**Parameters**

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| symbols | value | Yes | Warrant symbol code array, max 50, e.g., `value::array({value::string(U("15792"))})` |

**Return**

`web::json::value` JSON object

Return field descriptions:

| Field | Type | Description |
| --- | --- | --- |
| symbol | string | Symbol code |
| name | string | Name |
| exchange | string | Exchange |
| market | string | Market |
| sec_type | string | Security type |
| currency | string | Currency |
| expiry | string | Expiry date yyyy-mm-dd |
| strike | string | Strike price |
| right | string | Direction (put/call) |
| multiplier | double | Lot size |
| last_trading_date | long | Last trading date timestamp |
| entitlement_ratio | double | Entitlement ratio |
| entitlement_price | double | Entitlement price |
| min_tick | double | Minimum tick size |
| listing_date | long | Listing date timestamp |
| call_price | double | Call price (CBBCs only) |
| halted | int | Whether halted. 0: Normal, 3: Halted, 4: Delisted |
| underlying_symbol | string | Underlying asset symbol |
| timestamp | long | Timestamp |
| latest_price | double | Latest price |
| pre_close | double | Previous close price |
| open | double | Open price |
| high | double | High price |
| low | double | Low price |
| volume | int | Volume |
| amount | double | Turnover |
| premium | double | Premium |
| outstanding_ratio | double | Outstanding ratio |
| implied_volatility | double | Implied volatility (warrants only) |
| in_out_price | double | In/out of the money |
| delta | double | Delta (warrants only) |
| leverage_ratio | double | Leverage ratio |
| breakeven_point | double | Breakeven point at expiry |

**Example**

```cpp
#include "tigerapi/quote_client.h"
#include "tigerapi/client_config.h"

using namespace TIGER_API;

ClientConfig config(false, U("/path/to/your/properties/"));
QuoteClient quote_client(config);

value symbols = value::array();
symbols[0] = value::string(U("15792"));
symbols[1] = value::string(U("58603"));

value result = quote_client.get_warrant_briefs(symbols);
ucout << result.serialize() << std::endl;
```