---
title: Новые возможности оценки безопасности Майкрософт
description: В этой статье описано, какие изменения были внесены в оценку безопасности Майкрософт в центре безопасности Майкрософт 365.
keywords: Оценка безопасности Майкрософт, Оценка безопасности, Оценка безопасности Office 365, Оценка безопасности Майкрософт, центр безопасности Майкрософт 365
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 0ba3d7a5e46f7e0f8677ce2844c5551bf70739e3
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367119"
---
# <a name="whats-new-in-microsoft-secure-score"></a><span data-ttu-id="3ed1f-104">Новые возможности оценки безопасности Майкрософт</span><span class="sxs-lookup"><span data-stu-id="3ed1f-104">What's new in Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="3ed1f-105">Чтобы сделать Microsoft Secure рейтинг более подходящим для вашей безопасности, мы внесли некоторые изменения.</span><span class="sxs-lookup"><span data-stu-id="3ed1f-105">To make Microsoft Secure Score a better representative of your security posture, we have made some changes.</span></span> <span data-ttu-id="3ed1f-106">Чтобы узнать о запланированных изменениях, посмотрите, [что поступает в рейтинге безопасности Майкрософт?](microsoft-secure-score-whats-coming.md).</span><span class="sxs-lookup"><span data-stu-id="3ed1f-106">To learn about planned changes, see [What's coming in Microsoft Secure Score?](microsoft-secure-score-whats-coming.md).</span></span>

## <a name="november-2020"></a><span data-ttu-id="3ed1f-107">Ноябрь 2020 г.</span><span class="sxs-lookup"><span data-stu-id="3ed1f-107">November 2020</span></span>

### <a name="added-3-services-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a><span data-ttu-id="3ed1f-108">Добавлено 3 действия по улучшению, связанные со службами, для защитника Майкрософт для конечной точки (ранее для защитника Майкрософт):</span><span class="sxs-lookup"><span data-stu-id="3ed1f-108">Added 3 services-related improvement actions for Microsoft Defender for Endpoint (previously Microsoft Defender ATP):</span></span>

- <span data-ttu-id="3ed1f-109">Исправление пути службы без кавычек для служб Windows</span><span class="sxs-lookup"><span data-stu-id="3ed1f-109">Fix unquoted service path for Windows services</span></span>
- <span data-ttu-id="3ed1f-110">Изменение пути к исполняемому файлу службы на общее защищенное расположение</span><span class="sxs-lookup"><span data-stu-id="3ed1f-110">Change service executable path to a common protected location</span></span>
- <span data-ttu-id="3ed1f-111">Изменение учетной записи службы для предотвращения кэширования паролей в реестре Windows</span><span class="sxs-lookup"><span data-stu-id="3ed1f-111">Change service account to avoid cached password in windows registry</span></span>

## <a name="october-2020"></a><span data-ttu-id="3ed1f-112">Октябрь 2020 г.</span><span class="sxs-lookup"><span data-stu-id="3ed1f-112">October 2020</span></span>

### <a name="remove-improvement-action-related-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="3ed1f-113">Удаление действия улучшения, связанного с защитником Майкрософт для конечной точки</span><span class="sxs-lookup"><span data-stu-id="3ed1f-113">Remove improvement action related to Microsoft Defender for Endpoint</span></span>

- <span data-ttu-id="3ed1f-114">Настройка фильтра SmartScreen защитника Майкрософт веб-контент приложения Windows Store для предупреждения</span><span class="sxs-lookup"><span data-stu-id="3ed1f-114">Set Microsoft Defender SmartScreen Windows Store app web content checking to warn</span></span>

## <a name="august-2020"></a><span data-ttu-id="3ed1f-115">Август 2020 г.</span><span class="sxs-lookup"><span data-stu-id="3ed1f-115">August 2020</span></span>

### <a name="updated-improvement-action-for-azure-active-directory"></a><span data-ttu-id="3ed1f-116">Обновленное действие по улучшению для Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="3ed1f-116">Updated improvement action for Azure Active Directory</span></span>

- <span data-ttu-id="3ed1f-117">Включение политики для блокирования устаревшей проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="3ed1f-117">Enable policy to block legacy authentication</span></span>

## <a name="incompatibility-with-identity-secure-score-and-graph-api"></a><span data-ttu-id="3ed1f-118">Несовместимость с оценками безопасности удостоверения и Graph API</span><span class="sxs-lookup"><span data-stu-id="3ed1f-118">Incompatibility with Identity Secure Score and Graph API</span></span>

<span data-ttu-id="3ed1f-119">В последней версии оценки безопасности Майкрософт была выпущена улучшенная модель оценки.</span><span class="sxs-lookup"><span data-stu-id="3ed1f-119">In the recent release of Microsoft Secure Score, an improved scoring model has been released.</span></span> <span data-ttu-id="3ed1f-120">Эти изменения обеспечивают более гибкое и точное представление обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="3ed1f-120">These changes allow for a more flexible and accurate view of your security posture.</span></span> <span data-ttu-id="3ed1f-121">Тем не менее, они временно несовместимы с оценкой безопасности Identity и API Graph.</span><span class="sxs-lookup"><span data-stu-id="3ed1f-121">However, these updates have made Microsoft Secure Score temporarily incompatible with Identity Secure Score and the Graph API.</span></span>

