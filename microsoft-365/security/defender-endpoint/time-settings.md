---
title: Параметры часового пояса Центра безопасности Microsoft Defender
description: Используйте сведения, содержащиеся здесь, чтобы настроить параметры часового пояса Microsoft Defender Security Center и просмотреть сведения о лицензии.
keywords: параметры, Microsoft Defender, разведка угроз кибербезопасности, расширенные средства защиты от угроз, часовой пояс, utc, местное время, лицензия
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c6338155aae3605ac5721958363b8c2d86618d9b
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51183853"
---
# <a name="microsoft-defender-security-center-time-zone-settings"></a><span data-ttu-id="ec847-104">Параметры часового пояса Центра безопасности Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ec847-104">Microsoft Defender Security Center time zone settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ec847-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="ec847-105">**Applies to:**</span></span>
- [<span data-ttu-id="ec847-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="ec847-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ec847-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ec847-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)




><span data-ttu-id="ec847-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="ec847-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ec847-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="ec847-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-settings-abovefoldlink)

<span data-ttu-id="ec847-110">Чтобы настроить **часовой** пояс и просмотреть сведения о лицензии, используйте значок параметров часовой ![ ](images/atp-time-zone.png) зоны .</span><span class="sxs-lookup"><span data-stu-id="ec847-110">Use the **Time zone** menu ![Time zone settings icon1](images/atp-time-zone.png) to configure the time zone and view license information.</span></span>

## <a name="time-zone-settings"></a><span data-ttu-id="ec847-111">Параметры часовой зоны</span><span class="sxs-lookup"><span data-stu-id="ec847-111">Time zone settings</span></span>
<span data-ttu-id="ec847-112">Аспект времени имеет важное значение для оценки и анализа предполагаемых и фактических кибератак.</span><span class="sxs-lookup"><span data-stu-id="ec847-112">The aspect of time is important in the assessment and analysis of perceived and actual cyberattacks.</span></span>

<span data-ttu-id="ec847-113">Киберфоренсические расследования часто используют штампы времени, чтобы собрать последовательность событий.</span><span class="sxs-lookup"><span data-stu-id="ec847-113">Cyberforensic investigations often rely on time stamps to piece together the sequence of events.</span></span> <span data-ttu-id="ec847-114">Важно, чтобы система отражала правильные параметры часовой пояс.</span><span class="sxs-lookup"><span data-stu-id="ec847-114">It’s important that your system reflects the correct time zone settings.</span></span>

<span data-ttu-id="ec847-115">Защитник Microsoft для конечной точки может отображать как скоординированное универсальное время (UTC), так и локальное время.</span><span class="sxs-lookup"><span data-stu-id="ec847-115">Microsoft Defender for Endpoint can display either Coordinated Universal Time (UTC) or local time.</span></span>

<span data-ttu-id="ec847-116">Текущий параметр часовой пояс отображается в меню Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="ec847-116">Your current time zone setting is shown in the Microsoft Defender for Endpoint menu.</span></span> <span data-ttu-id="ec847-117">Вы можете изменить отображаемую часовую зону в **меню часовой** зоны.</span><span class="sxs-lookup"><span data-stu-id="ec847-117">You can change the displayed time zone in the **Time zone** menu.</span></span>

![Значок параметров часовой зоны2](images/atp-time-zone-menu.png)<span data-ttu-id="ec847-119">.</span><span class="sxs-lookup"><span data-stu-id="ec847-119">.</span></span>

### <a name="utc-time-zone"></a><span data-ttu-id="ec847-120">Часовой пояс UTC</span><span class="sxs-lookup"><span data-stu-id="ec847-120">UTC time zone</span></span>
<span data-ttu-id="ec847-121">Microsoft Defender для конечной точки использует время UTC по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ec847-121">Microsoft Defender for Endpoint uses UTC time by default.</span></span>

<span data-ttu-id="ec847-122">Настройка часовой зоны Microsoft Defender для конечной точки для UTC отображает все системные периоды времени (оповещения, события и другие) в UTC для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="ec847-122">Setting the Microsoft Defender for Endpoint time zone to UTC will display all system timestamps (alerts, events, and others) in UTC for all users.</span></span> <span data-ttu-id="ec847-123">Это может помочь аналитикам безопасности, работающим в разных местах по всему миру, использовать одинаковые штампы времени при расследовании событий.</span><span class="sxs-lookup"><span data-stu-id="ec847-123">This can help security analysts working in different locations across the globe to use the same time stamps while investigating events.</span></span>

