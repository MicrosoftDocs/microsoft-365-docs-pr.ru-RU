---
title: Устаревшие протоколы TLS 1,0 и 1,1 в Office 365 GCC High и DoD
description: Сведения о том, как корпорация Майкрософт перемещает дату вперед для прекращения поддержки протоколов TLS 1,1 и 1,0 в средах GCC High и DoD в Office 365 и готовится к использованию протокола TLS 1,2.
author: simonxjx
manager: dcscontentpm
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: v-six
ms.reviewer: lobrion
appliesto:
- Office 365 Business
ms.openlocfilehash: f61c0a809c4666981ee0f2d67eea21474b83a675
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024841"
---
# <a name="deprecating-tls-10-and-11-in-office-365-gcc-high-and-dod"></a><span data-ttu-id="c7a59-103">Устаревшие протоколы TLS 1,0 и 1,1 в Office 365 GCC High и DoD</span><span class="sxs-lookup"><span data-stu-id="c7a59-103">Deprecating TLS 1.0 and 1.1 in Office 365 GCC High and DoD</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c7a59-104">Пандемия в мире в разгаре, и мы в Microsoft понимаем, как это влияет на наших клиентов и партнеров.</span><span class="sxs-lookup"><span data-stu-id="c7a59-104">The world is in the middle of a pandemic, and we at Microsoft are aware of the impact on our customers and partners.</span></span> <span data-ttu-id="c7a59-105">Чтобы снизить нагрузку на наших коммерческих клиентов, мы временно прекратили отключение TLS 1.0 и 1.1.</span><span class="sxs-lookup"><span data-stu-id="c7a59-105">To lighten the burden on our commercial customers, we have temporarily halted any deprecation enforcement of TLS 1.0 and 1.1.</span></span> <span data-ttu-id="c7a59-106">Обновление будет отправлено в новые сроки после того, как текущий кризис стабилизируется.</span><span class="sxs-lookup"><span data-stu-id="c7a59-106">An update will be sent on a revised timeline after the current crisis stabilizes.</span></span> <span data-ttu-id="c7a59-107">(Эта статья пересматривается с учетом изменений.)</span><span class="sxs-lookup"><span data-stu-id="c7a59-107">(This article is revised to reflect the change.)</span></span>

## <a name="summary"></a><span data-ttu-id="c7a59-108">Аннотация</span><span class="sxs-lookup"><span data-stu-id="c7a59-108">Summary</span></span>

