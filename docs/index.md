# Getting started

## Hardware information

<style>
    table, tr, th, td {
        border: 1px solid gray !important;
        border-collapse: collapse;
    }
</style>

<table>
<tr>
<td><strong>Compute</strong></td>
<td>
<ul style="list-style: none">
<li>Model name: Intel(R) Xeon(R) CPU X5660 @ 2.80GHz</li>
<li>Architecture: x86_64</li> 
<li>24 core and 48 threads</li> 
<li>32GiB system memory</li> 
<li>Four 8GiB DIMM DDR3 SSD</li> 
</ul>
</td>
</tr>
<tr>
<td><strong>Storage</strong></td>
<td>
<ul style="list-style: none">
<li>/public 1.2PB usable storage capacity</li>
<li>/collab 1.8TB usable storage capacity</li>
</ul>
</td>
</table>

## Web access

* <https://stash.osgconnect.net/public>
* <https://stash.osgconnect.net/collab> 

## xrootd access

You can also access the server using xrootd. Below is an example of copying a file with xrootd.

    xrdcp root://stash.osgconnect.net:1094//osgconnect/public/<user_id>/<file> -> /tmp