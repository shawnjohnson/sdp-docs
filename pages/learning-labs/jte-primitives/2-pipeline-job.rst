.. _JTE Primitives Pipeline Job: 

---------------------
Create a Pipeline Job
---------------------

Before we get started, we'll need to create a Pipeline job in Jenkins 
that we can play around with. 

Feel free to reuse the Pipeline job created during JTE: The Basics or 
follow the :ref:`same instructions<JTE The Basics Pipeline Job>` to 
create a new job for this lab. 

When you're finished, you should have: 

**1. A pipeline template that reads:** 

.. code:: groovy 

    build()
    static_code_analysis()

**2. A pipeline configuration of:**

.. code:: groovy

    libraries{
        maven
        sonarqube
    }

.. note:: 

    If you're reusing the same Pipeline job, your pipeline configuration may 
    specify the ``gradle`` instead of the ``maven`` library.  Either will do 
    for the purposes of this lab. 


This Pipeline job is going to be the playground within which we learn about 
the different pipeline primitives for the rest of the lab. 