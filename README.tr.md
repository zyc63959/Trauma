# Sunucusuz CF Çalışanları ve Sayfaları kullanarak Truva Atı'nı dağıtın

🇮🇷[Farsça](README.fa.md)| 🇹🇷[Türkçe](README.tr.md)

🇬🇧[İngilizce](README.md)\|[🇩🇪 Almanya](README.de.md)

Bu, Cloudflare Worker platformunu temel alan bir komut dosyasıdır. Orijinal versiyona dayanarak, Truva atı yapılandırma bilgilerini görüntüleyecek ve bunu abonelik içeriğine dönüştürecek şekilde değiştirildi. Bu betiği kullanarak Truva atı yapılandırma bilgilerini çevrimiçi yapılandırmayı kullanarak Clash veya Singbox gibi araçlara kolayca dönüştürebilirsiniz.

[TG Kanalı](https://t.me/F_NiREvil)

![rainbow](https://github.com/NiREvil/vless/assets/126243832/1aca7f5d-6495-44b7-aced-072bae52f256)

## İçindekiler

-   [İşçi dağıtım yöntemi](#Workers-deployment-method)
-   [Sayfa dağıtım yöntemi](#Pages-deployment-method)
-   [Proxy IP](#proxyIP)
-   [Ortam Değişkeni açıklaması](#Environment-variables-description)
-   [Video eğitimleri](#Video-tutorials)![rainbow](https://github.com/NiREvil/vless/assets/126243832/1aca7f5d-6495-44b7-aced-072bae52f256)

<details>
<summary> Use </summary>

-   Bu proje yalnızca öğrenme, araştırma ve güvenlik testi amacıyla tasarlanmış ve geliştirilmiştir. Güvenlik araştırmacılarına, akademisyenlere ve teknoloji meraklılarına ağ iletişim teknolojisini anlamak ve uygulamak için bir araç sağlamayı amaçlamaktadır.
    </details>

<details>
<summary> Legality </summary>
  
  - Users must comply with local laws and regulations when downloading and using this project.
  - Users are responsible for ensuring that their actions comply with the laws, regulations and other applicable requirements of their region

</details>

<details>
<summary> Risk warning </summary>
  - Avoid leaking node configuration information by submitting false node configurations to the subscription service 
</details>

## İşçi dağıtım yöntemi

1.  Cloudflare Worker'ı dağıtın:

    -   Cloudflare Worker konsolunda yeni bir Worker oluşturun.

    -   İrade[işçi.js](https://github.com/NiREvil/Trauma/blob/main/_worker.js)İçeriği Worker düzenleyicisine yapıştırın.

    -   3\. satırı değiştir`password`Kendinize göre değiştirin**şifre**

    -   Alternatif olarak doğrudan dağıtmak için aşağıdaki düğmeye tıklayabilirsiniz.

    [![Deploy to Cloudflare Workers](https://deploy.workers.cloudflare.com/button)](https://deploy.workers.cloudflare.com/?url=https://github.com/NiREvil/Trauma)

2.  Tercih edilen rotayı ekle:
    -   Vermek`addresses`Tercih edilen alan adını/tercih edilen temiz IP'yi formata göre ekleyin. Bağlantı noktası numarası yoksa varsayılan TLS bağlantı noktası 443'tür ve # işareti açıklama takma adıdır, örneğin:
        ```js
        let addresses = [
        	// Everything you want, Cloudflare Domains & Clean IP addresses.
        	'www.speedtest.net:443#Ni1',
        	'time.is#Ni2',
        	'zula.ir#Ni3',
        	'www.visa.com.sg:2053#Ni4',
        ];
        ```

3.  Abonelik içeriğine erişin:
    -   erişim`https://[YOUR-WORKERS-URL]/[password]`Abonelik içeriğini alın.
    -   Örneğin`https://vless.trauma.workers.dev/auto`Bu sizin evrensel uyarlanabilir abonelik adresinizdir.
    -   Örneğin`https://vless.trauma.workers.dev/auto?sub`Base64 abonelik formatı; PassWall, SSR+ vb. için uygundur.
    -   Örneğin`https://vless.trauma.workers.dev/auto?clash`OpenClash vb. için uygun Clash abonelik formatı.
    -   Örneğin`https://vless.trauma.workers.dev/auto?sb`singbox abonelik formatı, singbox vb. için uygundur.

4.  Çalışanlara özel bir alan adı bağlayın:
    -   İşçi konsolunda`trigger`sekme, aşağıya tıklayın`Add a custom domain`。
    -   CloudFlare alan adı çözümleme hizmetine aktardığınız ikincil alan adını girin, örneğin:`vless.trauma.com`Tıkladıktan sonra`Add a custom domain`, sertifikanın geçerli olmasını bekleyin.

![rainbow](https://github.com/NiREvil/vless/assets/126243832/1aca7f5d-6495-44b7-aced-072bae52f256)

## Sayfa dağıtım yöntemi

1.  Cloudflare Sayfalarını Dağıtın:
    -   Çatal[Github'daki bu proje](https://github.com/NiREvil/Trauma/fork)
    -   Cloudflare Sayfaları konsolunda seçin`Connected to Git`Bundan sonra seçin`trauma`Öğeden sonra tıklayın`Start setting up`。
    -   var olmak`Setting up build and deployment`Sayfanın alt kısmında`Environment variables (advanced)`daha sonra birleştir[Değişken ekle](#Environment-variables-description),
    -   Değişken adını girin**ŞİFRE**, değer şifrenizdir, ardından tıklayın`Save and deploy`Bu kadar.

2.  Tercih edilen rotayı ekle:
    -   Değişken ekle`ADD`Yerel statik tercihli hat; bağlantı noktası numarası yoksa, varsayılan TLS bağlantı noktası 443'tür ve # numarasının ardından bir açıklama takma adı gelir, örneğin:
        ```js
         discord.com#You can just put the domain name as follows
         www.speedtest.net:443#Ni1
         time.is#Ni2
         zula.ir#Ni3
         www.visa.com.sg:2053#Ni4
         104.17.152.41#IP Also available
         [2606:4700:e7:25:4b9:f8f8:9bfb:774a]#IPv6 also OK
        ```

3.  Abonelik içeriğine erişin:
    -   erişim`https://[YOUR-PAGES-URL]/[password]`Abonelik içeriği mevcuttur.
    -   Örneğin`https://trauma.pages.dev/auto`Bu sizin evrensel uyarlanabilir abonelik adresinizdir.
    -   Örneğin`https://trauma.pages.dev/auto?sub`Base64 abonelik formatı; PassWall, SSR+ vb. için uygundur.
    -   Örneğin`https://trauma.pages.dev/auto?clash`OpenClash vb. için uygun Clash abonelik formatı.
    -   Örneğin`https://trauma.pages.dev/auto?sb`singbox abonelik formatı, singbox vb. için uygundur.

4.  CNAME özel alan adını Sayfalara bağlayın:
    -   Sayfalar konsolunda`Custom domains`sekme, aşağıya tıklayın`Set up a custom domain`.
    -   Özel ikincil alan adınızı girin, kök alan adınızı kullanmamaya dikkat edin, örneğin:
    -   Size atanan alan adı`fuck.cloudns.biz`, ardından doldurulacak özel bir alan ekleyin`iran.fuck.cloudns.biz`Bu kadar;
    -   Cloudflare gereksinimlerine göre alan adı DNS servis sağlayıcınız iade edilecek ve özel alan adı eklenecektir.`trauma`CNAME kaydı`trauma.pages.dev`Bundan sonra tıklayın`Activate Domain`Bu kadar.

![rainbow](https://github.com/NiREvil/vless/assets/126243832/1aca7f5d-6495-44b7-aced-072bae52f256)

## Proxy IP

1.  Cloudflare sayfalarında dağıtım yaparken proxyIP'yi 4. satırda ayarlayabilirsiniz.`_worker.js`dosya. veya ortam değişkenini ayarlayın, değişken adı`PROXYIP`

2.  Worker.dev'de dağıtım yaparken proxyIP'yi 4. satırda ayarlayabilirsiniz.`_worker.js`dosya. veya ortam değişkenini ayarlayın, değişken adı`proxyIP`

### ProxyIP nasıl bulunur?

[(KAYNAK)](https://github.com/NiREvil/vless/edit/main/sub/ProxyIP.md)

## Ortam değişkenleri açıklaması

> [!NOT]Bunlardan sadece ikisini ayarlamak yeterli, ilk değişken`PASSWORD`ve ikinci`PROXYIP`, aşağıdaki tabloda listelenen değişkenler yalnızca eğitim amaçlıdır ve ek açıklamalar içindir.![rainbow](https://github.com/NiREvil/vless/assets/126243832/1aca7f5d-6495-44b7-aced-072bae52f256)

| değişken ismi    | Örnek                                                                                                                                          | Açıklama                                                                                                                                                                                       |
| ---------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ŞİFRE            | Oto                                                                                                                                            | Her değeri alabilir                                                                                                                                                                            |
| PROXY IP         | [buraya tıklayın](https://github.com/NiREvil/vless/edit/main/sub/ProxyIP.md)veya kullan`ni.radically.pro`                                      | CloudFlareCDN sitesine erişmek için bir proxy düğümü olarak (ProxyIP'ler arasında kullanılan birden fazla ProxyIP'yi destekler)`,`veya aralık olarak satır besleme)                            |
| EKLEMEK          | [zula.ir,www.csgo.com:2087](http://zula.ir,www.csgo.com:2087)                                                                                  | Yerel tercih edilen alan adı/tercih edilen IP (birden fazla öğeyi destekler)`,`veya aralık olarak satır besleme)                                                                               |
| ADDAPI           | <https://raw.githubusercontent.com/NiREvil/Trauma/main/cleanIPs.txt>                                                                           | Açıklamaya gerek yok herkes anlıyor                                                                                                                                                            |
| ADCCSV           |                                                                                                                                                | Açıklamaya gerek yok herkes anlıyor                                                                                                                                                            |
| DLS              | 8                                                                                                                                              | Açıklamaya gerek yok herkes anlıyor                                                                                                                                                            |
| TGTOKEN          | 6894123456:XXXXXXXXXX0qExVsBPUhHDAbXXXXXqWXgBA                                                                                                 | TG bildirimlerini göndermek için robot belirteci                                                                                                                                               |
| SİZ YAPIYORSUNUZ | 6946912345                                                                                                                                     | TG bildirimlerini almak için hesap dijital kimliği                                                                                                                                             |
| ALT              | trojan.fxxk.dedyn.io                                                                                                                           | Tercih edilen abonelik oluşturucu adresi (aboneyi kullanmak,`ADD`içinde yerel premium abonelik içeriği)                                                                                        |
| subapi           | apiurl.v1.mk                                                                                                                                   | Clash, singbox vb. abonelik dönüşümü arka ucu                                                                                                                                                  |
| ALT YAPILANDIRMA | [https://raw.github.../ACL4SSR_Online_Mini.ini](https://raw.githubusercontent.com/ACL4SSR/ACL4SSR/master/Clash/config/ACL4SSR_Online_Mini.ini) | Clash, singbox vb. Abonelik dönüşüm profilleri                                                                                                                                                 |
| ALT AD           | kötü                                                                                                                                           | Abonelik adı                                                                                                                                                                                   |
| 02               | <https://t.me/F_NiREvil>                                                                                                                       | Ana sayfa 302 atlaması (URL'ler arasında kullanılan birden fazla URL'yi destekler)`,`Veya satır sonunu aralayıcı olarak kullanın, eğer bu konuda yeniyseniz kullanmayın)                       |
| URL'si           | <https://t.me/F_NiREvil>                                                                                                                       | Ana sayfa gizleme (URL'ler arasında kullanılan birden fazla URL'yi destekler)`,`Veya satır sonlarını aralık olarak kullanın, rastgele ayarlar dolandırıcılığı önlemeyi kolayca tetikleyebilir) |

![rainbow](https://github.com/NiREvil/vless/assets/126243832/1aca7f5d-6495-44b7-aced-072bae52f256)

## Video eğitimleri

<https://github.com/NiREvil/Trauma/assets/126243832/92a430c3-4884-4831-bf8c-e328cfd78af8>

![rainbow](https://github.com/NiREvil/vless/assets/126243832/1aca7f5d-6495-44b7-aced-072bae52f256)

<https://github.com/NiREvil/Trauma/assets/126243832/f20a0215-bd75-4302-89dd-90a5bdd75cbc>

![rainbow](https://github.com/NiREvil/vless/assets/126243832/1aca7f5d-6495-44b7-aced-072bae52f256)

<https://github.com/NiREvil/Trauma/assets/126243832/f63c74c9-0e86-40a2-8894-e027c06776f5>

![rainbow](https://github.com/NiREvil/vless/assets/126243832/1aca7f5d-6495-44b7-aced-072bae52f256)

<https://github.com/NiREvil/Trauma/assets/126243832/61ce0b14-2c26-4325-a6c0-6f12cfc608d7>

![rainbow](https://github.com/NiREvil/vless/assets/126243832/1aca7f5d-6495-44b7-aced-072bae52f256)

# minnettar

[ca110us](https://github.com/ca110us/epeius)\|[Sterilize et](https://github.com/3Kmfi6HP/EDtunnel/tree/trojan)\|[zizifn](https://github.com/zizifn/edgetunnel)\|[Yemen 178](https://github.com/emn178/js-sha256)\|[ACL4SSR](https://github.com/ACL4SSR/ACL4SSR/tree/master/Clash/config)\|[Sheggs1999](https://github.com/SHIJS1999/cloudflare-worker-vless-ip)

![rainbow](https://github.com/NiREvil/vless/assets/126243832/1aca7f5d-6495-44b7-aced-072bae52f256)
