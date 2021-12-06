Percona Monitoring and Management (PMM) is a best-of-breed open source database monitoring solution for MySQL, MongoDB, PostgreSQL, and MariaDB databases.
Connect your PMM server to Percona Platform to add additional functionality for improving the performance of your databases, inlcuding more advisors and more security checks.

## Pre-requisites
To ensure that Percona Platform can establish a communication with the PMM instance: 

#### Set the public address of your PMM server 

1. Log into PMM and go to **PMM > Advanced Settings**.
2. Enter your address/hostname or click **Get from browser** to enable your browser to automatically detect and populate this field.
3. Save the changes.

#### Check that you are a member of an existing organization
1. Log in to [Percona Platform](https://portal.percona.com) using your Percona Account.
2. On the **Getting Started page**, check that the **Create organization** step shows an option to view your organization. If you see an option to create a new organizatiopn instead, your Percona Account is not linked to any organization yet. In this is the case, contact your account administrator or create a new organization for your P
ercona Account.


## Connect PMM
To connect your PMM instance to Percona Platform:

1. Log in to PMM and go to **PMM > Settings > Percona Platform** tab.

2. Fill in the **Connect PMM to Percona Portal** form with the name of your PMM instance and the credentials of your Percona Account, then click **Connect**.

## Signing in to PMM with your Percona Account
Once you've sucessfully connected your PMM instance to Percona Platform, use your Percona Account to sign in to PMM:

1. Log out of your existing PMM session.

2.  On the PMM login screen, click the **Sign in with Percona Account**.
 If you have an active Percona Account session on the same browser, PMM will log you in automatically. Otherwise, enter your Percona Account credentials to start a new session.

