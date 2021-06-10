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
description: Сводка. Описывает поддержку IPv6 в Microsoft Office 365 компонентах и в Office 365 государственных предложениях.
ms.openlocfilehash: 7f06ed6f8df2c6552ee0a331ad958bca289d0a09
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909686"
---
# <a name="ipv6-support-in-office-365-services"></a>Поддержка протокола IPv6 в службах Office 365

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Office 365 поддерживает IPv6 и IPv4; однако не все Office 365 полностью включены с помощью IPv6. Это означает, что для подключения к Office 365 необходимо использовать IPv4 и IPv6. Если вы фильтруете исходящие потоки Office 365, полный список адресов IPv6, поддерживаемых Office 365, можно найти [](urls-and-ip-address-ranges.md)в диапазонах URL Office 365 и IP-адресов. После настройки сети и разрешены соответствующие адреса IPv6, вы можете скачать тестовый план [Office 365 IPv6](https://go.microsoft.com/fwlink/?LinkId=293447) из Центра загрузки Майкрософт.
  
## <a name="ipv6-support-in-office-365-subscription-service"></a>Поддержка IPv6 в Office 365 службе подписки

### <a name="exchange-online-and-ipv6"></a>Exchange Online и IPv6

Если программа, используемая для подключения к Exchange Online поддерживает IPv6, она будет использовать IPv6 по умолчанию как в проводных, так и в беспроводных сетях. Если вы хотите управлять связью для Exchange Online, используйте диапазоны IP-адресов в [Office 365 URL-адресов и диапазонах IP-адресов.](urls-and-ip-address-ranges.md)
  
### <a name="sharepoint-online-and-ipv6"></a>SharePoint Online и IPv6

 **Office 365 для государственных организаций G1/G3/G4/K1** Если программа, используемая для подключения к SharePoint Online, поддерживает IPv6, она будет пытаться использовать IPv6 по умолчанию.
  
 **Общедоступные облачные платформы с несколькими клиентами** Корпорация Майкрософт включает SharePoint IPv6 по вашему запросу. Для DNS-инфраструктуры организации необходимо предоставить IP-адреса CIDR, замещенные нотами. Имейте в виду, что эта инфраструктура DNS не может быть совместной другими организациями для включения IPv6 для клиента. После включения IPv6 программа, используемая для подключения к SharePoint Online, поддерживает IPv6, по умолчанию использует IPv6.
  
Если программа, используемая для подключения к SharePoint Online, поддерживает IPv6, она по умолчанию будет использовать IPv6 как в проводных, так и в беспроводных сетях. Если вы хотите управлять связью SharePoint Online, используйте диапазоны IP-адресов в Office 365 [url-адресов и IP-адресов.](urls-and-ip-address-ranges.md)
  
 **Office 365 для государственных организаций G1/G3/G4/K1** Если программа, используемая для подключения к SharePoint Online, поддерживает IPv6, она будет пытаться использовать IPv6 по умолчанию.
  
### <a name="skype-for-business-and-ipv6"></a>Skype для бизнеса и IPv6

Обратите внимание, что IPv6 не поддерживается в Skype для бизнеса и больше не может быть включена.

### <a name="microsoft-teams-and-ipv6"></a>Microsoft Teams и IPV6

Microsoft Teams Прямая маршрутная маршрутия поддерживает только IPv4. Служба Microsoft Teams и клиентская поддержка как IPv4, так и IPv6. Если вы хотите управлять Microsoft Teams, используйте диапазоны IP Office 365 URL-адресов и [IP-адресов.](urls-and-ip-address-ranges.md)
  
### <a name="exchange-online-protection-and-ipv6"></a>Exchange Online Protection и IPv6

Exchange Online Protection (EOP) поддерживает IPv6, если передача происходит по протоколу безопасности транспортного слоя. Для диапазона EOP используйте [Office 365 URL-адреса и диапазоны IP-адресов.](urls-and-ip-address-ranges.md)
  
### <a name="ipv6-support-for-office-365-government-offerings"></a>Поддержка IPv6 для Office 365 правительственных предложений

Office 365 Поддержка IPv6 для государственных предложений соответствует меморандуму Office по управлению и бюджету (OMB) для главных должностных лиц по информационным вопросам исполнительных департаментов и учреждений, а также меморандуму о принятии федеральным правительством протокола к Интернету версии 6 (IPv6). [Microsoft Office 365 для правительства —](https://go.microsoft.com/fwlink/p/?LinkId=325414) это служба с несколькими клиентами, которая хранит данные правительства США в изолированном облаке сообщества. Как и другие Office 365, она предоставляет службы производительности и совместной работы, включая Exchange Online, Skype для бизнеса, SharePoint Online и Приложения Microsoft 365 для предприятий. 

Предложения Microsoft Office 365 действуют только в 2013 году и более позднем. Дополнительные сведения о предложениях Office 365 правительства см. в Office 365 [Для правительства:](https://go.microsoft.com/fwlink/p/?LinkId=325414)облако сообщества для государственных организаций . International Traffic in Arms Regulations (ITAR) — это набор правительственных правил США, которые контролируют экспорт и импорт статей и служб, связанных с обороной, в списке боеприпасов США [(USML).](https://go.microsoft.com/fwlink/p/?LinkId=325415) 

Microsoft Office 365 для предприятий предоставляет специализированные службы хостинга для решений по производительности Майкрософт, которые поддерживают требования к безопасности, конфиденциальности и нормативным требованиям для федеральных учреждений США, которым требуется сертификация Федеральной службы управления информационной безопасностью (FISMA) и коммерческих субъектов, подчиняющихся ИТАР.
  
## <a name="things-to-consider-when-using-ipv6-and-office-365"></a>Что следует учитывать при использовании IPv6 и Office 365

Рекомендуется не отключать IPv6. Дополнительные сведения см. в статье [руководство](https://support.microsoft.com/help/929852/guidance-for-configuring-ipv6-in-windows-for-advanced-users). Чтобы определить, какие IP-версии используются в сети, рассмотрим следующее:
  
- Если отображение команды **IPConfig** в командной строке содержит строки с именем "адрес IPv6" или "Временный адрес IPv6", в вашей среде есть IPv6.

- Если все адреса IPv6 начинаются с "fe80" и соответствуют строкам с именем "Link-Local IPv6 Address", у вас нет IPv6 в среде.

Эти соображения могут применяться к вашей сети:
  
- Государственная служба подписки не поддерживает покупку с помощью кредитной карты через IPv6. Это не относится к облако сообщества для государственных организаций (GCC), так как правительства Соглашение Enterprise (EA).

- IPv6 не поддерживает некоторые сценарии служб управления правами (RMS).

- IPv6 не поддерживает сервер BlackBerry® Enterprise (BES), так как BlackBerry не поддерживает IPv6.

- Если вы используете службы федерации Active Directory (AD FS) с Office 365, реклама конечной точки сети AD FS в Office 365 с помощью IPv6 не поддерживается. Не следует включать записи AAAA в запись DNS AD FS при использовании Exchange Online. 

Вы можете быстро вернуться сюда с помощью этой короткой ссылки: [https://aka.ms/o365ip6]()
  
## <a name="see-also"></a>См. также

[Дорожная карта обучения IPv6](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/gg250710(v%3dws.10))
  
[Руководство по выживанию IPv6](https://social.technet.microsoft.com/wiki/contents/articles/1728.ipv6-survival-guide.aspx)