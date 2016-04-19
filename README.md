App Dev Cloud with JBoss Mortgage Demo 
======================================
This demo is to install JBoss BPM Suite Mortgage Demo in the Cloud based on leveraging the Red Hat 
Container Development Kit (CDK) and the provided OpenShift Enterprise (OSE) image. 
It delivers a fully functioning JBoss BPM Mortgage example containerized on OSE.


Install on Red Hat CDK OpenShift Enterprise image
-------------------------------------------------
1. First complete the installation and start the OpenShift image supplied in the
	 [cdk-install-demo](https://github.com/eschabell/cdk-install-demo).

2. Install [OpenShift Client Tools](https://developers.openshift.com/managing-your-applications/client-tools.html) if you have not
	 done so previously.

2. [Download and unzip this demo.](https://github.com/redhatdemocentral/rhcs-mortgage-demo/archive/master.zip)

3. Add products to installs directory.

5. Run 'init.sh' or 'init.bat' file. 'init.bat' must be run with Administrative privileges.

6. Login to JBoss BPM Suite to start developing your BPM projects:

    [http://rhcs-mortgage-demo.10.1.2.2.xip.io/business-central](http://rhcs-mortgage-demo.10.1.2.2.xip.io/business-central)
    ( u:erics / p:bpmsuite1! )


Notes
-----
Should your local network DNS not handle the resolution of the above address, giving you page not found errors, you can apply the
following to your local hosts file:

    ```
    $ sudo vi /etc/hosts

    # add host for CDK demo resolution.
    10.1.2.2   rhcs-mortgage-demo.10.1.2.2.xip.io    rhcs-mortage-demo.10.1.2.2.xip.io
    ```

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
- [How to take a Mortgage Finance Process into the Clouds](http://www.schabell.org/2016/04/howto-take-mortgage-finance-process-into-clouds.html)


Released versions
-----------------
See the tagged releases for the following versions of the product:

- v1.0 - JBoss BPM Suite 6.2.0-BZ-1299002, JBoss EAP 6.4.4 with mortgage process installed on Red Hat CDK using OpenShift Enterprise image.

![Cloudy BPM Suite](https://raw.githubusercontent.com/redhatdemocentral/rhcs-mortgage-demo/master/docs/demo-images/rhcs-mortgage-demo.png)

![Mortgage OSE](https://raw.githubusercontent.com/redhatdemocentral/rhcs-mortgage-demo/master/docs/demo-images/rhcs-mortgage-pod.png)


