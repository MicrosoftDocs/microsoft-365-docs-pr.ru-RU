---
title: Устранение неполадок с бортами и сообщения об ошибках
description: Устранение неполадок с учетом проблем и сообщений об ошибке при выполнении установки Microsoft Defender для конечной точки.
keywords: устранение неполадок, устранение неполадок, Azure Active Directory, onboarding, сообщение об ошибке, сообщения об ошибках, защитник Майкрософт для конечной точки
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 1b769c1b3e4201802ea6150358568bf57894d305
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185815"
---
# <a name="troubleshoot-subscription-and-portal-access-issues"></a><span data-ttu-id="22452-104">Устранение неполадок с подпиской и доступом на портал</span><span class="sxs-lookup"><span data-stu-id="22452-104">Troubleshoot subscription and portal access issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="22452-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="22452-105">**Applies to:**</span></span>
- [<span data-ttu-id="22452-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="22452-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="22452-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="22452-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="22452-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="22452-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="22452-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="22452-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-troublshootonboarding-abovefoldlink)

<span data-ttu-id="22452-110">На этой странице подробно описаны действия по устранению неполадок, которые могут возникнуть при настройке службы Microsoft Defender для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="22452-110">This page provides detailed steps to troubleshoot issues that might occur when setting up your Microsoft Defender for Endpoint service.</span></span>

<span data-ttu-id="22452-111">Если вы получите сообщение об ошибке, Центр безопасности Защитника Майкрософт предоставит подробные пояснения о том, что такое проблема, и будут предоставлены соответствующие ссылки.</span><span class="sxs-lookup"><span data-stu-id="22452-111">If you receive an error message, Microsoft Defender Security Center will provide a detailed explanation on what the issue is and relevant links will be supplied.</span></span>

## <a name="no-subscriptions-found"></a><span data-ttu-id="22452-112">Подписки не найдены</span><span class="sxs-lookup"><span data-stu-id="22452-112">No subscriptions found</span></span>

<span data-ttu-id="22452-113">Если при доступе к Центру  безопасности Microsoft Defender вы получаете сообщение Без подписок, это означает, что Azure Active Directory (Azure AD), используемый для входа пользователя на портал, не имеет лицензии Microsoft Defender для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="22452-113">If while accessing Microsoft Defender Security Center you get a **No subscriptions found** message, it means the Azure Active Directory (Azure AD) used to log in the user to the portal, does not have a Microsoft Defender for Endpoint license.</span></span>

<span data-ttu-id="22452-114">Возможные причины:</span><span class="sxs-lookup"><span data-stu-id="22452-114">Potential reasons:</span></span>
- <span data-ttu-id="22452-115">Лицензии Windows E5 и Office E5 - это две разные лицензии.</span><span class="sxs-lookup"><span data-stu-id="22452-115">The Windows E5 and Office E5 licenses are separate licenses.</span></span>
- <span data-ttu-id="22452-116">Лицензия была приобретена, но не была предусмотрена для этого экземпляра Azure AD.</span><span class="sxs-lookup"><span data-stu-id="22452-116">The license was purchased but not provisioned to this Azure AD instance.</span></span>
    - <span data-ttu-id="22452-117">Это может быть проблема с подготовкаю лицензии.</span><span class="sxs-lookup"><span data-stu-id="22452-117">It could be a license provisioning issue.</span></span>
    - <span data-ttu-id="22452-118">Это может быть случайное предоставление лицензии другому Microsoft Azure AD, чем лицензия, используемая для проверки подлинности в службе.</span><span class="sxs-lookup"><span data-stu-id="22452-118">It could be you inadvertently provisioned the license to a different Microsoft Azure AD than the one used for authentication into the service.</span></span>

