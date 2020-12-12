---
title: Использование Подключения к домену
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
description: Узнайте, как работать с регистраторами с поддержкой Domain Connect и добавлять домен в Microsoft 365.
ms.openlocfilehash: 109255d82100e636e3472242866a519ff64a9e54
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2020
ms.locfileid: "49655616"
---
# <a name="using-domain-connect"></a>Использование Подключения к домену

 Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.yml)**.
  
[Регистраторы ](https://www.domainconnect.org/) с включенным подключением к домену позволяют добавлять домен в Microsoft 365 в течение трех этапов, который занимает несколько минут. 
  
В мастере мы просто подтвердим, что вы владеете доменом, а затем автоматически настроим записи домена, поэтому электронная почта поступает в Microsoft 365 и другие службы Microsoft 365, например Teams, работают с вашим доменом.
  
> [!NOTE]
> Прежде чем запускать мастер установки, убедитесь, что в браузере отключено блокирование всплывающих окон.
  
## <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>Интеграция регистраторов Domain Connect с Microsoft 365

- [1 &amp; 1 IONOS](https://www.1and1.com/)
- [123Reg](https://www.123-reg.co.uk/)
- [GoDaddy](https://www.godaddy.com/)
- [WordPress](https://wordpress.com/)
- [Plesk](https://www.plesk.com/)
- [MediaTemple](https://mediatemple.net/)
- SecureServer или WildWestDomains (resellers GoDaddy using SecureServer DNS hosting)
    - [Домены MadDog](https://www.maddogdomains.com/)
    - [CheapNames](https://www.cheapnames.com)

## <a name="what-happens-to-my-email-and-website"></a>Что происходит с электронной почтой и веб-сайтом?

После завершения настройки запись MX для вашего домена будет обновлена так, чтобы она указыировала на Microsoft 365, и вся электронная почта для вашего домена начнет приходить в Microsoft 365. Убедитесь, что вы добавили пользователей и настроили почтовые ящики в Microsoft 365 для всех, кто получает электронную почту в вашем домене!
  
Если у вас есть веб-сайт, который вы используете для бизнеса, он будет работать как прежде. Действия по настройке Domain Connect не влияют на ваш веб-сайт.
