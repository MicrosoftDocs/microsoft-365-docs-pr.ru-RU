---
title: Устаревшие протоколы TLS 1,0 и 1,1 в Office 365 GCC High и DoD
description: Сведения о том, как корпорация Майкрософт перемещает дату вперед для прекращения поддержки протоколов TLS 1,1 и 1,0 в средах GCC High и DoD в Office 365 и готовится к использованию протокола TLS 1,2.
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
ms.openlocfilehash: 76e9b203e58ba7fa23942ea42810456e3bee377d
ms.sourcegitcommit: 42b618231e9f608f3ae7226a313b0366601d0ea2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/17/2020
ms.locfileid: "45158884"
---
# <a name="deprecating-tls-10-and-11-in-office-365-gcc-high-and-dod"></a><span data-ttu-id="ccdc3-103">Устаревшие протоколы TLS 1,0 и 1,1 в Office 365 GCC High и DoD</span><span class="sxs-lookup"><span data-stu-id="ccdc3-103">Deprecating TLS 1.0 and 1.1 in Office 365 GCC High and DoD</span></span>

## <a name="summary"></a><span data-ttu-id="ccdc3-104">Сводка</span><span class="sxs-lookup"><span data-stu-id="ccdc3-104">Summary</span></span>

<span data-ttu-id="ccdc3-105">Для обеспечения соответствия новейшим стандартам, предъявляемым к федеральным рискам и программам управления авторизацией (FedRAMP), мы не рекомендуем использовать протокол TLS версии 1,1 и 1,0 в Microsoft Office 365 для общедоступных сред со GCC High и DoD.</span><span class="sxs-lookup"><span data-stu-id="ccdc3-105">In order to comply with the latest compliance standards for the Federal Risk and Authorization Management Program (FedRAMP), we are deprecating Transport Layer Security (TLS) versions 1.1 and 1.0 in Microsoft Office 365 for GCC High and DoD environments.</span></span> <span data-ttu-id="ccdc3-106">Это изменение было ранее объявлено в службе поддержки Майкрософт при [подготовке обязательного использования протокола TLS 1,2 в Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="ccdc3-106">This change was previously announced through Microsoft Support in [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

<span data-ttu-id="ccdc3-107">Важна безопасность ваших данных, и мы зафиксированы прозрачность изменений, которые могут повлиять на использование службы.</span><span class="sxs-lookup"><span data-stu-id="ccdc3-107">The security of your data is important, and we are committed to transparency about changes that could affect your use of the service.</span></span>

<span data-ttu-id="ccdc3-108">Несмотря на то, что [Реализация Microsoft TLS 1,0](https://support.microsoft.com/help/3117336) не содержит известных уязвимостей безопасности, мы сохранили соответствие стандартам соответствия требованиям FedRAMP.</span><span class="sxs-lookup"><span data-stu-id="ccdc3-108">Although the [Microsoft TLS 1.0 implementation](https://support.microsoft.com/help/3117336) has no known security vulnerabilities, we remain committed to the FedRAMP compliance standards.</span></span> <span data-ttu-id="ccdc3-109">Поэтому мы будем использовать протоколы TLS 1,1 и 1,0 в Office 365 в средах GCC High и DoD, начиная с 15 января 2020 г.</span><span class="sxs-lookup"><span data-stu-id="ccdc3-109">Therefore, we will deprecate TLS 1.1 and 1.0 in Office 365 in GCC High and DoD environments starting on January 15, 2020.</span></span> <span data-ttu-id="ccdc3-110">Сведения о том, как удалять зависимости TLS 1,1 и 1,0, можно найти в следующем техническом документе:</span><span class="sxs-lookup"><span data-stu-id="ccdc3-110">For information about how to remove TLS 1.1 and 1.0 dependencies, see the following white paper:</span></span>

[<span data-ttu-id="ccdc3-111">Решение проблемы с протоколом TLS 1,0</span><span class="sxs-lookup"><span data-stu-id="ccdc3-111">Solving the TLS 1.0 problem</span></span>](https://www.microsoft.com/download/details.aspx?id=55266)

<span data-ttu-id="ccdc3-112">При подготовке к этому изменению для TLS 1,1 и 1,0 рекомендуется вместо этого использовать TLS версии 1,2.</span><span class="sxs-lookup"><span data-stu-id="ccdc3-112">In preparing for this change for TLS 1.1 and 1.0, we recommend that you use TLS version 1.2 instead.</span></span> <span data-ttu-id="ccdc3-113">Дополнительные сведения приведены в статье [Подготовка к обязательному использованию протокола TLS 1,2 в Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="ccdc3-113">For more information, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

## <a name="more-information"></a><span data-ttu-id="ccdc3-114">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="ccdc3-114">More information</span></span>

<span data-ttu-id="ccdc3-115">Начиная с 15 января 2020, Office 365 в средах GCC High и DoD не рекомендуют протоколы TLS 1,1 и 1,0.</span><span class="sxs-lookup"><span data-stu-id="ccdc3-115">Starting on January 15, 2020, Office 365 in the GCC High and DoD environments will deprecate TLS 1.1 and 1.0.</span></span>

<span data-ttu-id="ccdc3-116">По 15 января 2020 г. все комбинации клиентских серверов и серверов браузера должны использовать протокол TLS версии 1,2 (или более поздней версии), чтобы все подключения могли быть выполнены без проблем со службами Office 365.</span><span class="sxs-lookup"><span data-stu-id="ccdc3-116">By January 15, 2020, all combinations of client servers and browser servers should use TLS version 1.2 (or a later version) to make sure that all connections can be made without issues to Office 365 services.</span></span> <span data-ttu-id="ccdc3-117">Для этого может потребоваться обновление определенных комбинаций клиентских серверов и серверов браузера.</span><span class="sxs-lookup"><span data-stu-id="ccdc3-117">This may require updates to certain combinations of client servers and browser servers.</span></span>

<span data-ttu-id="ccdc3-118">Если не выполнить обновление до версии 1,2 (или более поздней версии) до 15 января 2020, при попытке подключения к Office 365 будут возникать проблемы.</span><span class="sxs-lookup"><span data-stu-id="ccdc3-118">If you do not update to TLS version 1.2 (or a later version) by January 15, 2020, you will experience issues when you try to connect to Office 365.</span></span> <span data-ttu-id="ccdc3-119">Кроме того, в качестве части решения потребуется выполнить обновление до протокола TLS 1,2 (или более поздней версии).</span><span class="sxs-lookup"><span data-stu-id="ccdc3-119">Additionally, you will be required to update to TLS 1.2 (or a later version) as part of the resolution.</span></span>

<span data-ttu-id="ccdc3-120">Мы знаем, что следующие клиенты не могут использовать TLS 1,2:</span><span class="sxs-lookup"><span data-stu-id="ccdc3-120">We know that the following clients cannot use TLS 1.2:</span></span>

- <span data-ttu-id="ccdc3-121">Android 4.3 и более ранние версии</span><span class="sxs-lookup"><span data-stu-id="ccdc3-121">Android 4.3 and earlier versions</span></span>
- <span data-ttu-id="ccdc3-122">Firefox 5.0 и более ранние версии:</span><span class="sxs-lookup"><span data-stu-id="ccdc3-122">Firefox version 5.0 and earlier versions</span></span>
- <span data-ttu-id="ccdc3-123">Internet Explorer 8 – 10 в Windows 7 и более ранних версиях</span><span class="sxs-lookup"><span data-stu-id="ccdc3-123">Internet Explorer 8–10 on Windows 7 and earlier versions</span></span>
- <span data-ttu-id="ccdc3-124">Internet Explorer 10 на Windows Phone 8,0</span><span class="sxs-lookup"><span data-stu-id="ccdc3-124">Internet Explorer 10 on Windows Phone 8.0</span></span>
- <span data-ttu-id="ccdc3-125">Safari 6.0.4/OS X 10.8.4 и более ранние версии</span><span class="sxs-lookup"><span data-stu-id="ccdc3-125">Safari 6.0.4/OS X 10.8.4 and earlier versions</span></span>

<span data-ttu-id="ccdc3-126">Рекомендуется обновить клиенты, чтобы обеспечить бесперебойный доступ к Office 365 GCC High и DoD.</span><span class="sxs-lookup"><span data-stu-id="ccdc3-126">We recommend that you update your clients to make sure that you maintain uninterrupted access to Office 365 GCC High and DoD.</span></span>

<span data-ttu-id="ccdc3-127">Несмотря на то, что текущий анализ подключений к службам Microsoft Online показывает, что большинство служб и конечных точек видят очень небольшое использование TLS 1,1 и 1,0, мы предоставляем уведомление об этом изменении, чтобы вы могли обновить все затронутые клиенты или серверы до того, как они будут поддерживать TLS 1,1 и 1,0.</span><span class="sxs-lookup"><span data-stu-id="ccdc3-127">Although current analysis of connections to Microsoft Online services shows that most services and endpoints see very little TLS 1.1 and 1.0 usage, we are providing notice of this change so that you can update any affected clients or servers as necessary before support for TLS 1.1 and 1.0 ends.</span></span> <span data-ttu-id="ccdc3-128">Если вы используете локальную инфраструктуру для гибридных сценариев или служб федерации Active Directory (AD FS), убедитесь, что инфраструктура поддерживает как входящие, так и исходящие подключения, использующие протокол TLS 1,2 (или более поздней версии).</span><span class="sxs-lookup"><span data-stu-id="ccdc3-128">If you are using any on-premises infrastructure for hybrid scenarios or Active Directory Federation Services (AD FS), make sure that the infrastructure can support both inbound and outbound connections that use TLS 1.2 (or a later version).</span></span>

<span data-ttu-id="ccdc3-129">В дополнение к простоям, которые могут возникнуть при использовании перечисленных клиентов, которые не могут использовать протокол TLS 1,2, удаление TLS 1,1 и 1,0 приведет к тому, что вы не сможете использовать следующий продукт Майкрософт:</span><span class="sxs-lookup"><span data-stu-id="ccdc3-129">In addition to the outages that you might experience if you use the listed clients that cannot use TLS 1.2, removing TLS 1.1 and 1.0 will prevent you from being able to use the following Microsoft product:</span></span>

- <span data-ttu-id="ccdc3-130">Телефон Lync</span><span class="sxs-lookup"><span data-stu-id="ccdc3-130">Lync phone</span></span>

## <a name="references"></a><span data-ttu-id="ccdc3-131">Ссылки</span><span class="sxs-lookup"><span data-stu-id="ccdc3-131">References</span></span>

<span data-ttu-id="ccdc3-132">В следующей статье для поддержки описываются рекомендации и справочные материалы, которые помогут убедиться в том, что ваши клиенты используют протокол TLS 1,2:</span><span class="sxs-lookup"><span data-stu-id="ccdc3-132">The following support article describes guidance and references to help make sure that your clients are using TLS 1.2:</span></span>

[<span data-ttu-id="ccdc3-133">Подготовка к обязательному использованию протокола TLS 1,2 в Office 365</span><span class="sxs-lookup"><span data-stu-id="ccdc3-133">Preparing for the mandatory use of TLS 1.2 in Office 365</span></span>](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)
