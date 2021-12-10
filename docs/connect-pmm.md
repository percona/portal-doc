Percona Monitoring and Management (PMM) is a best-of-breed open source database monitoring solution for MySQL, MongoDB, PostgreSQL, and MariaDB databases.

Connect your PMM servers to Percona Platform to leverage Platform services that boost the monitoring capabilities of your PMM installations.

## Pre-requisites
To ensure that Percona Platform can establish a connection with the PMM instance:


### Install PMM 2.25.0 or later
 Before connecting your PMM server to Percona Platform, make sure that you are using PMM version 2.25 or newer. Otherwise, upgrade your PMM installation before continuing.

### Set the public address of your PMM server 

1. Log into PMM and go to **PMM > Settings > Advanced Settings**.
2. Enter your address/hostname or click **Get from browser** to enable your browser to automatically detect and populate this field.
3. Save the changes.

### Check that you are a member of an existing organization
1. Log in to [Percona Platform](https://portal.percona.com) using your Percona Account.
2. On the **Getting Started page**, check that the **Create organization** step shows an option to view your organization. <br/> 
If you see an option to create a new organization instead, your Percona Account is not linked to any organization yet. If this is the case, contact your account administrator, or create a new organization for your Percona Account.


## Connect PMM to Percona Platform
To connect your PMM instance to Percona Platform:

1. Log in to PMM and go to **PMM > Settings > Percona Platform** tab.

2. Fill in the **Connect PMM to Percona Portal** form with the name of your PMM instance and the credentials of your Percona Account:

    ![Connect PMM to Percona Portal](_images/pmm-connect-to-platform.png)

3. Click **Connect**.

## Sign into PMM with your Percona Account
Once you've successfully connected your PMM instance to Percona Platform, use your Percona Account to sign in to PMM:

1. Log out of your existing PMM session.

2. On the PMM login screen, click the **Sign in with Percona Account**. <br/>
 If you have an active Percona Account session on the same browser, PMM will log you in automatically. Otherwise, enter your Percona Account credentials to start a new session.