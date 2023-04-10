.. Copyright (C) 2015, Wazuh, Inc.

.. meta::
  :description: Learn about the required dependencies for using the AWS integration in a Wazuh agent.

.. _amazon_dependencies:

Installing dependencies
=======================

.. note::
  The integration with AWS S3 can be configured in the Wazuh manager (which also behaves as an agent) or directly in a Wazuh agent. This choice merely depends on how you decide to access your AWS infrastructure in your environment.

.. warning::
  The Wazuh manager includes all dependencies installed, these steps are only necessary when configuring the integration in a Wazuh agent.


Python
------

The AWS module requires Python 3. It is compatible with Python 3.7+. Future Python releases should maintain compatibility although it cannot be guaranteed.

.. tabs::

   .. group-tab:: Yum

      .. code-block:: console

         # yum update && yum install python3

   .. group-tab:: APT

      .. code-block:: console

         # apt-get update && apt-get install python3


The required modules can be installed with Pip, the Python package manager. Most UNIX distributions have this tool available in their software repositories:

.. tabs::

   .. group-tab:: Yum

      .. code-block:: console

         # yum update && yum install python3-pip

   .. group-tab:: APT

      .. code-block:: console

         # apt-get update && apt-get install python3-pip

It is recommended to use a pip version greater than or equal to 19.3 to ease the installation of the required dependencies.

.. code-block:: console

  # pip3 install --upgrade pip

.. _boto-3:

AWS pip dependencies
-----------------------

`Boto3 <https://boto3.readthedocs.io/>`_ is the official package supported by Amazon to manage AWS resources. It is used to download the log messages from the different AWS services supported by Wazuh. The module is compatible with boto3 from ``1.13.1`` to ``1.17.85``. Future boto3 releases should maintain compatibility although it cannot be guaranteed.

To install the dependencies, execute the following command:

.. code-block:: console

  # pip3 install boto3==1.17.85 botocore==1.20.85 jmespath==0.9.5 python-dateutil==2.8.1 six==1.14.0 urllib3==1.26.5 s3transfer==0.4.2