---
title: Использование кода QR для регистрации в мобильных приложениях Outlook
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
description: Узнайте, как использовать QR-код для проверки подлинности и загрузки мобильного телефона Outlook.
ms.openlocfilehash: bc8ab14d3c1c0621e84d0c95ad7448c6c50825d6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914970"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a>Использование кода QR для регистрации в мобильных приложениях Outlook

> [!IMPORTANT]
> Эта функция доступна только организациям, которые включили целевой выпуск в центре администрирования Microsoft 365. Чтобы включить целевой выпуск и узнать больше о том, как он работает, см. в выпуске [Set up the Standard or Targeted release options.](release-options-in-office-365.md) В ближайшие недели мы будем расширяться до нескольких организаций с помощью общедоступных предварительных просмотров. Общедоступный предварительный просмотр предоставляет ранний доступ к функциям Microsoft 365.

В качестве администратора Microsoft 365 вы можете позволить пользователям войти в приложение Outlook для Android или iOS на своих мобильных устройствах без ввода имени пользователя и пароля. Сканируя код QR, пользователи могут надежно проверить подлинность и войти в Outlook mobile.

В Outlook в веб-или других приложениях Outlook для настольных компьютеров пользователи могут видеть уведомления, информирующие их о том, что они могут использовать Outlook на своем мобильном устройстве. Администратор может управлять этими уведомлениями с помощью Exchange Powershell. Если пользователи решили отправить себе SMS-текстовое сообщение, чтобы скачать приложение на мобильном устройстве, на компьютере появится код QR. Они смогут сканировать код QR для входа в Outlook на телефоне или планшете. Этот код QR — это недолговежий маркер, который можно использовать только один раз.

> [!NOTE]
> В некоторых случаях пользователям придется повторно проверить подлинность на компьютере для создания кода QR.

## <a name="use-exchange-powershell"></a>Использование PowerShell Exchange

По умолчанию эта функция включена. Чтобы отключить эту функцию, выполните ниже действия.

1. [Подключение к Exchange PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).
2. С помощью PowerShell можно отключить уведомления, информирующие пользователей о мобильных приложениях Outlook. Это также предотвратит от показаний поток регистрации кода QR.

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

Родственные темы

[Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig?view=exchange-ps)