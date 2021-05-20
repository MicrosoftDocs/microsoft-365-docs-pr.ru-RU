---
title: Изменение адреса электронной почты с использованием пользовательского домена
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: f4d8cae9-6d06-4c4b-b4e5-6581fd05ea82
description: Измените свой адрес электронной почты на дружественный адрес электронной почты, tom@fourthcoffee.com, покупая доменное имя и добавляя его Microsoft 365.
ms.openlocfilehash: d5e70856c9200cd7e5df0eded25b6ff460e5d1fe
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572097"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a>Изменение адреса электронной почты с использованием пользовательского домена

 Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.yml)**. 
  
::: moniker range="o365-worldwide"

Ваш первоначальный адрес электронной почты в Microsoft 365 включает в себя onmicrosoft.com, как tom@fourthcoffee.onmicrosoft.com. Вы можете изменить его на более понятный адрес, например ivan@fourthcoffee.com. Сначала вам потребуется получить собственное доменное имя, например fourthcoffee.com. Если оно у вас уже есть, отлично! Если нет, вы можете узнать, как [приобрести имя у регистратора доменных имен](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

::: moniker range="o365-germany"

Ваш первоначальный адрес электронной почты в Office 365 включает в себя .onmicrosoft.de, как tom@fourthcoffee.onmicrosoft.de. Вы можете изменить его на более дружелюбный адрес, как tom@fourthcoffee.de. Вам понадобится ваше собственное доменное имя, как и fourthcoffee.de первый. Если оно у вас уже есть, отлично! Если нет, вы можете узнать, как [приобрести имя у регистратора доменных имен](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

::: moniker range="o365-21vianet"

Ваш первоначальный адрес электронной почты в Office 365 управляется 21Vianet включает в себя partner.onmschina.cn, как tom@fourthcoffee.partner.onmschina.cn. Вы можете изменить его на более дружелюбный адрес, как tom@fourthcoffee.cn. Вам понадобится ваше собственное доменное имя, как и fourthcoffee.cn первый. Если оно у вас уже есть, отлично! Если нет, вы можете узнать, как [приобрести имя у регистратора доменных имен](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

Когда вы измените электронную почту вашего домена, чтобы прийти к Microsoft 365, путем обновления MX записи вашего домена во время установки, все письма, отправленные на этот домен начнет приходить в Microsoft 365. Убедитесь, что вы добавили пользователей и создали почтовые ящики в Microsoft 365 для всех, кто имеет электронную почту на вашем домене, прежде чем изменить запись MX. Не хотите, чтобы переместить электронную почту для всех на вашем домене, чтобы Microsoft 365? Вы можете принять меры для [пилотного Microsoft 365 с помощью всего лишь нескольких адресов электронной почты, а не](../misc/pilot-microsoft-365-from-my-custom-domain.md).
  
## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a>Измените свой адрес электронной почты, чтобы использовать пользовательский домен, используя Microsoft 365-центр

Для выполнения этих шагов необходимо иметь глобальную учетную запись администратора. 

::: moniker range="o365-worldwide"

1. Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>. 

::: moniker-end
   
::: moniker range="o365-germany"
    
1. Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>. 
    
::: moniker-end

::: moniker range="o365-21vianet"

1. Перейти к админ-центру в <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn </a>. 

::: moniker-end 

2. Перейдите на **страницу**  >  **Настройка доменов.** 

3. На странице **Домены** выберите **Добавить домен**.
    
4. Следуйте указаниям, чтобы подтвердить право собственности на домен и изменить адрес электронной почты.
    
Вы будете руководствоваться, чтобы получить все настроить правильно с вашим доменом в Microsoft 365.

> [!NOTE]
> Если вы не используете лицензию Exchange, вы не можете использовать домен для отправки или получения писем от Microsoft 365 арендатора.
  
## <a name="related-content"></a>См. также:

[Купить пользовательский домен с помощью Microsoft 365](../get-help-with-domains/buy-a-domain-name.md) (статья)
