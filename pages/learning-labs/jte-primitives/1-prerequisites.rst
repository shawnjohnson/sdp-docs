.. _JTE Primitives Prerequisites: 

-------------
Prerequisites
-------------

================
Jenkins Instance
================

A Jenkins instance will be required for this lab.  If you don't have one available to you,
we would recommend going through the :ref:`Local Development<Local Development>` learning lab 
to deploy a local Jenkins instance through Docker. 

===============
JTE: The Basics 
===============

This lab continues to build upon our knowledge of the Jenkins Templating Engine so first completing 
the :ref:`JTE: The Basics <JTE The Basics>` lab would be very helpful. 

This lab will assume we're using the same pipeline configuration repository used during The Basics lab 
and that it is already configured as a Library Source in the Global Governance Tier. 

**********************************************************
Remove the Global Governance Tier's Pipeline Configuration
**********************************************************

For the purposes of this lab, we will only be using the Pipeline Job type.  In JTE: The Basics, we created added a 
Pipeline Configuration to the Global Governance Tier that applies to every job on the Jenkins instance. 

If this is still configured, remove it. 

1.  From the Jenkins homepage, Click ``Manage Jenkins`` in the lefthand navigation menu
2.  Click ``Configure System`` 
3.  Scroll down to the ``Jenkins Templating Engine`` configuration section 
4.  For the ``Source Location`` dropdown menu, select ``None``
5.  Remove any text in the ``Configuration Base Directory`` text box
6.  Click ``Save`` 

.. note:: 

    There should still be a global Library Source configured.  Leave that there. 