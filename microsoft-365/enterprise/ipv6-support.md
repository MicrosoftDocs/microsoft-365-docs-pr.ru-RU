---
title: Поддержка протокола IPv6 в службах Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 10/10/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: c08786fb-298e-437c-8222-dab7625fc815
description: Сводка. Описание поддержки IPv6 в Microsoft Office 365 и в предложениях Office 365 для государственных органов.
ms.openlocfilehash: f671e8caf868ebbed628a155b73ce6fe413949a9
ms.sourcegitcommit: c1ee4ed3c5826872b57339e1e1aa33b4d2209711
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48235610"
---
# <a name="ipv6-support-in-office-365-services"></a>Поддержка протокола IPv6 в службах Office 365

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Office 365 поддерживает как IPv6, так и IPv4; Однако не все функции Office 365 полностью включены с помощью IPv6. Это означает, что для подключения к Office 365 необходимо использовать как IPv4, так и IPv6. Если вы фильтруете исходящие трафикы в Office 365, полный список IPv6-адресов, поддерживаемых Office 365, можно найти в статье URL-адреса и диапазоны IP-адресов [Office 365.](urls-and-ip-address-ranges.md) После настройки сети и разрешения соответствующих IPv6-адресов вы можете скачать план тестирования [IPv6 для Office 365](https://go.microsoft.com/fwlink/?LinkId=293447) из Центра загрузки Майкрософт.
  
## <a name="ipv6-support-in-office-365-subscription-service"></a>Поддержка IPv6 в службе подписки На Office 365

### <a name="exchange-online-and-ipv6"></a>Exchange Online и IPv6

Если программа, используемая для подключения к Exchange Online, поддерживает IPv6, по умолчанию она будет использовать IPv6 в проводных и беспроводных сетях. Если вы хотите управлять связью с Exchange Online, используйте диапазоны IP-адресов в URL-адресах и диапазонах IP-адресов [Office 365.](urls-and-ip-address-ranges.md)
  
### <a name="sharepoint-online-and-ipv6"></a>SharePoint Online и IPv6

 **Office 365 для государственных служб G1/G3/G4/K1** Если программа, используемая для подключения к SharePoint Online, поддерживает IPv6, она попытается использовать IPv6 по умолчанию.
  
 **Общедоступные многоязычные облачные службы** Корпорация Майкрософт включает IPv6 в SharePoint Online по вашему запросу. Необходимо предоставить IP-адреса, нотированные CIDR, для инфраструктуры DNS вашей организации. Помните, что другие организации не могут совместно использовать эту инфраструктуру DNS, чтобы включить IPv6 для вашего клиента. Если после включения IPv6 программа, используемая для подключения к SharePoint Online, поддерживает IPv6, она использует IPv6 по умолчанию.
  
Если программа, используемая для подключения к SharePoint Online, поддерживает IPv6, по умолчанию она будет использовать IPv6 в проводных и беспроводных сетях. Если вы хотите управлять взаимодействием с SharePoint Online, используйте диапазоны IP-адресов в URL-адресах и диапазонах IP-адресов [Office 365.](urls-and-ip-address-ranges.md)
  
 **Office 365 для государственных служб G1/G3/G4/K1** Если программа, используемая для подключения к SharePoint Online, поддерживает IPv6, она попытается использовать IPv6 по умолчанию.
  
### <a name="skype-for-business-and-ipv6"></a>Skype для бизнеса и IPv6

Обратите внимание, что IPv6 не поддерживается в Skype для бизнеса и больше не может быть включен.

### <a name="microsoft-teams-and-ipv6"></a>Microsoft Teams и IPV6

Прямая маршрутка Microsoft Teams поддерживает только IPv4. Служба и клиент Microsoft Teams поддерживают IPv4 и IPv6. Если вы хотите управлять взаимодействием с Microsoft Teams, используйте диапазоны IP-адресов в URL-адресах и диапазонах IP-адресов [Office 365.](urls-and-ip-address-ranges.md)
  
### <a name="exchange-online-protection-and-ipv6"></a>Exchange Online Protection и IPv6

Exchange Online Protection (EOP) поддерживает протокол IPv6, если передача происходит по протоколу безопасности транспортного уровня. Для диапазона EOP используйте [URL-адреса и диапазоны IP-адресов Office 365.](urls-and-ip-address-ranges.md)
  
### <a name="ipv6-support-for-office-365-government-offerings"></a>Поддержка IPv6 для правительственных предложений Office 365

Поддержка office 365 IPv6 для правительственных предложений соответствует соглашению об управлении и бюджете (OMB) для руководителей информационных отделов и агентств, а также федеральному руководству по внедрению протокола IPv6. [Microsoft Office 365](https://go.microsoft.com/fwlink/p/?LinkId=325414) для государственных организаций — это служба с несколькими арендаторами, которая хранит данные правительства США в отдельном облаке сообщества. Как и другие предложения Office 365, он предоставляет службы повышения производительности и совместной работы, включая Exchange Online, Skype для бизнеса, SharePoint Online и приложения Microsoft 365 для предприятий. 

Предложения Microsoft Office 365 для государственных органов применимы только к 2013 и более поздним. Дополнительные сведения о предложениях office 365 для государственных организаций см. в объявлении [Office 365](https://go.microsoft.com/fwlink/p/?LinkId=325414)для государственных организаций: облако сообщества для государственных организаций США. Международный трафик в оружейном регламенте (ITAR) — это набор нормативных актов правительства США, которые контролируют экспорт и импорт статей и служб, связанных с защитой, в [usML-списке](https://go.microsoft.com/fwlink/p/?LinkId=325415)США. 

Microsoft Office 365 для предприятий предоставляет специализированные службы размещения для решений майкрософт для повышения производительности, которые поддерживают требования безопасности, конфиденциальности и соответствия нормативным требованиям для федеральных агентств США, требующих сертификации FISMA, и коммерческих организаций, подчиняющихся ITAR.
  
## <a name="things-to-consider-when-using-ipv6-and-office-365"></a>Что следует учитывать при использовании IPv6 и Office 365

Не рекомендуется отключать IPv6. Дополнительные сведения см. в этой [статье.](https://support.microsoft.com/help/929852/guidance-for-configuring-ipv6-in-windows-for-advanced-users) Чтобы определить, какие версии IP-адресов используются в сети, рассмотрите следующие вопросы:
  
- Если отображение команды **IPConfig** в командной строке содержит строки с именами "IPv6-адрес" или "Временный IPv6-адрес", в вашей среде есть IPv6.

- If all the IPv6 addresses begin with "fe80" and correspond to rows named "Link-Local IPv6 Address", you don't have IPv6 in your environment.

Эти вопросы могут быть применимы к вашей сети:
  
- Служба общедоступных подписок не поддерживает покупку с помощью кредитной карты по IPv6. Это не относится к облаку сообщества для государственных организаций (GCC), так как Соглашение Enterprise лицензий (EA).

- IPv6 не поддерживает некоторые сценарии служб управления правами (RMS).

- IPv6 не поддерживает BlackBerry® Enterprise Server (BES), так как BlackBerry не поддерживает IPv6.

- Если вы используете службы федерации Active Directory (AD FS) с Office 365, реклама конечной точки сети AD FS в Office 365 с помощью IPv6 не поддерживается. Не следует включать записи AAAA в запись DNS AD FS при использовании Exchange Online. 

Вы можете быстро вернуться сюда с помощью этой короткой ссылки: [https://aka.ms/o365ip6](https://aka.ms/o365ip6)
  
## <a name="see-also"></a>См. также

[План обучения по IPv6](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/gg250710(v%3dws.10))
  
[Руководство по выявиванию IPv6](https://social.technet.microsoft.com/wiki/contents/articles/1728.ipv6-survival-guide.aspx)
