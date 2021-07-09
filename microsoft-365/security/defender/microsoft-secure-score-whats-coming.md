---
title: Что происходит в Microsoft Secure Score
description: Описывает новые изменения в Microsoft Secure Score в центре Microsoft 365 безопасности.
keywords: Microsoft secure score, secure score, office 365 secure score, microsoft security score, Microsoft 365 security center, improvement actions
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 910eb16ad33555ca61875a346b50cea7e63b2220
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/08/2021
ms.locfileid: "53338557"
---
# <a name="whats-coming-to-microsoft-secure-score"></a><span data-ttu-id="e72dd-104">Что происходит в Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="e72dd-104">What's coming to Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="e72dd-105">Microsoft Secure Score можно найти в центре Microsoft 365 https://security.microsoft.com/securescore [безопасности.](overview-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="e72dd-105">Microsoft Secure Score can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

## <a name="proposed-changes"></a><span data-ttu-id="e72dd-106">Предлагаемые изменения</span><span class="sxs-lookup"><span data-stu-id="e72dd-106">Proposed changes</span></span>

<span data-ttu-id="e72dd-107">В ближайшее время мы внося некоторые изменения, чтобы [сделать Microsoft Secure Score](microsoft-secure-score.md) лучшим представителем вашей позиции в области безопасности и повысить эффективность использования.</span><span class="sxs-lookup"><span data-stu-id="e72dd-107">We're making some changes in the near future to make [Microsoft Secure Score](microsoft-secure-score.md) a better representative of your security posture and improve usability.</span></span> <span data-ttu-id="e72dd-108">Ваш счет и максимально возможный балл могут измениться.</span><span class="sxs-lookup"><span data-stu-id="e72dd-108">Your score and the maximum possible score may change.</span></span>

### <a name="july-2021"></a><span data-ttu-id="e72dd-109">Июль 2021 г.</span><span class="sxs-lookup"><span data-stu-id="e72dd-109">July 2021</span></span>

#### <a name="add-improvement-action-related-to-microsoft-teams"></a><span data-ttu-id="e72dd-110">Добавление действия по улучшению, связанное с Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e72dd-110">Add improvement action related to Microsoft Teams</span></span>

- <span data-ttu-id="e72dd-111">Ограничить пользователей, взбирающихся в диалог, обходя вестибюль собрания.</span><span class="sxs-lookup"><span data-stu-id="e72dd-111">Restrict dial-in users from bypassing a meeting lobby.</span></span>
- <span data-ttu-id="e72dd-112">Ограничить доступ внешних участников к контролю Teams собрания.</span><span class="sxs-lookup"><span data-stu-id="e72dd-112">Limit external participants from having control in a Teams meeting.</span></span>
- <span data-ttu-id="e72dd-113">Запретить анонимным пользователям начинать Teams собрания.</span><span class="sxs-lookup"><span data-stu-id="e72dd-113">Restrict anonymous users from starting Teams meetings.</span></span>
- <span data-ttu-id="e72dd-114">Необходимо настроить лобби для Teams собраний.</span><span class="sxs-lookup"><span data-stu-id="e72dd-114">Require lobbies to be set up for Teams meetings.</span></span>
- <span data-ttu-id="e72dd-115">Настройка того, какие пользователи могут присутствовать на собраниях Teams собраниях.</span><span class="sxs-lookup"><span data-stu-id="e72dd-115">Configure which users are allowed to be present in Teams meetings.</span></span>

