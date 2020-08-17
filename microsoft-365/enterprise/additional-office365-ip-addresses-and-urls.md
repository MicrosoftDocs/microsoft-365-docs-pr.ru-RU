---
title: Дополнительные конечные точки не включены в веб-службу IP-адресов и URL-адресов Office 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/29/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- MOM160
- BCS160
ms.assetid: ''
description: Сводка. В новой веб-службе конечных точек отсутствует небольшое количество конечных точек для определенных сценариев.
hideEdit: true
ms.openlocfilehash: e9f8a2b50900641327cebc6574ad09f388272bba
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693363"
---
# <a name="additional-endpoints-not-included-in-the-office-365-ip-address-and-url-web-service"></a>Дополнительные конечные точки не включены в веб-службу IP-адресов и URL-адресов Office 365

Некоторые конечные точки сети были опубликованы ранее и не были включены в [веб-службу URL-адресов и IP-адресов Office 365](microsoft-365-ip-web-service.md). Область действия веб-службы — конечные точки сети, необходимые для подключения пользователей Office 365 к корпоративной сети периметра. В настоящее время к ней не относится следующее:

1. Возможные сетевые подключения из центра обработки данных Майкрософт к сети клиента (входящий гибридный сетевой трафик сервера).
2. Сетевое подключение от серверов клиентской сети к корпоративному периметру (исходящий сетевой трафик сервера).
3. Редкие сценарии с требованиями к сетевому подключению от пользователя.
4. Требование в отношении подключения для разрешения DNS (не представлено ниже).
5. Надежные сайты Internet Explorer или Microsoft Edge.

Эти параметры (кроме DNS) являются необязательными для большинства клиентов, за исключением особого описанного сценария.

