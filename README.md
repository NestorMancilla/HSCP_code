# HSCP code

The task is to compile/build the code using the command line:
<br>
scram b -j 16
<br>
Initially, the build was failing due to a problem in the file HSCPAnalysis/muSimHits/plugins/muSimHits.cc, the main problem was the package to use the following line:
<br>
rollId.station
<br>
For this reason, the Roumyana solution was to update the package MuonDetId on the DataFormats. Now, the command still fails.  Roumyana believes that the code needs to be updated to the CMSSW_12_0_2 version, particularly the geometry and she sent the following links
<br>
https://github.com/cms-sw/cmssw/issues/31061
<br>
https://twiki.cern.ch/twiki/bin/view/CMSPublic/WorkBookTroubleShooting#Error_undefined_reference
<br>
The idea would be related to migrating ED modules to use esConsumes, with respect to Geometry in particular MuonGeometryRecord, since the error says that the reference is not defined, at least that's what I understand. I tried to update the "Geometry/Records" package, but it didn’t work. I guess it is something related to data access, but I don’t know how to apply the idea. 
<br>
https://twiki.cern.ch/twiki/bin/view/CMSPublic/SWGuideHowToGetDataFromES#Registering_for_data_access
<br>
