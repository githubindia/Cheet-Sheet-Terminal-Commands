# IBMCLOUD

## Steps to deploy Node.JS webapp to IBM Bluemix

[![IBMCloud](https://secure.meetupstatic.com/photos/event/6/b/f/c/600_474327644.jpeg)](https://cloud.ibm.com)
#### First of all download and install ibmcloud-cli from [here]

##### Login to IBM-cloud
```sh
$ ibmcloud login
```
##### Target the deploymemt region
```sh
$ ibmcloud regions 
$ ibmcloud target -r <region-name>
```
##### Target the cloudfoundary
```sh
$ ibmcloud target -cf
```
##### deploy the code
```sh
$ ibmcloud cf push
```

   [here]: <https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases>