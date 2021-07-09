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
description: Измените адрес электронной почты на дружественный адрес электронной почты tom@fourthcoffee.com, купив доменное имя и добавив его в Microsoft 365.
ms.openlocfilehash: 7fb113c0efd6462c4c703956a20c390f2d555d5f
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341464"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a>Изменение адреса электронной почты с использованием пользовательского домена

 Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.yml)**. 
  
::: moniker range="o365-worldwide"

Начальный адрес электронной почты в Microsoft 365 включает .onmicrosoft.com, например tom@fourthcoffee.onmicrosoft.com. Вы можете изменить его на более понятный адрес, например ivan@fourthcoffee.com. Сначала вам потребуется получить собственное доменное имя, например fourthcoffee.com. Если оно у вас уже есть, отлично! Если нет, вы можете узнать, как [приобрести имя у регистратора доменных имен](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

::: moniker range="o365-germany"

Начальный адрес электронной почты в Office 365 Германии включает в себя .onmicrosoft.de, например tom@fourthcoffee.onmicrosoft.de. Вы можете изменить его на более дружелюбный адрес, например tom@fourthcoffee.de. Сначала вам потребуется собственное доменное имя, например fourthcoffee.de. Если оно у вас уже есть, отлично! Если нет, вы можете узнать, как [приобрести имя у регистратора доменных имен](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

::: moniker range="o365-21vianet"

Начальный адрес электронной почты в Office 365 21Vianet включает partner.onmschina.cn, например tom@fourthcoffee.partner.onmschina.cn. Вы можете изменить его на более дружелюбный адрес, например tom@fourthcoffee.cn. Вам понадобится собственное доменное имя, например fourthcoffee.cn сначала. Если оно у вас уже есть, отлично! Если нет, вы можете узнать, как [приобрести имя у регистратора доменных имен](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

При изменении электронной почты домена для Microsoft 365, обновив запись MX домена во время настройки, все отправленные в этот домен электронные письма начнут приходить в Microsoft 365. Убедитесь, что вы добавили пользователей и создали почтовые ящики в Microsoft 365 для всех, у кого есть электронная почта на вашем домене перед изменением записи MX. Не хотите переместить электронную почту для всех на вашем домене, чтобы Microsoft 365? Вы можете предпринять шаги, чтобы Microsoft 365 [с несколькими адресами электронной почты вместо](../misc/pilot-microsoft-365-from-my-custom-domain.md).
  
## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a>Измените адрес электронной почты, чтобы использовать настраиваемый домен с помощью Центр администрирования Microsoft 365

Эти действия может выполнять только глобальный администратор.

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

4. Следуйте шагам, чтобы подтвердить, что у вас есть домен. Вы будете руководствоваться, чтобы все правильно настроить с доменом в Microsoft 365.

5. Перейдите к **пользователям**  >  **Активные пользователи**.

6. Выберите пользователя, чтобы изменить имя пользователя и изменить его на только что добавленный домен.

> [!NOTE]
> Если вы не используете лицензию Exchange, вы не можете использовать домен для отправки или получения электронных Microsoft 365 клиента.
  
## <a name="related-content"></a>Связанные материалы

[Купить настраиваемый домен с Microsoft 365](../get-help-with-domains/buy-a-domain-name.md) (статья)\
[Управление доменами](../get-help-with-domains/index.yml) (страница ссылки)\
[Вопросы и ответы о доменах](../setup/domains-faq.yml) (статья)