.. _JTE The Basics: 

---------------
JTE: The Basics
---------------

The purpose of this lab is to introduce you to the Jenkins Templating Engine as a **framework**
for building Jenkins pipelines in a way that allows you to share pipeline templates between teams. 

By being able to build reusable, tool-agnostic pipeline templates and apply them to multiple
applications simultaneously, you can then **remove** individual Jenkinsfiles from each 
source code repository. 

.. important:: 

    In JTE, we talk a lot about the concept of governance.  When we say governance, we mean 
    that JTE allows you to **enforce** a common software delivery process by applying the 
    the **same** pipeline template to *multiple* repositories at the same time. 

    The modularity that JTE promotes allows you to do this across teams *regardless* of the 
    specific tools that each application may be using. 

=================
What You'll Learn
=================

* Configure your first tool-agnostic pipeline template 
* Create your first set of pipeline libraries to provide tool-specific implementations of steps
* Create your first pipeline configuration file that implements the template
* Learn the difference types of jobs available in Jenkins and when to use them 
* Learn how to take the Jenkinsfile (pipeline template) **out** of the repository
* Learn how to consolidate pipeline configurations and apply the same template across multiple repositories


Click ``Next`` to move on to this lab's prerequisites. 


.. toctree::
   :hidden:
   :titlesonly:

   1-prerequisites
   2-pipeline-job
   3-first-libraries 
   4-first-configuration-file
   5-swap-to-gradle 
   6-multibranch 
   7-github-org 
   8-summary
