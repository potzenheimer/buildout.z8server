buildout.z8server
=================

Buildout installing the necessary tools on the z8server. Just boostrap the 
buildout and run

    python bootstrap.py -c deployment.cfg
    bin/buildout -c deployment.cfg


Note:
-----

In order to make this reusable it could also be an option to add a sedicated 
buildout profile **z8.cfg** to be explicit and potentially be able to run
this simple webserver setup on several machines (via different profiles).


