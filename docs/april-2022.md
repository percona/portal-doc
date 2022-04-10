This release brings key enhancements to Percona Platform's integration with PMM, along with important design and UX improvements.

## Revamped Registration and Log in screen

The first thing you'll notice with this update is the new look-and feel of the landing page. The new design subtly simplifies the Log in and Registration flow, to make it easier for you to onboard your account. 

We've leveraged the old minimal design to create a sleek and modern look, that is more aligned with the Percona branding we love. 

## Enhanced User Experience to boost your productivity
We’ve also tweaked the structure of the main menu to improve the navigation when moving from one flow to another. 

The links to managing existing organizations and any connected PMM instances are no longer hidden inside the **Get Started** tab. Instead, they are exposed as dedicated tabs on the main menu: **Organization Management** and **Connect PMM**. 

In addition, the **Get Started** tab has been merged into the **Dasboard** tab, which now hosts all the tools for creating your organization and start connecting PMM instances to it. 
You'll also find here all information related to your account, and links to contact Percona for support, consulting or managed services. 

There' s also a new link to the Percona Platform online Help in the **Resources** menu.  


## Enhanced integration with PMM
With this update we are improving PMM connections to Perfona Platform with increased security and synchronized customer account information across PMM and Percona Platform.  

### Support for federated identity
Percona Platform now includes support for federated identity, which enables authentication via custom identity providers. 

With the 2.27 release, PMM is leveraging this enhancement by requiring access-token authorization when connecting PMM instances to Percona Platform. 

The previous **Percona Account email** and **Password** fields in  **PMM > Settings > Percona Platform** have been replaced with the new **Percona Platform Access Token** field and an option to **Get token from Percona Platform**.

For more information, see [Connect your PMM server](connect-pmm.md).

### Synchronized customer information with PMM 
After connecting PMM to Percona Platform as a Percona customer, PMM now reveals two new tabs on the main menu: **Entitlements** and **Support tickets**. 
 
Percona Platform populates these tabs with  information related to their Percona Platform  entitlements and Customer Support cases.

For more information, see [Integrate PMM with Percona Platform]() in the PMM online Help.