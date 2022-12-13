# `Домашнее задание к занятию "10.1. Keepalived/vrrp"` - `Черепанов Владислав`

### Задание 1. 

Требуется развернуть топологию из лекции и выполнить установку и настройку сервиса Keepalived. 

```
vrrp_instance test {

state "name_mode"

interface "name_interface"

virtual_router_id "number id"

priority "number priority"

advert_int "number advert"

authentication {

auth_type "auth type"

auth_pass "password"

}

unicast_peer {

"ip address host"

}

virtual_ipaddress {

"ip address host" dev "interface" label "interface":vip

}

}

```

*Пришлите  конфигурацию сервисов для каждой ноды и скриншот вывода команды  ip address.*
Node 1
![Скриншот-1 keepalived conf node 1](https://github.com/plusvaldis/10-01-hw/blob/main/img/img0.png)
![Скриншот-2 keepalived conf node 2](https://github.com/plusvaldis/10-01-hw/blob/main/img/2.png)
![Скриншот-3 node 1 ip a](https://github.com/plusvaldis/10-01-hw/blob/main/img/3.png)
![Скриншот-4 node 2 ip a](https://github.com/plusvaldis/10-01-hw/blob/main/img/4.png)

## Дополнительные задания (со звездочкой*)

Эти задания дополнительные (не обязательные к выполнению) и никак не повлияют на получение вами зачета по этому домашнему заданию. Вы можете их выполнить, если хотите глубже и/или шире разобраться в материале.
 
### Задание 2*.

Проведите тестирование работы ноды, когда один из интерфейсов выключен. Для этого:
- добавьте еще одну виртуальную машину и включите ее в сеть;
- на машине установите wireshark и запустите процесс прослеживания интерфейса;
- запустите процесс ping на виртуальный хост;
- выключите интерфейс на одной ноде (мастер), остановите wireshark;
- найдите пакеты ICMP, в которых будет отображён процесс изменения MAC адреса одной ноды на другой. 

 *Пришлите скриншот до и после выключения интерфейса из Wireshark.*
 Вкладываю скриншоты выполнив не wireshark а tcpdump
![Скриншот-1 keepalived enable master](https://github.com/plusvaldis/10-01-hw/blob/main/img/5.png)
![Скриншот-2 keepalived down master](https://github.com/plusvaldis/10-01-hw/blob/main/img/6.png)
 
