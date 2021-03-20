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
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a><span data-ttu-id="1a596-103">Использование кода QR для регистрации в мобильных приложениях Outlook</span><span class="sxs-lookup"><span data-stu-id="1a596-103">Use a QR code to sign-in to the Outlook mobile apps</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1a596-104">Эта функция доступна только организациям, которые включили целевой выпуск в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1a596-104">This feature is only available to organizations who have turned on Targeted Release in the Microsoft 365 admin center.</span></span> <span data-ttu-id="1a596-105">Чтобы включить целевой выпуск и узнать больше о том, как он работает, см. в выпуске [Set up the Standard or Targeted release options.](release-options-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="1a596-105">To turn on Targeted release and learn more about how it works, see [Set up the Standard or Targeted release options](release-options-in-office-365.md).</span></span> <span data-ttu-id="1a596-106">В ближайшие недели мы будем расширяться до нескольких организаций с помощью общедоступных предварительных просмотров.</span><span class="sxs-lookup"><span data-stu-id="1a596-106">We’ll be expanding to more organizations in the coming weeks through public preview.</span></span> <span data-ttu-id="1a596-107">Общедоступный предварительный просмотр предоставляет ранний доступ к функциям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1a596-107">Public preview provides early access to Microsoft 365 features.</span></span>

<span data-ttu-id="1a596-108">В качестве администратора Microsoft 365 вы можете позволить пользователям войти в приложение Outlook для Android или iOS на своих мобильных устройствах без ввода имени пользователя и пароля.</span><span class="sxs-lookup"><span data-stu-id="1a596-108">As the Microsoft 365 administrator, you can enable your users to sign in to Outlook for Android or iOS app on their mobile devices without having to enter their username and password.</span></span> <span data-ttu-id="1a596-109">Сканируя код QR, пользователи могут надежно проверить подлинность и войти в Outlook mobile.</span><span class="sxs-lookup"><span data-stu-id="1a596-109">By scanning a QR code, users can securely authenticate and sign in to Outlook mobile.</span></span>

<span data-ttu-id="1a596-110">В Outlook в веб-или других приложениях Outlook для настольных компьютеров пользователи могут видеть уведомления, информирующие их о том, что они могут использовать Outlook на своем мобильном устройстве.</span><span class="sxs-lookup"><span data-stu-id="1a596-110">In Outlook on the web or other desktop Outlook applications, users may see notifications informing them that they can use Outlook on their mobile device.</span></span> <span data-ttu-id="1a596-111">Администратор может управлять этими уведомлениями с помощью Exchange Powershell.</span><span class="sxs-lookup"><span data-stu-id="1a596-111">These notifications can be managed by the administrator using Exchange Powershell.</span></span> <span data-ttu-id="1a596-112">Если пользователи решили отправить себе SMS-текстовое сообщение, чтобы скачать приложение на мобильном устройстве, на компьютере появится код QR.</span><span class="sxs-lookup"><span data-stu-id="1a596-112">If users choose to send themselves an SMS text message to download the app on their mobile device, a QR code will appear on their computer.</span></span> <span data-ttu-id="1a596-113">Они смогут сканировать код QR для входа в Outlook на телефоне или планшете.</span><span class="sxs-lookup"><span data-stu-id="1a596-113">They will be able to scan the QR code to log into Outlook on their phone or tablet.</span></span> <span data-ttu-id="1a596-114">Этот код QR — это недолговежий маркер, который можно использовать только один раз.</span><span class="sxs-lookup"><span data-stu-id="1a596-114">This QR code is a short lived token that can only be redeemed once.</span></span>

> [!NOTE]
> <span data-ttu-id="1a596-115">В некоторых случаях пользователям придется повторно проверить подлинность на компьютере для создания кода QR.</span><span class="sxs-lookup"><span data-stu-id="1a596-115">In some cases, your users will have to re-authenticate on their computer to generate the QR code.</span></span>

## <a name="use-exchange-powershell"></a><span data-ttu-id="1a596-116">Использование PowerShell Exchange</span><span class="sxs-lookup"><span data-stu-id="1a596-116">Use Exchange PowerShell</span></span>

<span data-ttu-id="1a596-117">По умолчанию эта функция включена.</span><span class="sxs-lookup"><span data-stu-id="1a596-117">This feature is on by default.</span></span> <span data-ttu-id="1a596-118">Чтобы отключить эту функцию, выполните ниже действия.</span><span class="sxs-lookup"><span data-stu-id="1a596-118">To disable this feature, follow the steps below.</span></span>

1. <span data-ttu-id="1a596-119">[Подключение к Exchange PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="1a596-119">[Connect to Exchange PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
2. <span data-ttu-id="1a596-120">С помощью PowerShell можно отключить уведомления, информирующие пользователей о мобильных приложениях Outlook.</span><span class="sxs-lookup"><span data-stu-id="1a596-120">Using PowerShell, you can disable the notifications informing your users about the Outlook mobile apps.</span></span> <span data-ttu-id="1a596-121">Это также предотвратит от показаний поток регистрации кода QR.</span><span class="sxs-lookup"><span data-stu-id="1a596-121">This will also prevent the QR code sign-in flow from being shown.</span></span>

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

<span data-ttu-id="1a596-122">Родственные темы</span><span class="sxs-lookup"><span data-stu-id="1a596-122">Related topics</span></span>

[<span data-ttu-id="1a596-123">Set-OrganizationConfig</span><span class="sxs-lookup"><span data-stu-id="1a596-123">Set-OrganizationConfig</span></span>](/powershell/module/exchange/set-organizationconfig?view=exchange-ps)