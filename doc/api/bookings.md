# Bookings

```java
BookingsApi bookingsApi = client.getBookingsApi();
```

## Class Name

`BookingsApi`

## Methods

* [Create Booking](/doc/api/bookings.md#create-booking)
* [Search Availability](/doc/api/bookings.md#search-availability)
* [Retrieve Business Booking Profile](/doc/api/bookings.md#retrieve-business-booking-profile)
* [List Team Member Booking Profiles](/doc/api/bookings.md#list-team-member-booking-profiles)
* [Retrieve Team Member Booking Profile](/doc/api/bookings.md#retrieve-team-member-booking-profile)
* [Retrieve Booking](/doc/api/bookings.md#retrieve-booking)
* [Update Booking](/doc/api/bookings.md#update-booking)
* [Cancel Booking](/doc/api/bookings.md#cancel-booking)


# Create Booking

Creates a booking.

```java
CompletableFuture<CreateBookingResponse> createBookingAsync(
    final CreateBookingRequest body)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CreateBookingRequest`](/doc/models/create-booking-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Response Type

[`CreateBookingResponse`](/doc/models/create-booking-response.md)

## Example Usage

```java
Booking bodyBooking = new Booking.Builder()
    .id("id8")
    .version(148)
    .status("ACCEPTED")
    .createdAt("created_at6")
    .updatedAt("updated_at4")
    .build();
CreateBookingRequest body = new CreateBookingRequest.Builder(
        bodyBooking)
    .idempotencyKey("idempotency_key2")
    .build();

bookingsApi.createBookingAsync(body).thenAccept(result -> {
    // TODO success callback handler
}).exceptionally(exception -> {
    // TODO failure callback handler
    return null;
});
```


# Search Availability

Searches for availabilities for booking.

```java
CompletableFuture<SearchAvailabilityResponse> searchAvailabilityAsync(
    final SearchAvailabilityRequest body)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`SearchAvailabilityRequest`](/doc/models/search-availability-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Response Type

[`SearchAvailabilityResponse`](/doc/models/search-availability-response.md)

## Example Usage

```java
TimeRange bodyQueryFilterStartAtRange = new TimeRange.Builder()
    .startAt("start_at8")
    .endAt("end_at4")
    .build();
List<SegmentFilter> bodyQueryFilterSegmentFilters = new LinkedList<>();

List<String> bodyQueryFilterSegmentFilters0TeamMemberIdFilterAll = new LinkedList<>();
bodyQueryFilterSegmentFilters0TeamMemberIdFilterAll.add("all7");
List<String> bodyQueryFilterSegmentFilters0TeamMemberIdFilterAny = new LinkedList<>();
bodyQueryFilterSegmentFilters0TeamMemberIdFilterAny.add("any0");
bodyQueryFilterSegmentFilters0TeamMemberIdFilterAny.add("any1");
List<String> bodyQueryFilterSegmentFilters0TeamMemberIdFilterNone = new LinkedList<>();
bodyQueryFilterSegmentFilters0TeamMemberIdFilterNone.add("none5");
FilterValue bodyQueryFilterSegmentFilters0TeamMemberIdFilter = new FilterValue.Builder()
    .all(bodyQueryFilterSegmentFilters0TeamMemberIdFilterAll)
    .any(bodyQueryFilterSegmentFilters0TeamMemberIdFilterAny)
    .none(bodyQueryFilterSegmentFilters0TeamMemberIdFilterNone)
    .build();
SegmentFilter bodyQueryFilterSegmentFilters0 = new SegmentFilter.Builder(
        "service_variation_id8")
    .teamMemberIdFilter(bodyQueryFilterSegmentFilters0TeamMemberIdFilter)
    .build();
bodyQueryFilterSegmentFilters.add(bodyQueryFilterSegmentFilters0);

List<String> bodyQueryFilterSegmentFilters1TeamMemberIdFilterAll = new LinkedList<>();
bodyQueryFilterSegmentFilters1TeamMemberIdFilterAll.add("all6");
bodyQueryFilterSegmentFilters1TeamMemberIdFilterAll.add("all7");
bodyQueryFilterSegmentFilters1TeamMemberIdFilterAll.add("all8");
List<String> bodyQueryFilterSegmentFilters1TeamMemberIdFilterAny = new LinkedList<>();
bodyQueryFilterSegmentFilters1TeamMemberIdFilterAny.add("any1");
bodyQueryFilterSegmentFilters1TeamMemberIdFilterAny.add("any2");
bodyQueryFilterSegmentFilters1TeamMemberIdFilterAny.add("any3");
List<String> bodyQueryFilterSegmentFilters1TeamMemberIdFilterNone = new LinkedList<>();
bodyQueryFilterSegmentFilters1TeamMemberIdFilterNone.add("none6");
bodyQueryFilterSegmentFilters1TeamMemberIdFilterNone.add("none7");
FilterValue bodyQueryFilterSegmentFilters1TeamMemberIdFilter = new FilterValue.Builder()
    .all(bodyQueryFilterSegmentFilters1TeamMemberIdFilterAll)
    .any(bodyQueryFilterSegmentFilters1TeamMemberIdFilterAny)
    .none(bodyQueryFilterSegmentFilters1TeamMemberIdFilterNone)
    .build();
SegmentFilter bodyQueryFilterSegmentFilters1 = new SegmentFilter.Builder(
        "service_variation_id7")
    .teamMemberIdFilter(bodyQueryFilterSegmentFilters1TeamMemberIdFilter)
    .build();
bodyQueryFilterSegmentFilters.add(bodyQueryFilterSegmentFilters1);

SearchAvailabilityFilter bodyQueryFilter = new SearchAvailabilityFilter.Builder(
        bodyQueryFilterStartAtRange)
    .locationId("location_id6")
    .segmentFilters(bodyQueryFilterSegmentFilters)
    .bookingId("booking_id6")
    .build();
SearchAvailabilityQuery bodyQuery = new SearchAvailabilityQuery.Builder(
        bodyQueryFilter)
    .build();
SearchAvailabilityRequest body = new SearchAvailabilityRequest.Builder(
        bodyQuery)
    .build();

bookingsApi.searchAvailabilityAsync(body).thenAccept(result -> {
    // TODO success callback handler
}).exceptionally(exception -> {
    // TODO failure callback handler
    return null;
});
```


# Retrieve Business Booking Profile

Retrieves a seller's booking profile.

```java
CompletableFuture<RetrieveBusinessBookingProfileResponse> retrieveBusinessBookingProfileAsync()
```

## Response Type

[`RetrieveBusinessBookingProfileResponse`](/doc/models/retrieve-business-booking-profile-response.md)

## Example Usage

```java
bookingsApi.retrieveBusinessBookingProfileAsync().thenAccept(result -> {
    // TODO success callback handler
}).exceptionally(exception -> {
    // TODO failure callback handler
    return null;
});
```


# List Team Member Booking Profiles

Lists booking profiles for team members.

```java
CompletableFuture<ListTeamMemberBookingProfilesResponse> listTeamMemberBookingProfilesAsync(
    final Boolean bookableOnly,
    final Integer limit,
    final String cursor,
    final String locationId)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `bookableOnly` | `Boolean` | Query, Optional | Indicates whether to include only bookable team members in the returned result (`true`) or not (`false`).<br>**Default**: `false` |
| `limit` | `Integer` | Query, Optional | The maximum number of results to return. |
| `cursor` | `String` | Query, Optional | The cursor for paginating through the results. |
| `locationId` | `String` | Query, Optional | Indicates whether to include only team members enabled at the given location in the returned result. |

## Response Type

[`ListTeamMemberBookingProfilesResponse`](/doc/models/list-team-member-booking-profiles-response.md)

## Example Usage

```java
Boolean bookableOnly = false;
Integer limit = 172;
String cursor = "cursor6";
String locationId = "location_id4";

bookingsApi.listTeamMemberBookingProfilesAsync(bookableOnly, limit, cursor, locationId).thenAccept(result -> {
    // TODO success callback handler
}).exceptionally(exception -> {
    // TODO failure callback handler
    return null;
});
```


# Retrieve Team Member Booking Profile

Retrieves a team member's booking profile.

```java
CompletableFuture<RetrieveTeamMemberBookingProfileResponse> retrieveTeamMemberBookingProfileAsync(
    final String teamMemberId)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `teamMemberId` | `String` | Template, Required | The ID of the team member to retrieve. |

## Response Type

[`RetrieveTeamMemberBookingProfileResponse`](/doc/models/retrieve-team-member-booking-profile-response.md)

## Example Usage

```java
String teamMemberId = "team_member_id0";

bookingsApi.retrieveTeamMemberBookingProfileAsync(teamMemberId).thenAccept(result -> {
    // TODO success callback handler
}).exceptionally(exception -> {
    // TODO failure callback handler
    return null;
});
```


# Retrieve Booking

Retrieves a booking.

```java
CompletableFuture<RetrieveBookingResponse> retrieveBookingAsync(
    final String bookingId)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `bookingId` | `String` | Template, Required | The ID of the [Booking](#type-booking) object representing the to-be-retrieved booking. |

## Response Type

[`RetrieveBookingResponse`](/doc/models/retrieve-booking-response.md)

## Example Usage

```java
String bookingId = "booking_id4";

bookingsApi.retrieveBookingAsync(bookingId).thenAccept(result -> {
    // TODO success callback handler
}).exceptionally(exception -> {
    // TODO failure callback handler
    return null;
});
```


# Update Booking

Updates a booking.

```java
CompletableFuture<UpdateBookingResponse> updateBookingAsync(
    final String bookingId,
    final UpdateBookingRequest body)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `bookingId` | `String` | Template, Required | The ID of the [Booking](#type-booking) object representing the to-be-updated booking. |
| `body` | [`UpdateBookingRequest`](/doc/models/update-booking-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Response Type

[`UpdateBookingResponse`](/doc/models/update-booking-response.md)

## Example Usage

```java
String bookingId = "booking_id4";
Booking bodyBooking = new Booking.Builder()
    .id("id8")
    .version(148)
    .status("ACCEPTED")
    .createdAt("created_at6")
    .updatedAt("updated_at4")
    .build();
UpdateBookingRequest body = new UpdateBookingRequest.Builder(
        bodyBooking)
    .idempotencyKey("idempotency_key2")
    .build();

bookingsApi.updateBookingAsync(bookingId, body).thenAccept(result -> {
    // TODO success callback handler
}).exceptionally(exception -> {
    // TODO failure callback handler
    return null;
});
```


# Cancel Booking

Cancels an existing booking.

```java
CompletableFuture<CancelBookingResponse> cancelBookingAsync(
    final String bookingId,
    final CancelBookingRequest body)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `bookingId` | `String` | Template, Required | The ID of the [Booking](#type-booking) object representing the to-be-cancelled booking. |
| `body` | [`CancelBookingRequest`](/doc/models/cancel-booking-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Response Type

[`CancelBookingResponse`](/doc/models/cancel-booking-response.md)

## Example Usage

```java
String bookingId = "booking_id4";
CancelBookingRequest body = new CancelBookingRequest.Builder()
    .idempotencyKey("idempotency_key2")
    .bookingVersion(8)
    .build();

bookingsApi.cancelBookingAsync(bookingId, body).thenAccept(result -> {
    // TODO success callback handler
}).exceptionally(exception -> {
    // TODO failure callback handler
    return null;
});
```

