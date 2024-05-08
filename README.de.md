# Stellen Sie einen Trojaner mit einem serverlosen CF-Workers & Pages bereit

🇮🇷[Persian](README.fa.md)| 🇹🇷[Türkisch](README.tr.md)

🇬🇧[Englisch](README.md)\|[Deutschland](README.de.md)

Dies ist ein Skript, das auf der Cloudflare Worker-Plattform basiert. Basierend auf der Originalversion wurde es so modifiziert, dass es Trojaner-Konfigurationsinformationen anzeigt und diese in Abonnementinhalte umwandelt. Mit diesem Skript können Sie mithilfe der Online-Konfiguration problemlos Trojaner-Konfigurationsinformationen in Tools wie Clash oder Singbox konvertieren.

[TG-Kanal](https://t.me/F_NiREvil)

![rainbow](https://github.com/NiREvil/vless/assets/126243832/1aca7f5d-6495-44b7-aced-072bae52f256)

## Inhaltsverzeichnis

-   [Methode zur Bereitstellung von Arbeitskräften](#Workers-deployment-method)
-   [Bereitstellungsmethode für Seiten](#Pages-deployment-method)
-   [ProxyIP](#proxyIP)
-   [Beschreibung der Umgebungsvariablen](#Environment-variables-description)
-   [Videoanleitungen](#Video-tutorials)![rainbow](https://github.com/NiREvil/vless/assets/126243832/1aca7f5d-6495-44b7-aced-072bae52f256)

<details>
<summary> Use </summary>

-   Dieses Projekt ist ausschließlich für Lern-, Forschungs- und Sicherheitstestzwecke konzipiert und entwickelt. Ziel ist es, Sicherheitsforschern, Akademikern und Technologiebegeisterten ein Werkzeug zum Verständnis und zur Praxis der Netzwerkkommunikationstechnologie zur Verfügung zu stellen.
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

## Methode zur Bereitstellung von Arbeitskräften

1.  Stellen Sie Cloudflare Worker bereit:

    -   Erstellen Sie einen neuen Worker in der Cloudflare Worker-Konsole.

    -   Wille[worker.js](https://github.com/NiREvil/Trauma/blob/main/_worker.js)Fügen Sie den Inhalt in den Worker-Editor ein.

    -   Ändern Sie Zeile 3`password`Ändern Sie es in Ihr eigenes**Passwort**

    -   Alternativ können Sie auf die Schaltfläche unten klicken, um die Bereitstellung direkt durchzuführen.

    [![Deploy to Cloudflare Workers](https://deploy.workers.cloudflare.com/button)](https://deploy.workers.cloudflare.com/?url=https://github.com/NiREvil/Trauma)

2.  Bevorzugte Route hinzufügen:
    -   Geben`addresses`Fügen Sie den bevorzugten Domänennamen/die bevorzugte saubere IP entsprechend dem Format hinzu. Wenn keine Portnummer vorhanden ist, ist der Standard-TLS-Port 443 und das #-Zeichen ist der Bemerkungsalias, zum Beispiel:
        ```js
        let addresses = [
        	// Everything you want, Cloudflare Domains & Clean IP addresses.
        	'www.speedtest.net:443#Ni1',
        	'time.is#Ni2',
        	'zula.ir#Ni3',
        	'www.visa.com.sg:2053#Ni4',
        ];
        ```

3.  Zugriff auf Abonnementinhalte:
    -   Zugang`https://[YOUR-WORKERS-URL]/[password]`Erhalten Sie Abonnementinhalte.
    -   Zum Beispiel`https://vless.trauma.workers.dev/auto`Dies ist Ihre universelle adaptive Abonnementadresse.
    -   Zum Beispiel`https://vless.trauma.workers.dev/auto?sub`Base64-Abonnementformat, geeignet für PassWall, SSR+ usw.
    -   Zum Beispiel`https://vless.trauma.workers.dev/auto?clash`Clash-Abonnementformat, geeignet für OpenClash usw.
    -   Zum Beispiel`https://vless.trauma.workers.dev/auto?sb`Singbox-Abonnementformat, geeignet für Singbox usw.

4.  Binden Sie eine benutzerdefinierte Domäne an Worker:
    -   In der Arbeiterkonsole`trigger`Klicken Sie auf die Registerkarte unten`Add a custom domain`。
    -   Geben Sie den sekundären Domänennamen ein, den Sie an den CloudFlare-Domänennamenauflösungsdienst übertragen haben, zum Beispiel:`vless.trauma.com`Nach dem Klicken`Add a custom domain`, warten Sie einfach, bis das Zertifikat wirksam wird.

![rainbow](https://github.com/NiREvil/vless/assets/126243832/1aca7f5d-6495-44b7-aced-072bae52f256)

## Bereitstellungsmethode für Seiten

1.  Stellen Sie Cloudflare-Seiten bereit:
    -   Gabel[dieses Projekt auf Github](https://github.com/NiREvil/Trauma/fork)
    -   Wählen Sie in der Cloudflare Pages-Konsole aus`Connected to Git`Danach wählen Sie aus`trauma`Klicken Sie hinter dem Element`Start setting up`。
    -   existieren`Setting up build and deployment`Wählen Sie unten auf der Seite aus`Environment variables (advanced)`später zusammenführen[Variablen hinzufügen](#Environment-variables-description),
    -   Geben Sie den Variablennamen ein**PASSWORT**, der Wert ist Ihr Passwort, dann klicken Sie`Save and deploy`Das ist es.

2.  Bevorzugte Route hinzufügen:
    -   Variablen hinzufügen`ADD`Lokale statische bevorzugte Leitung. Wenn keine Portnummer vorhanden ist, ist der Standard-TLS-Port 443 und auf die #-Nummer folgt ein Bemerkungsalias, zum Beispiel:
        ```js
         discord.com#You can just put the domain name as follows
         www.speedtest.net:443#Ni1
         time.is#Ni2
         zula.ir#Ni3
         www.visa.com.sg:2053#Ni4
         104.17.152.41#IP Also available
         [2606:4700:e7:25:4b9:f8f8:9bfb:774a]#IPv6 also OK
        ```

3.  Zugriff auf Abonnementinhalte:
    -   Zugang`https://[YOUR-PAGES-URL]/[password]`Abonnementinhalte sind verfügbar.
    -   Zum Beispiel`https://trauma.pages.dev/auto`Dies ist Ihre universelle adaptive Abonnementadresse.
    -   Zum Beispiel`https://trauma.pages.dev/auto?sub`Base64-Abonnementformat, geeignet für PassWall, SSR+ usw.
    -   For example `https://trauma.pages.dev/auto?clash`Clash-Abonnementformat, geeignet für OpenClash usw.
    -   Zum Beispiel`https://trauma.pages.dev/auto?sb`Singbox-Abonnementformat, geeignet für Singbox usw.

4.  Benutzerdefinierte CNAME-Domäne an Seiten binden:
    -   In der Pages-Konsole`Custom domains`Klicken Sie auf die Registerkarte unten`Set up a custom domain`.
    -   Geben Sie Ihren benutzerdefinierten sekundären Domänennamen ein. Achten Sie darauf, nicht Ihren Stammdomänennamen zu verwenden, zum Beispiel:
    -   Der Ihnen zugewiesene Domainname lautet`fuck.cloudns.biz`und fügen Sie dann ein benutzerdefiniertes Feld zum Ausfüllen hinzu`iran.fuck.cloudns.biz`Das ist es;
    -   Gemäß den Anforderungen von Cloudflare wird Ihr Domainname-DNS-Dienstanbieter zurückgegeben und die benutzerdefinierte Domain hinzugefügt.`trauma`CNAME-Eintrag von`trauma.pages.dev`Klicken Sie anschließend auf`Activate Domain`Das ist es.

![rainbow](https://github.com/NiREvil/vless/assets/126243832/1aca7f5d-6495-44b7-aced-072bae52f256)

## ProxyIP

1.  Bei der Bereitstellung auf Cloudflare-Seiten können Sie ProxyIP in der 4. Zeile festlegen`_worker.js`Datei. Oder legen Sie die Umgebungsvariable fest. Der Variablenname lautet`PROXYIP`

2.  Bei der Bereitstellung in worker.dev können Sie ProxyIP in der 4. Zeile von festlegen`_worker.js`Datei. Oder legen Sie die Umgebungsvariable fest. Der Variablenname lautet`proxyIP`

### So finden Sie ProxyIP

[(QUELLE)](https://github.com/NiREvil/vless/edit/main/sub/ProxyIP.md)

## Beschreibung der Umgebungsvariablen

> [!NOTIZ]Es reicht aus, nur zwei davon festzulegen, die erste Variable`PASSWORD`und der zweite`PROXYIP`Die in der folgenden Tabelle aufgeführten Variablen dienen nur zu Bildungszwecken und zusätzlichen Erläuterungen.![rainbow](https://github.com/NiREvil/vless/assets/126243832/1aca7f5d-6495-44b7-aced-072bae52f256)

| Variablennamen | Beispiel                                                                                                                                       | Anmerkung                                                                                                                                                                                                  |
| -------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| PASSWORT       | Auto                                                                                                                                           | Kann jeden Wert annehmen                                                                                                                                                                                   |
| PROXYIP        | [klicken Sie hier](https://github.com/NiREvil/vless/edit/main/sub/ProxyIP.md)oder Verwendung`ni.radically.pro`                                 | Als Proxy-Knoten für den Zugriff auf die CloudFlareCDN-Site (unterstützt mehrere ProxyIPs, die zwischen ProxyIPs verwendet werden).`,`oder Zeilenvorschub als Intervall)                                   |
| HINZUFÜGEN     | [zula.ir,www.csgo.com:2087](http://zula.ir,www.csgo.com:2087)                                                                                  | Lokaler bevorzugter Domänenname/bevorzugte IP (unterstützt mehrere Elemente`,`oder Zeilenvorschub als Intervall)                                                                                           |
| ADDAPI         | <https://raw.githubusercontent.com/NiREvil/Trauma/main/cleanIPs.txt>                                                                           | Kein Grund zur Erklärung, jeder versteht es                                                                                                                                                                |
| ADDCSV         |                                                                                                                                                | Kein Grund zur Erklärung, jeder versteht es                                                                                                                                                                |
| DLS            | 8                                                                                                                                              | Kein Grund zur Erklärung, jeder versteht es                                                                                                                                                                |
| TGTOKEN        | 6894123456:XXXXXXXXXX0qExVsBPUhHDAbXXXXXqWXgBA                                                                                                 | Roboter-Token zum Versenden von TG-Benachrichtigungen                                                                                                                                                      |
| DU TUST        | 6946912345                                                                                                                                     | Digitale Konto-ID, um TG-Benachrichtigungen zu erhalten                                                                                                                                                    |
| SUB            | trojan.fxxk.dedyn.io                                                                                                                           | Bevorzugte Abonnement-Generator-Adresse (mit der der Abonnent aufgibt).`ADD`lokaler Premium-Abonnementinhalt innerhalb von )                                                                               |
| subapi         | apiurl.v1.mk                                                                                                                                   | Clash, Singbox usw. Abonnementkonvertierungs-Backend                                                                                                                                                       |
| UNTERKONFIG    | [https://raw.github.../ACL4SSR_Online_Mini.ini](https://raw.githubusercontent.com/ACL4SSR/ACL4SSR/master/Clash/config/ACL4SSR_Online_Mini.ini) | Clash, Singbox usw. Abonnementkonvertierungsprofile                                                                                                                                                        |
| UNTERNAME      | REvil                                                                                                                                          | Abonnementname                                                                                                                                                                                             |
| 02             | <https://t.me/F_NiREvil>                                                                                                                       | Startseite 302-Sprung (unterstützt mehrere URLs, wird zwischen URLs verwendet)`,`Oder Zeilenumbruch als Abstandshalter, verwenden Sie ihn nicht, wenn Sie damit noch nicht vertraut sind.)                 |
| URL            | <https://t.me/F_NiREvil>                                                                                                                       | Homepage-Verkleidung (unterstützt mehrere URLs, die zwischen URLs verwendet werden)`,`Oder verwenden Sie Zeilenumbrüche als Intervalle, zufällige Einstellungen können leicht Betrugsbekämpfung auslösen.) |

![rainbow](https://github.com/NiREvil/vless/assets/126243832/1aca7f5d-6495-44b7-aced-072bae52f256)

## Videoanleitungen

<https://github.com/NiREvil/Trauma/assets/126243832/92a430c3-4884-4831-bf8c-e328cfd78af8>

![rainbow](https://github.com/NiREvil/vless/assets/126243832/1aca7f5d-6495-44b7-aced-072bae52f256)

<https://github.com/NiREvil/Trauma/assets/126243832/f20a0215-bd75-4302-89dd-90a5bdd75cbc>

![rainbow](https://github.com/NiREvil/vless/assets/126243832/1aca7f5d-6495-44b7-aced-072bae52f256)

<https://github.com/NiREvil/Trauma/assets/126243832/f63c74c9-0e86-40a2-8894-e027c06776f5>

![rainbow](https://github.com/NiREvil/vless/assets/126243832/1aca7f5d-6495-44b7-aced-072bae52f256)

<https://github.com/NiREvil/Trauma/assets/126243832/61ce0b14-2c26-4325-a6c0-6f12cfc608d7>

![rainbow](https://github.com/NiREvil/vless/assets/126243832/1aca7f5d-6495-44b7-aced-072bae52f256)

# dankbar

[ca110us](https://github.com/ca110us/epeius)  \|  [Sterilisieren Sie es](https://github.com/3Kmfi6HP/EDtunnel/tree/trojan)\|[zizifn](https://github.com/zizifn/edgetunnel)\|[Jemen 178](https://github.com/emn178/js-sha256)\|[ACL4SSR](https://github.com/ACL4SSR/ACL4SSR/tree/master/Clash/config)\|[Sheggs1999](https://github.com/SHIJS1999/cloudflare-worker-vless-ip)

![rainbow](https://github.com/NiREvil/vless/assets/126243832/1aca7f5d-6495-44b7-aced-072bae52f256)
