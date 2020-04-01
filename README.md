# dfhz_hue_mpack
<h1>DFHeinz Hue Management Pack for Ambari.</h1>

Install Hue with Ambari using this management pack created by DFHz.  The original Ambari 2.x Hue Service started
by [Kyle Joe](https://github.com/EsharEditor) was upgraded for HDP3 and Hue 4.x by DFHz before starting on this Hue Management Pack.  You can see more info on the HDP3 repo: [HDP3 Hue Service](https://github.com/steven-dfheinz/HDP3-Hue-Service). Also see https://gethue.com for more information, versions, and official Hue documentation.

#### Version Key
- &nbsp;&nbsp;hue_mpack-3.11.0-0.0.tar.gz - Hue 3.11.0 HDP 2.x
- &nbsp;&nbsp;hue_mpack-3.11.0-0.1.tar.gz - Hue 3.11.0 HDP 3.x (coming soon)
- &nbsp;&nbsp;hue_mpack-4.6.0-0.0.tar.gz - Hue 4.6.0 HDP 2.x (coming soon)
- &nbsp;&nbsp;hue_mpack-4.6.0-0.1.tar.gz - Hue 4.6.0 HDP 3.x

#### Usage Notes
- Make sure you get the correct /raw/ link if using the github links to download (see sample below).
- Be sure to restart ambari after all M-Pack changes.
- Your nodes need to be able to install all dependencies. Epel Repository is helpful here.

#### Management Pack Installaion
- Example  Install & Remove commands are:

<pre>ambari-server install-mpack --mpack=https://github.com/steven-dfheinz/dfhz_hue_mpack/raw/master/hue_mpack-4.6.0-0.1.tar.gz --verbose
ambari-server restart
ambari-server uninstall-mpack --mpack-name=hue-ambari.mpack
ambari-server restart</pre>


#### HDP 2.x Usage Notes


#### HDP 3.x Usage Notes

- There is a current bug in User Group Management for HDP 3.x.  The work around is the following python command before installing Hue
<pre>python /var/lib/ambari-server/resources/scripts/configs.py -u admin -p admin -n [CLUSTER_NAME] -l [CLUSTER_FQDN] -t 8080 -a set -c cluster-env -k  ignore_groupsusers_create -v true</pre>
**** be sure to get the correct [CLUSTER_NAME] and [CLUSTER_FQDN] for command above

#### Coming Soon
- Create a Stack Structure
- Hue 3.11.0 Versions - [HDP3-Hue-Service](https://github.com/steven-dfheinz/HDP3-Hue-Service)
- HDP 2.x Versions - [ambari-hue-service](https://github.com/EsharEditor/ambari-hue-service)
- Revisions & Improvements to HDP 3.x Functionality - [HDP3-Hue-Service](https://github.com/steven-dfheinz/HDP3-Hue-Service)