<span data-ttu-id="22452-119">В обоих случаях следует обратиться в службу поддержки Майкрософт в [Службу](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636419533611396913) поддержки конечных точек или поддержку [лицензий на объем.](https://www.microsoft.com/licensing/servicecenter/Help/Contact.aspx)</span><span class="sxs-lookup"><span data-stu-id="22452-119">For both cases, you should contact Microsoft support at [General Microsoft Defender for Endpoint Support](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636419533611396913) or [Volume license support](https://www.microsoft.com/licensing/servicecenter/Help/Contact.aspx).</span></span>

![Изображение не найденных подписок](images/atp-no-subscriptions-found.png)

## <a name="your-subscription-has-expired"></a><span data-ttu-id="22452-121">Срок действия подписки истек</span><span class="sxs-lookup"><span data-stu-id="22452-121">Your subscription has expired</span></span>

<span data-ttu-id="22452-122">Если при доступе к Центру  безопасности Microsoft Defender вы получаете сообщение с истекшим сроком действия подписки, срок действия подписки на службу в Интернете истек.</span><span class="sxs-lookup"><span data-stu-id="22452-122">If while accessing Microsoft Defender Security Center you get a **Your subscription has expired** message, your online service subscription has expired.</span></span> <span data-ttu-id="22452-123">Подписка Microsoft Defender для конечной точки, как и любая другая подписка на онлайн-службу, имеет срок действия.</span><span class="sxs-lookup"><span data-stu-id="22452-123">Microsoft Defender for Endpoint subscription, like any other online service subscription, has an expiration date.</span></span> 

<span data-ttu-id="22452-124">Вы можете продлить или продлить лицензию в любой момент времени.</span><span class="sxs-lookup"><span data-stu-id="22452-124">You can choose to renew or extend the license at any point in time.</span></span> <span data-ttu-id="22452-125">При доступе к порталу  по истечении срока действия подписки будет представлено сообщение с возможностью скачивания пакета offboarding устройства, если вы решите не продлевать лицензию.</span><span class="sxs-lookup"><span data-stu-id="22452-125">When accessing the portal after the expiration date a **Your subscription has expired** message will be presented with an option to download the device offboarding package, should you choose to not renew the license.</span></span>

> [!NOTE]
> <span data-ttu-id="22452-126">По соображениям безопасности срок действия пакета, используемой для устройств Offboard, истекает через 30 дней после даты его загрузки.</span><span class="sxs-lookup"><span data-stu-id="22452-126">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="22452-127">Просроченные пакеты offboarding, отправленные на устройство, будут отклонены.</span><span class="sxs-lookup"><span data-stu-id="22452-127">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="22452-128">При загрузке пакета offboarding вы будете уведомлены о дате истечения срока действия пакетов и он также будет включен в имя пакета.</span><span class="sxs-lookup"><span data-stu-id="22452-128">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

![Срок действия подписи](images/atp-subscription-expired.png)

## <a name="you-are-not-authorized-to-access-the-portal"></a><span data-ttu-id="22452-130">Доступ к порталу не разрешен</span><span class="sxs-lookup"><span data-stu-id="22452-130">You are not authorized to access the portal</span></span>

<span data-ttu-id="22452-131">Если вы получаете средство, не уполномоченное получать доступ к порталу, следует помнить, что Microsoft Defender for Endpoint — это продукт мониторинга безопасности, расследования инцидентов и реагирования, поэтому доступ к нему ограничен и контролируется пользователем.</span><span class="sxs-lookup"><span data-stu-id="22452-131">If you receive a **You are not authorized to access the portal**, be aware that Microsoft Defender for Endpoint is a security monitoring, incident investigation and response product, and as such, access to it is restricted and controlled by the user.</span></span>
<span data-ttu-id="22452-132">Дополнительные сведения см. в [**ссылке Назначение доступа пользователей к порталу.**](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/assign-portal-access-windows-defender-advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="22452-132">For more information, see, [**Assign user access to the portal**](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/assign-portal-access-windows-defender-advanced-threat-protection).</span></span>

![Изображение не авторизованного портала доступа](images/atp-not-authorized-to-access-portal.png)

## <a name="data-currently-isnt-available-on-some-sections-of-the-portal"></a><span data-ttu-id="22452-134">Данные в настоящее время недоступны на некоторых разделах портала</span><span class="sxs-lookup"><span data-stu-id="22452-134">Data currently isn't available on some sections of the portal</span></span>
<span data-ttu-id="22452-135">Если панель мониторинга портала и другие разделы показывают сообщение об ошибке, например "Данные в настоящее время недоступны":</span><span class="sxs-lookup"><span data-stu-id="22452-135">If the portal dashboard and other sections show an error message such as "Data currently isn't available":</span></span>

![Изображение данных в настоящее время не доступно](images/atp-data-not-available.png)

<span data-ttu-id="22452-137">Необходимо разрешить все поддомены под `securitycenter.windows.com` ней.</span><span class="sxs-lookup"><span data-stu-id="22452-137">You'll need to allow the `securitycenter.windows.com` and all subdomains under it.</span></span> <span data-ttu-id="22452-138">Например, `*.securitycenter.windows.com`.</span><span class="sxs-lookup"><span data-stu-id="22452-138">For example, `*.securitycenter.windows.com`.</span></span>


## <a name="portal-communication-issues"></a><span data-ttu-id="22452-139">Проблемы с связью портала</span><span class="sxs-lookup"><span data-stu-id="22452-139">Portal communication issues</span></span>
<span data-ttu-id="22452-140">Если у вас возникнут проблемы с доступом к порталу, отсутствием данных или ограниченным доступом к частям портала, необходимо убедиться, что следующие URL-адреса разрешены и открыты для связи.</span><span class="sxs-lookup"><span data-stu-id="22452-140">If you encounter issues with accessing the portal, missing data, or restricted access to portions of the portal, you'll need to verify that the following URLs are allowed and open for communication.</span></span>

- `*.blob.core.windows.net`
- `crl.microsoft.com`
- `https://*.microsoftonline-p.com`
- `https://*.securitycenter.windows.com` 
- `https://automatediracs-eus-prd.securitycenter.windows.com`
- `https://login.microsoftonline.com`
- `https://login.windows.net`
- `https://onboardingpackagescusprd.blob.core.windows.net`
- `https://secure.aadcdn.microsoftonline-p.com` 
- `https://securitycenter.windows.com` 
- `https://static2.sharepointonline.com` 



