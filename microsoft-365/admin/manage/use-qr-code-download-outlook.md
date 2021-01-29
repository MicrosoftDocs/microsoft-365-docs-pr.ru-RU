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
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a><span data-ttu-id="c38f6-103">Использование QR-кода для вход в мобильные приложения Outlook</span><span class="sxs-lookup"><span data-stu-id="c38f6-103">Use a QR code to sign-in to the Outlook mobile apps</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c38f6-104">Эта функция Microsoft 365 находится в открытой предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="c38f6-104">This Microsoft 365 feature is in public preview.</span></span> <span data-ttu-id="c38f6-105">Общедоступный предварительный просмотр предоставляет ранний доступ к функциям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c38f6-105">Public preview provides early access to Microsoft 365 features.</span></span>

<span data-ttu-id="c38f6-106">Как администратор Microsoft 365 вы можете позволить пользователям входить в приложение Outlook для Android или iOS на своих мобильных устройствах без ввода имени пользователя и пароля.</span><span class="sxs-lookup"><span data-stu-id="c38f6-106">As the Microsoft 365 administrator, you can enable your users to sign in to Outlook for Android or iOS app on their mobile devices without having to enter their username and password.</span></span> <span data-ttu-id="c38f6-107">Сканируя QR-код, пользователи могут безопасно проверить подлинность и войти в Outlook Mobile.</span><span class="sxs-lookup"><span data-stu-id="c38f6-107">By scanning a QR code, users can securely authenticate and sign in to Outlook mobile.</span></span>

<span data-ttu-id="c38f6-108">В Outlook в Интернете или других классических приложениях Outlook пользователи могут видеть уведомления о том, что они могут использовать Outlook на мобильном устройстве.</span><span class="sxs-lookup"><span data-stu-id="c38f6-108">In Outlook on the web or other desktop Outlook applications, users may see notifications informing them that they can use Outlook on their mobile device.</span></span> <span data-ttu-id="c38f6-109">Администратор может управлять этими уведомлениями с помощью Exchange Powershell.</span><span class="sxs-lookup"><span data-stu-id="c38f6-109">These notifications can be managed by the administrator using Exchange Powershell.</span></span> <span data-ttu-id="c38f6-110">Если пользователи решили отправить себе SMS-сообщение для скачивания приложения на мобильном устройстве, на его компьютере появится QR-код.</span><span class="sxs-lookup"><span data-stu-id="c38f6-110">If users choose to send themselves an SMS text message to download the app on their mobile device, a QR code will appear on their computer.</span></span> <span data-ttu-id="c38f6-111">Они смогут сканировать QR-код для входа в Outlook на телефоне или планшете.</span><span class="sxs-lookup"><span data-stu-id="c38f6-111">They will be able to scan the QR code to log into Outlook on their phone or tablet.</span></span> <span data-ttu-id="c38f6-112">Этот QR-код — это кратковременный маркер, который можно активировать только один раз.</span><span class="sxs-lookup"><span data-stu-id="c38f6-112">This QR code is a short lived token that can only be redeemed once.</span></span>

> [!NOTE]
> <span data-ttu-id="c38f6-113">В некоторых случаях пользователям придется повторно проверить подлинность на своем компьютере, чтобы создать QR-код.</span><span class="sxs-lookup"><span data-stu-id="c38f6-113">In some cases, your users will have to re-authenticate on their computer to generate the QR code.</span></span>

## <a name="use-exchange-powershell"></a><span data-ttu-id="c38f6-114">Использование Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="c38f6-114">Use Exchange PowerShell</span></span>

<span data-ttu-id="c38f6-115">Этот режим по умолчанию находится в режиме "в режиме".</span><span class="sxs-lookup"><span data-stu-id="c38f6-115">This experience is on by default.</span></span> <span data-ttu-id="c38f6-116">Чтобы отключить эту функцию, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="c38f6-116">To disable this feature, follow the steps below.</span></span>

1. <span data-ttu-id="c38f6-117">[Подключите к Exchange PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="c38f6-117">[Connect to Exchange PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
2. <span data-ttu-id="c38f6-118">С помощью PowerShell можно отключить уведомления, информирующие пользователей о мобильных приложениях Outlook.</span><span class="sxs-lookup"><span data-stu-id="c38f6-118">Using PowerShell, you can disable the notifications informing your users about the Outlook mobile apps.</span></span> <span data-ttu-id="c38f6-119">Это также предотвратит поток входов в QR-код.</span><span class="sxs-lookup"><span data-stu-id="c38f6-119">This will also prevent the QR code sign-in flow from being shown.</span></span>

```powershell
Set-Organization -MobileAppEducationEnabled <Boolean>
```

<span data-ttu-id="c38f6-120">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="c38f6-120">Related topics</span></span>

[<span data-ttu-id="c38f6-121">Set-OrganizationConfig</span><span class="sxs-lookup"><span data-stu-id="c38f6-121">Set-OrganizationConfig</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig?view=exchange-ps)