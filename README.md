# CCNA2020_DHCP
Dynamic Host Config Protocol


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

(to be continued...)
