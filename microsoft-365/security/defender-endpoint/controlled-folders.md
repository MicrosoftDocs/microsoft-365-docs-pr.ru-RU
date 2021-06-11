---
title: Защита важных папок от программ-вымогателей от шифрования файлов с помощью управляемого доступа к папкам
description: Файлы в папках по умолчанию могут быть защищены от изменения вредоносными приложениями. Предотвращение шифрования файлов программ-вымогателей.
keywords: управляемый доступ к папкам, Windows 10, защитник Windows, вымогатели, защита, файлы, папки
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
audience: ITPro
ms.date: 06/10/2021
ms.reviewer: v-maave
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: c60620d2a589c8473764b810d1fcb0e24f674451
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904060"
---
# <a name="protect-important-folders-with-controlled-folder-access"></a><span data-ttu-id="6348b-105">Защита важных папок с управляемым доступом к папкам</span><span class="sxs-lookup"><span data-stu-id="6348b-105">Protect important folders with controlled folder access</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6348b-106">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="6348b-106">**Applies to:**</span></span>
- [<span data-ttu-id="6348b-107">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="6348b-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6348b-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6348b-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="6348b-109">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="6348b-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6348b-110">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="6348b-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-controlled-folder-access"></a><span data-ttu-id="6348b-111">Что такое управляемый доступ к папкам?</span><span class="sxs-lookup"><span data-stu-id="6348b-111">What is controlled folder access?</span></span>

<span data-ttu-id="6348b-112">Управляемый доступ к папкам помогает защитить ценные данные от вредоносных приложений и угроз, таких как вымогателей.</span><span class="sxs-lookup"><span data-stu-id="6348b-112">Controlled folder access helps protect your valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="6348b-113">Управляемый доступ к папкам защищает данные, проверяя приложения со списком известных надежных приложений.</span><span class="sxs-lookup"><span data-stu-id="6348b-113">Controlled folder access protects your data by checking apps against a list of known, trusted apps.</span></span> <span data-ttu-id="6348b-114">Поддерживаемый Windows Server 2019 и Windows 10 клиенты, управляемый доступ к папкам можно включить с помощью Безопасность Windows App, Microsoft Endpoint Configuration Manager или Intune (для управляемых устройств).</span><span class="sxs-lookup"><span data-stu-id="6348b-114">Supported on Windows Server 2019 and Windows 10 clients, controlled folder access can be turned on using the Windows Security App, Microsoft Endpoint Configuration Manager, or Intune (for managed devices).</span></span> 

> [!NOTE]
> <span data-ttu-id="6348b-115">Скрипты не доверяются, и вы не можете разрешить им доступ к управляемым защищенным папок.</span><span class="sxs-lookup"><span data-stu-id="6348b-115">Scripting engines are not trusted and you cannot allow them access to controlled protected folders.</span></span>  <span data-ttu-id="6348b-116">Например, PowerShell не доверяется управляемым доступом к папкам, даже если вы позволяете с индикаторами сертификата [и файла](/microsoft-365/security/defender-endpoint/indicator-certificates).</span><span class="sxs-lookup"><span data-stu-id="6348b-116">For example, PowerShell is not trusted by controlled folder access, even if you allow with [certificate and file indicators](/microsoft-365/security/defender-endpoint/indicator-certificates).</span></span> 

<span data-ttu-id="6348b-117">Управляемый доступ к папкам лучше всего работает с [Microsoft Defender для конечной](microsoft-defender-endpoint.md)точки, что позволяет подробно сообщать о событиях и блоках управляемого доступа к папкам в рамках обычных сценариев расследования оповещений. [](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="6348b-117">Controlled folder access works best with [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md), which gives you detailed reporting into controlled folder access events and blocks as part of the usual [alert investigation scenarios](investigate-alerts.md).</span></span>

> [!TIP]
> <span data-ttu-id="6348b-118">Блоки доступа к управляемым папкам не создают оповещений в [очереди Оповещения.](alerts-queue.md)</span><span class="sxs-lookup"><span data-stu-id="6348b-118">Controlled folder access blocks don't generate alerts in the [Alerts queue](alerts-queue.md).</span></span> <span data-ttu-id="6348b-119">Тем не менее, вы можете просматривать сведения о блоках доступа к контролируемым папкам в представлении временной шкалы [устройства,](investigate-machines.md)при использовании расширенных методов охоты [или](advanced-hunting-overview.md)с пользовательскими [правилами обнаружения.](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="6348b-119">However, you can view information about controlled folder access blocks in the [device timeline view](investigate-machines.md), while using [advanced hunting](advanced-hunting-overview.md), or with [custom detection rules](custom-detection-rules.md).</span></span>

## <a name="how-does-controlled-folder-access-work"></a><span data-ttu-id="6348b-120">Как работает управляемый доступ к папкам?</span><span class="sxs-lookup"><span data-stu-id="6348b-120">How does controlled folder access work?</span></span>

<span data-ttu-id="6348b-121">Управляемый доступ к папкам работает, только позволяя доверенным приложениям получать доступ к защищенным папкам.</span><span class="sxs-lookup"><span data-stu-id="6348b-121">Controlled folder access works by only allowing trusted apps to access protected folders.</span></span> <span data-ttu-id="6348b-122">Защищенные папки заданы при настройке управляемого доступа к папкам.</span><span class="sxs-lookup"><span data-stu-id="6348b-122">Protected folders are specified when controlled folder access is configured.</span></span> <span data-ttu-id="6348b-123">Как правило, обычно используемые папки, например используемые для документов, фотографий, скачиваний и т. д., включаются в список управляемых папок.</span><span class="sxs-lookup"><span data-stu-id="6348b-123">Typically, commonly used folders, such as those used for documents, pictures, downloads, and so on, are included in the list of controlled folders.</span></span> 

<span data-ttu-id="6348b-124">Управляемый доступ к папкам работает со списком доверенных приложений.</span><span class="sxs-lookup"><span data-stu-id="6348b-124">Controlled folder access works with a list of trusted apps.</span></span> <span data-ttu-id="6348b-125">Приложения, включенные в список доверенных программных продуктов, работают, как и ожидалось.</span><span class="sxs-lookup"><span data-stu-id="6348b-125">Apps that are included in the list of trusted software work as expected.</span></span> <span data-ttu-id="6348b-126">Приложения, не включенные в список, не могут вносить изменения в файлы в защищенных папках.</span><span class="sxs-lookup"><span data-stu-id="6348b-126">Apps that are not included in the list are prevented from making any changes to files inside protected folders.</span></span> 

<span data-ttu-id="6348b-127">Приложения добавляются в список в зависимости от их распространенности и репутации.</span><span class="sxs-lookup"><span data-stu-id="6348b-127">Apps are added to the list based upon their prevalence and reputation.</span></span> <span data-ttu-id="6348b-128">Приложения, которые широко распространены в вашей организации и никогда не отображали никаких действий, которые считаются вредоносными, считаются заслуживающими доверия.</span><span class="sxs-lookup"><span data-stu-id="6348b-128">Apps that are highly prevalent throughout your organization and that have never displayed any behavior deemed malicious are considered trustworthy.</span></span> <span data-ttu-id="6348b-129">Эти приложения добавляются в список автоматически.</span><span class="sxs-lookup"><span data-stu-id="6348b-129">Those apps are added to the list automatically.</span></span>

<span data-ttu-id="6348b-130">Приложения также можно добавлять вручную в доверенный список с помощью Configuration Manager или Intune.</span><span class="sxs-lookup"><span data-stu-id="6348b-130">Apps can also be added manually to the trusted list by using Configuration Manager or Intune.</span></span> <span data-ttu-id="6348b-131">Дополнительные действия, например добавление [индикатора](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file) файла для приложения, можно выполнить из консоли Центра безопасности.</span><span class="sxs-lookup"><span data-stu-id="6348b-131">Additional actions, such as [adding a file indicator](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file) for an app, can be performed from the Security Center Console.</span></span>

## <a name="why-controlled-folder-access-is-important"></a><span data-ttu-id="6348b-132">Почему важен управляемый доступ к папкам</span><span class="sxs-lookup"><span data-stu-id="6348b-132">Why controlled folder access is important</span></span>

<span data-ttu-id="6348b-133">Управляемый доступ к папкам особенно полезен для защиты документов и сведений от [программ-вымогателей.](https://www.microsoft.com/wdsi/threats/ransomware)</span><span class="sxs-lookup"><span data-stu-id="6348b-133">Controlled folder access is especially useful in helping to protect your documents and information from [ransomware](https://www.microsoft.com/wdsi/threats/ransomware).</span></span> <span data-ttu-id="6348b-134">При атаке вымогателей ваши файлы могут быть зашифрованы и взяты в заложники.</span><span class="sxs-lookup"><span data-stu-id="6348b-134">In a ransomware attack, your files can get encrypted and held hostage.</span></span> <span data-ttu-id="6348b-135">С управляемым доступом к папке на компьютере появляется уведомление, в котором приложение пыталось внести изменения в файл в защищенной папке.</span><span class="sxs-lookup"><span data-stu-id="6348b-135">With controlled folder access in place, a notification appears on the computer where an app attempted to make changes to a file in a protected folder.</span></span> <span data-ttu-id="6348b-136">Вы можете [настроить уведомление](customize-attack-surface-reduction.md#customize-the-notification), указав сведения о вашей организации и контактные данные.</span><span class="sxs-lookup"><span data-stu-id="6348b-136">You can [customize the notification](customize-attack-surface-reduction.md#customize-the-notification) with your company details and contact information.</span></span> <span data-ttu-id="6348b-137">Вы также можете включить правила по отдельности, чтобы настроить, какие методы отслеживает функция.</span><span class="sxs-lookup"><span data-stu-id="6348b-137">You can also enable the rules individually to customize what techniques the feature monitors.</span></span>

<span data-ttu-id="6348b-138">Защищенные [папки включают общие](#review-controlled-folder-access-events-in-windows-event-viewer) системные папки (включая сектора загрузки), и вы можете [добавить больше папок.](customize-controlled-folders.md#protect-additional-folders)</span><span class="sxs-lookup"><span data-stu-id="6348b-138">The [protected folders](#review-controlled-folder-access-events-in-windows-event-viewer) include common system folders (including boot sectors), and you can [add more folders](customize-controlled-folders.md#protect-additional-folders).</span></span> <span data-ttu-id="6348b-139">Вы также [можете разрешить приложениям](customize-controlled-folders.md#allow-specific-apps-to-make-changes-to-controlled-folders) предоставить им доступ к защищенным папкам.</span><span class="sxs-lookup"><span data-stu-id="6348b-139">You can also [allow apps](customize-controlled-folders.md#allow-specific-apps-to-make-changes-to-controlled-folders) to give them access to the protected folders.</span></span>

<span data-ttu-id="6348b-140">Вы можете использовать [режим аудита,](audit-windows-defender.md) чтобы оценить, как управляемый доступ к папкам повлияет на организацию, если она включена.</span><span class="sxs-lookup"><span data-stu-id="6348b-140">You can use [audit mode](audit-windows-defender.md) to evaluate how controlled folder access would impact your organization if it were enabled.</span></span> <span data-ttu-id="6348b-141">Вы также можете посетить веб-сайт [](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) Защитник Windows test ground в demo.wd.microsoft.com, чтобы подтвердить, что функция работает, и посмотреть, как она работает.</span><span class="sxs-lookup"><span data-stu-id="6348b-141">You can also visit the Windows Defender Test ground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the feature is working and see how it works.</span></span>

<span data-ttu-id="6348b-142">Управляемый доступ к папке поддерживается в следующих версиях Windows:</span><span class="sxs-lookup"><span data-stu-id="6348b-142">Controlled folder access is supported on the following versions of Windows:</span></span>
- <span data-ttu-id="6348b-143">[Windows 10 версии 1709](/windows/whats-new/whats-new-windows-10-version-1709) и более поздней версии</span><span class="sxs-lookup"><span data-stu-id="6348b-143">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) and later</span></span>
- [<span data-ttu-id="6348b-144">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="6348b-144">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

## <a name="windows-system-folders-are-protected-by-default"></a><span data-ttu-id="6348b-145">Windows системные папки защищены по умолчанию</span><span class="sxs-lookup"><span data-stu-id="6348b-145">Windows system folders are protected by default</span></span>

<span data-ttu-id="6348b-146">Windows по умолчанию защищены по умолчанию, а также несколько других папок:</span><span class="sxs-lookup"><span data-stu-id="6348b-146">Windows system folders are protected by default, along with several other folders:</span></span> 

- `c:\Users\<username>\Documents`
- `c:\Users\Public\Documents`
- `c:\Users\<username>\Pictures`
- `c:\Users\Public\Pictures`
- `c:\Users\Public\Videos`
- `c:\Users\<username>\Videos`
- `c:\Users\<username>\Music`
- `c:\Users\Public\Music`
- `c:\Users\<username>\Favorites`

> [!NOTE]
> <span data-ttu-id="6348b-147">Можно настроить дополнительные папки в качестве защищенных, но нельзя удалить Windows системные папки, защищенные по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6348b-147">You can configure additional folders as protected, but you cannot remove the Windows system folders that are protected by default.</span></span>

## <a name="requirements-for-controlled-folder-access"></a><span data-ttu-id="6348b-148">Требования к управляемому доступу к папкам</span><span class="sxs-lookup"><span data-stu-id="6348b-148">Requirements for controlled folder access</span></span>

<span data-ttu-id="6348b-149">Доступ к управляемой папке требует включения антивирусная программа в Microsoft Defender защиты в [режиме реального времени.](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="6348b-149">Controlled folder access requires enabling [Microsoft Defender Antivirus real-time protection](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus).</span></span>

## <a name="review-controlled-folder-access-events-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="6348b-150">Просмотр событий управляемого доступа к папкам на портале Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6348b-150">Review controlled folder access events in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="6348b-151">Defender for Endpoint предоставляет подробные отчеты [](investigate-alerts.md) о событиях и блоках в рамках сценариев расследования предупреждений на портале Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="6348b-151">Defender for Endpoint provides detailed reporting into events and blocks as part of its [alert investigation scenarios](investigate-alerts.md) in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="6348b-152">[(См. microsoft Defender для конечной точки в Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).)</span><span class="sxs-lookup"><span data-stu-id="6348b-152">(See [Microsoft Defender for Endpoint in Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).)</span></span>

<span data-ttu-id="6348b-153">Вы можете запрашивать данные Microsoft Defender для конечных точек с помощью [расширенных методов охоты.](/microsoft-365/security/defender-endpoint/advanced-hunting-windows-defender-advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="6348b-153">You can query Microsoft Defender for Endpoint data by using [Advanced hunting](/microsoft-365/security/defender-endpoint/advanced-hunting-windows-defender-advanced-threat-protection).</span></span> <span data-ttu-id="6348b-154">Если используется режим аудита, можно [](advanced-hunting-overview.md) использовать расширенный режим охоты, чтобы узнать, как параметры управляемого доступа к папкам влияют на среду, если они включены. [](audit-windows-defender.md)</span><span class="sxs-lookup"><span data-stu-id="6348b-154">If you're using [audit mode](audit-windows-defender.md), you can use [advanced hunting](advanced-hunting-overview.md) to see how controlled folder access settings would affect your environment if they were enabled.</span></span>

<span data-ttu-id="6348b-155">Пример запроса</span><span class="sxs-lookup"><span data-stu-id="6348b-155">Example query:</span></span>

```PowerShell
DeviceEvents
| where ActionType in ('ControlledFolderAccessViolationAudited','ControlledFolderAccessViolationBlocked')
```

## <a name="review-controlled-folder-access-events-in-windows-event-viewer"></a><span data-ttu-id="6348b-156">Просмотр событий управляемого доступа к папкам в Windows просмотра событий</span><span class="sxs-lookup"><span data-stu-id="6348b-156">Review controlled folder access events in Windows Event Viewer</span></span>

<span data-ttu-id="6348b-157">Вы можете просмотреть журнал Windows событий, чтобы просмотреть события, созданные при блоке управляемого доступа к папке (или аудите) приложения:</span><span class="sxs-lookup"><span data-stu-id="6348b-157">You can review the Windows event log to see events that are created when controlled folder access blocks (or audits) an app:</span></span>

1. <span data-ttu-id="6348b-158">Скачайте [пакет оценки](https://aka.ms/mp7z2w) и извлеките *файл* cfa-events.xmlв доступное расположение на устройстве.</span><span class="sxs-lookup"><span data-stu-id="6348b-158">Download the [Evaluation Package](https://aka.ms/mp7z2w) and extract the file *cfa-events.xml* to an easily accessible location on the device.</span></span>
2. <span data-ttu-id="6348b-159">Введите **viewer события** в меню Пуск, чтобы открыть Windows просмотра событий.</span><span class="sxs-lookup"><span data-stu-id="6348b-159">Type **Event viewer** in the Start menu to open the Windows Event Viewer.</span></span>
3. <span data-ttu-id="6348b-160">На левой панели в статье **Действия** выберите импорт **настраиваемого представления...**.</span><span class="sxs-lookup"><span data-stu-id="6348b-160">On the left panel, under **Actions**, select **Import custom view...**.</span></span>
4. <span data-ttu-id="6348b-161">Перейдите к месту, где *cfa-events.xml* и выберите его.</span><span class="sxs-lookup"><span data-stu-id="6348b-161">Navigate to where you extracted *cfa-events.xml* and select it.</span></span> <span data-ttu-id="6348b-162">Кроме того, [скопируйте XML напрямую.](event-views.md)</span><span class="sxs-lookup"><span data-stu-id="6348b-162">Alternatively, [copy the XML directly](event-views.md).</span></span>
5. <span data-ttu-id="6348b-163">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6348b-163">Select **OK**.</span></span>

<span data-ttu-id="6348b-164">В следующей таблице показаны события, связанные с доступом к управляемой папке:</span><span class="sxs-lookup"><span data-stu-id="6348b-164">The following table shows events related to controlled folder access:</span></span>

|<span data-ttu-id="6348b-165">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="6348b-165">Event ID</span></span> | <span data-ttu-id="6348b-166">Описание</span><span class="sxs-lookup"><span data-stu-id="6348b-166">Description</span></span> |
|:---|:---|
|<span data-ttu-id="6348b-167">5007</span><span class="sxs-lookup"><span data-stu-id="6348b-167">5007</span></span> | <span data-ttu-id="6348b-168">Событие при смене параметров</span><span class="sxs-lookup"><span data-stu-id="6348b-168">Event when settings are changed</span></span> |
|<span data-ttu-id="6348b-169">1124</span><span class="sxs-lookup"><span data-stu-id="6348b-169">1124</span></span> | <span data-ttu-id="6348b-170">Событие доступа к контролируемой управляемой папке</span><span class="sxs-lookup"><span data-stu-id="6348b-170">Audited controlled folder access event</span></span> | 
|<span data-ttu-id="6348b-171">1123</span><span class="sxs-lookup"><span data-stu-id="6348b-171">1123</span></span> | <span data-ttu-id="6348b-172">Событие доступа к заблокированной управляемой папке</span><span class="sxs-lookup"><span data-stu-id="6348b-172">Blocked controlled folder access event</span></span> |

## <a name="view-or-change-the-list-of-protected-folders"></a><span data-ttu-id="6348b-173">Просмотр или изменение списка защищенных папок</span><span class="sxs-lookup"><span data-stu-id="6348b-173">View or change the list of protected folders</span></span>

<span data-ttu-id="6348b-174">Вы можете использовать Безопасность Windows для просмотра списка папок, защищенных управляемым доступом к папкам.</span><span class="sxs-lookup"><span data-stu-id="6348b-174">You can use the Windows Security app to view the list of folders that are protected by controlled folder access.</span></span> 

1. <span data-ttu-id="6348b-175">На Windows 10 откройте приложение Безопасность Windows.</span><span class="sxs-lookup"><span data-stu-id="6348b-175">On your Windows 10 device, open the Windows Security app.</span></span>
2. <span data-ttu-id="6348b-176">Выберите **Защита от вирусов и угроз**.</span><span class="sxs-lookup"><span data-stu-id="6348b-176">Select **Virus & threat protection**.</span></span>
3. <span data-ttu-id="6348b-177">Под **защитой вымогателей** выберите **Управление защитой вымогателей.**</span><span class="sxs-lookup"><span data-stu-id="6348b-177">Under **Ransomware protection**, select **Manage ransomware protection**.</span></span>
4. <span data-ttu-id="6348b-178">Если доступ к управляемой папке отключен, его необходимо включить.</span><span class="sxs-lookup"><span data-stu-id="6348b-178">If controlled folder access is turned off, you'll need to turn it on.</span></span> <span data-ttu-id="6348b-179">Выберите **защищенные папки.**</span><span class="sxs-lookup"><span data-stu-id="6348b-179">Select **protected folders**.</span></span>
5. <span data-ttu-id="6348b-180">Выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="6348b-180">Do one of the following steps:</span></span>
   - <span data-ttu-id="6348b-181">Чтобы добавить папку, выберите **+ Добавить защищенную папку.**</span><span class="sxs-lookup"><span data-stu-id="6348b-181">To add a folder, select **+ Add a protected folder**.</span></span>
   - <span data-ttu-id="6348b-182">Чтобы удалить папку, выберите ее, а затем выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="6348b-182">To remove a folder, select it, and then select **Remove**.</span></span> 

> [!NOTE]
> <span data-ttu-id="6348b-183">[Windows по](#windows-system-folders-are-protected-by-default) умолчанию защищены системные папки, и удалить их из списка невозможно.</span><span class="sxs-lookup"><span data-stu-id="6348b-183">[Windows system folders](#windows-system-folders-are-protected-by-default) are protected by default, and you cannot remove them from the list.</span></span>