#### <a name="add-improvement-action-related-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="e72dd-116">Добавление действий по улучшению, связанных с Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="e72dd-116">Add improvement action related to Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="e72dd-117">Исправление microsoft Defender для сбора данных датчиков конечных точек для macOS</span><span class="sxs-lookup"><span data-stu-id="e72dd-117">Fix Microsoft Defender for Endpoint sensor data collection for macOS</span></span>
- <span data-ttu-id="e72dd-118">Исправление microsoft Defender для связи с нарушениями конечных точек для macOS</span><span class="sxs-lookup"><span data-stu-id="e72dd-118">Fix Microsoft Defender for Endpoint impaired communications for macOS</span></span>
- <span data-ttu-id="e72dd-119">Установите минимальную длину пароля до 15 или более символов в macOS</span><span class="sxs-lookup"><span data-stu-id="e72dd-119">Set minimum password length to 15 or more characters in macOS</span></span>
- <span data-ttu-id="e72dd-120">Установите в macOS 'Enforce password history' to '24 or more password(s)'</span><span class="sxs-lookup"><span data-stu-id="e72dd-120">Set 'Enforce password history' to '24 or more password(s)' in macOS</span></span>
- <span data-ttu-id="e72dd-121">Установите "Максимальный возраст пароля" до "90 или меньше дней, но не 0" в macOS</span><span class="sxs-lookup"><span data-stu-id="e72dd-121">Set 'Maximum password age' to '90 or fewer days, but not 0' in macOS</span></span>
- <span data-ttu-id="e72dd-122">Установите пороговое значение блокировки учетной записи до 5 или ниже в macOS</span><span class="sxs-lookup"><span data-stu-id="e72dd-122">Set account lockout threshold to 5 or lower in macOS</span></span>
- <span data-ttu-id="e72dd-123">Включи брандмауэр на macOS</span><span class="sxs-lookup"><span data-stu-id="e72dd-123">Turn on Firewall on macOS</span></span>
- <span data-ttu-id="e72dd-124">Включить привратник</span><span class="sxs-lookup"><span data-stu-id="e72dd-124">Enable Gatekeeper</span></span>
- <span data-ttu-id="e72dd-125">Включить защиту целостности системы (SIP)</span><span class="sxs-lookup"><span data-stu-id="e72dd-125">Enable System Integrity Protection (SIP)</span></span>
- <span data-ttu-id="e72dd-126">Включить шифрование дисков FileVault</span><span class="sxs-lookup"><span data-stu-id="e72dd-126">Enable FileVault Disk Encryption</span></span>
- <span data-ttu-id="e72dd-127">Настройка экрана для блокировки при старте экрана в macOS</span><span class="sxs-lookup"><span data-stu-id="e72dd-127">Set screen to lock when screensaver starts in macOS</span></span>
- <span data-ttu-id="e72dd-128">Убедитесь в том, что набор экрана должен начинаться через 20 минут или менее в macOS</span><span class="sxs-lookup"><span data-stu-id="e72dd-128">Ensure screensaver is set to start in 20 minutes or less in macOS</span></span>
- <span data-ttu-id="e72dd-129">Безопасность домашних папок</span><span class="sxs-lookup"><span data-stu-id="e72dd-129">Secure Home Folders</span></span>
- <span data-ttu-id="e72dd-130">Включаем антивирусная программа в Microsoft Defender защиту в режиме реального времени для macOS</span><span class="sxs-lookup"><span data-stu-id="e72dd-130">Turn on Microsoft Defender Antivirus real-time protection for macOS</span></span>
- <span data-ttu-id="e72dd-131">Включить защиту антивирусная программа в Microsoft Defender PUA в режиме блокировки для macOS</span><span class="sxs-lookup"><span data-stu-id="e72dd-131">Turn on Microsoft Defender Antivirus PUA protection in block mode for macOS</span></span>
- <span data-ttu-id="e72dd-132">Включить антивирусная программа в Microsoft Defender облачной защиты для macOS</span><span class="sxs-lookup"><span data-stu-id="e72dd-132">Enable Microsoft Defender Antivirus cloud-delivered protection for macOS</span></span>
- <span data-ttu-id="e72dd-133">Обновление антивирусная программа в Microsoft Defender определений для macOS</span><span class="sxs-lookup"><span data-stu-id="e72dd-133">Update Microsoft Defender Antivirus definitions for macOS</span></span>
- <span data-ttu-id="e72dd-134">Исправление microsoft Defender для сбора данных датчиков конечной точки для Linux</span><span class="sxs-lookup"><span data-stu-id="e72dd-134">Fix Microsoft Defender for Endpoint sensor data collection for Linux</span></span>
- <span data-ttu-id="e72dd-135">Исправление microsoft Defender для нарушенных коммуникаций конечной точки для Linux</span><span class="sxs-lookup"><span data-stu-id="e72dd-135">Fix Microsoft Defender for Endpoint impaired communications for Linux</span></span>
- <span data-ttu-id="e72dd-136">Неограниченные учетные записи доступа</span><span class="sxs-lookup"><span data-stu-id="e72dd-136">Unrestricted Access Accounts</span></span>
- <span data-ttu-id="e72dd-137">Включи антивирусная программа в Microsoft Defender защиту в режиме реального времени для Linux</span><span class="sxs-lookup"><span data-stu-id="e72dd-137">Turn on Microsoft Defender Antivirus real-time protection for Linux</span></span>
- <span data-ttu-id="e72dd-138">Включаем антивирусная программа в Microsoft Defender защиты PUA в режиме блокировки для Linux</span><span class="sxs-lookup"><span data-stu-id="e72dd-138">Turn on Microsoft Defender Antivirus PUA protection in block mode for Linux</span></span>
- <span data-ttu-id="e72dd-139">Включить антивирусная программа в Microsoft Defender облачной защиты для Linux</span><span class="sxs-lookup"><span data-stu-id="e72dd-139">Enable Microsoft Defender Antivirus cloud-delivered protection for Linux</span></span>
- <span data-ttu-id="e72dd-140">Обновление антивирусная программа в Microsoft Defender определений для Linux</span><span class="sxs-lookup"><span data-stu-id="e72dd-140">Update Microsoft Defender Antivirus definitions for Linux</span></span>



## <a name="related-resources"></a><span data-ttu-id="e72dd-141">Связанные ресурсы</span><span class="sxs-lookup"><span data-stu-id="e72dd-141">Related resources</span></span>

- [<span data-ttu-id="e72dd-142">Обзор результатов microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="e72dd-142">Microsoft Secure Score overview</span></span>](microsoft-secure-score.md)
- [<span data-ttu-id="e72dd-143">Доступ к состоянию безопасности</span><span class="sxs-lookup"><span data-stu-id="e72dd-143">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="e72dd-144">Отслеживание истории microsoft Secure Score и достижения целей</span><span class="sxs-lookup"><span data-stu-id="e72dd-144">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="e72dd-145">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="e72dd-145">What's new</span></span>](microsoft-secure-score-whats-new.md)
