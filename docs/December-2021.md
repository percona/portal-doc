## Enhancements

- **Check the list of PMM instances connected to an organization**.
If your organization is linked to at least one PMM server, you can now click **View Instances** on the **Dashboard** tab to go to the **PMM page**.    

    Here you can find all the servers currently connected to the organization, check the server details and access the server URLs. 

- **At-a-glance overview of Percona entitlements**. If you are a member of a customer organization, you can now check the entitlements for your account on the **Dashboard** tab.

- **Improved user experience around viewing organization entitlements**. 
You can now see your customer entitlements in a bigger modal window with a scroll bar for long lists of entitlements.

    In addition, this now also displays your entitlement's Expiry Date.



## Fixed issues
-  Fixed issue in Platform's trusted origin API that prevented users from connecting PMM to Portal when using *localhost* and other common addresses.
- Clicking on **View Organization** in the **Dashboard** page now opens the organization details in the current tab instead of opening a separate one. 

## Known issue
After connecting to Percona Platform, PMM occasionally shows a false permission issue notification, incorrectly suggesting that the connection could not be established due to missing permissions. 

Reload the page in PMM to remove the incorrect notification and confirm the connection.
