---
title: Отключение TLS 1.0 и 1.1 в Office 365 GCC High и DoD
description: Обсуждается, как корпорация Майкрософт отключает поддержку TLS 1.1 и 1.0 в средах GCC High и DoD в Microsoft 365.
author: workshay
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.collection: M365-security-compliance
ms.service: information-protection
ms.topic: article
ms.reviewer: krowley
ms.author: shmehta
appliesto:
- Office 365 Business
ms.openlocfilehash: 006f81ee5b17baca4f42a78c5a87a59e8e90648f
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166444"
---
# <a name="disabling-tls-10-and-11-in-office-365-gcc-high-and-dod"></a><span data-ttu-id="f187f-103">Отключение TLS 1.0 и 1.1 в Office 365 GCC High и DoD</span><span class="sxs-lookup"><span data-stu-id="f187f-103">Disabling TLS 1.0 and 1.1 in Office 365 GCC High and DoD</span></span>

## <a name="summary"></a><span data-ttu-id="f187f-104">Аннотация</span><span class="sxs-lookup"><span data-stu-id="f187f-104">Summary</span></span>

<span data-ttu-id="f187f-105">Чтобы соответствовать последним стандартам соответствия федеральной программе управления рисками и авторизацией (FedRAMP), мы отключаем версии TLS 1.1 и 1.0 в Microsoft 365 для сред GCC High и DoD.</span><span class="sxs-lookup"><span data-stu-id="f187f-105">In order to comply with the latest compliance standards for the Federal Risk and Authorization Management Program (FedRAMP), we are disabling Transport Layer Security (TLS) versions 1.1 and 1.0 in Microsoft 365 for GCC High and DoD environments.</span></span> <span data-ttu-id="f187f-106">Это изменение было объявлено в службе поддержки Майкрософт при подготовке к обязательному использованию [TLS 1.2 в Office 365.](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="f187f-106">This change was previously announced through Microsoft Support in [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

<span data-ttu-id="f187f-107">Безопасность данных важна, и мы стремимся к прозрачности изменений, которые могут повлиять на использование службы.</span><span class="sxs-lookup"><span data-stu-id="f187f-107">The security of your data is important, and we are committed to transparency about changes that could affect your use of the service.</span></span>

<span data-ttu-id="f187f-108">Хотя реализация [Microsoft TLS 1.0](https://support.microsoft.com/help/3117336) не имеет известных уязвимостей безопасности, мы по-прежнему стремимся к стандартам соответствия FedRAMP.</span><span class="sxs-lookup"><span data-stu-id="f187f-108">Although the [Microsoft TLS 1.0 implementation](https://support.microsoft.com/help/3117336) has no known security vulnerabilities, we remain committed to the FedRAMP compliance standards.</span></span> <span data-ttu-id="f187f-109">Поэтому мы отключили TLS 1.1 и 1.0 в Office 365 в средах GCC High и DoD 15 января 2020 г.</span><span class="sxs-lookup"><span data-stu-id="f187f-109">Therefore, we disabled TLS 1.1 and 1.0 in Office 365 in GCC High and DoD environments on January 15, 2020.</span></span> <span data-ttu-id="f187f-110">Сведения об устранении зависимостей TLS 1.1 и 1.0 см. в следующем документе:</span><span class="sxs-lookup"><span data-stu-id="f187f-110">For information about how to remove TLS 1.1 and 1.0 dependencies, see the following white paper:</span></span>

[<span data-ttu-id="f187f-111">Решение проблемы TLS 1.0</span><span class="sxs-lookup"><span data-stu-id="f187f-111">Solving the TLS 1.0 problem</span></span>](https://www.microsoft.com/download/details.aspx?id=55266)

<span data-ttu-id="f187f-112">Вместо этого необходимо использовать TLS версии 1.2.</span><span class="sxs-lookup"><span data-stu-id="f187f-112">You must use TLS version 1.2 instead.</span></span> <span data-ttu-id="f187f-113">Дополнительные сведения см. в подготовии к обязательному использованию [TLS 1.2 в Office 365.](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="f187f-113">For more information, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

<span data-ttu-id="f187f-114">Для SharePoint и OneDrive необходимо обновить и настроить .NET для поддержки TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="f187f-114">For SharePoint and OneDrive, you'll need to update and configure .NET to support TLS 1.2.</span></span> <span data-ttu-id="f187f-115">Сведения см. в [том, как включить TLS 1.2 на клиентах.](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)</span><span class="sxs-lookup"><span data-stu-id="f187f-115">For information, see [How to enable TLS 1.2 on clients](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span>

## <a name="more-information"></a><span data-ttu-id="f187f-116">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="f187f-116">More information</span></span>

<span data-ttu-id="f187f-117">Начиная с 15 января 2020 г., Office 365 в средах GCC High и DoD не будет амортизации TLS 1.1 и 1.0.</span><span class="sxs-lookup"><span data-stu-id="f187f-117">Starting on January 15, 2020, Office 365 in the GCC High and DoD environments will deprecate TLS 1.1 and 1.0.</span></span>

<span data-ttu-id="f187f-118">До 15 января 2020 г. все комбинации клиентских и браузерных серверов должны использовать TLS версии 1.2 (или более поздней), чтобы убедиться, что все подключения к службам Office 365 могут быть без проблем.</span><span class="sxs-lookup"><span data-stu-id="f187f-118">By January 15, 2020, all combinations of client servers and browser servers should use TLS version 1.2 (or a later version) to make sure that all connections can be made without issues to Office 365 services.</span></span> <span data-ttu-id="f187f-119">Для этого может потребоваться обновление определенных комбинаций клиентских серверов и серверов браузера.</span><span class="sxs-lookup"><span data-stu-id="f187f-119">This may require updates to certain combinations of client servers and browser servers.</span></span>

<span data-ttu-id="f187f-120">Если вы не обновите TLS версии 1.2 (или более поздней) до 15 января 2020 г., при попытке подключения к Office 365 у вас будут проблемы.</span><span class="sxs-lookup"><span data-stu-id="f187f-120">If you do not update to TLS version 1.2 (or a later version) by January 15, 2020, you will experience issues when you try to connect to Office 365.</span></span> <span data-ttu-id="f187f-121">Кроме того, вам потребуется обновить TLS 1.2 (или более поздней версии) в рамках решения.</span><span class="sxs-lookup"><span data-stu-id="f187f-121">Additionally, you will be required to update to TLS 1.2 (or a later version) as part of the resolution.</span></span>

<span data-ttu-id="f187f-122">Мы знаем, что следующие клиенты не могут использовать TLS 1.2:</span><span class="sxs-lookup"><span data-stu-id="f187f-122">We know that the following clients cannot use TLS 1.2:</span></span>

- <span data-ttu-id="f187f-123">Android 4.3 и более ранние версии</span><span class="sxs-lookup"><span data-stu-id="f187f-123">Android 4.3 and earlier versions</span></span>
- <span data-ttu-id="f187f-124">Firefox 5.0 и более ранние версии:</span><span class="sxs-lookup"><span data-stu-id="f187f-124">Firefox version 5.0 and earlier versions</span></span>
- <span data-ttu-id="f187f-125">Internet Explorer 8–10 в Windows 7 и более ранних версиях</span><span class="sxs-lookup"><span data-stu-id="f187f-125">Internet Explorer 8–10 on Windows 7 and earlier versions</span></span>
- <span data-ttu-id="f187f-126">Internet Explorer 10 Windows Phone 8.0</span><span class="sxs-lookup"><span data-stu-id="f187f-126">Internet Explorer 10 on Windows Phone 8.0</span></span>
- <span data-ttu-id="f187f-127">Safari 6.0.4/OS X 10.8.4 и более ранних версий</span><span class="sxs-lookup"><span data-stu-id="f187f-127">Safari 6.0.4/OS X 10.8.4 and earlier versions</span></span>

<span data-ttu-id="f187f-128">Мы рекомендуем обновить клиенты, чтобы обеспечить бесперебойный доступ к Office 365 GCC High и DoD.</span><span class="sxs-lookup"><span data-stu-id="f187f-128">We recommend that you update your clients to make sure that you maintain uninterrupted access to Office 365 GCC High and DoD.</span></span>

<span data-ttu-id="f187f-129">Хотя текущий анализ подключений к службам Microsoft Online показывает, что в большинстве служб и конечных точек использование TLS 1.1 и 1.0 очень мало, мы предоставляем уведомление об этом изменении, чтобы вы могли обновлять все затронутые клиенты или серверы по мере необходимости до окончания поддержки TLS 1.1 и 1.0.</span><span class="sxs-lookup"><span data-stu-id="f187f-129">Although current analysis of connections to Microsoft Online services shows that most services and endpoints see very little TLS 1.1 and 1.0 usage, we are providing notice of this change so that you can update any affected clients or servers as necessary before support for TLS 1.1 and 1.0 ends.</span></span> <span data-ttu-id="f187f-130">При использовании локальной инфраструктуры для гибридных сценариев или служб федерации Active Directory (AD FS) убедитесь, что она поддерживает как входящие, так и исходящие подключения, использующие TLS 1.2 (или более поздней версии).</span><span class="sxs-lookup"><span data-stu-id="f187f-130">If you are using any on-premises infrastructure for hybrid scenarios or Active Directory Federation Services (AD FS), make sure that the infrastructure can support both inbound and outbound connections that use TLS 1.2 (or a later version).</span></span>

<span data-ttu-id="f187f-131">Помимо простоев, которые могут возникнуть при использовании перечисленных клиентов, которые не могут использовать TLS 1.2, удаление TLS 1.1 и 1.0 предотвратит использование следующего продукта Майкрософт:</span><span class="sxs-lookup"><span data-stu-id="f187f-131">In addition to the outages that you might experience if you use the listed clients that cannot use TLS 1.2, removing TLS 1.1 and 1.0 will prevent you from being able to use the following Microsoft product:</span></span>

- <span data-ttu-id="f187f-132">Телефон Lync</span><span class="sxs-lookup"><span data-stu-id="f187f-132">Lync phone</span></span>

## <a name="references"></a><span data-ttu-id="f187f-133">Ссылки</span><span class="sxs-lookup"><span data-stu-id="f187f-133">References</span></span>

<span data-ttu-id="f187f-134">В следующей статье поддержки описываются рекомендации и справочные материалы, которые помогут убедиться, что ваши клиенты используют TLS 1.2:</span><span class="sxs-lookup"><span data-stu-id="f187f-134">The following support article describes guidance and references to help make sure that your clients are using TLS 1.2:</span></span>

[<span data-ttu-id="f187f-135">Подготовка к обязательному использованию TLS 1.2 в Office 365</span><span class="sxs-lookup"><span data-stu-id="f187f-135">Preparing for the mandatory use of TLS 1.2 in Office 365</span></span>](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)
