---
title: Изменение адреса электронной почты с использованием пользовательского домена
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
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
description: 'Замените начальный адрес электронной почты на понятный адрес электронной почты, такой как tom@fourthcoffee.com. Для этого необходимо приобрести доменное имя и добавить его в Microsoft 365. '
ms.openlocfilehash: e1ac40fb38a207cc0f19f48ac4ab7c6f34ffbb35
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400164"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a>Изменение адреса электронной почты с использованием пользовательского домена

::: moniker range="o365-21vianet"

> [!NOTE]
> Изменяется Центр администрирования. Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

 Если вы не нашли то, что вы ищете, обратитесь к разделу **[вопросы и ответы по доменам](../setup/domains-faq.md)**. 
  
::: moniker range="o365-worldwide"

Ваш исходный адрес электронной почты в Microsoft 365 включает. onmicrosoft.com, например tom@fourthcoffee.onmicrosoft.com. Вы можете изменить его на более понятный адрес, например ivan@fourthcoffee.com. Сначала вам потребуется получить собственное доменное имя, например fourthcoffee.com. Если оно у вас уже есть, отлично! Если нет, вы можете узнать, как [приобрести имя у регистратора доменных имен](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

::: moniker range="o365-germany"

Ваш исходный адрес электронной почты в Office 365 Германия включает. onmicrosoft.de, например tom@fourthcoffee.onmicrosoft.de. Вы можете изменить его на более понятный адрес, такой как tom@fourthcoffee.de. Вам потребуется собственное доменное имя, например fourthcoffee.de. Если оно у вас уже есть, отлично! Если нет, вы можете узнать, как [приобрести имя у регистратора доменных имен](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

::: moniker range="o365-21vianet"

Ваш исходный адрес электронной почты в Office 365 под управлением 21Vianet включает partner.onmschina.cn, например tom@fourthcoffee.partner.onmschina.cn. Вы можете изменить его на более понятный адрес, такой как tom@fourthcoffee.cn. Вам потребуется собственное доменное имя, например fourthcoffee.cn. Если оно у вас уже есть, отлично! Если нет, вы можете узнать, как [приобрести имя у регистратора доменных имен](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

Когда вы изменяете электронную почту вашего домена на поступающий в Microsoft 365, обновляя запись MX вашего домена во время установки, все сообщения, отправленные в этот домен, начнут приходить в Microsoft 365. Убедитесь, что добавлены пользователи и созданные почтовые ящики в Microsoft 365 для всех пользователей, у которых есть электронная почта в вашем домене, прежде чем изменять запись MX. Не хотите перемещать электронную почту для всех пользователей вашего домена в Microsoft 365? Вы можете выполнить действия для [пилотного развертывания Microsoft 365 с использованием всего нескольких адресов электронной почты](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).
  
## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a>Изменение адреса электронной почты для использования личного домена с помощью центра администрирования Microsoft 365

Для выполнения этих действий необходимо иметь глобальную учетную запись администратора. 

::: moniker range="o365-worldwide"

1. Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>. 

::: moniker-end
   
::: moniker range="o365-germany"
    
1. Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>. 
    
::: moniker-end

::: moniker range="o365-21vianet"

1. Перейдите в центр администрирования по адресу <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn </a>. 

::: moniker-end 

2. Перейдите на страницу **Setup**"  >  **домены** установки". 

3. На странице **домены** выберите **Добавить домен**.
    
4. Следуйте указаниям, чтобы подтвердить право собственности на домен и изменить адрес электронной почты.
    
Вы узнаете, как правильно настроить все параметры домена в Microsoft 365.

> [!NOTE]
> Если вы не используете лицензию Exchange, вы не можете использовать домен для отправки или получения электронных сообщений от клиента Microsoft 365.
  
## <a name="related-articles"></a>Статьи по теме

[Приобретение настраиваемого домена с помощью Microsoft 365](../get-help-with-domains/buy-a-domain-name.md)
 
