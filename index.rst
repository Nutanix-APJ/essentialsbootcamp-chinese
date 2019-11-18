.. title:: Nutanix Essentials Bootcamp

.. toctree::
  :maxdepth: 2
  :caption: Prism Central
  :name: _prism_central
  :hidden:

  what_is_prism_central/what_is_prism_central
  prism_central_overview/prism_central_overview
  prism_central_dashboards_reports/prism_central_dashboards_reports

.. toctree::
  :maxdepth: 2
  :caption: Prism Pro
  :name: _prism_pro
  :hidden:

  what_is_prism_pro/what_is_prism_pro
  prism_pro_efficiency_anomaly/prism_pro_efficiency_anomaly
  prism_pro_resource_planning/prism_pro_resource_planning
  prism_pro_xplay/prism_pro_xplay

.. toctree::
  :maxdepth: 2
  :caption: Era
  :name: _era
  :hidden:

  era/era

.. toctree::
  :maxdepth: 2
  :caption: Flow
  :name: _flow
  :hidden:

  what_is_flow/what_is_flow
  flow_enable/flow_enable
  flow_isolate_environments/flow_isolate_environments
  flow_secure_app/flow_secure_app
  
  //flow_quarantine_vm/flow_quarantine_vm


.. toctree::
  :maxdepth: 2
  :caption: Appendix
  :name: _appendix
  :hidden:

  appendix/glossary
  appendix/basics
  tools_vms/windows_tools_vm
  tools_vms/linux_tools_vm_cloud-init
  taskman/taskman

.. _getting_started:

---------------
开动实验
---------------

欢迎来到Nutanix 训练营！ 本实验手册伴随着讲师指导的培训，介绍了Nutanix解决方案和许多常见的管理任务。 每个部分都有一个课程和实验，为您提供实践练习。 讲师会讲解练习并回答您可能遇到的任何其他问题。


版本
++++++++++

- Workshop updated for the following software versions:
    - AOS & PC 5.11

- 可选的实验更新:


日程
++++++

- 通过实验掌握在Nutanix环境下Prism Central统一管理平台的特性及测试方法。

- 通过实验掌握在Nutanix环境下Flow原生网络服务的特性及测试方法。

- 通过实验掌握在Nutanix环境下Era数据库管理服务平台的特性及测试方法。

简介
+++++++++++++

环境说明
+++++++++++++++++++

Nutanix Workshop旨在Nutanix Hosted POC环境中运行。 将为您的群集配置完成练习所需的所有必要图像，网络和VM。


网络
..........

Hosted POC 集群遵循标准命名约定:

- **Cluster Name** - POC\ *XYZ*
- **Subnet** - 10.**42**.\ *XYZ*\ .0
- **Cluster IP** - 10.**42**.\ *XYZ*\ .37

If provisioned from the marketing pool:
- **Cluster Name** - MKT\ *XYZ*
- **Subnet** - 10.**42**.\ *XYZ*\ .0
- **Cluster IP** - 10.**42**.\ *XYZ*\ .37

示例:

- **Cluster Name** - POC055
- **Subnet** - 10.21.55.0
- **Cluster IP** - 10.21.55.37

在整个Workshop期间，有多个实例需要用* XYZ *替换正确的子网，例如:

.. list-table::
   :widths: 25 75
   :header-rows: 1

   * - IP Address
     - Description
   * - 10.21.\ *XYZ*\ .37
     - Nutanix Cluster Virtual IP
   * - 10.21.\ *XYZ*\ .39
     - **PC** VM IP, Prism Central
   * - 10.21.\ *XYZ*\ .40
     - **DC** VM IP, NTNXLAB.local Domain Controller

每个群集配置有2个可用于VM的VLAN:

.. list-table::
  :widths: 25 25 10 40
  :header-rows: 1

  * - Network Name
    - Address
    - VLAN
    - DHCP Scope
  * - Primary
    - 10.42.\ *XYZ*\ .1/25
    - 0
    - 10.42.\ *XYZ*\ .50-10.21.\ *XYZ*\ .124
  * - Secondary
    - 10.42.\ *XYZ*\ .129/25
    - *XYZ1*
    - 10.42.\ *XYZ*\ .132-10.21.\ *XYZ*\ .253

认证
...........

.. note::

  The *<Cluster Password>* 对每个群集都是唯一的，将由Workshop的负责人提供.

.. list-table::
   :widths: 25 35 40
   :header-rows: 1

   * - Credential
     - Username
     - Password
   * - Prism Element
     - admin
     - *<Cluster Password>*
   * - Prism Central
     - admin
     - *<Cluster Password>*
   * - Controller VM
     - nutanix
     - *<Cluster Password>*
   * - Prism Central VM
     - nutanix
     - *<Cluster Password>*

每个群集都有一个专用的域控制器VM, **DC**, 负责为 **NTNXLAB.local** 域提供AD服务. 该域包括了以下用户和组：:


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
   * - SSP Power Users
     - poweruser01-poweruser25
     - nutanix/4u
   * - SSP Basic Users
     - basicuser01-basicuser25
     - nutanix/4u

访问说明
+++++++++++++++++++

可以通过多种不同方式访问Nutanix Hosted POC环境:

Parallels VDI
.................

Login to: https://xld-uswest1.nutanix.com (for PHX) or https://xld-useast1.nutanix.com (for RTP)

**Nutanix Employees** - Use your NUTANIXDC credentials
**Non-Employees** - **Username:** POCxxx-User01 (up to POCxxx-User20), **Password:** *<Provided by Instructor>*




Nutanix 版本信息
++++++++++++++++++++

- **AHV Version** - AHV 20170830.279 (5.10+)
- **AOS Version** - 5.11
- **PC Version** - 5.11
