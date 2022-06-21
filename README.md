# HSCP code

From the original code:
<br>
Changes on the file DataFormats/MuonDetId/interface/RPCDetId.h
<br>
Add
<br>
bool isIRPC() const{
<br>
     return ((this->region() !=0) && ((this->station() ==3) || (this->station() ==4)) && (this->ring() == 1));
     <br>
     }
<br>
Changes on the file HSCPAnalysis/muSimHits/plugins/muSimHits.cc
<br>
      
      DETId detId = DetId(simHitRPC.detUnitId());
      <br>
      if(detId.subdetId() == MuonSubdetId::RPC)
      <br>
      {
      <br>
        RPCDetId rollId(detId);
        <br>
        cout << simHitRPC.particleType() << endl;
        <br>
        cout << rollId.station() << endl;
        <br>
        cout << "is iRPC: " << rollId.isIRPC();
        <br>
        //cout << rollId.station() << endl;
        <br>
        //cout << "is iRPC: " << roll->isIRPC();
        <br>
        
        DTLayerId layerId(detId);
        <br>
        cout << "DT: " << layerId.station() <<endl;
        <br>
        //cout << "DT: " << dtLayerId.station() <<endl;
        <br>
To solve the problems:
<br>
undefined reference to char const* edm::typelookup::className<MuonGeometryRecord>()
<br>
undefined reference to `std::type_info const& edm::typelookup::classTypeInfo<MuonGeometryRecord>()'
<br>
Changes on the file HSCPAnalysis/HSCPRecHits/plugins/BuildFile.xml
  <br>
  Add the code line:
  <br>
  use name="Geometry/Records"/
