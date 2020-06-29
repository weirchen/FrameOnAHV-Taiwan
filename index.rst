.. title:: Nutanix Frame on AHV Bootcamp

.. toctree::
   :maxdepth: 2
   :caption: End User Computing - Xi Frame
   :name: _eucframe
   :hidden:

   gettingstarted/gettingstarted
   goldimage/goldimage
   deploycca/deploycca
   manage/manage
   flow_secure_desktops/flow_secure_desktops
   prismops/prismops_rightsize_frm_lab/prismops_rightsize_euc_lab
   framefiles/framefiles

.. toctree::
   :maxdepth: 2
   :caption: Optional Labs
   :name: _optional
   :hidden:

   edeploycca/deploycca

.. toctree::
  :maxdepth: 2
  :caption: Appendix
  :name: _appendix
  :hidden:

  tools_vms/windows_tools_vm
  tools_vms/linux_tools_vm
  appendix/glossary

.. _getting_started:

---------------
Getting Started
---------------

Welcome to the End User Computing bootcamp featuring Xi Frame. This bootcamp is meant to provide you with first hand experience in why Nutanix is an ideal platform for VDI workloads, and can deliver a fully integrated experience with our cloud-hosted broker, Xi Frame. In addition to the benefits than Nutanix HCI brings to any virtual desktop deployment, such as linear scalability and consistent performance, Nutanix brings additional benefits that you'll explore through labs:

- Integration with AHV to provide a no-cost, easy to manage platform for running on-premises virtual desktops
- Fast desktop provisioning, including rolling out image updates to large pools of desktops
- Native file services with Nutanix Files to deliver user data, profiles, and User Personalization Layers
- Native microsegmentation with Nutanix Flow to secure a virtual desktop environment
- Rich monitoring and automation capabilities with Prism Ops

What's New
++++++++++

- Workshop updated for the following software versions:
    - AOS & PC 5.15.1

- Optional Lab Updates:

Agenda
++++++

- Introductions
- Preparing Golden Image
- Managing Frame
- Using with Files
- Using with Flow
- Using with Prism Ops

Introductions
+++++++++++++

- Name
- Familiarity with Nutanix

Initial Setup
+++++++++++++

- Take note of the *Passwords* being used.
- Log into your virtual desktops (connection info below)

Environment Details
+++++++++++++++++++

Nutanix Workshops are intended to be run in the Nutanix POC environment. Your cluster will be provisioned with all necessary images, networks, and VMs required to complete the exercises.

Networking
..........

- **Cluster Name** - ZOTDEMO
- **Subnet** - 192.168.2.0
- **Cluster IP** - 192.168.2.220

Throughout the Workshop there are multiple instances where you will need to access, for example:

.. list-table::
   :widths: 25 75
   :header-rows: 1

   * - IP Address
     - Description
   * - 192.168.2.220
     - Nutanix Cluster Virtual IP
   * - 192.168.2.222
     - **PC** VM IP, Prism Central
   * - 192.168.2.234
     - **DC** VM IP, ntnxlab Domain Controller

This cluster is configured with one VLANs which can be used for VMs:

.. list-table::
  :widths: 25 25 10 40
  :header-rows: 1

  * - Network Name
    - Address
    - VLAN
    - DHCP Scope
  * - Frame-IPAM
    - 192.168.2.0/24
    - 0
    - 192.168.2.60-192.168.2.254
  


Credentials
...........

.. note::

  The *<Cluster Password>* is unique to each cluster and will be provided by the leader of the Workshop.

.. list-table::
   :widths: 25 35 40
   :header-rows: 1

   * - Credential
     - Username
     - Password
   * - Prism Element
     - admin
     - *1qaz@WSX3edc*
   * - Prism Central
     - admin
     - *1qaz@WSX3edc*
   * - Controller VM
     - nutanix
     - *1qaz@WSX3edc*
   * - Prism Central VM
     - nutanix
     - *1qaz@WSX3edc*

This cluster has a dedicated domain controller VM, **DC**, responsible for providing AD services for the **ntnxlab.local** domain. The domain is populated with the following Users and Groups:

.. list-table::
   :widths: 25 35 40
   :header-rows: 1

   * - Group
     - Username(s)
     - Password
   * - Administrators
     - Administrator
     - nutanix/4u
   * - SSP Admins
     - adminuser01-adminuser25
     - nutanix/4u
   * - SSP Developers
     - devuser01-devuser25
     - nutanix/4u
   * - SSP Consumers
     - consumer01-consumer25
     - nutanix/4u
   * - SSP Operators
     - operator01-operator25
     - nutanix/4u
   * - SSP Custom
     - custom01-custom25
     - nutanix/4u
   * - Bootcamp Users
     - user01-user25
     - nutanix/4u



Nutanix Version Info
++++++++++++++++++++

- **AHV Version** - AHV 20170830.396
- **AOS Version** - 5.10.10.1
- **PC Version** - 5.17.0.3
