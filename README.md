# CCNA2020_DHCPv4
Dynamic Host Config Protocol

最常見的情境是 Wi-Fi AP 配置靜態 IP 予進入此私有網域的設備如手機或筆電。（飛機上或是捷運內。）

此協定屬於 OSI 七層中的第三層，邏輯網路層，故網管需要把三層的設備準備好喔～

雖然擁有此功能的設備，某些也能做靜態設定，但是這就失去本設備的優勢功能囉！（沒有意義的行為。）

# Public IP within NAT

通常家用或企業會向電信公司或 ISP 租用一個公有（Gloabl）IP 位址，然而這對需要管理網路的企業來說，相當不便，
故企業會自行設定 static IP 、 家庭則會運用 DHCP dynamic 配置 static IP，兩者再利用 NAT 映射（對應）到數量有限的 public IP。 

經過 NAT 轉換後，對於外部網路存取內部網路的途徑等於做了一道安全防護的閘門。

# Static IP within DHCP

對於動態設置（分配）私有邏輯網路給設備是 DHCP 設備的功能與優勢，節省了網管人的靜態部署的不便。

# Broadcast as query

新設備進入此內部網路時，需要被配置一個私有的 Local 網段的 IP 位址，故此設備會發出廣播詢問 DHCP server，
ask: Hi 請問你是 DHCP server 嗎？我是新加入的成員，需要有個能辨識的家庭位址。

通常廣播網域中所有能夠接收廣播封包的設備都會回應或是過濾，但是在 DHCP 的 case 上，其他非 DHCP 功能的設備完全
不會理會此類封包，只有真正具備 DHCP 功能的設備才會理會。

# Reply from DHCP server

具備動態配置主機協定功能的伺服器或是設備回應內容：

http://www.tsnien.idv.tw/Manager_WebBook/ppt/chap5/5-4-3%20DHCP%20封包格式.pdf (詳見封包格式)

1. stactic IP

2. subnet (本機網域非遠端網域)

3. valid time

4. GW & DNS (閘道路由位址與域名伺服器位址)

# DHCP server/client

主從式溝通模式，DHCP 採用 UDP (第四層傳輸層)來進行溝通，伺服器端阜號為 67，用戶端阜號為 68。

# Config Procedures

              Discovery 用戶端→DHCP伺服器

                 |

                 V

               Offer DHCP伺服器→用戶端

                |

                V

              Request 用戶端→DHCP伺服器

                |

                V

               Ack DHCP伺服器→用戶端

               

# Free IP Resorces

當設備關機或是離開此區域網域時，這些 IP 位址會歸還。

# DHCPv6

因為 IPv6 位址很多，並非如同 IPv4 位址那樣數量那麼有限，所以 DHCPv6 有另外的運作方式，此議題不詳述。

