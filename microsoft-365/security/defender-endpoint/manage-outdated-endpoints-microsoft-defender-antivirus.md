---
title: Применение обновлений av-защиты Защитника Майкрософт к конечным точкам устарели
description: Определите, когда и как следует применять обновления для конечных точек, которые не обновлялись некоторое время.
keywords: обновления, защита, устаревшие, устаревшие, старые, догонять
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 4199f55488ef0dc5989af88e8be83a3d51190d1f
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275064"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-scans-for-endpoints-that-are-out-of-date"></a><span data-ttu-id="6922a-104">Управление обновлениями и проверками устаревших конечных точек антивирусной программы в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6922a-104">Manage Microsoft Defender Antivirus updates and scans for endpoints that are out of date</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="6922a-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="6922a-105">**Applies to:**</span></span>

- [<span data-ttu-id="6922a-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="6922a-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="6922a-107">антивирусная программа в Microsoft Defender позволяет определить, как долго конечная точка может избежать обновления или сколько сканов она может пропустить, прежде чем потребуется обновить и сканировать себя.</span><span class="sxs-lookup"><span data-stu-id="6922a-107">Microsoft Defender Antivirus lets you define how long an endpoint can avoid an update or how many scans it can miss before it is required to update and scan itself.</span></span> <span data-ttu-id="6922a-108">Это особенно полезно в средах, где устройства не часто подключены к корпоративной или внешней сети, или устройства, которые не используются ежедневно.</span><span class="sxs-lookup"><span data-stu-id="6922a-108">This is especially useful in environments where devices are not often connected to a corporate or external network, or devices that are not used on a daily basis.</span></span>

<span data-ttu-id="6922a-109">Например, сотрудник, использующий определенный компьютер, находится в перерыве в течение трех дней и не входит на свой компьютер в течение этого времени.</span><span class="sxs-lookup"><span data-stu-id="6922a-109">For example, an employee that uses a particular PC is on break for three days and does not log on to their PC during that time.</span></span>

<span data-ttu-id="6922a-110">Когда пользователь возвращается к работе и войдет на свой компьютер, антивирусная программа в Microsoft Defender немедленно проверит и загрузит последние обновления защиты и запустит сканирование.</span><span class="sxs-lookup"><span data-stu-id="6922a-110">When the user returns to work and logs on to their PC, Microsoft Defender Antivirus will immediately check and download the latest protection updates, and run a scan.</span></span>

## <a name="set-up-catch-up-protection-updates-for-endpoints-that-havent-updated-for-a-while"></a><span data-ttu-id="6922a-111">Настройка обновлений защиты для конечных точек, которые не обновлялись некоторое время</span><span class="sxs-lookup"><span data-stu-id="6922a-111">Set up catch-up protection updates for endpoints that haven't updated for a while</span></span>

<span data-ttu-id="6922a-112">Если антивирусная программа в Microsoft Defender не скачали обновления защиты за указанный период, вы можете настроить его для автоматической проверки и скачивания последнего обновления в следующем журнале.</span><span class="sxs-lookup"><span data-stu-id="6922a-112">If Microsoft Defender Antivirus did not download protection updates for a specified period, you can set it up to automatically check and download the latest update at the next log on.</span></span> <span data-ttu-id="6922a-113">Это полезно, если во всем мире отключены автоматические загрузки обновлений [при запуске.](manage-event-based-updates-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="6922a-113">This is useful if you have [globally disabled automatic update downloads on startup](manage-event-based-updates-microsoft-defender-antivirus.md).</span></span>

### <a name="use-configuration-manager-to-configure-catch-up-protection-updates"></a><span data-ttu-id="6922a-114">Использование Диспетчер конфигурации для настройки обновлений защиты догонять</span><span class="sxs-lookup"><span data-stu-id="6922a-114">Use Configuration Manager to configure catch-up protection updates</span></span>

1.  <span data-ttu-id="6922a-115">На консоли Microsoft Endpoint Manager откройте политику противомалярийных программ,  которые необходимо изменить (щелкните Активы и соответствие требованиям в области навигации слева, а затем разогнайте дерево до Endpoint Protection  >    >  **antimalware Policies**)</span><span class="sxs-lookup"><span data-stu-id="6922a-115">On your Microsoft Endpoint Manager console, open the antimalware policy you want to change (click **Assets and Compliance** in the navigation pane on the left, then expand the tree to **Overview** > **Endpoint Protection** > **Antimalware Policies**)</span></span>

2.  <span data-ttu-id="6922a-116">Перейдите в **раздел Обновления** сведении безопасности и настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="6922a-116">Go to the **Security intelligence updates** section and configure the following settings:</span></span>

    1. <span data-ttu-id="6922a-117">Установите **force a security intelligence update if the client computer is offline for more than two consecutive scheduled updates** to **Yes**.</span><span class="sxs-lookup"><span data-stu-id="6922a-117">Set **Force a security intelligence update if the client computer is offline for more than two consecutive scheduled updates** to **Yes**.</span></span>
    2. <span data-ttu-id="6922a-118">Для  **if Configuration Manager** используется в качестве источника обновления сведении о безопасности... Укажите часы, до которых обновления защиты, доставленные диспетчером конфигурации, должны считаться устарели.</span><span class="sxs-lookup"><span data-stu-id="6922a-118">For the  **If Configuration Manager is used as a source for security intelligence updates...**, specify the hours before which the protection updates delivered by Configuration Manager should be considered out-of-date.</span></span> <span data-ttu-id="6922a-119">Это приведет к следующему расположению обновления, основанному на определенном порядке источника [отката.](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)</span><span class="sxs-lookup"><span data-stu-id="6922a-119">This will cause the next update location to be used, based on the defined [fallback source order](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order).</span></span>

3. <span data-ttu-id="6922a-120">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6922a-120">Click **OK**.</span></span>

4.  <span data-ttu-id="6922a-121">[Развертывание обновленной политики в обычном режиме.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)</span><span class="sxs-lookup"><span data-stu-id="6922a-121">[Deploy the updated policy as usual](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span></span>

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-update-feature"></a><span data-ttu-id="6922a-122">Используйте групповую политику, чтобы включить и настроить функцию догонять обновление</span><span class="sxs-lookup"><span data-stu-id="6922a-122">Use Group Policy to enable and configure the catch-up update feature</span></span>

1. <span data-ttu-id="6922a-123">На компьютере управления групповой политикой откройте консоль управления групповой политикой [,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))щелкните правой кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.</span><span class="sxs-lookup"><span data-stu-id="6922a-123">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="6922a-124">В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера.**</span><span class="sxs-lookup"><span data-stu-id="6922a-124">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="6922a-125">Щелкните **Политики,** а **затем административные шаблоны**.</span><span class="sxs-lookup"><span data-stu-id="6922a-125">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="6922a-126">Расширь **дерево до Windows компонентов > антивирусная программа в Microsoft Defender > обновлений подписи.**</span><span class="sxs-lookup"><span data-stu-id="6922a-126">Expand the tree to **Windows components > Microsoft Defender Antivirus > Signature Updates**.</span></span>

5. <span data-ttu-id="6922a-127">Дважды щелкните **определение** числа дней, после которых требуется настройка догонять обновление сведении о безопасности, и установите параметр **Включено**.</span><span class="sxs-lookup"><span data-stu-id="6922a-127">Double-click the **Define the number of days after which a catch-up security intelligence update is required** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="6922a-128">Введите количество дней, после которых вы хотите, чтобы microsoft Defender AV проверил и скачал последнее обновление защиты.</span><span class="sxs-lookup"><span data-stu-id="6922a-128">Enter the number of days after which you want Microsoft Defender AV to check for and download the latest protection update.</span></span>

6. <span data-ttu-id="6922a-129">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6922a-129">Click **OK**.</span></span>

### <a name="use-powershell-cmdlets-to-configure-catch-up-protection-updates"></a><span data-ttu-id="6922a-130">Используйте cmdlets PowerShell для настройки обновлений защиты наверстать упущенное</span><span class="sxs-lookup"><span data-stu-id="6922a-130">Use PowerShell cmdlets to configure catch-up protection updates</span></span>

<span data-ttu-id="6922a-131">Используйте следующие cmdlets:</span><span class="sxs-lookup"><span data-stu-id="6922a-131">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -SignatureUpdateCatchupInterval
```

<span data-ttu-id="6922a-132">Дополнительные сведения о том, как использовать [PowerS антивирусная программа в Microsoft Defender hell](use-powershell-cmdlets-microsoft-defender-antivirus.md) с антивирусная программа в Microsoft Defender и [Defender,](/powershell/module/defender/) см. в этой ссылке.</span><span class="sxs-lookup"><span data-stu-id="6922a-132">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)  and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-protection-updates"></a><span data-ttu-id="6922a-133">Используйте Windows управления (WMI) для настройки догонять обновления защиты</span><span class="sxs-lookup"><span data-stu-id="6922a-133">Use Windows Management Instruction (WMI) to configure catch-up protection updates</span></span>

<span data-ttu-id="6922a-134">Используйте метод [ **Set** класса **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) для следующих свойств:</span><span class="sxs-lookup"><span data-stu-id="6922a-134">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
SignatureUpdateCatchupInterval
```

<span data-ttu-id="6922a-135">Дополнительные сведения и допустимые параметры см. в следующих сведениях:</span><span class="sxs-lookup"><span data-stu-id="6922a-135">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="6922a-136">Защитник Windows API WMIv2</span><span class="sxs-lookup"><span data-stu-id="6922a-136">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="set-the-number-of-days-before-protection-is-reported-as-out-of-date"></a><span data-ttu-id="6922a-137">Установите количество дней до того, как защита будет отчитаться о том, что она устарела</span><span class="sxs-lookup"><span data-stu-id="6922a-137">Set the number of days before protection is reported as out-of-date</span></span>

<span data-ttu-id="6922a-138">Можно также указать количество дней, после которых антивирусная программа в Microsoft Defender считается старой или устарелой.</span><span class="sxs-lookup"><span data-stu-id="6922a-138">You can also specify the number of days after which Microsoft Defender Antivirus protection is considered old or out-of-date.</span></span> <span data-ttu-id="6922a-139">После указанного числа дней клиент будет сообщать о себе как о устарелом состоянии и показывать ошибку пользователю компьютера.</span><span class="sxs-lookup"><span data-stu-id="6922a-139">After the specified number of days, the client will report itself as out-of-date, and show an error to the user of the PC.</span></span> <span data-ttu-id="6922a-140">Кроме того, антивирусная программа в Microsoft Defender может привести к попытке скачивания обновления из [](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)других источников (на основе определенного порядка источника отката), например при использовании MMPC в качестве дополнительного источника после установки WSUS или Microsoft Update в качестве первого источника.</span><span class="sxs-lookup"><span data-stu-id="6922a-140">It may also cause Microsoft Defender Antivirus to attempt to download an update from other sources (based on the defined [fallback source order](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)), such as when using MMPC as a secondary source after setting WSUS or Microsoft Update as the first source.</span></span>

### <a name="use-group-policy-to-specify-the-number-of-days-before-protection-is-considered-out-of-date"></a><span data-ttu-id="6922a-141">Используйте групповую политику, чтобы указать количество дней до того, как защита будет считаться устарелой</span><span class="sxs-lookup"><span data-stu-id="6922a-141">Use Group Policy to specify the number of days before protection is considered out-of-date</span></span>

1.  <span data-ttu-id="6922a-142">На компьютере управления групповой политикой откройте консоль управления групповой политикой [правой](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.</span><span class="sxs-lookup"><span data-stu-id="6922a-142">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="6922a-143">В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера.**</span><span class="sxs-lookup"><span data-stu-id="6922a-143">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="6922a-144">Щелкните **Политики,** а **затем административные шаблоны**.</span><span class="sxs-lookup"><span data-stu-id="6922a-144">Click **Policies** then **Administrative templates**.</span></span>

5.  <span data-ttu-id="6922a-145">Расширив **дерево, Windows компоненты** > антивирусная программа в Microsoft Defender > обновления подписи и настроив следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="6922a-145">Expand the tree to **Windows components > Microsoft Defender Antivirus > Signature Updates** and configure the following settings:</span></span>

    1.  <span data-ttu-id="6922a-146">Дважды **щелкните Определить количество** дней до того, как определения программ-шпионов будут считаться устарели, и установите параметр **Включен**.</span><span class="sxs-lookup"><span data-stu-id="6922a-146">Double-click **Define the number of days before spyware definitions are considered out of date** and set the option to **Enabled**.</span></span> <span data-ttu-id="6922a-147">Введите количество дней, после которых microsoft Defender AV считает данные службы безопасности шпионских программ устарели.</span><span class="sxs-lookup"><span data-stu-id="6922a-147">Enter the number of days after which you want Microsoft Defender AV to consider spyware Security intelligence to be out-of-date.</span></span>

    2. <span data-ttu-id="6922a-148">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6922a-148">Click **OK**.</span></span>

    3.  <span data-ttu-id="6922a-149">Дважды **щелкните Определить количество дней до** того, как определения вирусов будут считаться устарели, и установите параметр **Включено**.</span><span class="sxs-lookup"><span data-stu-id="6922a-149">Double-click **Define the number of days before virus definitions are considered out of date** and set the option to **Enabled**.</span></span> <span data-ttu-id="6922a-150">Введите количество дней, после которых microsoft Defender AV считает данные службы безопасности вирусов устарели.</span><span class="sxs-lookup"><span data-stu-id="6922a-150">Enter the number of days after which you want Microsoft Defender AV to consider virus Security intelligence to be out-of-date.</span></span>

    4. <span data-ttu-id="6922a-151">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6922a-151">Click **OK**.</span></span>


## <a name="set-up-catch-up-scans-for-endpoints-that-have-not-been-scanned-for-a-while"></a><span data-ttu-id="6922a-152">Настройка доголовных сканов для конечных точек, которые не были сканированы некоторое время</span><span class="sxs-lookup"><span data-stu-id="6922a-152">Set up catch-up scans for endpoints that have not been scanned for a while</span></span>

<span data-ttu-id="6922a-153">Вы можете установить количество последовательных запланированных сканов, которые можно пропустить до антивирусная программа в Microsoft Defender будет принудительное сканирование.</span><span class="sxs-lookup"><span data-stu-id="6922a-153">You can set the number of consecutive scheduled scans that can be missed before Microsoft Defender Antivirus will force a scan.</span></span>

<span data-ttu-id="6922a-154">Процесс включения этой функции:</span><span class="sxs-lookup"><span data-stu-id="6922a-154">The process for enabling this feature is:</span></span>

1. <span data-ttu-id="6922a-155">Настройка по крайней мере одного запланированного сканирования (см. раздел [Проверка расписания).](scheduled-catch-up-scans-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="6922a-155">Set up at least one scheduled scan (see the [Schedule scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) topic).</span></span>
2. <span data-ttu-id="6922a-156">Включить функцию догонять сканирование.</span><span class="sxs-lookup"><span data-stu-id="6922a-156">Enable the catch-up scan feature.</span></span>
3. <span data-ttu-id="6922a-157">Определите количество сканов, которые можно пропустить до начала проверки.</span><span class="sxs-lookup"><span data-stu-id="6922a-157">Define the number of scans that can be skipped before a catch-up scan occurs.</span></span>

<span data-ttu-id="6922a-158">Эта функция может быть включена как для полного, так и для быстрого сканирования.</span><span class="sxs-lookup"><span data-stu-id="6922a-158">This feature can be enabled for both full and quick scans.</span></span>

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-scan-feature"></a><span data-ttu-id="6922a-159">Использование групповой политики, чтобы включить и настроить функцию догонять сканирование</span><span class="sxs-lookup"><span data-stu-id="6922a-159">Use Group Policy to enable and configure the catch-up scan feature</span></span>

1.  <span data-ttu-id="6922a-160">Убедитесь, что вы настроили хотя бы одно запланированное сканирование.</span><span class="sxs-lookup"><span data-stu-id="6922a-160">Ensure you have set up at least one scheduled scan.</span></span>

2.  <span data-ttu-id="6922a-161">На компьютере управления групповой политикой откройте консоль управления групповой политикой [правой](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.</span><span class="sxs-lookup"><span data-stu-id="6922a-161">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="6922a-162">В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера.**</span><span class="sxs-lookup"><span data-stu-id="6922a-162">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="6922a-163">Щелкните **Политики,** а **затем административные шаблоны**.</span><span class="sxs-lookup"><span data-stu-id="6922a-163">Click **Policies** then **Administrative templates**.</span></span>

5.  <span data-ttu-id="6922a-164">Расширив **дерево, Windows компоненты > антивирусная программа в Microsoft Defender > сканировать** и настроить следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="6922a-164">Expand the tree to **Windows components > Microsoft Defender Antivirus > Scan** and configure the following settings:</span></span>

    1.  <span data-ttu-id="6922a-165">Если вы настроили запланированные быстрые проверки, дважды нажмите кнопку Включить параметр быстрого сканирования и установите параметр **Включено**. </span><span class="sxs-lookup"><span data-stu-id="6922a-165">If you have set up scheduled quick scans, double-click the **Turn on catch-up quick scan** setting and set the option to **Enabled**.</span></span> 
    2. <span data-ttu-id="6922a-166">Если вы настроили запланированные полные проверки, дважды щелкните параметр **Turn on catch-up full scan** и установите параметр **Включено**.</span><span class="sxs-lookup"><span data-stu-id="6922a-166">If you have set up scheduled full scans, double-click the **Turn on catch-up full scan** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="6922a-167">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6922a-167">Click **OK**.</span></span>
    3. <span data-ttu-id="6922a-168">Дважды щелкните **кнопку Определить количество** дней, после которых принудительный параметр проверки наверстать упущенное, и установите параметр **Включено.**</span><span class="sxs-lookup"><span data-stu-id="6922a-168">Double-click the **Define the number of days after which a catch-up scan is forced** setting and set the option to **Enabled**.</span></span> 
    4. <span data-ttu-id="6922a-169">Введите число сканов, которые можно пропустить перед автоматическим запуском сканирования при следующем входе пользователя на компьютер.</span><span class="sxs-lookup"><span data-stu-id="6922a-169">Enter the number of scans that can be missed before a scan will be automatically run when the user next logs on to the PC.</span></span> <span data-ttu-id="6922a-170">Тип сканирования, который будет запускаться, определяется типом проверки, который необходимо использовать для запланированного сканирования **(см.** раздел Расписание [сканирования).](scheduled-catch-up-scans-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="6922a-170">The type of scan that is run is determined by the **Specify the scan type to use for a scheduled scan** (see the [Schedule scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) topic).</span></span> <span data-ttu-id="6922a-171">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6922a-171">Click **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="6922a-172">Заголовок параметра групповой политики относится к числу дней.</span><span class="sxs-lookup"><span data-stu-id="6922a-172">The Group Policy setting title refers to the number of days.</span></span> <span data-ttu-id="6922a-173">Однако этот параметр применяется к числу сканов (не дней) перед запуском догонять.</span><span class="sxs-lookup"><span data-stu-id="6922a-173">The setting, however, is applied to the number of scans (not days) before the catch-up scan will be run.</span></span>

### <a name="use-powershell-cmdlets-to-configure-catch-up-scans"></a><span data-ttu-id="6922a-174">Для настройки догоняемых сканов используйте cmdlets PowerShell</span><span class="sxs-lookup"><span data-stu-id="6922a-174">Use PowerShell cmdlets to configure catch-up scans</span></span>

<span data-ttu-id="6922a-175">Используйте следующие cmdlets:</span><span class="sxs-lookup"><span data-stu-id="6922a-175">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -DisableCatchupFullScan
Set-MpPreference -DisableCatchupQuickScan

```

<span data-ttu-id="6922a-176">Дополнительные сведения о том, как использовать [PowerS антивирусная программа в Microsoft Defender hell](use-powershell-cmdlets-microsoft-defender-antivirus.md) с антивирусная программа в Microsoft Defender и [Defender,](/powershell/module/defender/) см. в этой ссылке.</span><span class="sxs-lookup"><span data-stu-id="6922a-176">See [Use PowerShell cmdlets to manage Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)  and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-scans"></a><span data-ttu-id="6922a-177">Используйте Windows управления (WMI) для настройки доголовных сканов</span><span class="sxs-lookup"><span data-stu-id="6922a-177">Use Windows Management Instruction (WMI) to configure catch-up scans</span></span>

<span data-ttu-id="6922a-178">Используйте метод [ **Set** класса **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) для следующих свойств:</span><span class="sxs-lookup"><span data-stu-id="6922a-178">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
DisableCatchupFullScan
DisableCatchupQuickScan
```

<span data-ttu-id="6922a-179">Дополнительные сведения и допустимые параметры см. в следующих сведениях:</span><span class="sxs-lookup"><span data-stu-id="6922a-179">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="6922a-180">Защитник Windows API WMIv2</span><span class="sxs-lookup"><span data-stu-id="6922a-180">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


### <a name="use-configuration-manager-to-configure-catch-up-scans"></a><span data-ttu-id="6922a-181">Настройка доголовных сканов с помощью диспетчера конфигурации</span><span class="sxs-lookup"><span data-stu-id="6922a-181">Use Configuration Manager to configure catch-up scans</span></span>

1.  <span data-ttu-id="6922a-182">На консоли Microsoft Endpoint Manager откройте политику противомалярийных программ,  которые необходимо изменить (щелкните Активы и соответствие требованиям в области навигации слева, а затем разогнайте дерево до Endpoint Protection  >    >  **antimalware Policies**)</span><span class="sxs-lookup"><span data-stu-id="6922a-182">On your Microsoft Endpoint Manager console, open the antimalware policy you want to change (click **Assets and Compliance** in the navigation pane on the left, then expand the tree to **Overview** > **Endpoint Protection** > **Antimalware Policies**)</span></span>

2.  <span data-ttu-id="6922a-183">Перейдите в раздел **Запланированные** проверки и привяжье сканирование выбранного типа сканирования, если клиентский компьютер находится в автономном **режиме...**</span><span class="sxs-lookup"><span data-stu-id="6922a-183">Go to the **Scheduled scans** section and **Force a scan of the selected scan type if client computer is offline...** to **Yes**.</span></span> 

3. <span data-ttu-id="6922a-184">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6922a-184">Click **OK**.</span></span>

4.  <span data-ttu-id="6922a-185">[Развертывание обновленной политики в обычном режиме.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)</span><span class="sxs-lookup"><span data-stu-id="6922a-185">[Deploy the updated policy as usual](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span></span>

## <a name="related-articles"></a><span data-ttu-id="6922a-186">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="6922a-186">Related articles</span></span>

- [<span data-ttu-id="6922a-187">Развертывание антивирусная программа в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6922a-187">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="6922a-188">Управление антивирусная программа в Microsoft Defender обновлениями и применение базовых показателей</span><span class="sxs-lookup"><span data-stu-id="6922a-188">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="6922a-189">Управление загрузкой и приложением обновлений защиты</span><span class="sxs-lookup"><span data-stu-id="6922a-189">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [<span data-ttu-id="6922a-190">Управление принудительными обновлениями на основе событий</span><span class="sxs-lookup"><span data-stu-id="6922a-190">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md)
- [<span data-ttu-id="6922a-191">Управление обновлениями для мобильных устройств и виртуальных машин (ВМ)</span><span class="sxs-lookup"><span data-stu-id="6922a-191">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [<span data-ttu-id="6922a-192">Антивирусная программа в Microsoft Defender (Windows 10)</span><span class="sxs-lookup"><span data-stu-id="6922a-192">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)