### <a name="local-time-zone"></a><span data-ttu-id="ec847-124">Локальный часовой пояс</span><span class="sxs-lookup"><span data-stu-id="ec847-124">Local time zone</span></span>
<span data-ttu-id="ec847-125">Вы можете выбрать, чтобы Microsoft Defender для конечной точки использовали локальные параметры часовой пояс.</span><span class="sxs-lookup"><span data-stu-id="ec847-125">You can choose to have Microsoft Defender for Endpoint use local time zone settings.</span></span> <span data-ttu-id="ec847-126">Все оповещения и события будут отображаться в локальном часовом поясе.</span><span class="sxs-lookup"><span data-stu-id="ec847-126">All alerts and events will be displayed using your local time zone.</span></span>

<span data-ttu-id="ec847-127">Локальный часовой пояс взят из региональных параметров устройства.</span><span class="sxs-lookup"><span data-stu-id="ec847-127">The local time zone is taken from your device’s regional settings.</span></span> <span data-ttu-id="ec847-128">При изменении региональных параметров также изменится часовой пояс Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="ec847-128">If you change your regional settings, the Microsoft Defender for Endpoint time zone will also change.</span></span> <span data-ttu-id="ec847-129">Выбор этого параметра означает, что периоды времени, отображаемые в Microsoft Defender для конечной точки, будут согласованы с локальным временем для всех пользователей Конечных точек Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="ec847-129">Choosing this setting means that the timestamps displayed in Microsoft Defender for Endpoint will be aligned to local time for all Microsoft Defender for Endpoint users.</span></span> <span data-ttu-id="ec847-130">Аналитики, расположенные в разных глобальных расположениях, теперь будут видеть оповещений Microsoft Defender для конечных точек в соответствии с их региональными настройками.</span><span class="sxs-lookup"><span data-stu-id="ec847-130">Analysts located in different global locations will now see the Microsoft Defender for Endpoint alerts according to their regional settings.</span></span>

<span data-ttu-id="ec847-131">Выбор использования местного времени может быть полезен, если аналитики находятся в одном расположении.</span><span class="sxs-lookup"><span data-stu-id="ec847-131">Choosing to use local time can be useful if the analysts are located in a single location.</span></span> <span data-ttu-id="ec847-132">В этом случае может быть проще соотнести события с локальным временем, например, когда локальный пользователь нажал на подозрительную ссылку электронной почты.</span><span class="sxs-lookup"><span data-stu-id="ec847-132">In this case it might be easier to correlate events to local time, for example – when a local user clicked on a suspicious email link.</span></span>

### <a name="set-the-time-zone"></a><span data-ttu-id="ec847-133">Установите часовой пояс</span><span class="sxs-lookup"><span data-stu-id="ec847-133">Set the time zone</span></span>
<span data-ttu-id="ec847-134">Часовой пояс Microsoft Defender для конечной точки по умолчанию устанавливается для UTC.</span><span class="sxs-lookup"><span data-stu-id="ec847-134">The Microsoft Defender for Endpoint time zone is set by default to UTC.</span></span>
<span data-ttu-id="ec847-135">Настройка часовой зоны также изменяет время для всех представлений Microsoft Defender для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="ec847-135">Setting the time zone also changes the times for all Microsoft Defender for Endpoint views.</span></span>
<span data-ttu-id="ec847-136">Чтобы установить часовой пояс:</span><span class="sxs-lookup"><span data-stu-id="ec847-136">To set the time zone:</span></span>

1. <span data-ttu-id="ec847-137">Щелкните **значок** параметров часовой зоны меню ![ Часовой зоны3. ](images/atp-time-zone.png)</span><span class="sxs-lookup"><span data-stu-id="ec847-137">Click the **Time zone** menu ![Time zone settings icon3](images/atp-time-zone.png).</span></span>
2. <span data-ttu-id="ec847-138">Выберите индикатор **UTC часовой зоны.**</span><span class="sxs-lookup"><span data-stu-id="ec847-138">Select the **Timezone UTC** indicator.</span></span>
3. <span data-ttu-id="ec847-139">Выберите **UTC часовой** пояс или локальный часовой пояс, например -7:00.</span><span class="sxs-lookup"><span data-stu-id="ec847-139">Select **Timezone UTC** or your local time zone, for example -7:00.</span></span>

### <a name="regional-settings"></a><span data-ttu-id="ec847-140">Региональные параметры</span><span class="sxs-lookup"><span data-stu-id="ec847-140">Regional settings</span></span>
<span data-ttu-id="ec847-141">Чтобы применить различные форматы дат для Microsoft Defender для конечной точки, используйте региональные параметры для Internet Explorer (IE) и Microsoft Edge (Edge).</span><span class="sxs-lookup"><span data-stu-id="ec847-141">To apply different date formats for Microsoft Defender for Endpoint, use regional settings for Internet Explorer (IE) and Microsoft Edge (Edge).</span></span> <span data-ttu-id="ec847-142">Если вы используете другой браузер, например Google Chrome, выполните необходимые действия, чтобы изменить параметры времени и даты для этого браузера.</span><span class="sxs-lookup"><span data-stu-id="ec847-142">If you're using another browser such as Google Chrome, follow the required steps to change the time and date settings for that browser.</span></span> 


