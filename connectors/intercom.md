# Intercom

This page guides you through the process of setting up the Intercom connector.

## Requirements

We would need an [Access Token](https://developers.intercom.com/building-apps/docs/authentication-types#section-how-to-get-your-access-token) to authenticate your account.


## Set up the Intercom connector 

Our team will support you with that.

## Supported Streams

The Intercom source connector supports the following streams:

* [Admins](https://developers.intercom.com/intercom-api-reference/reference#list-admins) \(Full table\)
* [Companies](https://developers.intercom.com/intercom-api-reference/reference#list-companies) \(Incremental\)
  * [Company Segments](https://developers.intercom.com/intercom-api-reference/reference#list-attached-segments-1) \(Incremental\)
* [Conversations](https://developers.intercom.com/intercom-api-reference/reference#list-conversations) \(Incremental\)
  * [Conversation Parts](https://developers.intercom.com/intercom-api-reference/reference#get-a-single-conversation) \(Incremental\)
* [Data Attributes](https://developers.intercom.com/intercom-api-reference/reference#data-attributes) \(Full table\)
  * [Customer Attributes](https://developers.intercom.com/intercom-api-reference/reference#list-customer-data-attributes) \(Full table\)
  * [Company Attributes](https://developers.intercom.com/intercom-api-reference/reference#list-company-data-attributes) \(Full table\)
* [Contacts](https://developers.intercom.com/intercom-api-reference/reference#list-contacts) \(Incremental\)
* [Segments](https://developers.intercom.com/intercom-api-reference/reference#list-segments) \(Incremental\)
* [Tags](https://developers.intercom.com/intercom-api-reference/reference#list-tags-for-an-app) \(Full table\)
* [Teams](https://developers.intercom.com/intercom-api-reference/reference#list-teams) \(Full table\)


## Performance considerations

The connector is restricted by normal Intercom [requests limitation](https://developers.intercom.com/intercom-api-reference/reference#rate-limiting).

