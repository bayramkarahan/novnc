<img src=https://github.com/bayramkarahan/novncservice/raw/master/1.png/>

# noVnc Nedir?
novnc web tarayıcı ile vnc portuna erişimi sağlayan(masaüstüne) bir uygulamadır. Uzak veya yerelde tarayıcı üzerinden istenilen bilgisayara erişmeyi sağlamaktadır.
Avantajları şunlardır:

1- Her türlü web tarayıcısını kullanan cihazla uzak masaüstüne erişim imkanı sumaktadır. 

2- Hiç bir cihaz ve tarayıcı kısıtlaması olmadan. 

3- Erişen cihazlara hiçbir ek yazılım kurmadan.

Detaylı Bilgi için, https://github.com/novnc/noVNC ve https://novnc.com/info.html adreslerini ziyaret edebilirsiniz.

# Kurulum:
https://github.com/novnc/noVNC/releases adresinden indirip utils altındaki uygulamayı gerekli parametreleri vererek kullanabilirsiniz.

Debian sid depolarında olan bir pakettir. sudo apt install novnc ile kurabilirsiniz.

# Kullanım:
Kullanmak x11vnc kurulu ve çalışıyor olması gerekmektedir. 

sudo apt install x11vnc komutuyla kurulur. Çalıştırılır. Bunun için gerekli araştırmayı yapabilirsiniz. Aşağıdaki sayfaları da kullanabilirsiniz.

https://bayramkarahan.blogspot.com/2020/04/x11vnc-servis-olarak-calstrma.html

https://bayramkarahan.blogspot.com/2019/02/x11vnc-yazlmnn-sistem-acllsnda-otomatik.html

https://bayramkarahan.blogspot.com/2018/03/windowstan-linuxa-uzak-masaustu-ersimi.html

novnc_proxywebsockify'ı otomatik olarak indirmek ve başlatmak için komut dosyası bir mini web sunucusu ve WebSockets proxy'si içerir. bu --vnc seçenek çalışan bir VNC sunucusunun konumunu belirtmek için kullanılır:

./utils/novnc_proxy --vnc localhost:5902

bu komutu verince aşağıdaki resimde görünen bir çıktıyı alıyoruz.
<img src=https://github.com/bayramkarahan/novncservice/raw/master/2.png/>
Bu Kullanımda ise 6085 portundan erişim açılıyor. 5905 ile erişim kapatılmış oluyor.

./utils/novnc_proxy --vnc localhost:5905 --listen 0.0.0.0:6085

Sunucular bağlamında, 0.0.0.0 "yerel makinedeki tüm IPv4 adresleri" anlamına gelebilir. Eğer bir ana bilgisayarda 192.168.1.1 ve 10.1.2.1 olmak üzere iki IP adresi varsa ve ana bilgisayarda çalışan bir sunucu 0.0.0.0'da dinleyecek şekilde yapılandırılmışsa, bu IP adreslerinin her ikisinde de erişilebilir olacaktır.
# novncservice eklentisi
novncservice paketi kurulursa x11vnc ve noVnc sisteme kuulur ve gereklşi ayarlar yapılır. Tarayıcı üzerinden erişim yapılabilir.
<p> Bu paket 5905 portunu 6085 üzerinden paylaştırıyor.</p>

Tarayıcıya;

` 
ip:6085/vnc.html 
`

adressinden masaüstüne erişilebilir.
<img src=https://github.com/bayramkarahan/novncservice/raw/master/3.png/>


*Kaynaklar:*
* https://community.linuxmint.com/tutorial/view/2334
* https://forums.linuxmint.com/viewtopic.php?p=2270847
* https://wiki.archlinux.org/title/x11vnc
