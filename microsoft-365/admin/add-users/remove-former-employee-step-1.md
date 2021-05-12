---
title: Шаг 1 . Остановить вход сотрудника в систему Microsoft 365
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Блокирование входа в систему бывшего сотрудника и блокировка доступа к Microsoft 365 службам.
ms.openlocfilehash: 60f4cf6b5c9a0b5dc2023b3ef7b6460685142d07
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244302"
---
# <a name="step-1---prevent-a-former-employee-from-logging-in-and-block-access-to-microsoft-365-services"></a>Шаг 1 — запретить бывшему сотруднику войти в систему и заблокировать доступ к Microsoft 365 службам

Если необходимо немедленно предотвратить вход пользователя, необходимо сбросить пароль. На этом шаге вынудить пользователя выйти из него Microsoft 365.

1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.
2. Выберите поле рядом с именем пользователя, а затем выберите **пароль Reset**.
3. Введите новый пароль и выберите **Сброс**. (Не отправляйте его им.)
4. Выберите имя пользователя, чтобы перейти к области свойств, а на вкладке **Учетная** запись выберите **инициировать вход.**

В течение часа или после того, как они покидают текущую страницу Microsoft 365 они находятся на - им предложено войти снова. Маркер доступа хорош в течение часа, поэтому сроки зависят от того, сколько времени осталось на этом маркере, и от того, будут ли они переходить из текущей веб-страницы.
  
> [!IMPORTANT]
> Если пользователь находится в Outlook в Интернете, просто щелкнув в почтовом ящике, его могут не выгнать сразу. Как только они выбирают другую плитку, например OneDrive или обновляют браузер, инициировался выход.
  
Чтобы немедленно использовать PowerShell, чтобы выйти из-под действия пользователя, см. в этой ссылке см. в документе ["Revoke-AzureADUserAllRefreshToken".](/powershell/module/azuread/revoke-azureaduserallrefreshtoken)
  
Дополнительные сведения о времени, требуемом для завершения почтового сеанса, см. в разделе [Что нужно знать о завершении почтового сеанса сотрудника](remove-former-employee-step-7.md#what-you-need-to-know-about-terminating-an-employees-email-session).

## <a name="block-a-former-employees-access-to-microsoft-365-services"></a>Блокировка доступа бывшего сотрудника к Microsoft 365 службам

> [!IMPORTANT]
 > Блокировка учетной записи может занять до 24 часов. Если необходимо немедленно предотвратить вход пользователя, выполните действия, которые были выше, и сбросйте пароль.

1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.
2. Выберите имя сотрудника, которого вы хотите заблокировать, и под именем пользователя выберите символ **Block этого пользователя.**
3. Выберите **Блок для пользователя при входе,** а затем выберите **Сохранить**.

## <a name="block-a-former-employees-access-to-email-exchange-online"></a>Блокировка доступа бывшего сотрудника к электронной почте (Exchange Online)

Если у вас есть электронная почта в Microsoft 365 подписки, вопишитесь в центр администрирования Exchange и следуйте этим шагам, чтобы заблокировать доступ к электронной почте своему бывшему сотруднику.
  
1. Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Центр администрирования Exchange</a>.
2. В Центре администрирования Exchange выберите **Получатели** \> **Почтовые ящики**.
3. Дважды щелкните пользователя и перейдите на страницу функций **почтового ящика.** В **статье Мобильные устройства** выберите **отключение Exchange ActiveSync** и отключение **OWA** для устройств и ответ **"Да"** на оба запроса.
4. В **статье Подключение к электронной почте** выберите **Отключение** и **ответ да** при запросе.