Percona Monitoring and Management (PMMP) is a best-of-breed open source database monitoring solution for MySQL, MongoDB, PostgreSQL, and MariaDB databases.
Connect your PMM server to Percona Platform to 

## Pre-requisites
To ensure that Platform can establish a communication with the PMM instance: 

### Set the public address of your PMM server 

1. Log into PMM and go to **PMM > Advanced Settings**.

2. Enter your address/hostname or use the **Get from browser** action to have your browser detect and populate this field automatically.

3. Save the changes.

### Check that you are a member of an existing organization
1. Log in to [Percona Platform](https://portal.percona.com) using your Percona Account.
2. On the **Getting Started page**, verify that that the **Create organization** step is checked and you have an option to view your organization. If this is not the case, your Percona Account is not linked to any organization yet and you can create a new one instead.


## Connect PMM
To connect your PMM instance to Percona Platform:

1. Log in to PMM and go to **PMM > Settings > Percona Platform** tab.

2. Fill in the **Connect PMM to Percona Portal** form with the name of your PMM instance and the credentials of your Percona account, then click **Connect**.

## Signing in to PMM with your Percona Account
Once you've sucessfully connected your PMM instance to Percona Platform, use your Percona Account to sign in to PMM.

1. Log out from your existing PMM session.

2.  On the PMM login screen, click the **Sign in with Percona Account**, If you have an active Percona Account session on the same browser, PMM will log you in automatically. Otherwise, enter your Percona Account credentials to start a new session.

