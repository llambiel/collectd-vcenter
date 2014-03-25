collectd-Vcenter
================
This is a python plugin for collecting Vcenter statistics.

It requires the python plugin in collectd in order to gather data.

The script collect the following metrics:

- Hosts CPU usage
- Hosts Memory usage
- Hosts Healthstatus
- VMs count (Running, stopped, total)
- Datastores space usage

Hosts & VMs count metrics are aggregated at hosts, cluster, datacenter & zone level

Requirements
------------
*collectd*  
collectd must have the Python plugin installed. See (<http://collectd.org/documentation/manpages/collectd-python.5.shtml>)

*pysphere*
pyshere lib must be installed. See (<https://code.google.com/p/pysphere/>)

Example
-------
    <LoadPlugin python>
        Globals true
    </LoadPlugin>

    <Plugin python>
        # vcenter.py is at /opt/collectd/lib/collectd/python
        ModulePath "/usr/lib64/collectd/"
        Import vcenter
        <Module vcenter>
                Username "Vcenter read rights username here"
                Vcenter "myvcenter1 myvcenter2"
                Password "Vcenter user password here"
                Verbose false
        </Module>
    </Plugin>


Credits
-------

In production use at [exoscale](https://www.exoscale.ch) and licensed under the MIT License.
