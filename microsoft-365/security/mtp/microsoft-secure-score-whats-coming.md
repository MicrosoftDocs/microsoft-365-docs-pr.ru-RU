---
title: Что поступает в оценку безопасности Майкрософт
description: В этой статье описывается, какие новые изменения поступают в оценку безопасности Майкрософт в центре безопасности Майкрософт 365.
keywords: Оценка безопасности Майкрософт, Оценка безопасности, Оценка безопасности Office 365, Оценка безопасности Microsoft 365, центр безопасности Майкрософт, действия по улучшению
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
ms.openlocfilehash: 82ec67cae86525c055b2232667cccb603830d15f
ms.sourcegitcommit: c51de5e1a4cb9c4a7a9854a4226b32453d9e73e0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/28/2020
ms.locfileid: "48779252"
---
# <a name="whats-coming-to-microsoft-secure-score"></a><span data-ttu-id="c9557-104">Что поступает в оценку безопасности Майкрософт</span><span class="sxs-lookup"><span data-stu-id="c9557-104">What's coming to Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="c9557-105">Мы внесены некоторые изменения в ближайшем будущем, чтобы сделать [Microsoft Secure рейтинг](microsoft-secure-score.md) более эффективным для обеспечения безопасности и повышения удобства использования.</span><span class="sxs-lookup"><span data-stu-id="c9557-105">We're making some changes in the near future to make [Microsoft Secure Score](microsoft-secure-score.md) a better representative of your security posture and improve usability.</span></span> <span data-ttu-id="c9557-106">Ваш рейтинг и максимально возможный рейтинг могут измениться.</span><span class="sxs-lookup"><span data-stu-id="c9557-106">Your score and the maximum possible score may change.</span></span>

## <a name="proposed-changes"></a><span data-ttu-id="c9557-107">Предлагаемые изменения</span><span class="sxs-lookup"><span data-stu-id="c9557-107">Proposed changes</span></span>

### <a name="november-2020"></a><span data-ttu-id="c9557-108">Ноябрь 2020 г.</span><span class="sxs-lookup"><span data-stu-id="c9557-108">November 2020</span></span>

<span data-ttu-id="c9557-109">Чтобы **предоставить общий доступ к > ServiceNow** , удалите возможность создавать билеты с помощью безопасной оценки.</span><span class="sxs-lookup"><span data-stu-id="c9557-109">Removing the ability to create ServiceNow tickets through Secure Score by going to **Share > ServiceNow** .</span></span>

- <span data-ttu-id="c9557-110">Период предварительной версии для соединителя ServiceNow завершается.</span><span class="sxs-lookup"><span data-stu-id="c9557-110">The preview period for the ServiceNow connector is ending.</span></span> <span data-ttu-id="c9557-111">Эта возможность больше не будет доступна в конце 2020.</span><span class="sxs-lookup"><span data-stu-id="c9557-111">This capability will no longer available by the end of 2020.</span></span> <span data-ttu-id="c9557-112">Благодарим вас за отзыв и продолжение поддержки, пока мы определим дальнейшие действия.</span><span class="sxs-lookup"><span data-stu-id="c9557-112">Thank you for your feedback and continued support while we determine next steps.</span></span>

<span data-ttu-id="c9557-113">Добавление 18 действий по улучшению, связанных с защитником Майкрософт, для конечной точки (ранее для защитника Майкрософт):</span><span class="sxs-lookup"><span data-stu-id="c9557-113">Adding 18 improvement actions related to Microsoft Defender for Endpoint (previously Microsoft Defender ATP):</span></span>