<span data-ttu-id="c7a59-109">Для обеспечения соответствия новейшим стандартам, предъявляемым к федеральным рискам и программам управления авторизацией (FedRAMP), мы перемещаясь на устаревшую версию протокола TLS версии 1,1 и 1,0 в Microsoft Office 365 для сред High и DoD.</span><span class="sxs-lookup"><span data-stu-id="c7a59-109">In order to comply with the latest compliance standards for the Federal Risk and Authorization Management Program (FedRAMP), we are moving to deprecate Transport Layer Security (TLS) versions 1.1 and 1.0 in Microsoft Office 365 for GCC High and DoD environments.</span></span> <span data-ttu-id="c7a59-110">Это изменение было ранее объявлено в службе поддержки Майкрософт при [подготовке обязательного использования протокола TLS 1,2 в Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="c7a59-110">This change was previously announced through Microsoft Support in [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

<span data-ttu-id="c7a59-111">Мы понимаем, что важна безопасность ваших данных, и мы зафиксированы прозрачность изменений, которые могут повлиять на использование службы.</span><span class="sxs-lookup"><span data-stu-id="c7a59-111">We understand that the security of your data is important, and we are committed to transparency about changes that could affect your use of the service.</span></span>

<span data-ttu-id="c7a59-112">Несмотря на то, что [Реализация Microsoft TLS 1,0](https://support.microsoft.com/help/3117336) не содержит известных уязвимостей безопасности, мы сохранили соответствие стандартам соответствия требованиям FedRAMP.</span><span class="sxs-lookup"><span data-stu-id="c7a59-112">Although the [Microsoft TLS 1.0 implementation](https://support.microsoft.com/help/3117336) has no known security vulnerabilities, we remain committed to the FedRAMP compliance standards.</span></span> <span data-ttu-id="c7a59-113">Поэтому мы будем использовать протоколы TLS 1,1 и 1,0 в Office 365 в средах GCC High и DoD, начиная с 15 января 2020 г.</span><span class="sxs-lookup"><span data-stu-id="c7a59-113">Therefore, we will deprecate TLS 1.1 and 1.0 in Office 365 in GCC High and DoD environments starting on January 15, 2020.</span></span> <span data-ttu-id="c7a59-114">Сведения о том, как удалять зависимости TLS 1,1 и 1,0, можно найти в следующем техническом документе:</span><span class="sxs-lookup"><span data-stu-id="c7a59-114">For information about how to remove TLS 1.1 and 1.0 dependencies, see the following white paper:</span></span>

[<span data-ttu-id="c7a59-115">Решение проблемы с протоколом TLS 1,0</span><span class="sxs-lookup"><span data-stu-id="c7a59-115">Solving the TLS 1.0 problem</span></span>](https://www.microsoft.com/download/details.aspx?id=55266)

<span data-ttu-id="c7a59-116">При подготовке к этому изменению для TLS 1,1 и 1,0 рекомендуется вместо этого использовать TLS версии 1,2.</span><span class="sxs-lookup"><span data-stu-id="c7a59-116">In preparing for this change for TLS 1.1 and 1.0, we recommend that you use TLS version 1.2 instead.</span></span> <span data-ttu-id="c7a59-117">Дополнительные сведения приведены в статье [Подготовка к обязательному использованию протокола TLS 1,2 в Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="c7a59-117">For more information, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

## <a name="more-information"></a><span data-ttu-id="c7a59-118">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="c7a59-118">More information</span></span>

<span data-ttu-id="c7a59-119">Начиная с 15 января 2020, Office 365 в средах GCC High и DoD не рекомендуют протоколы TLS 1,1 и 1,0.</span><span class="sxs-lookup"><span data-stu-id="c7a59-119">Starting on January 15, 2020, Office 365 in the GCC High and DoD environments will deprecate TLS 1.1 and 1.0.</span></span>

<span data-ttu-id="c7a59-120">По 15 января 2020 г. все комбинации клиентских серверов и серверов браузера должны использовать протокол TLS версии 1,2 (или более поздней версии), чтобы все подключения могли быть выполнены без проблем со службами Office 365.</span><span class="sxs-lookup"><span data-stu-id="c7a59-120">By January 15, 2020, all combinations of client servers and browser servers should use TLS version 1.2 (or a later version) to make sure that all connections can be made without issues to Office 365 services.</span></span> <span data-ttu-id="c7a59-121">Для этого может потребоваться обновление определенных комбинаций клиентских серверов и серверов браузера.</span><span class="sxs-lookup"><span data-stu-id="c7a59-121">This may require updates to certain combinations of client servers and browser servers.</span></span>

<span data-ttu-id="c7a59-122">Если не выполнить обновление до версии 1,2 (или более поздней версии) до 15 января 2020, при попытке подключения к Office 365 будут возникать проблемы.</span><span class="sxs-lookup"><span data-stu-id="c7a59-122">If you do not update to TLS version 1.2 (or a later version) by January 15, 2020, you will experience issues when you try to connect to Office 365.</span></span> <span data-ttu-id="c7a59-123">Кроме того, в качестве части решения потребуется выполнить обновление до протокола TLS 1,2 (или более поздней версии).</span><span class="sxs-lookup"><span data-stu-id="c7a59-123">Additionally, you will be required to update to TLS 1.2 (or a later version) as part of the resolution.</span></span>

<span data-ttu-id="c7a59-124">Мы знаем, что следующие клиенты не могут использовать TLS 1,2:</span><span class="sxs-lookup"><span data-stu-id="c7a59-124">We know that the following clients cannot use TLS 1.2:</span></span>

- <span data-ttu-id="c7a59-125">Android 4.3 и более ранние версии</span><span class="sxs-lookup"><span data-stu-id="c7a59-125">Android 4.3 and earlier versions</span></span>
- <span data-ttu-id="c7a59-126">Firefox 5.0 и более ранние версии:</span><span class="sxs-lookup"><span data-stu-id="c7a59-126">Firefox version 5.0 and earlier versions</span></span>
- <span data-ttu-id="c7a59-127">Internet Explorer 8 – 10 в Windows 7 и более ранних версиях</span><span class="sxs-lookup"><span data-stu-id="c7a59-127">Internet Explorer 8–10 on Windows 7 and earlier versions</span></span>
- <span data-ttu-id="c7a59-128">Internet Explorer 10 на Windows Phone 8,0</span><span class="sxs-lookup"><span data-stu-id="c7a59-128">Internet Explorer 10 on Windows Phone 8.0</span></span>
- <span data-ttu-id="c7a59-129">Safari 6.0.4/OS X 10.8.4 и более ранние версии</span><span class="sxs-lookup"><span data-stu-id="c7a59-129">Safari 6.0.4/OS X 10.8.4 and earlier versions</span></span>

<span data-ttu-id="c7a59-130">Рекомендуется обновить клиенты, чтобы обеспечить бесперебойный доступ к Office 365 GCC High и DoD.</span><span class="sxs-lookup"><span data-stu-id="c7a59-130">We recommend that you update your clients to make sure that you maintain uninterrupted access to Office 365 GCC High and DoD.</span></span>

<span data-ttu-id="c7a59-131">Несмотря на то, что текущий анализ подключений к службам Microsoft Online показывает, что большинство служб и конечных точек видят очень небольшое использование TLS 1,1 и 1,0, мы предоставляем уведомление об этом изменении, чтобы вы могли обновить все затронутые клиенты или серверы до того, как они будут поддерживать TLS 1,1 и 1,0.</span><span class="sxs-lookup"><span data-stu-id="c7a59-131">Although current analysis of connections to Microsoft Online services shows that most services and endpoints see very little TLS 1.1 and 1.0 usage, we are providing notice of this change so that you can update any affected clients or servers as necessary before support for TLS 1.1 and 1.0 ends.</span></span> <span data-ttu-id="c7a59-132">Если вы используете локальную инфраструктуру для гибридных сценариев или служб федерации Active Directory (AD FS), убедитесь, что инфраструктура поддерживает как входящие, так и исходящие подключения, использующие протокол TLS 1,2 (или более поздней версии).</span><span class="sxs-lookup"><span data-stu-id="c7a59-132">If you are using any on-premises infrastructure for hybrid scenarios or Active Directory Federation Services (AD FS), make sure that the infrastructure can support both inbound and outbound connections that use TLS 1.2 (or a later version).</span></span>

<span data-ttu-id="c7a59-133">В дополнение к простоям, которые могут возникнуть при использовании перечисленных клиентов, которые не могут использовать протокол TLS 1,2, удаление TLS 1,1 и 1,0 приведет к тому, что вы не сможете использовать следующий продукт Майкрософт:</span><span class="sxs-lookup"><span data-stu-id="c7a59-133">In addition to the outages that you might experience if you use the listed clients that cannot use TLS 1.2, removing TLS 1.1 and 1.0 will prevent you from being able to use the following Microsoft product:</span></span>

- <span data-ttu-id="c7a59-134">Телефон Lync</span><span class="sxs-lookup"><span data-stu-id="c7a59-134">Lync phone</span></span>

## <a name="references"></a><span data-ttu-id="c7a59-135">Ссылки</span><span class="sxs-lookup"><span data-stu-id="c7a59-135">References</span></span>

<span data-ttu-id="c7a59-136">В следующей статье для поддержки описываются рекомендации и справочные материалы, которые помогут убедиться в том, что ваши клиенты используют протокол TLS 1,2:</span><span class="sxs-lookup"><span data-stu-id="c7a59-136">The following support article describes guidance and references to help make sure that your clients are using TLS 1.2:</span></span>

[<span data-ttu-id="c7a59-137">Подготовка к обязательному использованию протокола TLS 1,2 в Office 365</span><span class="sxs-lookup"><span data-stu-id="c7a59-137">Preparing for the mandatory use of TLS 1.2 in Office 365</span></span>](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)
