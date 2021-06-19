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
description: Сводка. Описывает поддержку IPv6 в 365 компонентах Microsoft Office 365 и в предложениях правительства Office 365.
ms.openlocfilehash: a509b19711092bddf153a677c41860e7a4e5277a
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028911"
---
# <a name="ipv6-support-in-office-365-services"></a>Поддержка протокола IPv6 в службах Office 365

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Office 365 поддерживает IPv6 и IPv4; однако не все функции Office 365 полностью включены с помощью IPv6. Это означает, что для подключения к Office 365 необходимо использовать IPv4 и IPv6. Если вы фильтруете исходящие потоки в Office 365, полный список адресов IPv6, поддерживаемых Office 365, можно найти в статье [URL-адреса Office 365](urls-and-ip-address-ranges.md)и диапазоны IP-адресов. После настройки сети и разрешены соответствующие адреса IPv6, вы можете скачать тестовый план [Office 365 IPv6](https://go.microsoft.com/fwlink/?LinkId=293447) из Центра загрузки Майкрософт.
  
## <a name="ipv6-support-in-office-365-subscription-service"></a>Поддержка IPv6 в службе подписки Office 365

### <a name="exchange-online-and-ipv6"></a>Exchange Online и IPv6

Если программа, используемая для подключения к Exchange Online, поддерживает IPv6, она по умолчанию будет использовать IPv6 как в проводных, так и в беспроводных сетях. Если вы хотите управлять связью с Exchange Online, используйте диапазоны IP-адресов в [URL-адресах Office 365 и ДИАПАЗОНАх IP-адресов.](urls-and-ip-address-ranges.md)
  
### <a name="sharepoint-online-and-ipv6"></a>SharePoint Online и IPv6

 **Office 365 Government G1/G3/G4/K1** Если программа, используемая для подключения к SharePoint Online, поддерживает IPv6, она по умолчанию будет пытаться использовать IPv6.
  
 **Общедоступные облачные платформы с несколькими клиентами** Корпорация Майкрософт включает IPv6 SharePoint Online по вашему запросу. Для DNS-инфраструктуры организации необходимо предоставить IP-адреса CIDR, замещенные нотами. Имейте в виду, что эта инфраструктура DNS не может быть совместной другими организациями для включения IPv6 для клиента. После включения IPv6 программа, используемая для подключения к SharePoint Online, поддерживает IPv6, по умолчанию использует IPv6.
  
Если программа, используемая для подключения к SharePoint Online, поддерживает IPv6, она по умолчанию будет использовать IPv6 как в проводных, так и в беспроводных сетях. Если вы хотите управлять связью с SharePoint Online, используйте диапазоны IP-адресов в [URL-адресах Office 365 и IP-адресах.](urls-and-ip-address-ranges.md)
  
 
  
### <a name="skype-for-business-and-ipv6"></a>Skype для бизнеса и IPv6

Обратите внимание, что IPv6 не поддерживается в Skype для бизнеса и больше не может быть включена.

### <a name="microsoft-teams-and-ipv6"></a>Microsoft Teams и IPV6

Прямая маршрутная маршрутия Microsoft Teams поддерживает только IPv4. Служба Microsoft Teams и клиентская поддержка IPv4 и IPv6. Чтобы управлять связью с Microsoft Teams, используйте диапазоны IP-адресов в [URL-адресах Office 365 и IP-адресах.](urls-and-ip-address-ranges.md)
  
### <a name="exchange-online-protection-and-ipv6"></a>Exchange Online Protection и IPv6

Exchange Online Protection (EOP) поддерживает IPv6, если передача происходит по протоколу безопасности транспортного слоя. Для диапазона EOP используйте [URL-адреса Office 365 и диапазоны IP-адресов.](urls-and-ip-address-ranges.md)
  
### <a name="ipv6-support-for-office-365-government-offerings"></a>Поддержка IPv6 для государственных предложений Office 365

Поддержка правительственных предложений Office 365 IPv6 соответствует меморандуму Office of Management and Budget (OMB) для главных должностных лиц по информационным вопросам исполнительных департаментов и учреждений, а также меморандуму о принятии федеральным правительством протокола Интернета Версии 6 (IPv6). [Microsoft Office 365 для](https://go.microsoft.com/fwlink/p/?LinkId=325414) правительства — это служба с несколькими клиентами, которая хранит данные правительства США в изолированном облаке сообщества. Как и другие предложения Office 365, он предоставляет службы производительности и совместной работы, в том числе Exchange Online, Skype для бизнеса, SharePoint Online и Microsoft 365 Apps для предприятия. 

Предложения Microsoft Office 365 государственных услуг применяются только в 2013 году и более позднем. Дополнительные сведения о предложениях для правительства Office 365 см. в анонсе [Office 365 для правительства: облако](https://go.microsoft.com/fwlink/p/?LinkId=325414)сообщества правительства США. International Traffic in Arms Regulations (ITAR) — это набор правительственных правил США, которые контролируют экспорт и импорт статей и служб, связанных с обороной, в списке боеприпасов США [(USML).](https://go.microsoft.com/fwlink/p/?LinkId=325415) 

Microsoft Office 365 для предприятий предоставляет специализированные службы хостинга для решений по производительности Майкрософт, которые поддерживают требования к безопасности, конфиденциальности и нормативным требованиям для федеральных учреждений США, требующих сертификации Федеральной службы управления информационной безопасностью (FISMA) и коммерческих субъектов, подчиняющихся ИТАР.
  
## <a name="things-to-consider-when-using-ipv6-and-office-365"></a>Что следует учитывать при использовании IPv6 и Office 365

Рекомендуется не отключать IPv6. Дополнительные сведения см. в статье [руководство](https://support.microsoft.com/help/929852/guidance-for-configuring-ipv6-in-windows-for-advanced-users). Чтобы определить, какие IP-версии используются в сети, рассмотрим следующее:
  
- Если отображение команды **IPConfig** в командной строке содержит строки с именем "адрес IPv6" или "Временный адрес IPv6", в вашей среде есть IPv6.

- Если все адреса IPv6 начинаются с "fe80" и соответствуют строкам с именем "Link-Local IPv6 Address", у вас нет IPv6 в среде.

Эти соображения могут применяться к вашей сети:
  
- Государственная служба подписки не поддерживает покупку с помощью кредитной карты через IPv6. Это не относится к облаку правительственных сообществ (GCC), так как у Соглашение Enterprise (EA) лицензирование.

- IPv6 не поддерживает некоторые сценарии служб управления правами (RMS).

- IPv6 не поддерживает Сервер ® (BES), так как BlackBerry не поддерживает IPv6.

- Если вы используете службы Федерации Active Directory (AD FS) с Office 365, реклама конечной точки сети AD FS в Office 365 с помощью IPv6 не поддерживается. Не следует включать записи AAAA в запись DNS AD FS при использовании Exchange Online. 

Вы можете быстро вернуться сюда с помощью этой короткой ссылки: [https://aka.ms/o365ip6]()
  
## <a name="see-also"></a>См. также

[Дорожная карта обучения IPv6](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/gg250710(v%3dws.10))
  
[Руководство по выживанию IPv6](https://social.technet.microsoft.com/wiki/contents/articles/1728.ipv6-survival-guide.aspx)
