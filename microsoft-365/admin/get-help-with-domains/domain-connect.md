---
title: Использование доменных Подключение
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ec6f4bd8-5996-4505-ba68-afaf8a141fb9
description: Узнайте, как работать с регистраторами Подключение домена и добавить домен в Microsoft 365.
ms.openlocfilehash: 5dec69f70273e6a9430ce5926ed07888e197adcd
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860659"
---
# <a name="using-domain-connect"></a>Использование доменных Подключение

 Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.yml)**.
  
[Регистраторы Подключение](https://www.domainconnect.org/) домена позволяют добавлять домен в Microsoft 365 в трехшаговом процессе, который занимает несколько минут. 
  
В мастере мы просто подтвердим, что вы владеете доменом, а затем автоматически настроим записи вашего домена, поэтому электронная почта поступает в Microsoft 365 и другие службы Microsoft 365, например Teams, работают с доменом.
  
> [!NOTE]
> Прежде чем запускать мастер установки, убедитесь, что в браузере отключено блокирование всплывающих окон.
  
## <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>Регистраторы Подключение доменов, интегрируясь с Microsoft 365

- [1 &amp; 1 IONOS](https://www.1and1.com/)
- [123Reg](https://www.123-reg.co.uk/)
- [GoDaddy](https://www.godaddy.com/)
- [WordPress](https://wordpress.com/)
- [Plesk](https://www.plesk.com/)
- [MediaTemple](https://mediatemple.net/)
- SecureServer или WildWestDomains (реселлеры GoDaddy с помощью DNS-хостинга SecureServer)
    - [Веб-хостинг MadDog](https://maddogwebhosting.com/domains/)
    - [CheapNames](https://www.cheapnames.com)

## <a name="what-happens-to-my-email-and-website"></a>Что происходит с моей электронной почтой и веб-сайтом?

После завершения настройки записи MX для вашего домена обновляется, чтобы указать на Microsoft 365 и вся электронная почта для вашего домена начнет приходить в Microsoft 365. Убедитесь, что вы добавили пользователей и настроили почтовые ящики в Microsoft 365 для всех, кто получает электронную почту на вашем домене!
  
Если у вас есть веб-сайт, который вы используете для бизнеса, он будет работать как прежде. Действия Подключение домена не влияют на веб-сайт.
