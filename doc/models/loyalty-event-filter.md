## Loyalty Event Filter

The filtering criteria. If the request specifies multiple filters, 
the endpoint uses a logical AND to evaluate them.

### Structure

`LoyaltyEventFilter`

### Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `LoyaltyAccountFilter` | [`LoyaltyEventLoyaltyAccountFilter`](/doc/models/loyalty-event-loyalty-account-filter.md) | Optional | Filter events by loyalty account. |
| `TypeFilter` | [`LoyaltyEventTypeFilter`](/doc/models/loyalty-event-type-filter.md) | Optional | Filter events by event type. |
| `DateTimeFilter` | [`LoyaltyEventDateTimeFilter`](/doc/models/loyalty-event-date-time-filter.md) | Optional | Filter events by date time range. |
| `LocationFilter` | [`LoyaltyEventLocationFilter`](/doc/models/loyalty-event-location-filter.md) | Optional | Filter events by location. |
| `OrderFilter` | [`LoyaltyEventOrderFilter`](/doc/models/loyalty-event-order-filter.md) | Optional | Filter events by the order associated with the event. |

### Example (as JSON)

```json
{
  "loyalty_account_filter": null,
  "type_filter": null,
  "date_time_filter": null,
  "location_filter": null,
  "order_filter": null
}
```
