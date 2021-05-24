---
title: Для регистрации в мобильных приложениях Outlook QR-код
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
description: Узнайте, как использовать QR-код для проверки подлинности и загрузки Outlook мобильного телефона.
ms.openlocfilehash: 2c1853a6ea1dd1a5d2ad30b975d1dbd23b942040
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636002"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a>Для регистрации в мобильных приложениях Outlook QR-код

> [!IMPORTANT]
> Эта функция доступна только организациям, которые включили целевой выпуск в центре Microsoft 365 администрирования. Чтобы включить целевой выпуск и узнать больше о том, как он работает, см. в выпуске [Set up the Standard or Targeted release options.](release-options-in-office-365.md) В ближайшие недели мы будем расширяться до нескольких организаций с помощью общедоступных предварительных просмотров. Общедоступный предварительный просмотр предоставляет ранний доступ к Microsoft 365 функциям.

Как администратор Microsoft 365, вы можете позволить пользователям войти в Outlook для android или iOS-приложения на своих мобильных устройствах без ввода имени пользователя и пароля. Сканируя код QR, пользователи могут безопасно проверить подлинность и войти в Outlook мобильный.

В Outlook веб-или других настольных Outlook приложениях пользователи могут видеть уведомления о том, что они могут использовать Outlook на своем мобильном устройстве. Администратор может управлять этими уведомлениями с помощью Exchange Powershell. Если пользователи решили отправить SMS для скачивания приложения на мобильном устройстве, на компьютере появится код QR. Они смогут сканировать QR-код, чтобы войти в Outlook на телефоне или планшете. Этот код QR — это недолговежий маркер, который можно использовать только один раз.

> [!NOTE]
> В некоторых случаях пользователям необходимо повторно проверить подлинность на компьютере для создания кода QR.

## <a name="use-exchange-powershell"></a>Использование Exchange PowerShell

По умолчанию эта функция включена. Чтобы отключить эту функцию, выполните ниже действия.

1. [Подключение Exchange PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).
2. С помощью PowerShell можно отключить уведомления, информирующие пользователей о Outlook мобильных приложениях. Это также не позволяет показывать поток входных кодов QR.

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

## <a name="related-content"></a>См. также:

[Настройка стандартных или целевых параметров](release-options-in-office-365.md) выпуска (статья)\
[Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig?view=exchange-ps) (статья)