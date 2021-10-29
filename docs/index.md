# Stash service and CephFS cluster

## Introduction

The purpose of the stash.osgconnect.net server is to provide read access to the distributed filesystem (CephFS) on the [OSG Connect Infrastructure](https://opensciencegrid.org/) storage. The storage hosts project space (by default 500 GB per user) to facilitate computational research on OSG beyond what is available in their home directories. Stash allows for users to have access to a larger storage allocation and for the user to access data there from jobs running on worker nodes on OSG using the stashcp tool or xrootd.

## Hardware on the CephFS cluster

<style>
    table, tr, th, td {
        border: 1px solid gray !important;
        border-collapse: collapse;
    }
</style>

The CephFS cluster has 33 nodes from three generations of purchases. 

Generation 1 nodes

<table>
<tr><th>Quantity</th><td>14</td></tr>
<tr><th>Model</th><td>Dell PowerEdge R730xd</td></tr>
<tr><th>Processor</th><td>2x Intel(R) Xeon(R) CPU E5-2650 v3 @ 2.30GHz</td></tr>
<tr><th>Memory</th><td>6x 16GB DDR4, 96 GB total</td></tr>
<tr><th>Disk</th><td>2x 1TB 7.2k RPM HDD SATA for system, 12x 6TB 7.2k RPM HDD SAS for Ceph</td></tr>
</table>

Generation 2 nodes

<table>
<tr><th>Quantity</th><td>17</td></tr>
<tr><th>Model</th><td>Dell PowerEdge R730xd</td></tr>
<tr><th>Processor</th><td>2x Intel(R) Xeon(R) CPU E5-2650 v3 @ 2.30GHz</td></tr>
<tr><th>Memory</th><td>6x 16GB DDR4, 96 GB total</td></tr>
<tr><th>Disk</th><td>2x 1TB 7.2k RPM HDD SATA for system, 16x 8TB 7.2k RPM HDD SAS for Ceph</td></tr>
</table>

Generation 3 nodes

<table>
<tr><th>Quantity</th><td>2</td></tr>
<tr><th>Model</th><td>Dell PowerEdge R740xd</td></tr>
<tr><th>Processor</th><td>2x Intel(R) Xeon(R) Silver 4110 CPU @ 2.10GHz</td></tr>
<tr><th>Memory</th><td>12x 16GB DDR4, 192 GB total</td></tr>
<tr><th>Disk</th><td>2x 240GB BOSS for system, 18x 12TB 7.2k RPM HDD SAS for Ceph</td></tr>
</table>

## Software on the stash server

* nginx server 
* xrootd server

## Web access via stash

* <https://stash.osgconnect.net/public>
* <https://stash.osgconnect.net/collab> 

## xrootd access via stash

You can access the Ceph cluster with xrootd. Below is an example of copying a file with xrootd.

    xrdcp root://stash.osgconnect.net:1094//osgconnect/public/<user_id>/<file> -> /tmp

    stashcp file_name stash://stash.osgconnect.net/

## stashcp tool for copying data

You can copy files to the Ceph cluster using the stashcp tool.

    stashcp output.dat stash:///osgconnect/public/<username>/output/output.dat
