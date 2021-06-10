---
title: Отключение TLS 1.0 и 1.1 в Microsoft 365 GCC и DoD
description: Обсуждается, как корпорация Майкрософт отключает поддержку TLS 1.1 и 1.0 в GCC среде high и DoD в Microsoft 365.
author: kccross
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.collection: M365-security-compliance
ms.service: information-protection
ms.topic: article
ms.reviewer: krowley
ms.author: krowley
appliesto:
- Office 365 Business
ms.openlocfilehash: 16a02985107c5f578d6d6c21bf2efc6e80297951
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919345"
---
# <a name="disabling-tls-10-and-11-in-microsoft-365-gcc-high-and-dod"></a><span data-ttu-id="bf044-103">Отключение TLS 1.0 и 1.1 в Microsoft 365 GCC и DoD</span><span class="sxs-lookup"><span data-stu-id="bf044-103">Disabling TLS 1.0 and 1.1 in Microsoft 365 GCC High and DoD</span></span>

## <a name="summary"></a><span data-ttu-id="bf044-104">Сводка</span><span class="sxs-lookup"><span data-stu-id="bf044-104">Summary</span></span>

<span data-ttu-id="bf044-105">Чтобы соответствовать последним стандартам соответствия требованиям Федеральной программы управления рисками и авторизациями (FedRAMP), мы отключаем версии 1.1 и 1.0 для Microsoft 365 сред с высоким уровнем GCC и doD.</span><span class="sxs-lookup"><span data-stu-id="bf044-105">In order to comply with the latest compliance standards for the Federal Risk and Authorization Management Program (FedRAMP), we are disabling Transport Layer Security (TLS) versions 1.1 and 1.0 in Microsoft 365 for GCC High and DoD environments.</span></span> <span data-ttu-id="bf044-106">Это изменение было ранее объявлено через Службу поддержки Майкрософт в подготовке к обязательному использованию [TLS 1.2 в Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="bf044-106">This change was previously announced through Microsoft Support in [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

<span data-ttu-id="bf044-107">Безопасность данных важна, и мы стремимся к прозрачности изменений, которые могут повлиять на использование службы.</span><span class="sxs-lookup"><span data-stu-id="bf044-107">The security of your data is important, and we are committed to transparency about changes that could affect your use of the service.</span></span>

<span data-ttu-id="bf044-108">Хотя реализация [Microsoft TLS 1.0](https://support.microsoft.com/help/3117336) не имеет известных уязвимостей в области безопасности, мы по-прежнему привержены стандартам соответствия требованиям FedRAMP.</span><span class="sxs-lookup"><span data-stu-id="bf044-108">Although the [Microsoft TLS 1.0 implementation](https://support.microsoft.com/help/3117336) has no known security vulnerabilities, we remain committed to the FedRAMP compliance standards.</span></span> <span data-ttu-id="bf044-109">Поэтому 15 января 2020 г. мы отключили TLS 1.1 и 1.0 в Microsoft 365 в среде GCC High и DoD.</span><span class="sxs-lookup"><span data-stu-id="bf044-109">Therefore, we disabled TLS 1.1 and 1.0 in Microsoft 365 in GCC High and DoD environments on January 15, 2020.</span></span> <span data-ttu-id="bf044-110">Сведения об устранении зависимостей TLS 1.1 и 1.0 см. в следующем документе:</span><span class="sxs-lookup"><span data-stu-id="bf044-110">For information about how to remove TLS 1.1 and 1.0 dependencies, see the following white paper:</span></span>

[<span data-ttu-id="bf044-111">Решение проблемы TLS 1.0</span><span class="sxs-lookup"><span data-stu-id="bf044-111">Solving the TLS 1.0 problem</span></span>](https://www.microsoft.com/download/details.aspx?id=55266)

## <a name="more-information"></a><span data-ttu-id="bf044-112">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="bf044-112">More information</span></span>

<span data-ttu-id="bf044-113">Начиная с 15 января 2020 г. Microsoft 365 среды GCC high и DoD отключят TLS 1.1 и 1.0.</span><span class="sxs-lookup"><span data-stu-id="bf044-113">Starting on January 15, 2020, Microsoft 365 in the GCC High and DoD environments will disable TLS 1.1 and 1.0.</span></span>

<span data-ttu-id="bf044-114">До 15 января 2020 г. все сочетания серверов клиентов и серверов браузеров должны использовать TLS версии 1.2 (или более поздней версии), чтобы убедиться, что все подключения можно сделать без проблем с Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bf044-114">By January 15, 2020, all combinations of client servers and browser servers should use TLS version 1.2 (or a later version) to make sure that all connections can be made without issues to Microsoft 365.</span></span> <span data-ttu-id="bf044-115">Для этого могут потребоваться обновления определенных комбинаций клиентских серверов и серверов браузера.</span><span class="sxs-lookup"><span data-stu-id="bf044-115">This may require updates to certain combinations of client servers and browser servers.</span></span>

<span data-ttu-id="bf044-116">Для SharePoint и OneDrive необходимо обновить и настроить .NET для поддержки TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="bf044-116">For SharePoint and OneDrive, you'll need to update and configure .NET to support TLS 1.2.</span></span> <span data-ttu-id="bf044-117">Сведения см. [в том, как включить TLS 1.2 для клиентов.](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)</span><span class="sxs-lookup"><span data-stu-id="bf044-117">For information, see [How to enable TLS 1.2 on clients](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span>

<span data-ttu-id="bf044-118">Необходимо обновить клиентские компьютеры, чтобы обеспечить непрерывный доступ к Office 365 GCC и doD.</span><span class="sxs-lookup"><span data-stu-id="bf044-118">You must update your client computers to make sure that you maintain uninterrupted access to Office 365 GCC High and DoD.</span></span>

<span data-ttu-id="bf044-119">Чтобы использовать TLS 1.2, необходимо обновить приложения, которые Microsoft 365 API через TLS 1.0 или TLS 1.1.</span><span class="sxs-lookup"><span data-stu-id="bf044-119">You'll need to update applications that call Microsoft 365 APIs over TLS 1.0 or TLS 1.1 to use TLS 1.2.</span></span> <span data-ttu-id="bf044-120">.NET 4.5 по умолчанию для TLS 1.1.</span><span class="sxs-lookup"><span data-stu-id="bf044-120">.NET 4.5 defaults to TLS 1.1.</span></span> <span data-ttu-id="bf044-121">Чтобы обновить конфигурацию .NET, см. в руб. Как включить безопасность транспортного слоя [(TLS) 1.2 для клиентов.](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)</span><span class="sxs-lookup"><span data-stu-id="bf044-121">To update your .NET configuration, see [How to enable Transport Layer Security (TLS) 1.2 on clients](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span> <span data-ttu-id="bf044-122">Дополнительные сведения см. в статью Подготовка к обязательному использованию [TLS 1.2 в Office 365.](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="bf044-122">For more information, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

<span data-ttu-id="bf044-123">Мы знаем, что следующие клиентские приложения не могут использовать TLS 1.2:</span><span class="sxs-lookup"><span data-stu-id="bf044-123">We know that the following client applications cannot use TLS 1.2:</span></span>

- <span data-ttu-id="bf044-124">Android 4.3 и более ранние версии</span><span class="sxs-lookup"><span data-stu-id="bf044-124">Android 4.3 and earlier versions</span></span>
- <span data-ttu-id="bf044-125">Firefox 5.0 и более ранние версии:</span><span class="sxs-lookup"><span data-stu-id="bf044-125">Firefox version 5.0 and earlier versions</span></span>
- <span data-ttu-id="bf044-126">Internet Explorer 8-10 в Windows 7 и более ранних версиях</span><span class="sxs-lookup"><span data-stu-id="bf044-126">Internet Explorer 8–10 on Windows 7 and earlier versions</span></span>
- <span data-ttu-id="bf044-127">Internet Explorer 10 на Windows Phone 8.0</span><span class="sxs-lookup"><span data-stu-id="bf044-127">Internet Explorer 10 on Windows Phone 8.0</span></span>
- <span data-ttu-id="bf044-128">Safari 6.0.4/OS X 10.8.4 и более ранние версии</span><span class="sxs-lookup"><span data-stu-id="bf044-128">Safari 6.0.4/OS X 10.8.4 and earlier versions</span></span>

<span data-ttu-id="bf044-129">Хотя текущий анализ подключений к службам Microsoft Online показывает, что большинство служб и конечных точек видят очень мало использования TLS 1.1 и 1.0, мы предоставляем уведомление об этом изменении, чтобы вы могли обновлять все затронутые клиенты или серверы до окончания поддержки TLS 1.1 и 1.0.</span><span class="sxs-lookup"><span data-stu-id="bf044-129">Although current analysis of connections to Microsoft Online services shows that most services and endpoints see very little TLS 1.1 and 1.0 usage, we're providing notice of this change so that you can update any affected clients or servers as necessary before support for TLS 1.1 and 1.0 ends.</span></span> <span data-ttu-id="bf044-130">При использовании локальной инфраструктуры для гибридных сценариев или служб Федерации Active Directory (AD FS) убедитесь, что инфраструктура может поддерживать как входящие, так и исходящие подключения, использующие TLS 1.2 (или более поздний вариант).</span><span class="sxs-lookup"><span data-stu-id="bf044-130">If you are using any on-premises infrastructure for hybrid scenarios or Active Directory Federation Services (AD FS), make sure that the infrastructure can support both inbound and outbound connections that use TLS 1.2 (or a later version).</span></span>

<span data-ttu-id="bf044-131">В дополнение к отключениям, которые могут возникнуть при использовании перечисленных клиентов, которые не могут использовать TLS 1.2, удаление TLS 1.1 и 1.0 не позволит вам использовать следующий продукт Майкрософт:</span><span class="sxs-lookup"><span data-stu-id="bf044-131">In addition to the outages that you might experience if you use the listed clients that cannot use TLS 1.2, removing TLS 1.1 and 1.0 will prevent you from being able to use the following Microsoft product:</span></span>

- <span data-ttu-id="bf044-132">Телефон Lync</span><span class="sxs-lookup"><span data-stu-id="bf044-132">Lync phone</span></span>

## <a name="references"></a><span data-ttu-id="bf044-133">Ссылки</span><span class="sxs-lookup"><span data-stu-id="bf044-133">References</span></span>

<span data-ttu-id="bf044-134">Инструкции и ссылки, которые помогут убедиться, что клиенты используют TLS 1.2, см. в статью Подготовка к обязательному использованию [TLS 1.2](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)в Office 365 .</span><span class="sxs-lookup"><span data-stu-id="bf044-134">For guidance and references to help make sure that your clients are using TLS 1.2, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>