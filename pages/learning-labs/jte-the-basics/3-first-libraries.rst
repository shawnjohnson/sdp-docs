.. _JTE The Basics First Libraries: 

--------------------
Create the Libraries
--------------------

In the previous section we created a pipeline template that invoked 
``build()`` and ``static_code_analysis()`` steps. 

In this part of the lab, we're going to create libraries for these 
steps to implement them in our template. 

==========================
Create a GitHub Repository
========================== 

Libraries can either be packaged into a separate plugin for distribution 
or fetched directly from a source code management repository. 

Retrieving libraries from a repository is the most common way of storing 
pipeline libraries for integration with the Jenkins Templating Engine (JTE). 

Go ahead and create a new GitHub repository.  It can be named whatever you like, 
though ``jte-the-basics`` would make sense. 

======================
Create the Libraries
====================== 

Create the following directory structure within your repository:

.. code:: 

    .
    └── libraries
        ├── maven
        │   └── build.groovy
        └── sonarqube
            └── static_code_analysis.groovy


.. important:: 

    When configuring this repository as a **Library Source** for JTE in Jenkins,
    you will be able to configure the base directory.  Since there might be other 
    resources in this repository in the future, all of the libraries we create will
    be stored in the ``libraries`` directory. 

It is important to understand that a library in JTE is just a *directory*, likely in a 
source code repository, that contains groovy files.  When a library is loaded, each 
groovy file in the library's directory will become a step named after the base filename. 

===================
Implement the Steps
===================

In this lab, we're just getting accustomed to the Jenkins Templating Engine and how it 
works.  So the implementation of the steps for this lab will just be print statements that 
show where the step is coming from.  

Generally, the most idiomatic way to define a step is to create a ``call`` method that takes no input 
parameters. 

.. note:: 

    In future labs, we'll learn how to pass information to our steps through the pipeline 
    configuration file.  

**libraries/maven/build.groovy**:  

.. code:: groovy

    void call(){
        stage("Maven: Build"){
            println "build from the maven library"
        }
    }

**libraries/sonarqube/static_code_analysis.groovy**: 

.. code:: groovy

    void call(){
        stage("SonarQube: Static Code Analysis"){
            println "static code analysis from the sonarqube library"
        }
    }

============================
Configure the Library Source
============================

Now that we have a GitHub repository containing pipeline libraries, we have
to tell JTE where to find them. 

This is done by configuring a **Library Source** in Jenkins. 

.. note:: 

    You can define as many Library Sources as you need.  They can be 
    defined globally for the entire Jenkins instance in
    ``Manage Jenkins > Configure System > Jenkins Templating Engine`` 
    or under the ``Jenkins Templating Engine`` configuration section on 
    Folders. 

To make our libraries accessible to every job configured to use JTE on the
Jenkins instace: 

1. In the lefthand navigation menu, click ``Manage Jenkins``
2. Select the first option, ``Configure System``
3. Scroll down to the ``Jenkins Templating Engine`` configuration section
4. Click ``Add`` under ``Library Sources`` 
5. Ensure the ``Library Provider`` is set to ``From SCM`` 
6. Select ``Git`` as the ``SCM`` type 
7. Enter the **https** repository URL
8. In the ``Credentials`` drop down menu, select the github credential created during the prerequisites
9. Enter ``libraries`` in the ``Base Directory`` text box
10. Click ``Save`` 

.. image:: ../../../images/learning-labs/jte-the-basics/library_source.gif
   :align: center