```puml
@startuml

node "External App" as external1
node "External App" as external2

node "Kubernetes Cluster" {
    component "Service"as service
    component "Service External" as external
    node "Node 1" {
        component "Pod Client" as client
        component "Pod ..." as podb2
    }
    node "Node 2" {
        component "Pod A" as poda2
        component "Pod A" as poda3
        component "Pod ..." as podb1
    }
}

client -up-> service
service --> poda2
service --> poda3
external --> external1
external --> external2
poda2 --> external
poda3 --> external

@enduml
```