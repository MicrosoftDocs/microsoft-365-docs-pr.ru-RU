---
title: Центр безопасности в Microsoft Defender часовой пояс
description: Используйте сведения, содержащиеся здесь, чтобы настроить параметры Центр безопасности в Microsoft Defender часовой пояс и просмотреть сведения о лицензии.
keywords: параметры, Microsoft Defender, разведка угроз кибербезопасности, Microsoft Defender для конечной точки, часовой пояс, utc, местное время, лицензия
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
ms.openlocfilehash: df55a1b0e92c24b5f52032330ef95bf19aeb8cb3
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932635"
---
# <a name="microsoft-defender-security-center-time-zone-settings"></a><span data-ttu-id="f6fee-104">Центр безопасности в Microsoft Defender часовой пояс</span><span class="sxs-lookup"><span data-stu-id="f6fee-104">Microsoft Defender Security Center time zone settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f6fee-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="f6fee-105">**Applies to:**</span></span>
- [<span data-ttu-id="f6fee-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="f6fee-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="f6fee-107">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="f6fee-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f6fee-108">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="f6fee-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-settings-abovefoldlink)

<span data-ttu-id="f6fee-109">Чтобы настроить **часовой** пояс и просмотреть сведения о лицензии, используйте значок параметров часовой ![ ](images/atp-time-zone.png) зоны .</span><span class="sxs-lookup"><span data-stu-id="f6fee-109">Use the **Time zone** menu ![Time zone settings icon1](images/atp-time-zone.png) to configure the time zone and view license information.</span></span>

## <a name="time-zone-settings"></a><span data-ttu-id="f6fee-110">Параметры часовой зоны</span><span class="sxs-lookup"><span data-stu-id="f6fee-110">Time zone settings</span></span>
<span data-ttu-id="f6fee-111">Аспект времени имеет важное значение для оценки и анализа предполагаемых и фактических кибератак.</span><span class="sxs-lookup"><span data-stu-id="f6fee-111">The aspect of time is important in the assessment and analysis of perceived and actual cyberattacks.</span></span>

<span data-ttu-id="f6fee-112">Киберфоренсические расследования часто используют штампы времени, чтобы собрать последовательность событий.</span><span class="sxs-lookup"><span data-stu-id="f6fee-112">Cyberforensic investigations often rely on time stamps to piece together the sequence of events.</span></span> <span data-ttu-id="f6fee-113">Важно, чтобы система отражала правильные параметры часовой пояс.</span><span class="sxs-lookup"><span data-stu-id="f6fee-113">It’s important that your system reflects the correct time zone settings.</span></span>

<span data-ttu-id="f6fee-114">Защитник Microsoft для конечной точки может отображать как скоординированное универсальное время (UTC), так и локальное время.</span><span class="sxs-lookup"><span data-stu-id="f6fee-114">Microsoft Defender for Endpoint can display either Coordinated Universal Time (UTC) or local time.</span></span>

<span data-ttu-id="f6fee-115">Текущий параметр часовой пояс отображается в меню Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="f6fee-115">Your current time zone setting is shown in the Microsoft Defender for Endpoint menu.</span></span> <span data-ttu-id="f6fee-116">Вы можете изменить отображаемую часовую зону в **меню часовой** зоны.</span><span class="sxs-lookup"><span data-stu-id="f6fee-116">You can change the displayed time zone in the **Time zone** menu.</span></span>

![Значок параметров часовой зоны2](images/atp-time-zone-menu.png)<span data-ttu-id="f6fee-118">.</span><span class="sxs-lookup"><span data-stu-id="f6fee-118">.</span></span>

### <a name="utc-time-zone"></a><span data-ttu-id="f6fee-119">Часовой пояс UTC</span><span class="sxs-lookup"><span data-stu-id="f6fee-119">UTC time zone</span></span>
<span data-ttu-id="f6fee-120">Microsoft Defender для конечной точки использует время UTC по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f6fee-120">Microsoft Defender for Endpoint uses UTC time by default.</span></span>

<span data-ttu-id="f6fee-121">Настройка часовой зоны Microsoft Defender для конечной точки для UTC отображает все системные периоды времени (оповещения, события и другие) в UTC для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="f6fee-121">Setting the Microsoft Defender for Endpoint time zone to UTC will display all system timestamps (alerts, events, and others) in UTC for all users.</span></span> <span data-ttu-id="f6fee-122">Это может помочь аналитикам безопасности, работающим в разных местах по всему миру, использовать одинаковые штампы времени при расследовании событий.</span><span class="sxs-lookup"><span data-stu-id="f6fee-122">This can help security analysts working in different locations across the globe to use the same time stamps while investigating events.</span></span>

### <a name="local-time-zone"></a><span data-ttu-id="f6fee-123">Локальный часовой пояс</span><span class="sxs-lookup"><span data-stu-id="f6fee-123">Local time zone</span></span>
<span data-ttu-id="f6fee-124">Вы можете выбрать, чтобы Microsoft Defender для конечной точки использовали локальные параметры часовой пояс.</span><span class="sxs-lookup"><span data-stu-id="f6fee-124">You can choose to have Microsoft Defender for Endpoint use local time zone settings.</span></span> <span data-ttu-id="f6fee-125">Все оповещения и события будут отображаться в локальном часовом поясе.</span><span class="sxs-lookup"><span data-stu-id="f6fee-125">All alerts and events will be displayed using your local time zone.</span></span>

<span data-ttu-id="f6fee-126">Локальный часовой пояс взят из региональных параметров устройства.</span><span class="sxs-lookup"><span data-stu-id="f6fee-126">The local time zone is taken from your device’s regional settings.</span></span> <span data-ttu-id="f6fee-127">При изменении региональных параметров также изменится часовой пояс Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="f6fee-127">If you change your regional settings, the Microsoft Defender for Endpoint time zone will also change.</span></span> <span data-ttu-id="f6fee-128">Выбор этого параметра означает, что периоды времени, отображаемые в Microsoft Defender для конечной точки, будут согласованы с локальным временем для всех пользователей Конечных точек Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="f6fee-128">Choosing this setting means that the timestamps displayed in Microsoft Defender for Endpoint will be aligned to local time for all Microsoft Defender for Endpoint users.</span></span> <span data-ttu-id="f6fee-129">Аналитики, расположенные в разных глобальных расположениях, теперь будут видеть оповещений Microsoft Defender для конечных точек в соответствии с их региональными настройками.</span><span class="sxs-lookup"><span data-stu-id="f6fee-129">Analysts located in different global locations will now see the Microsoft Defender for Endpoint alerts according to their regional settings.</span></span>

<span data-ttu-id="f6fee-130">Выбор использования местного времени может быть полезен, если аналитики находятся в одном расположении.</span><span class="sxs-lookup"><span data-stu-id="f6fee-130">Choosing to use local time can be useful if the analysts are located in a single location.</span></span> <span data-ttu-id="f6fee-131">В этом случае может быть проще соотнести события с локальным временем, например, когда локальный пользователь нажал на подозрительную ссылку электронной почты.</span><span class="sxs-lookup"><span data-stu-id="f6fee-131">In this case it might be easier to correlate events to local time, for example – when a local user clicked on a suspicious email link.</span></span>

### <a name="set-the-time-zone"></a><span data-ttu-id="f6fee-132">Установите часовой пояс</span><span class="sxs-lookup"><span data-stu-id="f6fee-132">Set the time zone</span></span>
<span data-ttu-id="f6fee-133">Часовой пояс Microsoft Defender для конечной точки по умолчанию устанавливается для UTC.</span><span class="sxs-lookup"><span data-stu-id="f6fee-133">The Microsoft Defender for Endpoint time zone is set by default to UTC.</span></span>
<span data-ttu-id="f6fee-134">Настройка часовой зоны также изменяет время для всех представлений Microsoft Defender для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="f6fee-134">Setting the time zone also changes the times for all Microsoft Defender for Endpoint views.</span></span>
<span data-ttu-id="f6fee-135">Чтобы установить часовой пояс:</span><span class="sxs-lookup"><span data-stu-id="f6fee-135">To set the time zone:</span></span>

1. <span data-ttu-id="f6fee-136">Щелкните **значок** параметров часовой зоны меню ![ Часовой зоны3. ](images/atp-time-zone.png)</span><span class="sxs-lookup"><span data-stu-id="f6fee-136">Click the **Time zone** menu ![Time zone settings icon3](images/atp-time-zone.png).</span></span>
2. <span data-ttu-id="f6fee-137">Выберите индикатор **UTC часовой зоны.**</span><span class="sxs-lookup"><span data-stu-id="f6fee-137">Select the **Timezone UTC** indicator.</span></span>
3. <span data-ttu-id="f6fee-138">Выберите **UTC часовой** пояс или локальный часовой пояс, например -7:00.</span><span class="sxs-lookup"><span data-stu-id="f6fee-138">Select **Timezone UTC** or your local time zone, for example -7:00.</span></span>

### <a name="regional-settings"></a><span data-ttu-id="f6fee-139">Региональные параметры</span><span class="sxs-lookup"><span data-stu-id="f6fee-139">Regional settings</span></span>
<span data-ttu-id="f6fee-140">Чтобы применить различные форматы дат для Microsoft Defender для конечной точки, используйте региональные параметры для Internet Explorer (IE) и Microsoft Edge (Edge).</span><span class="sxs-lookup"><span data-stu-id="f6fee-140">To apply different date formats for Microsoft Defender for Endpoint, use regional settings for Internet Explorer (IE) and Microsoft Edge (Edge).</span></span> <span data-ttu-id="f6fee-141">Если вы используете другой браузер, например Google Chrome, выполните необходимые действия, чтобы изменить параметры времени и даты для этого браузера.</span><span class="sxs-lookup"><span data-stu-id="f6fee-141">If you're using another browser such as Google Chrome, follow the required steps to change the time and date settings for that browser.</span></span> 


<span data-ttu-id="f6fee-142">**Internet Explorer (IE) и Microsoft Edge**</span><span class="sxs-lookup"><span data-stu-id="f6fee-142">**Internet Explorer (IE) and Microsoft Edge**</span></span>

<span data-ttu-id="f6fee-143">IE и Microsoft Edge параметры **Region,** настроенные в параметре **"Часы",** "Язык" и "Область" в панели управления.</span><span class="sxs-lookup"><span data-stu-id="f6fee-143">IE and Microsoft Edge use the **Region** settings configured in the **Clocks, Language, and Region** option in the Control panel.</span></span> 


#### <a name="known-issues-with-regional-formats"></a><span data-ttu-id="f6fee-144">Известные проблемы с региональными форматами</span><span class="sxs-lookup"><span data-stu-id="f6fee-144">Known issues with regional formats</span></span>

<span data-ttu-id="f6fee-145">**Форматы даты и времени**</span><span class="sxs-lookup"><span data-stu-id="f6fee-145">**Date and time formats**</span></span><br>
<span data-ttu-id="f6fee-146">Известны некоторые проблемы с форматами времени и даты.</span><span class="sxs-lookup"><span data-stu-id="f6fee-146">There are some known issues with the time and date formats.</span></span> <span data-ttu-id="f6fee-147">Если настроить региональные параметры на что-либо, кроме поддерживаемых форматов, портал может неправильно отражать ваши параметры.</span><span class="sxs-lookup"><span data-stu-id="f6fee-147">If you configure your regional settings to anything other than the supported formats, the portal may not correctly reflect your settings.</span></span>

<span data-ttu-id="f6fee-148">Поддерживаются следующие форматы даты и времени:</span><span class="sxs-lookup"><span data-stu-id="f6fee-148">The following date and time formats are supported:</span></span>
- <span data-ttu-id="f6fee-149">Формат даты MM/dd/yyyy</span><span class="sxs-lookup"><span data-stu-id="f6fee-149">Date format MM/dd/yyyy</span></span>
- <span data-ttu-id="f6fee-150">Формат даты dd/MM/yyyy</span><span class="sxs-lookup"><span data-stu-id="f6fee-150">Date format dd/MM/yyyy</span></span>
- <span data-ttu-id="f6fee-151">Формат времени hh:mm:ss (12-часовой формат)</span><span class="sxs-lookup"><span data-stu-id="f6fee-151">Time format hh:mm:ss (12 hour format)</span></span>

<span data-ttu-id="f6fee-152">В настоящее время не поддерживаются следующие форматы даты и времени:</span><span class="sxs-lookup"><span data-stu-id="f6fee-152">The following date and time formats are currently not supported:</span></span>
- <span data-ttu-id="f6fee-153">Формат yyyy-MM-dd</span><span class="sxs-lookup"><span data-stu-id="f6fee-153">Date format yyyy-MM-dd</span></span>
- <span data-ttu-id="f6fee-154">Формат даты dd-MMM-yy</span><span class="sxs-lookup"><span data-stu-id="f6fee-154">Date format dd-MMM-yy</span></span>
- <span data-ttu-id="f6fee-155">Формат даты dd/MM/yyy</span><span class="sxs-lookup"><span data-stu-id="f6fee-155">Date format dd/MM/yy</span></span>
- <span data-ttu-id="f6fee-156">Формат даты MM/dd/yyy</span><span class="sxs-lookup"><span data-stu-id="f6fee-156">Date format MM/dd/yy</span></span>
- <span data-ttu-id="f6fee-157">Формат даты с yy.</span><span class="sxs-lookup"><span data-stu-id="f6fee-157">Date format with yy.</span></span> <span data-ttu-id="f6fee-158">Будет показываться только yyyy.</span><span class="sxs-lookup"><span data-stu-id="f6fee-158">Will only show yyyy.</span></span>
- <span data-ttu-id="f6fee-159">Формат времени HH:mm:ss (24-часовой формат)</span><span class="sxs-lookup"><span data-stu-id="f6fee-159">Time format HH:mm:ss (24 hour format)</span></span>

<span data-ttu-id="f6fee-160">**Десятичной символ, используемый в числах**</span><span class="sxs-lookup"><span data-stu-id="f6fee-160">**Decimal symbol used in numbers**</span></span><br>
<span data-ttu-id="f6fee-161">Используемый десятичный символ всегда является точкой, даже если запятая выбрана в параметрах **формата Numbers** в **параметрах Region.**</span><span class="sxs-lookup"><span data-stu-id="f6fee-161">Decimal symbol used is always a dot, even if a comma is selected in  the **Numbers** format settings in **Region** settings.</span></span> <span data-ttu-id="f6fee-162">Например, 15,5K отображается как 15,5K.</span><span class="sxs-lookup"><span data-stu-id="f6fee-162">For example, 15,5K is displayed as 15.5K.</span></span>


