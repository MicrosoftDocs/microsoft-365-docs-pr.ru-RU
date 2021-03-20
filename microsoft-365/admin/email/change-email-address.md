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
description: 'Измените начальный адрес электронной почты на дружественный адрес электронной почты, например tom@fourthcoffee.com. Для этого необходимо купить доменное имя и добавить его в Microsoft 365. '
ms.openlocfilehash: 10dff4e0523062ae763c08a972563dc8b5582038
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915930"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a>Изменение адреса электронной почты с использованием пользовательского домена

::: moniker range="o365-21vianet"

> [!NOTE]
> Изменяется Центр администрирования. Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).

::: moniker-end

 Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.yml)**. 
  
::: moniker range="o365-worldwide"

Начальный адрес электронной почты в Microsoft 365 включает в себя .onmicrosoft.com, например tom@fourthcoffee.onmicrosoft.com. Вы можете изменить его на более понятный адрес, например ivan@fourthcoffee.com. Сначала вам потребуется получить собственное доменное имя, например fourthcoffee.com. Если оно у вас уже есть, отлично! Если нет, вы можете узнать, как [приобрести имя у регистратора доменных имен](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

::: moniker range="o365-germany"

Начальный адрес электронной почты в Office 365 в Германии включает в себя .onmicrosoft.de, например tom@fourthcoffee.onmicrosoft.de. Вы можете изменить его на более дружелюбный адрес, например tom@fourthcoffee.de. Сначала вам потребуется собственное доменное имя, например fourthcoffee.de. Если оно у вас уже есть, отлично! Если нет, вы можете узнать, как [приобрести имя у регистратора доменных имен](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

::: moniker range="o365-21vianet"

Начальный адрес электронной почты в Office 365, управляемый 21Vianet, включает partner.onmschina.cn, например tom@fourthcoffee.partner.onmschina.cn. Вы можете изменить его на более дружелюбный адрес, например tom@fourthcoffee.cn. Вам понадобится собственное доменное имя, например fourthcoffee.cn сначала. Если оно у вас уже есть, отлично! Если нет, вы можете узнать, как [приобрести имя у регистратора доменных имен](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

При изменении электронной почты домена для отправки в Microsoft 365 при обновлении записи MX домена во время настройки все отправленные в этот домен электронные письма начнут приходить в Microsoft 365. Убедитесь, что вы добавили пользователей и создали почтовые ящики в Microsoft 365 для всех, у кого есть электронная почта на вашем домене, прежде чем изменить запись MX. Не хотите перемещать электронную почту для всех на домене в Microsoft 365? Вы можете предпринять действия для [пилотирования Microsoft 365 с помощью нескольких адресов электронной почты.](../misc/pilot-microsoft-365-from-my-custom-domain.md?view=o365-worldwide)
  
## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a>Измените адрес электронной почты, чтобы использовать настраиваемый домен с помощью центра администрирования Microsoft 365

Для выполнения этих действий необходимо иметь глобальную учетную запись администратора. 

::: moniker range="o365-worldwide"

1. Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>. 

::: moniker-end
   
::: moniker range="o365-germany"
    
1. Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>. 
    
::: moniker-end

::: moniker range="o365-21vianet"

1. Перейдите в центр <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn </a>администрирования по крайней . 

::: moniker-end 

2. Перейдите на **страницу Setup**  >  **Domains.** 

3. На странице **Домены** выберите **Добавить домен**.
    
4. Следуйте указаниям, чтобы подтвердить право собственности на домен и изменить адрес электронной почты.
    
Вы будете руководствоваться, чтобы все правильно настроить с доменом в Microsoft 365.

> [!NOTE]
> Если вы не используете лицензию Exchange, вы не можете использовать домен для отправки или получения сообщений электронной почты от клиента Microsoft 365.
  
## <a name="related-articles"></a>Статьи по теме

[Купить настраиваемый домен с помощью Microsoft 365](../get-help-with-domains/buy-a-domain-name.md)
