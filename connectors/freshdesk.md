# Freshdesk

This page guides you through the process of setting up the Freshdesk source connector.

## Prerequisites

To set up the Freshdesk source connector, you'll need the Freshdesk [domain URL](https://support.freshdesk.com/en/support/solutions/articles/50000004704-customizing-your-helpdesk-url) and the [API key](https://support.freshdesk.com/support/solutions/articles/215517).

## Set up the Freshdesk connector 

Our team support you with it

## Supported Streams

Several output streams are available from this source:

* [Agents](https://developers.freshdesk.com/api/#agents)
* [Business Hours](https://developers.freshdesk.com/api/#business-hours)
* [Canned Responses](https://developers.freshdesk.com/api/#canned-responses)
* [Canned Response Folders](https://developers.freshdesk.com/api/#list_all_canned_response_folders)
* [Companies](https://developers.freshdesk.com/api/#companies)
* [Contacts](https://developers.freshdesk.com/api/#contacts) \(Native Incremental Sync\)
* [Conversations](https://developers.freshdesk.com/api/#conversations)
* [Discussion Categories](https://developers.freshdesk.com/api/#category_attributes)
* [Discussion Comments](https://developers.freshdesk.com/api/#comment_attributes)
* [Discussion Forums](https://developers.freshdesk.com/api/#forum_attributes)
* [Discussion Topics](https://developers.freshdesk.com/api/#topic_attributes)
* [Email Configs](https://developers.freshdesk.com/api/#email-configs)
* [Email Mailboxes](https://developers.freshdesk.com/api/#email-mailboxes)
* [Groups](https://developers.freshdesk.com/api/#groups)
* [Products](https://developers.freshdesk.com/api/#products)
* [Roles](https://developers.freshdesk.com/api/#roles)
* [Satisfaction Ratings](https://developers.freshdesk.com/api/#satisfaction-ratings)
* [Scenario Automations](https://developers.freshdesk.com/api/#scenario-automations)
* [Settings](https://developers.freshdesk.com/api/#settings)
* [Skills](https://developers.freshdesk.com/api/#skills)
* [SLA Policies](https://developers.freshdesk.com/api/#sla-policies)
* [Solution Articles](https://developers.freshdesk.com/api/#solution_article_attributes)
* [Solution Categories](https://developers.freshdesk.com/api/#solution_category_attributes)
* [Solution Folders](https://developers.freshdesk.com/api/#solution_folder_attributes)
* [Surveys](https://developers.freshdesk.com/api/#surveys)
* [Tickets](https://developers.freshdesk.com/api/#tickets) \(Native Incremental Sync\)
* [Ticket Fields](https://developers.freshdesk.com/api/#ticket-fields)
* [Time Entries](https://developers.freshdesk.com/api/#time-entries)

## Performance considerations

The Freshdesk connector should not run into Freshdesk API limitations under normal usage.

If you don't use the start date Freshdesk will retrieve only the last 30 days. More information [here](https://developers.freshdesk.com/api/#list_all_tickets).

