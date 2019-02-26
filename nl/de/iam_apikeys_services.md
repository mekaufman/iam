---

copyright:

  years: 2018, 2019

lastupdated: "2019-01-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# {{site.data.keyword.cloud_notm}}-Service-APIs aufrufen
{: #iamapikeysforservices}

Wenn Sie einen {{site.data.keyword.Bluemix}}-Service über eine Anwendungsprogrammierschnittstelle (API) aufrufen wollen, müssen Sie zum Authentifizieren Ihrer Benutzeridentität und Ihres Zugriffs Ihre Berechtigungsnachweise an die API des Service übergeben, um im Kontext des Service Aktionen ausführen zu können. 
{:shortdesc}

Sie können den Aufrufer auf eine der folgenden Arten ermitteln: 

* {{site.data.keyword.Bluemix_notm}}-API-Schlüssel oder API-Schlüssel für Service-ID
* Token für {{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM)

[{{site.data.keyword.Bluemix_notm}}-API-Schlüssel](/docs/iam?topic=iam-userapikey#userapikey), [API-Schlüssel für Service-IDs](/docs/iam?topic=iam-serviceidapikeys#serviceidapikeys) und IAM-Token geben die Identität des Aufrufers eindeutig an.  Bei der Identität des Aufrufers handelt es sich entweder um einen {{site.data.keyword.Bluemix_notm}}-Benutzer oder um eine Service-ID, die in einem {{site.data.keyword.Bluemix_notm}}-Konto erstellt wurde. 

Die API-Schlüssel sind Berechtigungsnachweise, die aus einer langen Reihe beliebiger Zeichen oder Zahlen bestehen. Für eine {{site.data.keyword.Bluemix_notm}}-Identität kann es mehrere API-Schlüssel geben. Jeder dieser API-Schlüssel kann unabhängig von den übrigen verwaltet werden. Wenn ein bestimmter API-Schlüssel nur von Ihrem Service verwendet wird, bedeutet das, dass Sie diesen API-Schlüssel löschen können, ohne dass es bei anderen Komponenten hierdurch zu Unterbrechungen kommt.

Sie können API-Schlüssel verwenden, um sich [bei der {{site.data.keyword.Bluemix_notm}}-Befehlszeilenschnittstelle (CLI) anzumelden](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_login#ibmcloud_login) oder um [IAM-Token zu generieren](/docs/iam?topic=iam-iamtoken_from_apikey#iamtoken_from_apikey). Obwohl dies nicht für den Produktionseinsatz empfohlen ist, können Sie API-Schlüssel auch an {{site.data.keyword.Bluemix_notm}}-Services senden.

## {{site.data.keyword.Bluemix_notm}}-API-Schlüssel zum Authentifizieren bei der API eines Service übergeben
{: #apikey_auth}

API-Clients können einen {{site.data.keyword.Bluemix_notm}}-API-Schlüssel direkt an die API des Zielservice übergeben. Dazu müssen Sie das Schlüsselwort `apikey` als Benutzername und den {{site.data.keyword.Bluemix_notm}}-API-Schlüssel als Kennwort unter Verwendung des HTTP-Headers für die Basisauthentifizierung an den Zielservice übergeben.

Die Zielservice-API muss den {{site.data.keyword.Bluemix_notm}}-API-Schlüssel unter Verwendung des {{site.data.keyword.Bluemix_notm}} IAM-Service selbst überwachen. In der folgenden Abbildung sind drei API-Interaktionen dargestellt. Der {{site.data.keyword.Bluemix_notm}}-API-Schlüssel wird an die API eines jeden Zielservice übergeben, so dass jeder Zielservice die Details des {{site.data.keyword.Bluemix_notm}}-API-Schlüssels durch Aufrufen von {{site.data.keyword.Bluemix_notm}} IAM suchen muss.

![Authentifizierung bei einer Service-API anhand eines API-Schlüssels](images/APIkeyauth.svg "Übergeben von API-Schlüsseln an Zielservices, die ihrerseits den API-Schlüssel zum Prüfen der Berechtigungsnachweise an IAM übergeben")

Die Verwendung eines {{site.data.keyword.Bluemix_notm}}-API-Schlüssels ist bequem und durch sie ist es einfach, neue APIs zu erkennen und Prototypen auszuprobieren. Bei diesem Verfahren ist es erforderlich, den {{site.data.keyword.Bluemix_notm}}-API-Schlüssel in lesbarem Format an die Zielservice-API zu schicken, was den API-Schlüssel unnötig beeinträchtigt. Da die API des Zielservice den API-Schlüssel stets selbst überwachen muss, ist dieses Verfahren außerdem weniger leistungsfähig und wird daher nicht für Arbeitslasten im Produktionsbetrieb empfohlen.

Führen Sie die folgenden Schritte aus, um die Authentifizierung bei der API eines Service anhand eines API-Schlüssels durchzuführen: 

  1. Zuerst müssen Sie einen [{{site.data.keyword.Bluemix_notm}}-API-Schlüssel erstellen](/docs/iam?topic=iam-userapikey#creating-an-api-key), sofern Sie dies noch nicht getan haben. 
  2. Senden Sie den {{site.data.keyword.Bluemix_notm}}-API-Schlüssel, wie in [RFC 7617](https://tools.ietf.org/html/rfc7617){: new_window} ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link") definiert, als HTTP-Header 'Authorization'. Verwenden Sie `apikey` als Benutzernamen und den Wert des API-Schlüssels als Kennwort.

In dem Beispiel in den folgenden Schritten wird davon ausgegangen, dass der API-Schlüssel den Wert '0a1A2b3B4c5C6d7D8e9E' hat:

  1.	Verknüpfen Sie den Benutzernamen `apikey` und den API-Schlüssel und verwenden Sie einen Doppelpunkt als Trennzeichen: `apikey:0a1A2b3B4c5C6d7D8e9E`
  2.	Setzen Sie die Zeichenfolge in Base64-Codierung: `base64("apikey:0a1A2b3B4c5C6d7D8e9E") => YXBpa2V5OjBhMUEyYjNCNGM1QzZkN0Q4ZTlF`
  3.	Legen Sie als Autorisierung für den HTTP-Header 'Authorization' des Basisschema fest, zum Beispiel wie folgt: `Authorization: Basic YXBpa2V5OjBhMUEyYjNCNGM1QzZkN0Q4ZTlF`. Bei Verwendung des Befehls 'curl' können Sie für die Übergabe den Parameter -u verwenden:

    ```
    curl -u "apikey:<Wert des IBM Cloud-API-Schlüssels>"
    ```

  Wenn Sie andere Tools verwenden, müssen Sie diese Berechtigungsnachweise gegebenenfalls anders angeben.
  {: tip}

## {{site.data.keyword.Bluemix_notm}} IAM-Token zum Authentifizieren bei der API eines Service übergeben
{: #token_auth}

Zum Abrufen eines IAM-Zugriffstokens muss der API-Client zuerst eine {{site.data.keyword.Bluemix_notm}} IAM-API aufrufen, um dieses Token zu authentifizieren und abzurufen. Das bevorzugte Verfahren für API-Clients des {{site.data.keyword.Bluemix_notm}}-Service besteht darin, ein IAM-Zugriffstoken mithilfe eines IAM-API-Schlüssels abzurufen. Das IAM-Zugriffstoken kann für mehrere Aufrufe von {{site.data.keyword.Bluemix_notm}}-Services verwendet werden, die IAM-Zugriffstoken als Authentifizierungsmethode akzeptieren. Da IAM-Zugriffstoken mit asymmetrischen Schlüsseln digital signiert sind, können {{site.data.keyword.Bluemix_notm}}-Services ein IAM-Zugriffstoken überprüfen, ohne dazu einen externen Service aufrufen zu müssen. Dadurch wird die Leistung beim Aufrufen einer API erheblich verbessert.

![Authentifizierung bei einer Service-API anhand eines Zugriffstokens](images/tokenauth.svg "Abrufen eines Tokens von IAM anhand eines API-Schlüssels und Übergeben des Tokens an Zielservices zwecks Überprüfung der Berechtigungsnachweise")

Führen Sie die folgenden Schritte aus, um die Authentifizierung bei der API eines Service anhand eines Zugriffstokens durchzuführen:

  1. Zuerst müssen Sie einen [{{site.data.keyword.Bluemix_notm}}-API-Schlüssel erstellen](/docs/iam?topic=iam-userapikey#creating-an-api-key), sofern Sie dies noch nicht getan haben.  
  2. Als nächsten Schritt muss der API-Client ein IAM-Zugriffstoken abrufen, wie in [IAM-Token mithilfe eines API-Schlüssels abrufen](/docs/iam?topic=iam-iamtoken_from_apikey#iamtoken_from_apikey) beschrieben.
  3. Extrahieren Sie aus der Antwort die Eigenschaft `access_token`, um das eigentliche IAM-Zugriffstoken zu erhalten. Dabei gibt `expires_in` den Zeitraum in Sekunden an, nach dessen Ablauf das IAM-Zugriffstoken `access_token` verfällt. Verwenden Sie entweder diesen relativen Wert oder aber die absolute Zeitmarke `expiration` auf der Grundlage der [UNIX-Zeit](https://en.wikipedia.org/wiki/Unix_time){: new_window} ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link"). 
  4. Senden Sie das IAM-Zugriffstoken wie in [RFC 6750, section 2.1. Authorization Request Header Field](https://tools.ietf.org/html/rfc6750#page-5){: new_window} ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link") beschrieben:
   
Sehen Sie sich das folgende Beispiel an:

  1.	Verwenden Sie den HTTP-Header 'Authorization'.
  2.	Setzen Sie dem IAM-Zugriffstoken das Literal 'Bearer' voran: `Bearer eyJhbGciOiJSUzI1Ng...`
  3.	Fügen Sie das mit Präfix versehene IAM-Zugriffstoken zum HTTP-Header hinzu: `Authorization: Bearer eyJhbGciOiJSUzI1Ng...`. Bei Verwendung des Befehls 'curl' können Sie für die Übergabe den Parameter -H verwenden:

    ```
    curl -H "Authorization: Bearer eyJhbGciOiJSUzI1Ng..."
    ```
        
  Verwenden Sie dasselbe IAM-Zugriffstoken für nachfolgende Aufrufe der IBM Cloud-Service-API, um die bestmögliche Leistung und die größtmögliche Skalierbarkeit zu erzielen.
  {: tip}



