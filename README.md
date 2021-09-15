```go
package main

import (
  "fmt"
  "html"
  "strconv"
)

var helloMsg string = html.UnescapeString("Hi there! &#" + strconv.Itoa(128406) + ";")

func main() {
  slnnk := Engineer{
    Name:     "Anton",
    Age:      30,
    Location: "Russia, Rostov-on-Don",
    Company:  "DDoS-Guard",
    Position: "Backend Developer / Lead DevOps Engineer",
    TechStack: TechStack{
      Code:       []string{"Go", "Python", "Perl"},
      DBs:        []string{"Clickhouse", "Cassandra", "PostgreSQL", "MySQL", "MongoDB"},
      MQ:         []string{"NATS", "RabbitMQ", "ZMQ"},
      Monitoring: []string{"Prometheus", "Loki", "Grafana", "Promtail", "Graylog", "Zabbix", "Sentry"},
      Containers: []string{"Docker", "Docker Compose", "Nomad"},
      CI:         []string{"Gitalb CI", "Jenkins"},
      Misc:       []string{"ETCD", "Redis", "Ansible", "Consul", "Nexus", "Nginx", "Traefik"},
    },
  }

  fmt.Println(slnnk.Hi())
}

type Engineer struct {
  Age       uint8
  Name      string
  Location  string
  Company   string
  Position  string
  TechStack TechStack
}

type TechStack struct {
  Code       []string
  DBs        []string
  Monitoring []string
  MQ         []string
  Containers []string
  Misc       []string
}

func (e *Engineer) Hi() string {
  return helloMsg
}
```
