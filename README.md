# HSCP code

The task is to compile/build the code using the command line:
<br>
scram b -j 16
<br>
Initially, the build was failing due to a problem in the file HSCPAnalysis/muSimHits/plugins/muSimHits.cc, the main problem was the package to use the following line:
<br>
rollId.station
<br>
For this reason, the Roumyana solution was to update the package MuonDetId on the DataFormats. Now I don’t understand the error, but Roumyana said that the code needs to be updated following the CMSSW general changes and she sent the following links
<br>
https://github.com/cms-sw/cmssw/issues/31061
<br>
https://twiki.cern.ch/twiki/bin/view/CMSPublic/WorkBookTroubleShooting#Error_undefined_reference
<br>
The CMSSW version is 12_0_2. I attach a screenshot of the error I get.
