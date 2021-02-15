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
ms.openlocfilehash: 1e5207a2792b557689a306fa1474a2c5fac81ed9
ms.sourcegitcommit: 78f48304f990e969a052fe6536b2e8d6856e1086
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "50242358"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a><span data-ttu-id="99de8-103">Использование QR-кода для вход в мобильные приложения Outlook</span><span class="sxs-lookup"><span data-stu-id="99de8-103">Use a QR code to sign-in to the Outlook mobile apps</span></span>

> [!IMPORTANT]
> <span data-ttu-id="99de8-104">Эта функция доступна только для организаций, которые включили выпуск Targeted в Центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="99de8-104">This feature is only available to organizations who have turned on Targeted Release in the Microsoft 365 admin center.</span></span> <span data-ttu-id="99de8-105">Чтобы включить выпуск Targeted и узнать больше о его работе, см. параметры "Настройка стандартного" или ["Целевого выпуска".](release-options-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="99de8-105">To turn on Targeted release and learn more about how it works, see [Set up the Standard or Targeted release options](release-options-in-office-365.md).</span></span> <span data-ttu-id="99de8-106">В ближайшие недели мы расширим его до других организаций в рамках открытой предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="99de8-106">We’ll be expanding to more organizations in the coming weeks through public preview.</span></span> <span data-ttu-id="99de8-107">Общедоступный предварительный просмотр предоставляет ранний доступ к функциям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="99de8-107">Public preview provides early access to Microsoft 365 features.</span></span>

<span data-ttu-id="99de8-108">Как администратор Microsoft 365 вы можете позволить пользователям входить в приложение Outlook для Android или iOS на своих мобильных устройствах без ввода имени пользователя и пароля.</span><span class="sxs-lookup"><span data-stu-id="99de8-108">As the Microsoft 365 administrator, you can enable your users to sign in to Outlook for Android or iOS app on their mobile devices without having to enter their username and password.</span></span> <span data-ttu-id="99de8-109">Сканируя QR-код, пользователи могут безопасно проверить подлинность и войти в Outlook Mobile.</span><span class="sxs-lookup"><span data-stu-id="99de8-109">By scanning a QR code, users can securely authenticate and sign in to Outlook mobile.</span></span>

<span data-ttu-id="99de8-110">В Outlook в Интернете или других классических приложениях Outlook пользователи могут видеть уведомления о том, что они могут использовать Outlook на мобильном устройстве.</span><span class="sxs-lookup"><span data-stu-id="99de8-110">In Outlook on the web or other desktop Outlook applications, users may see notifications informing them that they can use Outlook on their mobile device.</span></span> <span data-ttu-id="99de8-111">Администратор может управлять этими уведомлениями с помощью Exchange Powershell.</span><span class="sxs-lookup"><span data-stu-id="99de8-111">These notifications can be managed by the administrator using Exchange Powershell.</span></span> <span data-ttu-id="99de8-112">Если пользователи решили отправить себе SMS-сообщение для скачивания приложения на мобильном устройстве, на его компьютере появится QR-код.</span><span class="sxs-lookup"><span data-stu-id="99de8-112">If users choose to send themselves an SMS text message to download the app on their mobile device, a QR code will appear on their computer.</span></span> <span data-ttu-id="99de8-113">Они смогут сканировать QR-код для входа в Outlook на телефоне или планшете.</span><span class="sxs-lookup"><span data-stu-id="99de8-113">They will be able to scan the QR code to log into Outlook on their phone or tablet.</span></span> <span data-ttu-id="99de8-114">Этот QR-код — это кратковременный маркер, который можно активировать только один раз.</span><span class="sxs-lookup"><span data-stu-id="99de8-114">This QR code is a short lived token that can only be redeemed once.</span></span>

> [!NOTE]
> <span data-ttu-id="99de8-115">В некоторых случаях пользователям придется повторно проверить подлинность на своем компьютере, чтобы создать QR-код.</span><span class="sxs-lookup"><span data-stu-id="99de8-115">In some cases, your users will have to re-authenticate on their computer to generate the QR code.</span></span>

## <a name="use-exchange-powershell"></a><span data-ttu-id="99de8-116">Использование Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="99de8-116">Use Exchange PowerShell</span></span>

<span data-ttu-id="99de8-117">По умолчанию эта функция включена.</span><span class="sxs-lookup"><span data-stu-id="99de8-117">This feature is on by default.</span></span> <span data-ttu-id="99de8-118">Чтобы отключить эту функцию, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="99de8-118">To disable this feature, follow the steps below.</span></span>

1. <span data-ttu-id="99de8-119">[Подключите к Exchange PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="99de8-119">[Connect to Exchange PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
2. <span data-ttu-id="99de8-120">С помощью PowerShell можно отключить уведомления, информирующие пользователей о мобильных приложениях Outlook.</span><span class="sxs-lookup"><span data-stu-id="99de8-120">Using PowerShell, you can disable the notifications informing your users about the Outlook mobile apps.</span></span> <span data-ttu-id="99de8-121">Это также предотвратит поток входов в QR-код.</span><span class="sxs-lookup"><span data-stu-id="99de8-121">This will also prevent the QR code sign-in flow from being shown.</span></span>

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

<span data-ttu-id="99de8-122">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="99de8-122">Related topics</span></span>

[<span data-ttu-id="99de8-123">Set-OrganizationConfig</span><span class="sxs-lookup"><span data-stu-id="99de8-123">Set-OrganizationConfig</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig?view=exchange-ps)
