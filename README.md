# HSCP code

The task is to compile/build the code using the command line:
<br>
scram b -j 16
<br>
Initially, the complie fails because of a problem on the HSCPAnalysis/muSimHits/pluginsmuSimHits.cc file, the main problem was the package to use the next line:
<br>
rollId.station
