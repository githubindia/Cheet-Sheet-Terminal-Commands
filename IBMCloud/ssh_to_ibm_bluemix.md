# IBMCLOUD

## Steps to `ssh` to IBM Bluemix server

[![IBMCloud](https://secure.meetupstatic.com/photos/event/6/b/f/c/600_474327644.jpeg)](https://cloud.ibm.com)
#### 1) First of all download and install ibmcloud-cli from [here]

##### 2) Login to Bluemix
```sh
$ ibmcloud login
```

##### 3) Target the server region
```sh
$ ibmcloud regions
$ ibmcloud target -r <region-name>
```

##### 4) After login, target your workspace
```sh
$ ibmcloud target -cf
```
#### First of getting things ready required for `ssh` to Bluemix

##### 5) Get your username

###### To get username, you will require your appname. List your app name by this command.
```sh
$ ibmcloud cf apps
```
###### Select the appname and the command below
```sh
$ ibmcloud cf app <appname> --guid
```
###### This username will look similar to this -> `302271ff-eb97-49cf-b5d5-6f130023ecc2`

##### 6) Get your domain
```sh
$ ibmcloud cf curl /v2/info
```
##### Above command will return a JSON, copy the value of `app_ssh_endpoint` property.
##### `app_ssh_endpoint`  will look similar to  `ssh.us-south.cf.cloud.ibm.com:2222`
##### Here `2222` is the port number and `ssh.us-south.cf.cloud.ibm.com` is your domain

##### 7) Last step is to get the password
```sh
$ ibmcloud cf ssh-code
```

#### 8) `ssh` to your Bluemix server

```sh
$ ssh -p <port>  cf:<username>/0@<domain>
```

##### It requires password, get it from step 7.

##### After entering password you will be inside server, where you can see all your apps.

##### If your are faceing any error, please refer to IBMCloud [Docs] or raise an issue in the `Issues` section.

[Docs]: <https://docs.cloudfoundry.org/devguide/deploy-apps/ssh-apps.html>
[here]: <https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases>