<span data-ttu-id="3ed1f-122">В течение времени, Оценка безопасности удостоверения и API Graph приведут к новой модели определения показателей.</span><span class="sxs-lookup"><span data-stu-id="3ed1f-122">In time, Identity Secure Score and the Graph API will adopt the new scoring model.</span></span> <span data-ttu-id="3ed1f-123">Пока пользователи не увидят отличия от оценки безопасности Майкрософт, оценки безопасности удостоверения и API Graph.</span><span class="sxs-lookup"><span data-stu-id="3ed1f-123">Until then, customers will see differences in the scores reported by Microsoft Secure Score, Identity Secure Score, and the Graph API.</span></span> <span data-ttu-id="3ed1f-124">Приносим извинения за все неудобства, которые приносятся к этому, и работают над обеспечением совместимости этих возможностей в будущем.</span><span class="sxs-lookup"><span data-stu-id="3ed1f-124">We apologize for any inconvenience this causes, and are working to ensure these experiences are more compatible in the future.</span></span>

## <a name="updated-improvement-actions"></a><span data-ttu-id="3ed1f-125">Обновленные действия по улучшению</span><span class="sxs-lookup"><span data-stu-id="3ed1f-125">Updated improvement actions</span></span>

- <span data-ttu-id="3ed1f-126">Добавлены действия по улучшению Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="3ed1f-126">Added Azure Active Directory improvement actions</span></span>
- <span data-ttu-id="3ed1f-127">Добавлены сведения о защитнике Майкрософт для действий по улучшению удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ed1f-127">Added Microsoft Defender for Identity improvement actions</span></span>
- <span data-ttu-id="3ed1f-128">Рекомендации по обеспечению безопасности уязвимостей защитником Майкрософт для конечных точек [& уязвимостей](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)</span><span class="sxs-lookup"><span data-stu-id="3ed1f-128">Support for Microsoft Defender for Endpoint [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) security recommendations</span></span>
    - <span data-ttu-id="3ed1f-129">Все выпущенные рекомендации по безопасности, предоставляемые ТВМ, теперь доступны</span><span class="sxs-lookup"><span data-stu-id="3ed1f-129">All released security recommendations supplied by TVM are now available</span></span>

## <a name="updated-interface-and-functionality"></a><span data-ttu-id="3ed1f-130">Обновленный интерфейс и функциональные возможности</span><span class="sxs-lookup"><span data-stu-id="3ed1f-130">Updated interface and functionality</span></span>

* <span data-ttu-id="3ed1f-131">Все новые показатели и тенденции для ЦИСО и дискуссий на уровне ведущего</span><span class="sxs-lookup"><span data-stu-id="3ed1f-131">All new metrics and trends views for CISO and lead level discussions</span></span>
* <span data-ttu-id="3ed1f-132">Новые способы отслеживания и оценки оценки</span><span class="sxs-lookup"><span data-stu-id="3ed1f-132">New ways to track and benchmark your score</span></span>
* <span data-ttu-id="3ed1f-133">Улучшение отслеживания и понимания регрессий для оценок</span><span class="sxs-lookup"><span data-stu-id="3ed1f-133">Better tracking and understanding for score regressions</span></span>
* <span data-ttu-id="3ed1f-134">Фильтрация, пометка, Поиск и группировка действий по улучшению</span><span class="sxs-lookup"><span data-stu-id="3ed1f-134">Filter, tag, search, and group your improvement actions</span></span>
* <span data-ttu-id="3ed1f-135">Управляйте своими будущими целями, используя проекции оценок и запланированные действия</span><span class="sxs-lookup"><span data-stu-id="3ed1f-135">Manage towards your future goals using score projections and planned actions</span></span>
* <span data-ttu-id="3ed1f-136">И многое другое!</span><span class="sxs-lookup"><span data-stu-id="3ed1f-136">And more!</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="3ed1f-137">Мы хотим услышать вас</span><span class="sxs-lookup"><span data-stu-id="3ed1f-137">We want to hear from you</span></span>

<span data-ttu-id="3ed1f-138">Если у вас возникли какие – либо проблемы, сообщите нам о публикации в разделе [безопасность, конфиденциальность & соответствие требованиям](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) .</span><span class="sxs-lookup"><span data-stu-id="3ed1f-138">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="3ed1f-139">Мы отслеживаем сообщество и предоставите вам помощь.</span><span class="sxs-lookup"><span data-stu-id="3ed1f-139">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="3ed1f-140">Связанные ресурсы</span><span class="sxs-lookup"><span data-stu-id="3ed1f-140">Related resources</span></span>

- [<span data-ttu-id="3ed1f-141">Оценка уровня безопасности</span><span class="sxs-lookup"><span data-stu-id="3ed1f-141">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="3ed1f-142">Отслеживание журнала оценки безопасности Майкрософт и соответствующих целей</span><span class="sxs-lookup"><span data-stu-id="3ed1f-142">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="3ed1f-143">Что вскоре появится</span><span class="sxs-lookup"><span data-stu-id="3ed1f-143">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
