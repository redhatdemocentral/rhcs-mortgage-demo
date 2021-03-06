Update: June 2018 moved to [Gitlab](https://gitlab.com/redhatdemocentral/rhcs-mortgage-demo).



App Dev Cloud with Financial Services Mortgage Demo 
===================================================
This demo is to install JBoss BPM Suite process driven mortgage example in the Cloud based on leveraging the Red Hat 
OpenShift Container Platform (OCP).  It delivers a fully functioning JBoss BPM Mortgage example containerized on OCP.


Install FSI Mortgage on OpenShift
-----------------------------------
1. (OPTIONAL) First ensure you have an OpenShift container based installation, such as one of the following installed first:

  - [OCP Install Demo](https://github.com/redhatdemocentral/ocp-install-demo)

  - [Red Hat Container Development Kit (CDK) using Minishift](https://developers.redhat.com/products/cdk/overview)

  - or your own OpenShift installation.

2. [Download and unzip this demo.](https://github.com/redhatdemocentral/rhcs-mortgage-demo/archive/master.zip)

3. Download JBoss EAP & JBoss BPM Suite, add to installs directory (see installs/README).

4. Run 'init.sh' or 'init.bat' file. 'init.bat' must be run with Administrative privileges:
```
   # The installation needs to be pointed to a running version
   # of OpenShift, so pass an IP address such as:
   #
   $ ./init.sh 192.168.99.100  # example for OCP.
```

Log in to JBoss BPM Suite to start exploring the FSI mortgage processing application (the address will be generated by the init
script):

  - OCP example: http://rhcs-mortgage-demo-appdev-in-cloud.192.168.99.100.nip.io/business-central ( u:erics / p:bpmsuite1! )


Notes
-----

Should your local network DNS not handle the resolution of the above address, giving you page not found errors, you can apply the
following to your local hosts file:

```
$ sudo vi /etc/hosts

# add host for OCP demo resulution
192.168.99.100   rhcs-mortgage-demo-appdev-in-cloud.192.168.99.100.nip.io 
```

-----

To clone a repository in the running container, the following actions would need to occur from a developer's machine.

1. Execute port forwarding through the OpenShift CLI. This will open a tunnel between the developer's machine and the pod through
	 the OpenShift API pod proxy. The command window will block while the session is open:

   ```
   # Read-only access to repo on port 9418.
   #
   $ oc port-forward $(oc get pod -l=deploymentconfig=rhcs-mortgage-demo --template='{{ range .items }} {{ .metadata.name }} {{ end }}') 9418:9418

   # Read-write access to repo on port 8001.
   #
   $ oc port-forward $(oc get pod -l=deploymentconfig=rhcs-mortgage-demo --template='{{ range .items }} {{ .metadata.name }} {{ end }}') 8001:8001
   ```

2. Clone the repository. In another window, clone the remote repository after logging in to Business Central, creating a repository
	 and identifying the repository URL in the Admin Perspective (this example is a BackOffice repository):

   ```
   # Read-only access to repo on port 9418.
   #
   $ git clone git://localhost:9418/Mortgages

   # Read-write access to repo on port 8001.
   #
   $ git clone git://localhost:8001/Mortgages
   ```

-----

The following functionality is covered:

- One advanced process.

- Four Human Tasks assigned to 3 different roles

- Use of Swimlanes to assign a task to the user who previously took ownership

- Several guide business rules

- Several technical rules

- A guided web decision table

- Several Script Tasks for Java work

- One Web Service task using SOAP/HTTP

- Exclusive use of the BPMS Data Modeler for creating the Java fact model

- Use of graphic form designer to create 4 forms with an example of javascript validation

- Helper jar to pre-load with sixteen process instances in various states.

For 'Appraisal' task only, any claimed tasks that are not competed within a minute will be reassigned automatically back into the group for processing.

Note that the entire demo is running default in memory, restart server, lose your process instances, data, monitoring history.
Sources for the demo client jar can be found in the projects directory.


Supporting Articles
-------------------
- [How to Optimize Existing IT by Modernizing Financial Processes](http://www.schabell.org/2017/07/how-to-optimize-existing-it-modernizing-financial-processes.html)

- [How to Take New Improved Mortgage Finance Process in to the Clouds](http://www.schabell.org/2017/06/how-to-take-new-mortage-finance-process-into-clouds.html)
 
- [How to take a Mortgage Finance Process into the Clouds](http://www.schabell.org/2016/04/howto-take-mortgage-finance-process-into-clouds.html)


Released versions
-----------------
See the tagged releases for the following versions of the product:

- v1.6 - JBoss BPM Suite 6.4.0 and JBoss EAP 7.0.0 and available on CDK with Minishift.

- v1.5 - JBoss BPM Suite 6.4.0 and JBoss EAP 7.0.0 with OpenShift genereated routes and service URLs.

- v1.4 - JBoss BPM Suite 6.4.0 and JBoss EAP 7.0.0 with mortgage process installed on any given OpenShift installation and loading mulitple projects.

- v1.3 - JBoss BPM Suite 6.4.0 and JBoss EAP 7.0.0 with mortgage process installed on OpenShift Container Platform.

- v1.2 - JBoss BPM Suite 6.3.0 and JBoss EAP 6.4.4 with mortgage process installed on Red Hat CDK.

- v1.1 - JBoss BPM Suite 6.2.0.GA-redhat-1-bz-1334704 and JBoss EAP 6.4.4 with mortgage process installed on Red Hat CDK.

- v1.0 - JBoss BPM Suite 6.2.0-BZ-1299002, JBoss EAP 6.4.4 with mortgage process installed on Red Hat CDK using OpenShift Enterprise image.

![Cloudy BPM Suite](https://raw.githubusercontent.com/redhatdemocentral/rhcs-mortgage-demo/master/docs/demo-images/rhcs-mortgage-demo.png)

![Mortgage POD](https://raw.githubusercontent.com/redhatdemocentral/rhcs-mortgage-demo/master/docs/demo-images/rhcs-mortgage-pod.png)

![Cloud Suite](https://raw.githubusercontent.com/redhatdemocentral/rhcs-mortgage-demo/master/docs/demo-images/rhcs-arch.png)