| Строка | Назначение | Назначение | Тип |
|:-----|:-----|:-----|:-----|
| 1  | [Служба импорта](https://support.office.com/article/use-network-upload-to-import-your-organization-pst-files-to-office-365-103f940c-0468-4e1a-b527-cc8ad13a5ea6) для приема PST- и других файлов | Дополнительные требования см. в статье [Служба импорта](https://support.office.com/article/use-network-upload-to-import-your-organization-pst-files-to-office-365-103f940c-0468-4e1a-b527-cc8ad13a5ea6). | Редкий сценарий исходящего трафика |
| 2  | [Помощник по поддержке и восстановлению для Office 365 (Майкрософт)](https://diagnostics.office.com/#/)  | https<span>://</span>autodiscover.outlook.com <BR> <span>https://</span>officecdn.microsoft.com <BR> <span>https://</span>api.diagnostics.office.com <BR> <span>https://</span>apibasic.diagnostics.office.com <BR> <span>https://</span>autodiscover-s.outlook.com <BR> <span>https://</span>cloudcheckenabler.azurewebsites.net <BR> <span>https://</span>dcs-staging.azure-api.net <BR> <span>https://</span>login.live.com <BR> <span>https://</span>login.microsoftonline.com <BR> <span>https://</span>login.windows.net <BR> <span>https://</span>o365diagtelemetry.trafficmanager.net <BR> <span>https://</span>odc.officeapps.live.com <BR> <span>https://</span>offcatedge.azureedge.net <BR> <span>https://</span>officeapps.live.com <BR> <span>https://</span>outlook.office365.com <BR> <span>https://</span>outlookdiagnostics.azureedge.net | Исходящий серверный трафик |
| 3  | Azure AD Connect (с возможностью единого входа) — WinRM и удаленная оболочка PowerShell | Клиентская среда службы маркеров безопасности (сервер AD FS и прокси-сервер AD FS) \| TCP-порты 80 и 443 | Входящий серверный трафик |
| 4  | Служба маркеров безопасности, например прокси-серверы AD FS (только для федеративных клиентов) | Служба маркеров безопасности клиента (например, прокси-сервер AD FS) \| TCP-порты 443 или 49443 с клиентским TLS | Входящий серверный трафик |
| 5  | [Интеграция единой службы обмена сообщениями Exchange Online с SBC](https://technet.microsoft.com/library/jj673565.aspx) | Двунаправленный обмен между локальным пограничным контроллером сеансов и *. um.outlook.com | Только исходящий серверный трафик |
| 6  | Перенос почтовых ящиков. Если перенос почтовых ящиков запускается из локального [гибридного развертывания Exchange](https://docs.microsoft.com/exchange/exchange-deployment-assistant) в Office 365, служба Office 365 подключается к опубликованному серверу веб-служб Exchange (EWS) или служб репликации почтовых ящиков (MRS). Если вам нужны IP-адреса NAT, используемые серверами Exchange Online для ограничения входящих подключений от определенных диапазонов IP-адресов, они перечислены в статье [Диапазоны IP-адресов и URL-адреса Office 365](urls-and-ip-address-ranges.md) в области обслуживания Exchange Online. Необходимо принять меры, чтобы не затронуть доступ к опубликованным конечным точкам EWS (например, OWA) путем сопоставления прокси-службы MRS с другим полным доменным именем и общедоступным IP-адресом перед ограничением подключений через TCP 443 от определенных диапазонов IP-адресов источника. | Локальная прокси-служба EWS/MRS клиента<br> TCP-порт 443 | Входящий серверный трафик |
| 7  | Функции сосуществования для[гибридного развертывания Exchange](https://docs.microsoft.com/exchange/exchange-deployment-assistant), например обмен сведениями о доступности. | Локальный сервер Exchange клиента | Входящий серверный трафик |
| 8  | Проверка подлинности прокси-сервера для [гибридного развертывания Exchange](https://docs.microsoft.com/exchange/exchange-deployment-assistant) | Локальная служба маркеров безопасности клиента | Входящий серверный трафик |
| 9  | Используется для настройки [гибридного развертывания Exchange](https://docs.microsoft.com/exchange/exchange-deployment-assistant) с помощью [мастера гибридной конфигурации Exchange](https://docs.microsoft.com/exchange/hybrid-configuration-wizard). <br> Примечание. Эти конечные точки необходимы только для настройки гибридного развертывания Exchange  | domains.live.com на TCP-портах 80 и 443. Требуется только для мастера гибридной конфигурации Exchange 2010 с пакетом обновления 3 (SP3)<BR> <BR> IP-адреса GCC High, DoD: 40.118.209.192/32; 168.62.190.41/32 <BR> <BR> Коммерческое использование по всему миру и GCC: *.store.core.windows.net; asl.configure.office.com; mshrcstorageprod.blob.core.windows.net; tds.configure.office.com; mshybridservice.trafficmanager.net <BR>  | Только исходящий серверный трафик |
| 10  | Служба AutoDetect используется в сценариях [гибридного развертывания Exchange](https://docs.microsoft.com/exchange/exchange-deployment-assistant) с [гибридной современной проверкой подлинности в Outlook для iOS и Android](https://docs.microsoft.com/Exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth) <BR> <BR> ```*.acompli.net``` <BR> <BR> ```*.outlookmobile.com``` <BR> <BR> ```*.outlookmobile.us``` <BR> <BR> ```52.125.128.0/20``` <BR> ```52.127.96.0/23``` <BR> | Локальный сервер Exchange клиента на TCP 443 | Входящий серверный трафик |
| 11  | Skype для бизнеса в Office 2016 включает демонстрацию экрана с видео, для которой используются порты UDP. Более ранние клиенты Skype для бизнеса в Office 2013 и предшествовавших версий использовали RDP через порт 443 TCP. | Порт 443 TCP открыт для 52.112.0.0/14 | Более ранние версии клиента Skype для бизнеса в Office 2013 и предшествующих версиях |
| 12  | Возможность подключения гибридного локального сервера Skype для бизнеса к службе Skype для бизнеса Online | 13.107.64.0/18, 52.112.0.0/14  <BR> Порты UDP 50 000–59 999 <BR>  Порты TCP 50 000–59 999; 5061 | Возможность исходящего подключения к локальному серверу Skype для бизнеса |
| 13  | Облачной ТСОП с возможностью гибридного локального подключения требуется поддержка подключения сети к локальным узлам. Дополнительные сведения о гибридных конфигурациях Skype для бизнеса Online  | См. статью [Планирование гибридного соединения Skype для бизнеса Server и Office 365](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-hybrid-connectivity). | Гибридное входящее локальное подключение Skype для бизнеса |
| 14  | **FQDN для проверки подлинности и идентификации** <br> Для функционирования полное доменное имя ```secure.aadcdn.microsoftonline-p.com``` должно находиться в зоне надежных сайтов Internet Explorer (IE) или Microsoft Edge. |  | Надежные сайты |
| 15  |  **Полные доменные имена Microsoft Teams** <br> Если вы используете Internet Explorer или Microsoft Edge, вам нужно разрешить основные и сторонние файлы cookie, а также добавить полные доменные имена Teams в список надежных сайтов (в дополнение к полным доменным именам для всего набора, CDN и телеметрии, перечисленной в строке 14). Дополнительные сведения см. в статье [Известные проблемы Microsoft Teams](https://docs.microsoft.com/microsoftteams/known-issues). |  | Надежные сайты |
| 16  |  **Полные доменные имена SharePoint Online и OneDrive для бизнеса** <br> Для использования всех полных доменных имен .sharepoint.com, в которых указан "\<tenant>", их следует добавить в зону надежных сайтов IE или Microsoft Edge. Помимо полных доменных имен, сетей CDN и телеметрии, перечисленных в строке 14, для всего набора необходимо добавить указанные ниже конечные точки. |  | Надежные сайты |
| 17  | **Yammer**  <br> Приложение Yammer доступно только в браузере и требует, чтобы авторизованный пользователь проходил через прокси-сервер. Для функционирования все полные доменные имена приложения Yammer должны находиться в зоне надежных сайтов IE или Microsoft Edge вашего клиента. |  | Надежные сайты |
| 18  | Используйте [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/) для синхронизации учетных записей пользователей с Azure AD. | См. статьи [Порты и протоколы, необходимые для гибридной идентификации](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-ports), [Устранение неполадок подключения Azure AD](https://docs.microsoft.com/azure/active-directory/hybrid/tshoot-connect-connectivity) и [Установка агента Azure AD Connect Health](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-health-agent-install#outbound-connectivity-to-the-azure-service-endpoints). | Только исходящий серверный трафик |
| 19  | [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/) с 21 ViaNet в Китае для синхронизации локальных учетных записей пользователей с Azure AD. | \*.digicert.com:80 <BR> \*.entrust.net:80 <BR> \*.chinacloudapi.cn:443 <BR> secure.aadcdn.partner.microsoftonline-p.cn:443 <BR>*.partner.microsoftonline.cn:443 <BR> <BR>См. также [Устранение неполадок при входе с подключением Azure AD](https://docs.azure.cn/zh-cn/active-directory/hybrid/tshoot-connect-connectivity) | Только исходящий серверный трафик |
| 20  | Microsoft Stream (требуется маркер пользователя Azure AD). <BR> Office 365 Worldwide (включая GCC) | \*.cloudapp.net <BR> \*.api.microsoftstream.com <BR> \*.notification.api.microsoftstream.com <BR> amp.azure.net <BR> api.microsoftstream.com <BR> az416426.vo.msecnd.net <BR> s0.assets-yammer.com <BR> vortex.data.microsoft.com <BR> web.microsoftstream.com <BR> TCP-порт 443  | Входящий трафик сервера |
| 21  | Использование сервера MFA для запросов многофакторной проверки подлинности: как новых установок сервера, так и его настройки с помощью доменных служб Active Directory (AD DS). | См. статью [Приступая к работе с сервером многофакторной идентификации Azure](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-deploy#plan-your-deployment).  | Только исходящий серверный трафик |
| 22  | Уведомления об изменениях в Microsoft Graph | Разработчики могут использовать [уведомления об изменениях](https://docs.microsoft.com/graph/webhooks?context=graph%2Fapi%2F1.0&view=graph-rest-1.0), чтобы подписаться на события в Microsoft Graph. | *.cloudapp.net<BR> 104.43.130.21, 137.116.169.230, 13.79.38.63, 104.214.39.228, общедоступное облако: 168.63.250.205, 52.161.9.202, 40.68.103.62, 13.89.60.223, 23.100.95.104, 40.113.95.219, 104.214.32.10, 168.63.237.145, 52.161.110.176, 52.174.177.183 <BR> Microsoft Cloud for US Government: 52.244.231.173, 52.238.76.151, 52.244.250.211, 52.238.78.108 <BR> Microsoft Cloud (Германия): 51.4.231.136, 51.5.243.223, 51.4.226.154, 51.5.244.215 <BR> Microsoft Cloud (Китай) под управлением 21Vianet: 139.219.15.33, 42.159.154.223, 42.159.88.79, 42.159.155.77<BR> TCP-порт 443 <BR> Примечание. Разработчики могут указывать различные порты при создании подписок.  | Входящий трафик сервера |
|||||

## <a name="related-topics"></a>Статьи по теме

[Управление конечными точками Office 365](managing-office-365-endpoints.md)
  
[Устранение неполадок с подключением к Office 365](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d.aspx)
  
[Подключение клиентских компьютеров](https://support.office.com/article/client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b)
  
[Сети доставки содержимого](https://support.office.com/article/content-delivery-networks-0140f704-6614-49bb-aa6c-89b75dcd7f1f)
  
[Диапазоны IP-адресов центра обработки данных Microsoft Azure](https://www.microsoft.com/download/details.aspx?id=41653)
  
[Пространство публичных IP-адресов корпорации Майкрософт](https://www.microsoft.com/download/details.aspx?id=53602)