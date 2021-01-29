---
title: Использование QR-кода для вход в мобильные приложения Outlook
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
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
description: Узнайте, как использовать QR-код для проверки подлинности и скачивания Outlook Mobile.
ms.openlocfilehash: 2d62a49b93fa7bd5f2d747525de7244e8014e6a7
ms.sourcegitcommit: b8e9b2ecdc4927b67088c5fffb1585424c66fb10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2021
ms.locfileid: "50050782"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a>Использование QR-кода для вход в мобильные приложения Outlook

> [!IMPORTANT]
> Эта функция Microsoft 365 находится в открытой предварительной версии. Общедоступный предварительный просмотр предоставляет ранний доступ к функциям Microsoft 365.

Как администратор Microsoft 365 вы можете позволить пользователям входить в приложение Outlook для Android или iOS на своих мобильных устройствах без ввода имени пользователя и пароля. Сканируя QR-код, пользователи могут безопасно проверить подлинность и войти в Outlook Mobile.

В Outlook в Интернете или других классических приложениях Outlook пользователи могут видеть уведомления о том, что они могут использовать Outlook на мобильном устройстве. Администратор может управлять этими уведомлениями с помощью Exchange Powershell. Если пользователи решили отправить себе SMS-сообщение для скачивания приложения на мобильном устройстве, на его компьютере появится QR-код. Они смогут сканировать QR-код для входа в Outlook на телефоне или планшете. Этот QR-код — это кратковременный маркер, который можно активировать только один раз.

> [!NOTE]
> В некоторых случаях пользователям придется повторно проверить подлинность на своем компьютере, чтобы создать QR-код.

## <a name="use-exchange-powershell"></a>Использование Exchange PowerShell

Этот режим по умолчанию находится в режиме "в режиме". Чтобы отключить эту функцию, выполните следующие действия.

1. [Подключите к Exchange PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)
2. С помощью PowerShell можно отключить уведомления, информирующие пользователей о мобильных приложениях Outlook. Это также предотвратит поток входов в QR-код.

```powershell
Set-Organization -MobileAppEducationEnabled <Boolean>
```

Статьи по теме

[Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig?view=exchange-ps)