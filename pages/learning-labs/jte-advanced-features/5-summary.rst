.. _JTE Advanced Features Summary: 

-------
Summary
------- 

===========================
Default Step Implementation
===========================

The Default Step Implementation is used for creating steps on the fly from the Pipeline Configuration. 

It works by leveraging container images as pipeline runtime dependencies, executing a command or script 
inside the container image, and then allowing you to stash artifacts generated by the step. 

Care should be taken when exposing this functionality to users. 

========================
Pipeline Lifecycle Hooks
========================

The Jenkins Templating Engine exposes a feature called Pipeline Lifecycle Hooks that allows methods 
defined within library steps to register themselves to be automatically executed in response to events 
from the pipeline. 

These annotations accept Closure parameters for conditional hook execution to dynamically determine if a 
hook should be invoked. 

==========================
Multi-Method Library Steps
==========================

Steps contributed by libraries can define more than one method within the step.  This is most commonly used 
when creating steps representing utilities.  