<span data-ttu-id="c9557-114">Рекомендации по сокращению уязвимости (ASR):</span><span class="sxs-lookup"><span data-stu-id="c9557-114">Attack Surface Reduction (ASR) related recommendations:</span></span>
- <span data-ttu-id="c9557-115">Блокировать исполняемый контент из почтового клиента и из почтового ящика</span><span class="sxs-lookup"><span data-stu-id="c9557-115">Block executable content from email client and webmail</span></span>
- <span data-ttu-id="c9557-116">Блокировка создания дочерних процессов для всех приложений Office</span><span class="sxs-lookup"><span data-stu-id="c9557-116">Block all Office applications from creating child processes</span></span>
- <span data-ttu-id="c9557-117">Блокировка создания исполняемого контента приложениями Office</span><span class="sxs-lookup"><span data-stu-id="c9557-117">Block Office applications from creating executable content</span></span>
- <span data-ttu-id="c9557-118">Блокировка приложений Office при вставке кода в другие процессы</span><span class="sxs-lookup"><span data-stu-id="c9557-118">Block Office applications from injecting code into other processes</span></span>
- <span data-ttu-id="c9557-119">Блокировка JavaScript или VBScript для запуска загруженного исполняемого контента</span><span class="sxs-lookup"><span data-stu-id="c9557-119">Block JavaScript or VBScript from launching downloaded executable content</span></span>
- <span data-ttu-id="c9557-120">Блокировка выполнения потенциально запутанных сценариев</span><span class="sxs-lookup"><span data-stu-id="c9557-120">Block execution of potentially obfuscated scripts</span></span>
- <span data-ttu-id="c9557-121">Блокировка вызовов API Win32 из макросов Office</span><span class="sxs-lookup"><span data-stu-id="c9557-121">Block Win32 API calls from Office macros</span></span>
- <span data-ttu-id="c9557-122">Блокировать запуск исполняемых файлов, если они не удовлетворяют условию преобладание, возраст или доверенный список.</span><span class="sxs-lookup"><span data-stu-id="c9557-122">Block executable files from running unless they meet a prevalence, age, or trusted list criterion</span></span>
- <span data-ttu-id="c9557-123">Использование расширенной защиты от атаки с помощью средства защиты от атак</span><span class="sxs-lookup"><span data-stu-id="c9557-123">Use advanced protection against ransomware</span></span>
- <span data-ttu-id="c9557-124">Блокировка переноса учетных данных из подсистемы локального центра безопасности Windows (lsass.exe)</span><span class="sxs-lookup"><span data-stu-id="c9557-124">Block credential stealing from the Windows local security authority subsystem (lsass.exe)</span></span>
- <span data-ttu-id="c9557-125">Блокировка создания процессов, исходящих из команд PSExec и WMI</span><span class="sxs-lookup"><span data-stu-id="c9557-125">Block process creations originating from PSExec and WMI commands</span></span>
- <span data-ttu-id="c9557-126">Блокировка недоверенных и неподписанных процессов, выполняемых с USB</span><span class="sxs-lookup"><span data-stu-id="c9557-126">Block untrusted and unsigned processes that run from USB</span></span>
- <span data-ttu-id="c9557-127">Блокировка создания дочерних процессов приложением взаимодействия с Office</span><span class="sxs-lookup"><span data-stu-id="c9557-127">Block Office communication application from creating child processes</span></span>
- <span data-ttu-id="c9557-128">Блокировка создания дочерних процессов в Adobe Reader</span><span class="sxs-lookup"><span data-stu-id="c9557-128">Block Adobe Reader from creating child processes</span></span>
- <span data-ttu-id="c9557-129">Блокировка сохраняемости через подписку на события WMI</span><span class="sxs-lookup"><span data-stu-id="c9557-129">Block persistence through WMI event subscription</span></span>

<span data-ttu-id="c9557-130">Рекомендации, связанные со службами:</span><span class="sxs-lookup"><span data-stu-id="c9557-130">Services related recommendations:</span></span>
- <span data-ttu-id="c9557-131">Исправление пути службы без кавычек для служб Windows</span><span class="sxs-lookup"><span data-stu-id="c9557-131">Fix unquoted service path for Windows services</span></span>
- <span data-ttu-id="c9557-132">Изменение пути к исполняемому файлу службы на общее защищенное расположение</span><span class="sxs-lookup"><span data-stu-id="c9557-132">Change service executable path to a common protected location</span></span>
- <span data-ttu-id="c9557-133">Изменение учетной записи службы для предотвращения кэширования паролей в реестре Windows</span><span class="sxs-lookup"><span data-stu-id="c9557-133">Change service account to avoid cached password in windows registry</span></span>

## <a name="related-resources"></a><span data-ttu-id="c9557-134">Связанные ресурсы</span><span class="sxs-lookup"><span data-stu-id="c9557-134">Related resources</span></span>

- [<span data-ttu-id="c9557-135">Обзор оценки безопасности Майкрософт</span><span class="sxs-lookup"><span data-stu-id="c9557-135">Microsoft Secure Score overview</span></span>](microsoft-secure-score.md)
- [<span data-ttu-id="c9557-136">Оценка уровня безопасности</span><span class="sxs-lookup"><span data-stu-id="c9557-136">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="c9557-137">Отслеживание журнала оценки безопасности Майкрософт и соответствующих целей</span><span class="sxs-lookup"><span data-stu-id="c9557-137">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="c9557-138">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="c9557-138">What's new</span></span>](microsoft-secure-score-whats-new.md)
