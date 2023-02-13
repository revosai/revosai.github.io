# Mixpanel

This page contains the setup guide and reference information for the Mixpanel source connector.

## Prerequisites

To set up the Harvest source connector, you'll need a Mixpanel [Service Account](https://developer.mixpanel.com/reference/service-accounts) and it's [Project ID](https://help.mixpanel.com/hc/en-us/articles/115004490503-Project-Settings#project-id), the [Project Timezone](https://help.mixpanel.com/hc/en-us/articles/115004547203-Manage-Timezones-for-Projects-in-Mixpanel), and the Project region (`US` or `EU`).

## Set up the Mixpanel connector in RevOS

Our team will support you on that

### Supported Streams

* [Export](https://developer.mixpanel.com/reference/raw-event-export) \(Incremental\)
* [Engage](https://developer.mixpanel.com/reference/engage-query) \(Incremental\)
* [Funnels](https://developer.mixpanel.com/reference/funnels-query) \(Incremental\)
* [Revenue](https://developer.mixpanel.com/reference/engage-query) \(Incremental\)
* [Annotations](https://developer.mixpanel.com/reference/overview-1) \(Full table\)
* [Cohorts](https://developer.mixpanel.com/reference/cohorts-list) \(Incremental\)
* [Cohort Members](https://developer.mixpanel.com/reference/engage-query) \(Incremental\)

## Performance considerations

Syncing huge date windows may take longer due to Mixpanel's low API rate-limits \(**60 reqs per hour**\).