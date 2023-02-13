# HubSpot

This page guides you through setting up the HubSpot connector.

## Prerequisite

You can use OAuth, API key, or Private App to authenticate your HubSpot account. If you choose to use OAuth or Private App, you need to configure the appropriate [scopes](https://legacydocs.hubspot.com/docs/methods/oauth2/initiate-oauth-integration#scopes) for the following streams:

| Stream                      | Required Scope                                                                   |
| :-------------------------- | :------------------------------------------------------------------------------- |
| `campaigns`                 | `content`                                                                        |
| `companies`                 | `crm.objects.companies.read`, `crm.schemas.companies.read`                       |
| `contact_lists`             | `crm.objects.lists.read`                                                         |
| `contacts`                  | `crm.objects.contacts.read`                                                      |
| `contacts_list_memberships` | `crm.objects.contacts.read`                                                      |
| `deal_pipelines`            | either the `crm.objects.contacts.read` scope \(to fetch deals pipelines\) or the `tickets` scope. |
| `deals`                     | `crm.objects.deals.read`, `crm.schemas.deals.read`                               |
| `email_events`              | `content`                                                                        |
| `engagements`               | `crm.objects.companies.read`, `crm.objects.contacts.read`, `crm.objects.deals.read`, `tickets`, `e-commerce`|
| `engagements_emails`        | `sales-email-read`                                                               |
| `forms`                     | `forms`                                                                          |
| `form_submissions`          | `forms`                                                                          |
| `line_items`                | `e-commerce`                                                                     |
| `owners`                    | `crm.objects.owners.read`                                                        |
| `products`                  | `e-commerce`                                                                     |
| `property_history`          | `crm.objects.contacts.read`                                                      |
| `subscription_changes`      | `content`                                                                        |
| `tickets`                   | `tickets`                                                                        |
| `workflows`                 | `automation`                                                                     |


## Set up the HubSpot connector

We would need your API key for a Private Application.

## Supported Streams

The HubSpot connector supports the following streams:

* [Campaigns](https://developers.hubspot.com/docs/methods/email/get_campaign_data)
* [Companies](https://developers.hubspot.com/docs/api/crm/companies) \(Incremental\)
* [Contact Lists](http://developers.hubspot.com/docs/methods/lists/get_lists) \(Incremental\)
* [Contacts](https://developers.hubspot.com/docs/methods/contacts/get_contacts) \(Incremental\)
* [Contacts List Memberships](https://legacydocs.hubspot.com/docs/methods/contacts/get_contacts)
* [Deal Pipelines](https://developers.hubspot.com/docs/methods/pipelines/get_pipelines_for_object_type)
* [Deals](https://developers.hubspot.com/docs/api/crm/deals) \(including Contact associations\) \(Incremental\)
* [Email Events](https://developers.hubspot.com/docs/methods/email/get_events) \(Incremental\)
* [Engagements](https://legacydocs.hubspot.com/docs/methods/engagements/get-all-engagements) \(Incremental\)
* [Engagements Calls](https://developers.hubspot.com/docs/api/crm/calls) \(Incremental\)
* [Engagements Emails](https://developers.hubspot.com/docs/api/crm/email) \(Incremental\)
* [Engagements Meetings](https://developers.hubspot.com/docs/api/crm/meetings) \(Incremental\)
* [Engagements Notes](https://developers.hubspot.com/docs/api/crm/notes) \(Incremental\)
* [Engagements Tasks](https://developers.hubspot.com/docs/api/crm/tasks) \(Incremental\)
* [Forms](https://developers.hubspot.com/docs/api/marketing/forms)
* [Form Submissions](https://legacydocs.hubspot.com/docs/methods/forms/get-submissions-for-a-form)
* [Line Items](https://developers.hubspot.com/docs/api/crm/line-items) \(Incremental\)
* [Marketing Emails](https://legacydocs.hubspot.com/docs/methods/cms_email/get-all-marketing-email-statistics)
* [Owners](https://developers.hubspot.com/docs/methods/owners/get_owners)
* [Products](https://developers.hubspot.com/docs/api/crm/products) \(Incremental\)
* [Property History](https://legacydocs.hubspot.com/docs/methods/contacts/get_contacts) \(Incremental\)
* [Subscription Changes](https://developers.hubspot.com/docs/methods/email/get_subscriptions_timeline) \(Incremental\)
* [Tickets](https://developers.hubspot.com/docs/api/crm/tickets) \(Incremental\)
* [Ticket Pipelines](https://developers.hubspot.com/docs/api/crm/pipelines)
* [Workflows](https://legacydocs.hubspot.com/docs/methods/workflows/v3/get_workflows)

### A note on the `engagements` stream

Objects in the `engagements` stream can have one of the following types: `note`, `email`, `task`, `meeting`, `call`. Depending on the type of engagement, different properties is set for that object in the `engagements_metadata` table in the destination:

- A `call` engagement has a corresponding `engagements_metadata` object with non-null values in the `toNumber`, `fromNumber`, `status`, `externalId`, `durationMilliseconds`, `externalAccountId`, `recordingUrl`, `body`, and `disposition` columns.
- An `email` engagement has a corresponding `engagements_metadata` object with non-null values in the `subject`, `html`, and `text` columns. In addition, there will be records in four related tables, `engagements_metadata_from`, `engagements_metadata_to`, `engagements_metadata_cc`, `engagements_metadata_bcc`.
- A `meeting` engagement has a corresponding `engagements_metadata` object with non-null values in the `body`, `startTime`, `endTime`, and `title` columns.
- A `note` engagement has a corresponding `engagements_metadata` object with non-null values in the `body` column.
- A `task` engagement has a corresponding `engagements_metadata` object with non-null values in the `body`, `status`, and `forObjectType` columns.

## Performance considerations

The connector is restricted by normal HubSpot [rate limitations](https://legacydocs.hubspot.com/apps/api_guidelines).

Some streams, such as `workflows` need to be enabled before they can be read using a connector authenticated using an `API Key`. If reading a stream that is not enabled, a log message returned to the output and the sync operation only sync the other streams available.

HubSpot's API will [rate limit](https://developers.hubspot.com/docs/api/usage-details) the amount of records you can sync daily, so make sure that you are on the appropriate plan if you are planning on syncing more than 250,000 records per day.
