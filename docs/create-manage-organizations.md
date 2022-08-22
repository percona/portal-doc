# Create and manage organizations
Create an organization to collaborate with members of your team and share access to the software and services that Percona Platform provides. 

Organizations are linked to Percona Accounts. Each Percona Account gives access to only one organization. This means that you cannot be member of multiple organizations or create more than one organization for a Percona Account. 

To create an organization: 

1. Log in to [Percona Platform](https://portal.percona.com) using your Percona Account.
2. Click the **Organization** tab on the main menu, then click **Add Organization**. <br />
Existing Percona customers and Percona Accounts that are already associated with an organization will see an option to view their existing organization instead. 
3. Enter a relevant name for your new organization, then click **Save**. <br />
This creates the new organization and displays its general details like name and creation date.


## Existing organizations for Percona customers

If you are an existing Percona customer, you do not need to create or join organizations manually. Percona Platform can do that for you automatically.<br /><br />
Your Customer Portal organization is automatically linked to Percona Platform the first time that the account administrator logs into Percona Platform. Other organization members subsequently logging in to Percona Platform will be automatically added as members of the existing organization. 

!!! hint alert alert-success "Tip"
    To make sure you are logging in to the organization corresponding to the one in Percona Customer Account, make sure to sign in to Percona Platform using the same email address used for your Percona Customer Account. 

Information about Support entitlements, tickets, and contacts is automatically made available on the Platform organization. <br /> <br />
As an account administrator, finish setting up your Percona Platform organization by making sure all your organization members register for a Percona Account and log in to the Portal. <br />

## Check organization details

After creating or joining an organization, click the **Organization** tab on the left menu to open the **Manage organization** page.

Here you can manage your organization and check its details.

## Roles and permissions
When you create an organization, you are automatically assigned the role of **Admin** for that organization.
You can add people to your organization as **Admins** or **Technical users**.  <br /><br />
Here are the different permissions available for these roles:<br />

| Permission      | Admin user |  Technical user
| :----------| :----------- |:----------- |
|View users and organization|<input type="checkbox" disabled checked /> | <input type="checkbox" disabled checked />|
|Manage users and organization       | <input type="checkbox" disabled checked />    |  <input type="checkbox" disabled />|
|Invite members|<input type="checkbox" disabled checked /> | <input type="checkbox" disabled />|
|Change other user's role |    <input type="checkbox" disabled checked />     |   <input type="checkbox" disabled /> |
|View Customer data (entitlements, Support contacts, tickets)| <input type="checkbox" disabled checked />    |   <input type="checkbox" disabled checked /> |
|Connect PMM server| <input type="checkbox" disabled checked />| <input type="checkbox" disabled checked />|
|Raise Support tickets| <input type="checkbox" disabled checked />  |<input type="checkbox" disabled checked />  |

## Add organization members

Administrators can add any number of Technical users to the organization, and even add other Admins if necessary. <br /><br />
To add users to your organization:

1. Log in to [Percona Platform](https://portal.percona.com).
2. Click **Organization** tab on the left side menu. 
3. On the **Members** tab, click the **Invite Member** button. 
4. Enter the email address of the user you want to invite, and select a role.
5. Click **Add another user** if you want to invite more than one user. You can send up to ten invitations at a time. If you need to invite more users, send out the current invitations, then click **Invite Members** again. This reopens the invitation form where you can bulk-invite another ten users.
6. Click **Invite** to send the invitations for joining your organization. 

## Edit roles
Currently, organization users cannot change their own role. However, Administrators can change the user role for all the other members in their organization. <br /><br />
To do so:

1. Click the **Organization** tab on the left side menu. 
2. Open the **Members** tab.
3. In the **Actions** column, click on the **Edit** icon next to the user whose role you want to change.
This displays the **Edit Member** form.
4. In the **Role** field, select the new role that you want to assign to the user and click **Save**.

## Delete users
As an Administrator, you can remove any  member from your organization apart from yourself.

After deleting users, you may want to also remove these users from your Customer Portal organization.

To delete a user from your Percona Platform organization:

1. Click the **Organization** tab on the left side menu. 
2. Open the **Members** tab.
3. In the **Actions** column, click on the **Delete** icon next to the user you want to remove from the organization.
4. Confirm that you want to remove the user and click **Delete**.


## Delete organizations

As an Admin user, you can delete your organization and all its data. Organization users can still use their accounts to access Percona Platform and join or create other organizations. 
    !!! hint alert alert-success "Tip"
        Deleted organizations and their data cannot be restored, so be careful when performing this action.  

        To delete an organization as an Admin, go to the **Organization** tab  **> Organization** and click the  ![Delete](images/trash.png) icon.