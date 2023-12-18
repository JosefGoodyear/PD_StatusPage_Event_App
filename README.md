# PagerDuty Status Pages Event App 

[PagerDuty External Status Pages](https://support.pagerduty.com/docs/external-status-page) can be used by PagerDuty customers to notify their users and the general public about incidents and maintenance for services.\
This integration is designed for any PagerDuty users that want to integrate their PagerDuty instance with an external status page from another organization that is Powered by PagerDuty. Once configured, users can trigger and resolve incidents on their own PagerDuty account, based on any third party status page that is Powered by PagerDuty.


# How it Works

When a webhook from a status page is sent to the subscription url, this integration tranforms the payload so that it is ingestible and creates a formatted PagerDuty incident.


# Requirements

You must have a manager base role in order to add the integration to a PagerDuty service. The status page you are subscribing to must have webhooks enabled.


# Support

If you need help with this integration, please create an issue in this repo.

Integration Walkthrough


# In PagerDuty

1. Navigate to the **Services** menu and select **Service Directory** from the dropdown menu.

2. Choose the service you wish to add the integration to.

3. Select the **Integrations** tab, click **+ Add another integration**, and search for **PagerDuty StatusPages**.

4. Copy the **Integration URL**.\
   ![](https://lh7-us.googleusercontent.com/BE5GoR5guM_k-71uFw6OsLuJW58vOuyWoWYpoc8tlGmKvLx0NPe0YGYY-albgSviX_akZwbY5SEyKqaYztrTutFwymhlV4loNvTBT_Xk4DQvlFwK_m2fI_uU9ZjbUXeSVcewbzoq1m-THANAa256NvY)


# On the Powered By PagerDuty Status Page

1. Navigate to the Powered By PagerDuty Status Page that you want to subscribe to.

2. Click **Subscribe to Updates**.

3. Paste the URL that you copied from the previous section into the **Webhook URL** field.

4. Select **All Services** to be notified for all posts or enter specific services that you would like to be notified for.

![](https://lh7-us.googleusercontent.com/1uImqTVbOgVxIhMNfGGp472amtPC50qeFMYy099_ioLZ5EaEzCH1YnVUie3wV7roYq1Gz4wl4WAXVNoDCdWehi6_dY7-iK4zf9N_B_melatbfNAjIANpghCO3w2e7yionH2IdrySDLi3tpv0t6PFmmA)

5. Click Subscribe Webhook.


# FAQ

**Q: How do I know if a status page is “powered by PagerDuty”?**

A: Any status page that is powered by PagerDuty will have a **powered by PagerDuty** link on the footer of the status page.

![](https://lh7-us.googleusercontent.com/rY7Wop-7bJ5_FMfH_ABu50AyWrTIvEoMNOSl5d5Fgt1-hemkwiJVaEGCMhS6VhFLhXUGZiaL2PhFdG-IuboLAINMuHAPyitudLC9e58HQry21RUE0movK27yzk0yUkwOUEIwWdqi6_zqDwYs8z6VcRE)

**Q: Does this integration support incident and maintenance posts?**

A: Yes, this integrations supports both incident and maintenance posts

**Q: How do different types of posts correspond to PagerDuty events?**

A: StatusPage posts are deduplicated based on the incident or maintenance URL. All statuses besides Resolved (for incident) and Completed (for maintenance) send trigger events. Resolved and completed statuses send resolved events. 

**Q: Do postmortem updates send events?**

A: No, postmortem updates do not send events.

**Q: How is alert severity mapped when an alert is triggered?**

A: Major incident posts create alerts with critical severity. Minor incident posts create alerts with error severity. All other incidents and maintenance posts create alerts with info severity