<span data-ttu-id="ec847-143">**Internet Explorer (IE) и Microsoft Edge**</span><span class="sxs-lookup"><span data-stu-id="ec847-143">**Internet Explorer (IE) and Microsoft Edge**</span></span>

<span data-ttu-id="ec847-144">IE и Microsoft Edge используют **параметры Region,** настроенные в параметре **"Часы",** "Язык" и "Область" в панели управления.</span><span class="sxs-lookup"><span data-stu-id="ec847-144">IE and Microsoft Edge use the **Region** settings configured in the **Clocks, Language, and Region** option in the Control panel.</span></span> 


#### <a name="known-issues-with-regional-formats"></a><span data-ttu-id="ec847-145">Известные проблемы с региональными форматами</span><span class="sxs-lookup"><span data-stu-id="ec847-145">Known issues with regional formats</span></span>

<span data-ttu-id="ec847-146">**Форматы даты и времени**</span><span class="sxs-lookup"><span data-stu-id="ec847-146">**Date and time formats**</span></span><br>
<span data-ttu-id="ec847-147">Известны некоторые проблемы с форматами времени и даты.</span><span class="sxs-lookup"><span data-stu-id="ec847-147">There are some known issues with the time and date formats.</span></span> <span data-ttu-id="ec847-148">Если настроить региональные параметры на что-либо, кроме поддерживаемых форматов, портал может неправильно отражать ваши параметры.</span><span class="sxs-lookup"><span data-stu-id="ec847-148">If you configure your regional settings to anything other than the supported formats, the portal may not correctly reflect your settings.</span></span>

<span data-ttu-id="ec847-149">Поддерживаются следующие форматы даты и времени:</span><span class="sxs-lookup"><span data-stu-id="ec847-149">The following date and time formats are supported:</span></span>
- <span data-ttu-id="ec847-150">Формат даты MM/dd/yyyy</span><span class="sxs-lookup"><span data-stu-id="ec847-150">Date format MM/dd/yyyy</span></span>
- <span data-ttu-id="ec847-151">Формат даты dd/MM/yyyy</span><span class="sxs-lookup"><span data-stu-id="ec847-151">Date format dd/MM/yyyy</span></span>
- <span data-ttu-id="ec847-152">Формат времени hh:mm:ss (12-часовой формат)</span><span class="sxs-lookup"><span data-stu-id="ec847-152">Time format hh:mm:ss (12 hour format)</span></span>

<span data-ttu-id="ec847-153">В настоящее время не поддерживаются следующие форматы даты и времени:</span><span class="sxs-lookup"><span data-stu-id="ec847-153">The following date and time formats are currently not supported:</span></span>
- <span data-ttu-id="ec847-154">Формат yyyy-MM-dd</span><span class="sxs-lookup"><span data-stu-id="ec847-154">Date format yyyy-MM-dd</span></span>
- <span data-ttu-id="ec847-155">Формат даты dd-MMM-yy</span><span class="sxs-lookup"><span data-stu-id="ec847-155">Date format dd-MMM-yy</span></span>
- <span data-ttu-id="ec847-156">Формат даты dd/MM/yyy</span><span class="sxs-lookup"><span data-stu-id="ec847-156">Date format dd/MM/yy</span></span>
- <span data-ttu-id="ec847-157">Формат даты MM/dd/yyy</span><span class="sxs-lookup"><span data-stu-id="ec847-157">Date format MM/dd/yy</span></span>
- <span data-ttu-id="ec847-158">Формат даты с yy.</span><span class="sxs-lookup"><span data-stu-id="ec847-158">Date format with yy.</span></span> <span data-ttu-id="ec847-159">Будет показываться только yyyy.</span><span class="sxs-lookup"><span data-stu-id="ec847-159">Will only show yyyy.</span></span>
- <span data-ttu-id="ec847-160">Формат времени HH:mm:ss (24-часовой формат)</span><span class="sxs-lookup"><span data-stu-id="ec847-160">Time format HH:mm:ss (24 hour format)</span></span>

<span data-ttu-id="ec847-161">**Десятичной символ, используемый в числах**</span><span class="sxs-lookup"><span data-stu-id="ec847-161">**Decimal symbol used in numbers**</span></span><br>
<span data-ttu-id="ec847-162">Используемый десятичный символ всегда является точкой, даже если запятая выбрана в параметрах **формата Numbers** в **параметрах Region.**</span><span class="sxs-lookup"><span data-stu-id="ec847-162">Decimal symbol used is always a dot, even if a comma is selected in  the **Numbers** format settings in **Region** settings.</span></span> <span data-ttu-id="ec847-163">Например, 15,5K отображается как 15,5K.</span><span class="sxs-lookup"><span data-stu-id="ec847-163">For example, 15,5K is displayed as 15.5K.</span></span>


