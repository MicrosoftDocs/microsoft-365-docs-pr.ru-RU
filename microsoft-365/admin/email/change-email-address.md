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
description: 'Измените исходный адрес электронной почты на понятный адрес, например tom@fourthcoffee.com smtp. Для этого необходимо купить доменное имя и добавить его в Microsoft 365. '
ms.openlocfilehash: dc6d418961fe29a363aa6a787d8c0bb2d11d7e97
ms.sourcegitcommit: 167c05cc6a776f62f0a0c2de5f3ffeb68c4a27ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814484"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a>Изменение адреса электронной почты с использованием пользовательского домена

::: moniker range="o365-21vianet"

> [!NOTE]
> Изменяется Центр администрирования. Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

 Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.md)**. 
  
::: moniker range="o365-worldwide"

Ваш исходный адрес электронной почты в Microsoft 365 включает в себя расширение onmicrosoft.com,tom@fourthcoffee.onmicrosoft.com. Вы можете изменить его на более понятный адрес, например ivan@fourthcoffee.com. Сначала вам потребуется получить собственное доменное имя, например fourthcoffee.com. Если оно у вас уже есть, отлично! Если нет, вы можете узнать, как [приобрести имя у регистратора доменных имен](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

::: moniker range="o365-germany"

Исходный адрес электронной почты в Office 365 Germany включает расширение .onmicrosoft.de, например tom@fourthcoffee.onmicrosoft.de. Вы можете изменить его на более понятный адрес, например tom@fourthcoffee.de. Сначала вам понадобится ваше доменное имя, напримерfourthcoffee.de. Если оно у вас уже есть, отлично! Если нет, вы можете узнать, как [приобрести имя у регистратора доменных имен](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

::: moniker range="o365-21vianet"

Ваш исходный адрес электронной почты в службе Office 365, предоставляемой 21Vianet, включает partner.onmschina.cn, например tom@fourthcoffee.partner.onmschina.cn. Вы можете изменить его на более понятный адрес, например tom@fourthcoffee.cn. Для начала вам понадобится самостоятельное доменное имя, fourthcoffee.cn. Если оно у вас уже есть, отлично! Если нет, вы можете узнать, как [приобрести имя у регистратора доменных имен](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

Когда вы меняете электронную почту домена для Microsoft 365, обративая запись MX домена во время установки, все сообщения, отправляемые в этот домен, будут поступать в Microsoft 365. Убедитесь, что вы добавили пользователей и создали почтовые ящики в Microsoft 365 для всех пользователей, у которых есть электронная почта в вашем домене, ПРЕЖДЕ Чем изменить запись MX. Не планируете перемещать в Microsoft 365 электронную почту для всех пользователей вашего домена? Чтобы выполнить пилотное развертывание [Microsoft 365 с несколькими адресами электронной почты, можно предпринять меры.](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain?view=o365-worldwide)
  
## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a>Изменение адреса электронной почты на использование личного домена с помощью Центра администрирования Microsoft 365

Для выполнения этих действий требуются учетные записи глобального администратора. 

::: moniker range="o365-worldwide"

1. Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>. 

::: moniker-end
   
::: moniker range="o365-germany"
    
1. Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>. 
    
::: moniker-end

::: moniker range="o365-21vianet"

1. Перейдите в Центр <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn </a>администрирования в любой полю. 

::: moniker-end 

2. Перейдите на страницу **"Настройка**  >  **доменов".** 

3. На странице **Домены** выберите **Добавить домен**.
    
4. Следуйте указаниям, чтобы подтвердить право собственности на домен и изменить адрес электронной почты.
    
Пошаговые инструкции помогут вам правильно настроить домен в Microsoft 365.

> [!NOTE]
> Если вы не используете лицензию Exchange, вы не сможете использовать домен для отправки и получения сообщений электронной почты из клиента Microsoft 365.
  
## <a name="related-articles"></a>Статьи по теме

[Приобретение личного домена с помощью Microsoft 365](../get-help-with-domains/buy-a-domain-name.md)
 
