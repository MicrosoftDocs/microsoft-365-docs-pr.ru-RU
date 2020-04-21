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
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: f4d8cae9-6d06-4c4b-b4e5-6581fd05ea82
description: 'Замените начальный адрес электронной почты на понятный адрес электронной почты, такой как tom@fourthcoffee.com. Для этого необходимо приобрести доменное имя и добавить его в Microsoft 365. '
ms.openlocfilehash: d419521210740cfa76a911cf0d66e7826ee8e626
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629063"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a>Изменение адреса электронной почты с использованием пользовательского домена

 Если вы не нашли то, что вы ищете, обратитесь к разделу **[Вопросы и ответы по доменам](../setup/domains-faq.md)**. 
  
::: moniker range="o365-worldwide"

Ваш исходный адрес электронной почты в Microsoft 365 включает. onmicrosoft.com, например tom@fourthcoffee.onmicrosoft.com. Вы можете изменить его на более понятный адрес, например ivan@fourthcoffee.com. Сначала вам потребуется получить собственное доменное имя, например fourthcoffee.com. Если оно у вас уже есть, отлично! Если нет, вы можете узнать, как [приобрести имя у регистратора доменных имен](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

::: moniker range="o365-germany"

Ваш исходный адрес электронной почты в Office 365 Германия включает. onmicrosoft.de, например tom@fourthcoffee.onmicrosoft.de. Вы можете изменить его на более понятный адрес, такой как tom@fourthcoffee.de. Вам потребуется собственное доменное имя, например fourthcoffee.de. Если оно у вас уже есть, отлично! Если нет, вы можете узнать, как [приобрести имя у регистратора доменных имен](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

::: moniker range="o365-21vianet"

Ваш исходный адрес электронной почты в Office 365 под управлением 21Vianet включает partner.onmschina.cn, например tom@fourthcoffee.partner.onmschina.cn. Вы можете изменить его на более понятный адрес, такой как tom@fourthcoffee.cn. Вам потребуется собственное доменное имя, например fourthcoffee.cn. Если оно у вас уже есть, отлично! Если нет, вы можете узнать, как [приобрести имя у регистратора доменных имен](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

Когда вы изменяете электронную почту вашего домена на поступающий в Microsoft 365, обновляя запись MX вашего домена во время установки, все сообщения, отправленные в этот домен, начнут приходить в Microsoft 365. Убедитесь, что добавлены пользователи и созданные почтовые ящики в Microsoft 365 для всех пользователей, у которых есть электронная почта в вашем домене, прежде чем изменять запись MX. Не хотите перемещать электронную почту для всех пользователей вашего домена в Microsoft 365? Вы можете выполнить действия для [пилотного развертывания Microsoft 365 с использованием всего нескольких адресов электронной почты](https://support.office.com/article/39cee536-6a03-40cf-b9c1-f301bb6001d7.aspx).
  
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

2. Перейдите на страницу "**домены** **установки** > ". 

3. На странице **домены** выберите **Добавить домен**.
    
4. Следуйте указаниям, чтобы подтвердить право собственности на домен и изменить адрес электронной почты.
    
Вы узнаете, как правильно настроить все параметры домена в Microsoft 365.

> [!NOTE]
> Если вы не используете лицензию Exchange, вы не можете использовать домен для отправки или получения электронных сообщений от клиента Microsoft 365.
  
## <a name="related-articles"></a>Статьи по теме

[Приобретение настраиваемого домена с помощью Microsoft 365](../get-help-with-domains/buy-a-domain-name.md)
 
