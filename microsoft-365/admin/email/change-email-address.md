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
description: 'Измените исходный адрес электронной почты на адрес электронной почты, такой как tom@fourthcoffee.com. Для этого необходимо приобрести доменное имя и добавить его в Microsoft 365. '
ms.openlocfilehash: 445b78f759cee79a794f9656afd5b26051534e26
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114025"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a>Изменение адреса электронной почты с использованием пользовательского домена

::: moniker range="o365-21vianet"

> [!NOTE]
> Изменяется Центр администрирования. Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

 Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.yml)**. 
  
::: moniker range="o365-worldwide"

Исходный адрес электронной почты в Microsoft 365 включает .onmicrosoft.com, например tom@fourthcoffee.onmicrosoft.com. Вы можете изменить его на более понятный адрес, например ivan@fourthcoffee.com. Сначала вам потребуется получить собственное доменное имя, например fourthcoffee.com. Если оно у вас уже есть, отлично! Если нет, вы можете узнать, как [приобрести имя у регистратора доменных имен](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

::: moniker range="o365-germany"

Исходный адрес электронной почты в Office 365 Germany включает .onmicrosoft.de, например tom@fourthcoffee.onmicrosoft.de. Вы можете изменить его на более дружелюбный адрес, например tom@fourthcoffee.de. Вам потребуется собственное доменное имя, например fourthcoffee.de. Если оно у вас уже есть, отлично! Если нет, вы можете узнать, как [приобрести имя у регистратора доменных имен](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

::: moniker range="o365-21vianet"

Исходный адрес электронной почты в Службе Office 365 под управлением 21Vianet включает partner.onmschina.cn, например tom@fourthcoffee.partner.onmschina.cn. Вы можете изменить его на более дружелюбный адрес, например tom@fourthcoffee.cn. Вам потребуется собственное доменное имя, например fourthcoffee.cn. Если оно у вас уже есть, отлично! Если нет, вы можете узнать, как [приобрести имя у регистратора доменных имен](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

При изменении электронной почты домена на Microsoft 365 путем обновления записи MX домена во время настройки все сообщения, от отправленные в этот домен, будут отправляться в Microsoft 365. Перед изменением записи MX убедитесь, что вы добавили пользователей и создали почтовые ящики в Microsoft 365 для всех, у кого есть электронная почта в вашем домене. Не хотите перемещать электронную почту для всех в вашем домене в Microsoft 365? Вы можете предпринять действия для [пилотного проекта Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain?view=o365-worldwide)с несколькими адресами электронной почты.
  
## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a>Изменение адреса электронной почты для использования настраиваемого домена с помощью Центра администрирования Microsoft 365

Для выполнения этих действий необходимо иметь учетную запись глобального администратора. 

::: moniker range="o365-worldwide"

1. Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>. 

::: moniker-end
   
::: moniker range="o365-germany"
    
1. Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>. 
    
::: moniker-end

::: moniker range="o365-21vianet"

1. Перейдите в Центр <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn </a>администрирования по 

::: moniker-end 

2. Перейдите на **страницу "Домены**  >  **установки".** 

3. На странице **Домены** выберите **Добавить домен**.
    
4. Следуйте указаниям, чтобы подтвердить право собственности на домен и изменить адрес электронной почты.
    
Вы получите руководство по правильной настройкам домена в Microsoft 365.

> [!NOTE]
> Если вы не используете лицензию Exchange, вы не можете использовать домен для отправки и получения сообщений электронной почты от клиента Microsoft 365.
  
## <a name="related-articles"></a>Статьи по теме

[Покупка пользовательского домена с помощью Microsoft 365](../get-help-with-domains/buy-a-domain-name.md)
 
