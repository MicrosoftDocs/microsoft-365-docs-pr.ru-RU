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
ms.openlocfilehash: a403fbbed90229300e707653062c552104c47d97
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286709"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a><span data-ttu-id="5ee9d-103">Для регистрации в мобильных приложениях Outlook QR-код</span><span class="sxs-lookup"><span data-stu-id="5ee9d-103">Use a QR code to sign-in to the Outlook mobile apps</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5ee9d-104">Эта функция доступна только организациям, которые включили целевой выпуск в Центр администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5ee9d-104">This feature is only available to organizations that have turned on Targeted Release in the Microsoft 365 admin center.</span></span> <span data-ttu-id="5ee9d-105">Чтобы включить целевой выпуск и узнать больше о том, как он работает, см. в выпуске [Set up the Standard or Targeted release options.](release-options-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="5ee9d-105">To turn on Targeted release and learn more about how it works, see [Set up the Standard or Targeted release options](release-options-in-office-365.md).</span></span> <span data-ttu-id="5ee9d-106">В ближайшие недели мы будем расширяться до нескольких организаций с помощью общедоступных предварительных просмотров.</span><span class="sxs-lookup"><span data-stu-id="5ee9d-106">We’ll be expanding to more organizations in the coming weeks through public preview.</span></span> <span data-ttu-id="5ee9d-107">Общедоступный предварительный просмотр предоставляет ранний доступ к Microsoft 365 функциям.</span><span class="sxs-lookup"><span data-stu-id="5ee9d-107">Public preview provides early access to Microsoft 365 features.</span></span>

<span data-ttu-id="5ee9d-108">Как администратор Microsoft 365, вы можете позволить пользователям войти в Outlook для android или iOS-приложения на своих мобильных устройствах без ввода имени пользователя и пароля.</span><span class="sxs-lookup"><span data-stu-id="5ee9d-108">As the Microsoft 365 administrator, you can enable your users to sign in to Outlook for Android or iOS app on their mobile devices without having to enter their username and password.</span></span> <span data-ttu-id="5ee9d-109">Сканируя код QR, пользователи могут безопасно проверить подлинность и войти в Outlook мобильный.</span><span class="sxs-lookup"><span data-stu-id="5ee9d-109">By scanning a QR code, users can securely authenticate and sign in to Outlook mobile.</span></span>

<span data-ttu-id="5ee9d-110">В Outlook в Интернете или других настольных Outlook приложениях пользователи могут видеть уведомления, информирующие их о том, что они могут Outlook на своем мобильном устройстве.</span><span class="sxs-lookup"><span data-stu-id="5ee9d-110">In Outlook on the web or other desktop Outlook applications, users may see notifications informing them that they can use Outlook on their mobile device.</span></span> <span data-ttu-id="5ee9d-111">Администратор может управлять этими уведомлениями с помощью Exchange Powershell.</span><span class="sxs-lookup"><span data-stu-id="5ee9d-111">These notifications can be managed by the administrator using Exchange Powershell.</span></span> <span data-ttu-id="5ee9d-112">Если пользователи решили отправить себе SMS-текстовое сообщение, чтобы скачать приложение на мобильном устройстве, на компьютере появится код QR.</span><span class="sxs-lookup"><span data-stu-id="5ee9d-112">If users choose to send themselves an SMS text message to download the app on their mobile device, a QR code will appear on their computer.</span></span> <span data-ttu-id="5ee9d-113">Они смогут сканировать QR-код, чтобы войти в Outlook на телефоне или планшете.</span><span class="sxs-lookup"><span data-stu-id="5ee9d-113">They will be able to scan the QR code to log into Outlook on their phone or tablet.</span></span> <span data-ttu-id="5ee9d-114">Этот код QR — это недолговежий маркер, который можно использовать только один раз.</span><span class="sxs-lookup"><span data-stu-id="5ee9d-114">This QR code is a short lived token that can only be redeemed once.</span></span>

> [!NOTE]
> <span data-ttu-id="5ee9d-115">В некоторых случаях пользователям необходимо повторно проверить подлинность на компьютере для создания кода QR.</span><span class="sxs-lookup"><span data-stu-id="5ee9d-115">In some cases, your users must re-authenticate on their computer to generate the QR code.</span></span>

## <a name="use-exchange-powershell"></a><span data-ttu-id="5ee9d-116">Использование Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="5ee9d-116">Use Exchange PowerShell</span></span>

<span data-ttu-id="5ee9d-117">По умолчанию эта функция включена.</span><span class="sxs-lookup"><span data-stu-id="5ee9d-117">This feature is on by default.</span></span> <span data-ttu-id="5ee9d-118">Чтобы отключить эту функцию, выполните ниже действия.</span><span class="sxs-lookup"><span data-stu-id="5ee9d-118">To disable this feature, follow the steps below.</span></span>

1. <span data-ttu-id="5ee9d-119">[Подключение Exchange PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="5ee9d-119">[Connect to Exchange PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>
2. <span data-ttu-id="5ee9d-120">С помощью PowerShell можно отключить уведомления, информирующие пользователей о Outlook мобильных приложениях.</span><span class="sxs-lookup"><span data-stu-id="5ee9d-120">Using PowerShell, you can disable the notifications informing your users about the Outlook mobile apps.</span></span> <span data-ttu-id="5ee9d-121">Это также не позволяет показывать поток входных кодов QR.</span><span class="sxs-lookup"><span data-stu-id="5ee9d-121">This also prevents the QR code sign-in flow from being shown.</span></span>

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

## <a name="related-content"></a><span data-ttu-id="5ee9d-122">Связанные материалы</span><span class="sxs-lookup"><span data-stu-id="5ee9d-122">Related content</span></span>

<span data-ttu-id="5ee9d-123">[Настройка стандартных или целевых параметров](release-options-in-office-365.md) выпуска (статья)</span><span class="sxs-lookup"><span data-stu-id="5ee9d-123">[Set up the Standard or Targeted release options](release-options-in-office-365.md) (article)</span></span>\
<span data-ttu-id="5ee9d-124">[Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) (статья)</span><span class="sxs-lookup"><span data-stu-id="5ee9d-124">[Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) (article)</span></span>