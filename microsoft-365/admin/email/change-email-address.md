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
description: 'Замените начальный адрес электронной почты на понятный адрес электронной почты, такой как tom@fourthcoffee.com. Для этого необходимо приобрести доменное имя и добавить его в Office 365. '
ms.openlocfilehash: dc0ab64003b48eec50bf34e60d8a6df463b4fe89
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212037"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a>Изменение адреса электронной почты с использованием пользовательского домена

 **[Вопросы и ответы по доменам](../setup/domains-faq.md)**. 
  
::: moniker range="o365-worldwide"

Ваш исходный адрес электронной почты в Office 365 включает домен .onmicrosoft.com, например ivan@fourthcoffee.onmicrosoft.com. Вы можете изменить его на более понятный адрес, например ivan@fourthcoffee.com. Сначала вам потребуется получить собственное доменное имя, например fourthcoffee.com. Если оно у вас уже есть, отлично! Если нет, вы можете узнать, как [приобрести имя у регистратора доменных имен](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

::: moniker range="o365-germany"

Ваш исходный адрес электронной почты в Office 365 Германия включает. onmicrosoft.de, например tom@fourthcoffee.onmicrosoft.de. Вы можете изменить его на более понятный адрес, такой как tom@fourthcoffee.de. Вам потребуется собственное доменное имя, например fourthcoffee.de. Если оно у вас уже есть, отлично! Если нет, вы можете узнать, как [приобрести имя у регистратора доменных имен](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

::: moniker range="o365-21vianet"

Ваш исходный адрес электронной почты в Office 365 под управлением 21Vianet включает partner.onmschina.cn, например tom@fourthcoffee.partner.onmschina.cn. Вы можете изменить его на более понятный адрес, такой как tom@fourthcoffee.cn. Вам потребуется собственное доменное имя, например fourthcoffee.cn. Если оно у вас уже есть, отлично! Если нет, вы можете узнать, как [приобрести имя у регистратора доменных имен](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

После изменения записи MX на этапе настройки таким образом, чтобы электронная почта вашего домена поступала в систему Office 365, ВСЕ почтовые сообщения, отправленные в домен, будут направляться в Office 365. Не забудьте добавить пользователей и создать почтовые ящики в Office 365 для всех, кто работает с электронной почтой в вашем домене, ДО изменения записи MX. Если вы не планируете переносить в Office 365 электронную почту для всех пользователей своего домена, воспользуйтесь [инструкциями по пилотному развертыванию Office 365 с несколькими адресами электронной почты](https://support.office.com/article/39cee536-6a03-40cf-b9c1-f301bb6001d7.aspx).
  
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
    
Пошаговые инструкции помогут вам правильно выполнить все этапы настройки домена в Office 365.

> [!NOTE]
> Если вы не используете лицензию Exchange, вы не можете использовать домен для отправки и получения сообщений электронной почты от клиента Office 365.
  
## <a name="related-articles"></a>Статьи по теме

[Приобретение пользовательского домена с помощью Office 365](../get-help-with-domains/buy-a-domain-name.md)
 
