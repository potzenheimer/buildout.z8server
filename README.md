buildout.z8server
=================

Buildout installing the necessary tools on the z8server. Just boostrap the 
buildout and run

    python bootstrap.py -c deployment.cfg
    bin/buildout -c deployment.cfg


Note:
-----

In order to make this reusable it could also be an option to add a dedicated 
buildout profile **z8.cfg** to be explicit and potentially be able to run
this simple webserver setup on several machines (via different profiles).


Provided services:
------------------

* Nginx
* Varnish
* haproxy
* runscript
* logrotation
* supervisord (controlling the isntalled zope instances)

Cofiguration
------------

All configuration is based in variables. In order to extend the buildout for
a new site, add or copy the relevant parts starting with "zopeX", by simply 
appending a higher number, e.g for haproxy context switching:

    acl ${sites:zope1}_cluster hdr_beg(host) -i ${hosts:zope1}
    # Check that we have at least one node up in the zope1 cluster
    acl ${sites:zope1}_cluster_up nbsrv(default) gt 0

where you would simply copy the part and replace zope1 with zope2 accordingly.
