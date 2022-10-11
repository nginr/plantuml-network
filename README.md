# plantuml-network

A simple lib to use office icon and rectangle to draw network topology diagram.

# sample
```puml
@startuml NW
title Network Sample
!include https://raw.githubusercontent.com/Gowa2017/plantuml-network/main/network.puml

cloud "net"


NWBoundary(a, "Test Env", "192.168.10.1/24") {
    NWFirewall(fw, "FireWall")
    NWSwitch(sw, "Switch")
    NWServer(server, "Server")
    NWServerCluster(cluster, "Cluster")
    NWRouter(router, "Router","192.168.11.1/24")
    NWServerDatabase(db, "Database")
    NWServerProxy(proxy,"Proxy")
    NWWorkstation(workstation,"WorkStation")
    NWLaptop(laptop,"Laptop")
    NWMobile(mobile, "Mobile")
    NWLvs(lvs, "LVS")

    laptop --up-- router
    workstation --up-- router
    mobile --up-- router

    sw --up-- fw

    server --up-- sw
    proxy --right-- sw
    db --up-- sw
    cluster --up-- sw
    lvs --up-- sw

    router --up-- fw
    fw --up-- net
}

@enduml
```
![image](https://user-images.githubusercontent.com/33367355/177686822-a9180a1f-d5b1-46d7-88b4-807ff386a52d.png)


@enduml
