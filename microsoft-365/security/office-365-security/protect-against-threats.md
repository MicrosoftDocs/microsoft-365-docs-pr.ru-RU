---
title: Защита от угроз
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
ms.date: ''
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
description: Узнайте о защите от угроз Office 365 и настройке того, как ее использовать для вашей организации.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7bdc7d619f3c48318572116fbc52647a0858ec5e
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033894"
---
# <a name="protect-against-threats"></a><span data-ttu-id="96d3a-103">Защита от угроз</span><span class="sxs-lookup"><span data-stu-id="96d3a-103">Protect against threats</span></span>

<span data-ttu-id="96d3a-104">Microsoft 365 включает различные функции защиты от угроз.</span><span class="sxs-lookup"><span data-stu-id="96d3a-104">Microsoft 365 includes a variety of threat protection features.</span></span> <span data-ttu-id="96d3a-105">Вот краткое руководство, которое можно использовать в качестве контрольного списка, чтобы убедиться в том, что функции защиты от угроз настроены для Организации.</span><span class="sxs-lookup"><span data-stu-id="96d3a-105">Here's a quick-start guide you can use as a checklist to make sure your threat protection features are set up for your organization.</span></span> <span data-ttu-id="96d3a-106">Если вы не знакомы с функциями защиты от угроз в Office 365, или вы только не знаете, с чего начать, используйте следующие рекомендации в качестве отправной точки.</span><span class="sxs-lookup"><span data-stu-id="96d3a-106">If you're new to threat protection features in Office 365, or you're just not sure where to begin, use the following guidance as a starting point.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="96d3a-107">**Начальные Рекомендуемые параметры включены для каждого типа политики, но многие варианты доступны, и вы можете настроить параметры в соответствии с потребностями конкретной организации**.</span><span class="sxs-lookup"><span data-stu-id="96d3a-107">**Initial recommended settings are included for each kind of policy; however, many options are available, and you can adjust your settings to meet your specific organization's needs**.</span></span> <span data-ttu-id="96d3a-108">Разрешите около 30 минут, чтобы политики или изменения работали с центром обработки данных.</span><span class="sxs-lookup"><span data-stu-id="96d3a-108">Allow approximately 30 minutes for your policies or changes to work their way through your datacenter.</span></span>

## <a name="requirements"></a><span data-ttu-id="96d3a-109">Требования</span><span class="sxs-lookup"><span data-stu-id="96d3a-109">Requirements</span></span>

### <a name="subscriptions"></a><span data-ttu-id="96d3a-110">Подписки</span><span class="sxs-lookup"><span data-stu-id="96d3a-110">Subscriptions</span></span>

<span data-ttu-id="96d3a-111">Функции защиты от угроз включены во все подписки Microsoft 365; Однако некоторые подписки включают более сложные функции.</span><span class="sxs-lookup"><span data-stu-id="96d3a-111">Threat protection features are included in all Microsoft 365 subscriptions; however, some subscriptions include more advanced features.</span></span> <span data-ttu-id="96d3a-112">В следующей таблице перечислены функции защиты, включенные в эту статью, с минимальными требованиями к подписке.</span><span class="sxs-lookup"><span data-stu-id="96d3a-112">The following table lists the protection features included in this article together with the minimum subscription requirements.</span></span><br/>

|||
|---|---|
|<span data-ttu-id="96d3a-113">**Тип защиты**</span><span class="sxs-lookup"><span data-stu-id="96d3a-113">**Protection type**</span></span>|<span data-ttu-id="96d3a-114">**Требование к подписке**</span><span class="sxs-lookup"><span data-stu-id="96d3a-114">**Subscription requirement**</span></span>|
|<span data-ttu-id="96d3a-115">Защита от вредоносных программ</span><span class="sxs-lookup"><span data-stu-id="96d3a-115">Anti-malware protection</span></span>|<span data-ttu-id="96d3a-116">[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description) (EOP)</span><span class="sxs-lookup"><span data-stu-id="96d3a-116">[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description) (EOP)</span></span>|
|<span data-ttu-id="96d3a-117">Защита от вредоносных URL-адресов и файлов в электронной почте и документах Office</span><span class="sxs-lookup"><span data-stu-id="96d3a-117">Protection from malicious URLs and files in email and Office documents</span></span>|<span data-ttu-id="96d3a-118">[Office 365 Advanced Threat protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP)</span><span class="sxs-lookup"><span data-stu-id="96d3a-118">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP)</span></span>|
|<span data-ttu-id="96d3a-119">Защита от фишинга</span><span class="sxs-lookup"><span data-stu-id="96d3a-119">Anti-phishing protection</span></span>|[<span data-ttu-id="96d3a-120">EOP</span><span class="sxs-lookup"><span data-stu-id="96d3a-120">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)|
|<span data-ttu-id="96d3a-121">Расширенная защита от фишинга</span><span class="sxs-lookup"><span data-stu-id="96d3a-121">Advanced anti-phishing protection</span></span>|[<span data-ttu-id="96d3a-122">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="96d3a-122">Office 365 ATP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|<span data-ttu-id="96d3a-123">Защита от нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="96d3a-123">Anti-spam protection</span></span>|[<span data-ttu-id="96d3a-124">EOP</span><span class="sxs-lookup"><span data-stu-id="96d3a-124">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)|
|<span data-ttu-id="96d3a-125">Автоматическая очистка нулевого времени (для электронной почты)</span><span class="sxs-lookup"><span data-stu-id="96d3a-125">Zero-hour auto purge (for email)</span></span>|[<span data-ttu-id="96d3a-126">EOP</span><span class="sxs-lookup"><span data-stu-id="96d3a-126">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)|
|<span data-ttu-id="96d3a-127">Ведение журнала аудита (используется в целях создания отчетов)</span><span class="sxs-lookup"><span data-stu-id="96d3a-127">Audit logging (this is used for reporting purposes)</span></span>|[<span data-ttu-id="96d3a-128">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="96d3a-128">Exchange Online</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description)|
|

### <a name="roles-and-permissions"></a><span data-ttu-id="96d3a-129">Роли и разрешения</span><span class="sxs-lookup"><span data-stu-id="96d3a-129">Roles and permissions</span></span>

<span data-ttu-id="96d3a-130">Необходимо назначить соответствующую роль для настройки политик в [центре безопасности & соответствия требованиям](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span><span class="sxs-lookup"><span data-stu-id="96d3a-130">You must be assigned an appropriate role to configure policies in the [Security & Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span></span> <span data-ttu-id="96d3a-131">В таблице приведено несколько примеров.</span><span class="sxs-lookup"><span data-stu-id="96d3a-131">The following table includes some examples:</span></span>

|<span data-ttu-id="96d3a-132">Роль или группа ролей</span><span class="sxs-lookup"><span data-stu-id="96d3a-132">Role or role group</span></span>|<span data-ttu-id="96d3a-133">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="96d3a-133">Where to learn more</span></span>|
|---------|---------|
|<span data-ttu-id="96d3a-134">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="96d3a-134">global administrator</span></span>|[<span data-ttu-id="96d3a-135">О ролях администратора Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="96d3a-135">About Microsoft 365 admin roles</span></span>](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
|<span data-ttu-id="96d3a-136">Администратор безопасности</span><span class="sxs-lookup"><span data-stu-id="96d3a-136">Security Administrator</span></span>|[<span data-ttu-id="96d3a-137">Разрешения роли администратора в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="96d3a-137">Administrator role permissions in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|<span data-ttu-id="96d3a-138">Управление организациями в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="96d3a-138">Exchange Online Organization Management</span></span>|[<span data-ttu-id="96d3a-139">Разрешения в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="96d3a-139">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <br><span data-ttu-id="96d3a-140">и</span><span class="sxs-lookup"><span data-stu-id="96d3a-140">and</span></span><br> [<span data-ttu-id="96d3a-141">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="96d3a-141">Exchange Online PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)|
|

<span data-ttu-id="96d3a-142">Чтобы узнать больше, ознакомьтесь [с разрешениями &amp; в центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="96d3a-142">To learn more, see [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="part-1---anti-malware-protection"></a><span data-ttu-id="96d3a-143">Часть 1 — Защита от вредоносных программ</span><span class="sxs-lookup"><span data-stu-id="96d3a-143">Part 1 - Anti-malware protection</span></span>

<span data-ttu-id="96d3a-144">[Защита от вредоносных программ](anti-malware-protection.md) доступна в подписках, включающих [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="96d3a-144">[Anti-malware protection](anti-malware-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="96d3a-145">В [центре безопасности & соответствия требованиям](https://protection.office.com)выберите > **политику** >  **управления угрозами**для**защиты от вредоносных программ**.</span><span class="sxs-lookup"><span data-stu-id="96d3a-145">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-malware**.</span></span>

2. <span data-ttu-id="96d3a-146">Дважды щелкните политику **по умолчанию** , а затем выберите **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="96d3a-146">Double-click the **Default** policy, and then choose **settings**.</span></span>

3. <span data-ttu-id="96d3a-147">Укажите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="96d3a-147">Specify the following settings:</span></span>

    - <span data-ttu-id="96d3a-148">В разделе **ответ на обнаружение вредоносных программ** оставьте значение по умолчанию ( **нет**).</span><span class="sxs-lookup"><span data-stu-id="96d3a-148">In the **Malware Detection Response** section, keep the default setting of **No**.</span></span>

    - <span data-ttu-id="96d3a-149">В разделе **фильтр типов вложений** выберите **включено**.</span><span class="sxs-lookup"><span data-stu-id="96d3a-149">In the **Common Attachment Types Filter** section, choose **On**.</span></span>

4. <span data-ttu-id="96d3a-150">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="96d3a-150">Click **Save**.</span></span>

<span data-ttu-id="96d3a-151">Дополнительные сведения о параметрах политики защиты от вредоносных программ приведены в разделе [Настройка политик защиты от вредоносных](configure-anti-malware-policies.md)программ.</span><span class="sxs-lookup"><span data-stu-id="96d3a-151">To learn more about anti-malware policy options, see [Configure anti-malware policies](configure-anti-malware-policies.md).</span></span>

## <a name="part-2---protection-from-malicious-urls-and-files"></a><span data-ttu-id="96d3a-152">Часть 2 — Защита от вредоносных URL-адресов и файлов</span><span class="sxs-lookup"><span data-stu-id="96d3a-152">Part 2 - Protection from malicious URLs and files</span></span>

<span data-ttu-id="96d3a-153">Защита от использования вредоносных URL-адресов и файлов доступна в подписках, включающих [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP), и настраивается с помощью политик [безопасных вложений](atp-safe-attachments.md) ATP и " [безопасные ссылки ATP](atp-safe-links.md) ".</span><span class="sxs-lookup"><span data-stu-id="96d3a-153">Time-of-click protection from malicious URLs and files is available in subscriptions that include [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP), and is set up through [ATP Safe Attachments](atp-safe-attachments.md) and [ATP Safe Links](atp-safe-links.md) policies.</span></span>

### <a name="atp-safe-attachments-policies"></a><span data-ttu-id="96d3a-154">Политики безопасных вложений ATP</span><span class="sxs-lookup"><span data-stu-id="96d3a-154">ATP Safe Attachments policies</span></span>

<span data-ttu-id="96d3a-155">Для настройки [безопасных вложений ATP](atp-safe-attachments.md)необходимо определить по крайней мере одну политику безопасных вложений ATP.</span><span class="sxs-lookup"><span data-stu-id="96d3a-155">To set up [ATP Safe Attachments](atp-safe-attachments.md), you must define at least one ATP Safe Attachments policy.</span></span>

1. <span data-ttu-id="96d3a-156">В [центре безопасности & соответствия требованиям](https://protection.office.com)выберите > **Политика** >  **управления угрозами\*\*\*\*безопасные вложения ATP**.</span><span class="sxs-lookup"><span data-stu-id="96d3a-156">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP safe attachments**.</span></span>

2. <span data-ttu-id="96d3a-157">Выберите параметр **включить ATP для SharePoint, OneDrive и Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="96d3a-157">Select the option **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

3. <span data-ttu-id="96d3a-158">В разделе **защита вложений электронной почты** щелкните знак "плюс"**+**().</span><span class="sxs-lookup"><span data-stu-id="96d3a-158">In the **Protect email attachments** section, click the plus sign (**+**).</span></span>

4. <span data-ttu-id="96d3a-159">Укажите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="96d3a-159">Specify the following settings:</span></span>

   - <span data-ttu-id="96d3a-160">В поле **имя** введите `Block malware`.</span><span class="sxs-lookup"><span data-stu-id="96d3a-160">In the **Name** box, type `Block malware`.</span></span>

   - <span data-ttu-id="96d3a-161">В разделе ответ выберите пункт **блокировать**.</span><span class="sxs-lookup"><span data-stu-id="96d3a-161">In the response section, choose **Block**.</span></span>

   - <span data-ttu-id="96d3a-162">В разделе **Перенаправление вложения** выберите параметр **включить перенаправление**, а затем укажите адрес электронной почты администратора безопасности Организации или оператора, который будет просматривать обнаруженные файлы.</span><span class="sxs-lookup"><span data-stu-id="96d3a-162">In the **Redirect attachment** section, select the option **Enable redirect**, and then specify the email address for your organization's security administrator or operator who will review detected files.</span></span>

   - <span data-ttu-id="96d3a-163">В разделе **применено** выберите **домен получателя**.</span><span class="sxs-lookup"><span data-stu-id="96d3a-163">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="96d3a-164">Затем выберите свой домен, нажмите кнопку **Добавить**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="96d3a-164">Then, select your domain, choose **Add**, and then click **OK**.</span></span>

5. <span data-ttu-id="96d3a-165">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="96d3a-165">Click **Save**.</span></span>

6. <span data-ttu-id="96d3a-166">(**Рекомендуемое дополнительное действие**) Как глобальный администратор или администратор SharePoint Online выполните командлет **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** с параметром **дисалловинфектедфиледовнлоад** , для которого задано *значение true* для среды Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="96d3a-166">(**Recommended additional step**) As a global administrator or a SharePoint Online administrator run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet with the **DisallowInfectedFileDownload** parameter set to  *true* for your Microsoft 365 environment.</span></span> <span data-ttu-id="96d3a-167">(Это предотвращает открытие, перемещение, копирование или совместное использование файлов, обнаруженных как вредоносные.)</span><span class="sxs-lookup"><span data-stu-id="96d3a-167">(This prevents people from opening, moving, copying, or sharing files that are detected as malicious.)</span></span>

<span data-ttu-id="96d3a-168">Дополнительные сведения: [Настройка политик безопасных вложений office 365 ATP](set-up-atp-safe-attachments-policies.md) и [Включение Office 365 ATP для SharePoint, OneDrive и Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="96d3a-168">To learn more, see [Set up Office 365 ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="atp-safe-links-policies"></a><span data-ttu-id="96d3a-169">Политики безопасных ссылок ATP</span><span class="sxs-lookup"><span data-stu-id="96d3a-169">ATP Safe Links policies</span></span>

<span data-ttu-id="96d3a-170">Чтобы настроить [безопасные ссылки ATP](atp-safe-links.md), просмотрите и измените политику по умолчанию и добавьте политику для определенных пользователей.</span><span class="sxs-lookup"><span data-stu-id="96d3a-170">To set up [ATP Safe Links](atp-safe-links.md), review and edit your default policy, and add a policy for specific users.</span></span>

1. <span data-ttu-id="96d3a-171">В [центре безопасности & соответствия требованиям](https://protection.office.com)выберите > **политику** >  **управления угрозой\*\*\*\*безопасные ссылки ATP**.</span><span class="sxs-lookup"><span data-stu-id="96d3a-171">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP Safe Links**.</span></span>

2. <span data-ttu-id="96d3a-172">Дважды щелкните политику **по умолчанию** .</span><span class="sxs-lookup"><span data-stu-id="96d3a-172">Double-click the **Default** policy.</span></span>

3. <span data-ttu-id="96d3a-173">В разделе **использовать безопасные ссылки в** выберите параметр **Microsoft 365 для корпоративных приложений, Office для iOS и Android**, а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="96d3a-173">In the **Use safe links in** section, select the option **Microsoft 365 Apps for enterprise, Office for iOS and Android**, and then click **Save**.</span></span>

4. <span data-ttu-id="96d3a-174">В разделе **политики, которые применяются к определенным получателям** щелкните знак "плюс"**+**().</span><span class="sxs-lookup"><span data-stu-id="96d3a-174">In the **Policies that apply to specific recipients** section, click the plus sign (**+**).</span></span>

5. <span data-ttu-id="96d3a-175">Укажите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="96d3a-175">Specify the following settings:</span></span>

   - <span data-ttu-id="96d3a-176">В поле **имя** введите имя, например `Safe Links`.</span><span class="sxs-lookup"><span data-stu-id="96d3a-176">In the **Name** box, type a name, such as `Safe Links`.</span></span>

   - <span data-ttu-id="96d3a-177">В разделе **Выбор действия** выберите **включить**.</span><span class="sxs-lookup"><span data-stu-id="96d3a-177">In the **Select the action** section, choose **On**.</span></span>

   - <span data-ttu-id="96d3a-178">Выберите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="96d3a-178">Select these options:</span></span>

     - <span data-ttu-id="96d3a-179">**Использование безопасных вложений для сканирования загружаемого контента**</span><span class="sxs-lookup"><span data-stu-id="96d3a-179">**Use safe attachments to scan downloadable content**</span></span>

     - <span data-ttu-id="96d3a-180">**Применение безопасных ссылок к сообщениям электронной почты, отправленным в Организации**</span><span class="sxs-lookup"><span data-stu-id="96d3a-180">**Apply safe links to email messages sent within the organization**</span></span>

     - <span data-ttu-id="96d3a-181">**Не разрешать пользователям щелкать ссылки с исходным URL-адресом.**</span><span class="sxs-lookup"><span data-stu-id="96d3a-181">**Do not let users click through safe links to original URL**</span></span>

   - <span data-ttu-id="96d3a-182">В разделе **применено** выберите **домен получателя**.</span><span class="sxs-lookup"><span data-stu-id="96d3a-182">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="96d3a-183">Затем выберите свой домен, нажмите кнопку **Добавить**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="96d3a-183">Then, select your domain, choose **Add**, and then click **OK**.</span></span>

6. <span data-ttu-id="96d3a-184">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="96d3a-184">Click **Save**.</span></span>

<span data-ttu-id="96d3a-185">Дополнительные сведения см. в статье [Настройка политик безопасных ссылок ATP в Office 365](set-up-atp-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="96d3a-185">To learn more, see [Set up Office 365 ATP Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

## <a name="part-3---anti-phishing-protection"></a><span data-ttu-id="96d3a-186">Часть 3 — Защита от фишинга</span><span class="sxs-lookup"><span data-stu-id="96d3a-186">Part 3 - Anti-phishing protection</span></span>

<span data-ttu-id="96d3a-187">[Защита от фишинга]</span><span class="sxs-lookup"><span data-stu-id="96d3a-187">[Anti-phishing]</span></span>

<span data-ttu-id="96d3a-188">[Защита от фишинга](anti-phishing-protection.md) доступна в подписках, включающих [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="96d3a-188">[Anti-phishing protection](anti-phishing-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span> <span data-ttu-id="96d3a-189">Расширенная защита от фишинга доступна в [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="96d3a-189">Advanced anti-phishing protection is available in [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

<span data-ttu-id="96d3a-190">В следующей процедуре описывается настройка антифишинговой политики ATP.</span><span class="sxs-lookup"><span data-stu-id="96d3a-190">The following procedure describes how to configure an ATP anti-phishing policy.</span></span> <span data-ttu-id="96d3a-191">Эти действия похожи на настройку антифишинговой политики (без ATP).</span><span class="sxs-lookup"><span data-stu-id="96d3a-191">The steps are similar for configuring an anti-phishing policy (without ATP).</span></span>

1. <span data-ttu-id="96d3a-192">В [центре безопасности & соответствия требованиям](https://protection.office.com)выберите > **политику** >  **управления угрозами**для**защиты от фишинга ATP**.</span><span class="sxs-lookup"><span data-stu-id="96d3a-192">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="96d3a-193">Щелкните **Политика по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="96d3a-193">Click **Default policy**.</span></span>

3. <span data-ttu-id="96d3a-194">В разделе **олицетворение** нажмите кнопку **изменить**, а затем укажите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="96d3a-194">In the **Impersonation** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="96d3a-195">На вкладке **Добавление пользователей для защиты** включите защиту.</span><span class="sxs-lookup"><span data-stu-id="96d3a-195">On the **Add users to protect** tab, turn protection on.</span></span> <span data-ttu-id="96d3a-196">Затем добавьте пользователей, например, участников вашей организации, Генерального директора, финансового директора и других старших руководителей.</span><span class="sxs-lookup"><span data-stu-id="96d3a-196">Then add users, such as your organization's board members, your CEO, CFO, and other senior leaders.</span></span> <span data-ttu-id="96d3a-197">(Вы можете ввести отдельный адрес электронной почты или щелкнуть для отображения списка.)</span><span class="sxs-lookup"><span data-stu-id="96d3a-197">(You can type an individual email address, or click to display a list.)</span></span>

   - <span data-ttu-id="96d3a-198">На вкладке **Добавление доменов для защиты** включите **Автоматическое включение доменов, которыми я владеют**.</span><span class="sxs-lookup"><span data-stu-id="96d3a-198">On the **Add domains to protect** tab, turn on **Automatically include the domains I own**.</span></span> <span data-ttu-id="96d3a-199">Если у вас есть пользовательские домены, добавьте их также.</span><span class="sxs-lookup"><span data-stu-id="96d3a-199">If you have custom domains, add those as well.</span></span>

   - <span data-ttu-id="96d3a-200">На вкладке **действия** выберите пункт **карантин сообщения** для параметров **олицетворенного пользователя** и **олицетворенного домена** .</span><span class="sxs-lookup"><span data-stu-id="96d3a-200">On the **Actions** tab, select **Quarantine the message** for both the **impersonated user** and **impersonated domain** options.</span></span> <span data-ttu-id="96d3a-201">Кроме того, включите советы по безопасности олицетворения.</span><span class="sxs-lookup"><span data-stu-id="96d3a-201">In addition, turn on impersonation safety tips.</span></span>

   - <span data-ttu-id="96d3a-202">На вкладке **аналитика почтовых ящиков** убедитесь, что включена функция интеллектуального анализа почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="96d3a-202">On the **Mailbox intelligence** tab, make sure mailbox intelligence is turned on.</span></span> <span data-ttu-id="96d3a-203">Кроме того, включите защиту от олицетворения на основе логики почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="96d3a-203">In addition, turn on mailbox intelligence based impersonation protection.</span></span> <span data-ttu-id="96d3a-204">В разделе **Если сообщение отправляется в списке олицетворенного пользователя** , выберите пункт **помещать сообщение в карантин**.</span><span class="sxs-lookup"><span data-stu-id="96d3a-204">In the **If email is sent by an impersonated user** list, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="96d3a-205">На вкладке **Добавление надежных отправителей и доменов** укажите все доверенные отправители или домены, которые вы хотите добавить.</span><span class="sxs-lookup"><span data-stu-id="96d3a-205">On the **Add trusted senders and domains** tab, specify any trusted senders or domains that you want to add.</span></span>

   - <span data-ttu-id="96d3a-206">На вкладке **Проверка параметров** после просмотра параметров нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="96d3a-206">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span>

4. <span data-ttu-id="96d3a-207">В разделе **подделка** нажмите кнопку **изменить**, а затем укажите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="96d3a-207">In the **Spoof** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="96d3a-208">На вкладке **Параметры фильтра подделки** убедитесь, что включена защита от спуфинга.</span><span class="sxs-lookup"><span data-stu-id="96d3a-208">On the **Spoofing filter settings** tab, make sure anti-spoofing protection is turned on.</span></span>

   - <span data-ttu-id="96d3a-209">На вкладке **действия** выберите пункт **помещать сообщение в карантин**.</span><span class="sxs-lookup"><span data-stu-id="96d3a-209">On the **Actions** tab, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="96d3a-210">На вкладке **Проверка параметров** после просмотра параметров нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="96d3a-210">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span> <span data-ttu-id="96d3a-211">(Если изменения не были внесены, нажмите кнопку **Отмена**.)</span><span class="sxs-lookup"><span data-stu-id="96d3a-211">(If you didn't make any changes, click **Cancel**.)</span></span>

5. <span data-ttu-id="96d3a-212">Закройте страницу параметров политики по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="96d3a-212">Close the default policy settings page.</span></span>

<span data-ttu-id="96d3a-213">Чтобы узнать больше о параметрах политики защиты от фишинга, ознакомьтесь со статьей [Настройка политик защиты от фишинга ATP в Office 365](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="96d3a-213">To learn more about your anti-phishing policy options, see [Configure ATP anti-phishing policies in Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="part-4---anti-spam-protection"></a><span data-ttu-id="96d3a-214">Часть 4: защита от нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="96d3a-214">Part 4 - Anti-spam protection</span></span>

<span data-ttu-id="96d3a-215">[Защита от нежелательной почты](anti-spam-protection.md) доступна в подписках, включающих [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="96d3a-215">[Anti-spam protection](anti-spam-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="96d3a-216">В [центре безопасности & соответствия требованиям](https://protection.office.com)выберите > **Политика** >  **управления угрозами\*\*\*\*защиты от нежелательной почты**.</span><span class="sxs-lookup"><span data-stu-id="96d3a-216">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-spam**.</span></span>

2. <span data-ttu-id="96d3a-217">На вкладке **Настройка** включите **пользовательские параметры** .</span><span class="sxs-lookup"><span data-stu-id="96d3a-217">On the **Custom** tab, turn **Custom settings** on.</span></span>

3. <span data-ttu-id="96d3a-218">Разверните узел **Политика фильтрации нежелательной почты по умолчанию**, щелкните **изменить политику**, а затем укажите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="96d3a-218">Expand **Default spam filter policy**, click **Edit policy**, and then specify the following settings:</span></span>

   - <span data-ttu-id="96d3a-219">В разделе **Нежелательная почта и групповые действия** установите для порогового значения 5 или 6.</span><span class="sxs-lookup"><span data-stu-id="96d3a-219">In the **Spam and bulk actions** section, set the threshold to a value of 5 or 6.</span></span>

   - <span data-ttu-id="96d3a-220">В разделе **разрешить списки** просмотрите (и при необходимости измените) разрешенных отправителей и доменов.</span><span class="sxs-lookup"><span data-stu-id="96d3a-220">In the **Allow lists** section, review (and if necessary, edit) your allowed senders and domains.</span></span>

4. <span data-ttu-id="96d3a-221">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="96d3a-221">Click **Save**.</span></span>

<span data-ttu-id="96d3a-222">Чтобы узнать больше о параметрах политики защиты от нежелательной почты, см [в разделе Настройка политик защиты от нежелательной почты в Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="96d3a-222">To learn more about your anti-spam policy options, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

## <a name="part-5---additional-settings-to-configure"></a><span data-ttu-id="96d3a-223">Часть 5 — Дополнительные параметры для настройки</span><span class="sxs-lookup"><span data-stu-id="96d3a-223">Part 5 - Additional settings to configure</span></span>

<span data-ttu-id="96d3a-224">В дополнение к настройке защиты от вредоносных программ, вредоносных URL-адресов и файлов, фишинговых и нежелательных сообщений рекомендуется настраивать параметры ведения журнала в автоматическом и автоматическом времени.</span><span class="sxs-lookup"><span data-stu-id="96d3a-224">In addition to configuring protection from malware, malicious URLs and files, phishing, and spam, we recommend that you configure your zero-hour auto purge and audit logging settings.</span></span>

### <a name="zero-hour-auto-purge-for-email"></a><span data-ttu-id="96d3a-225">Автоматическая очистка электронной почты с нулевым часовым значением</span><span class="sxs-lookup"><span data-stu-id="96d3a-225">Zero-hour auto purge for email</span></span>

<span data-ttu-id="96d3a-226">[Автоматическая очистка](zero-hour-auto-purge.md) (ZAP) с нулевым часовым циклом доступна в подписках, включающих [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="96d3a-226">[Zero-hour auto purge](zero-hour-auto-purge.md) (ZAP) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span> <span data-ttu-id="96d3a-227">Эта защита включается по умолчанию; Однако для вступления в последствия защиты должны выполняться следующие условия:</span><span class="sxs-lookup"><span data-stu-id="96d3a-227">This protection is turned on by default; however, the following conditions must be met for protection to be in effect:</span></span>

- <span data-ttu-id="96d3a-228">Для действий нежелательной почты настраивается **Перемещение сообщения в папку нежелательной почты** в [политиках защиты от нежелательной почты](anti-spam-protection.md).</span><span class="sxs-lookup"><span data-stu-id="96d3a-228">Spam actions are set to **Move message to Junk Email folder** in [anti-spam policies](anti-spam-protection.md).</span></span>

- <span data-ttu-id="96d3a-229">Пользователи сохраняли свои [Параметры нежелательной почты](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)по умолчанию и не отключили защиту от нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="96d3a-229">Users have kept their default [junk email settings](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md), and have not turned off junk email protection.</span></span>

<span data-ttu-id="96d3a-230">Для получения дополнительных сведений о [нежелательной почте и вредоносном программном обеспечении автоматическая очистка без защиты от нежелательной почты](zero-hour-auto-purge.md).</span><span class="sxs-lookup"><span data-stu-id="96d3a-230">To learn more, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

### <a name="audit-logging-for-reporting-and-investigation"></a><span data-ttu-id="96d3a-231">Ведение журнала аудита для создания отчетов и исследования</span><span class="sxs-lookup"><span data-stu-id="96d3a-231">Audit logging for reporting and investigation</span></span>

<span data-ttu-id="96d3a-232">Ведение журнала аудита доступно в подписках, включающих [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description).</span><span class="sxs-lookup"><span data-stu-id="96d3a-232">Audit logging is available in subscriptions that include [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description).</span></span> <span data-ttu-id="96d3a-233">Для просмотра данных в отчетах защиты от угроз, таких как [панель мониторинга безопасности](security-dashboard.md), [отчеты о безопасности электронной почты](view-email-security-reports.md)и [проводник](threat-explorer.md), для Организации необходимо включить ведение журнала аудита.</span><span class="sxs-lookup"><span data-stu-id="96d3a-233">In order to view data in threat protection reports, such as the [Security Dashboard](security-dashboard.md), [email security reports](view-email-security-reports.md), and [Explorer](threat-explorer.md), audit logging must be turned on for your organization.</span></span> <span data-ttu-id="96d3a-234">Дополнительные сведения см. [в разделе Включение поиска в журнале аудита](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="96d3a-234">To learn more, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="post-setup-tasks"></a><span data-ttu-id="96d3a-235">Задачи, выполняемые после установки</span><span class="sxs-lookup"><span data-stu-id="96d3a-235">Post-setup tasks</span></span>

<span data-ttu-id="96d3a-236">После того как вы настроили функции защиты от угроз, следите за тем, как работают эти функции, изучите и измените свои политики, а также следите за новыми функциями и обновлениями служб.</span><span class="sxs-lookup"><span data-stu-id="96d3a-236">After you have configured your threat protection features, make sure to monitor how those features are working, review and revise your policies as needed, and watch for new features and service updates.</span></span>

|||
|---|---|
|<span data-ttu-id="96d3a-237">**Действия**</span><span class="sxs-lookup"><span data-stu-id="96d3a-237">**What to do**</span></span>|<span data-ttu-id="96d3a-238">**Дополнительные ресурсы**</span><span class="sxs-lookup"><span data-stu-id="96d3a-238">**Resources to learn more**</span></span>|
|<span data-ttu-id="96d3a-239">Узнайте, как функции защиты от угроз работают в вашей организации, просмотрев отчеты</span><span class="sxs-lookup"><span data-stu-id="96d3a-239">See how threat protection features are working for your organization by viewing reports</span></span>|[<span data-ttu-id="96d3a-240">Панель мониторинга безопасности</span><span class="sxs-lookup"><span data-stu-id="96d3a-240">Security dashboard</span></span>](security-dashboard.md)<br/>[<span data-ttu-id="96d3a-241">Отчеты по безопасности электронной почты</span><span class="sxs-lookup"><span data-stu-id="96d3a-241">Email security reports</span></span>](view-email-security-reports.md)<br/>[<span data-ttu-id="96d3a-242">Отчеты для Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="96d3a-242">Reports for Office 365 ATP</span></span>](view-reports-for-atp.md)<br/>[<span data-ttu-id="96d3a-243">Обозреватель угроз</span><span class="sxs-lookup"><span data-stu-id="96d3a-243">Threat Explorer</span></span>](threat-explorer.md)|
|<span data-ttu-id="96d3a-244">При необходимости периодически проверяйте и изменяйте политики защиты от угроз.</span><span class="sxs-lookup"><span data-stu-id="96d3a-244">Periodically review and revise your threat protection policies as needed</span></span>|[<span data-ttu-id="96d3a-245">Оценка безопасности</span><span class="sxs-lookup"><span data-stu-id="96d3a-245">Secure Score</span></span>](../mtp/microsoft-secure-score.md)<br/>[<span data-ttu-id="96d3a-246">Интеллектуальные отчеты и аналитика</span><span class="sxs-lookup"><span data-stu-id="96d3a-246">Smart reports and insights</span></span>](reports-and-insights-in-security-and-compliance.md)<br/>[<span data-ttu-id="96d3a-247">Исследование угроз и функции ответа Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="96d3a-247">Microsoft 365 threat investigation and response features</span></span>](keep-users-safe-with-office-365-ti.md)|
|<span data-ttu-id="96d3a-248">Просмотр новых компонентов и обновлений служб</span><span class="sxs-lookup"><span data-stu-id="96d3a-248">Watch for new features and service updates</span></span>|[<span data-ttu-id="96d3a-249">Варианты стандартных и целевых выпусков</span><span class="sxs-lookup"><span data-stu-id="96d3a-249">Standard and Targeted release options</span></span>](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide)<br/>[<span data-ttu-id="96d3a-250">Центр сообщений</span><span class="sxs-lookup"><span data-stu-id="96d3a-250">Message Center</span></span>](https://docs.microsoft.com/office365/admin/manage/message-center?view=o365-worldwide)<br/>[<span data-ttu-id="96d3a-251">План выпуска Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="96d3a-251">Microsoft 365 Roadmap</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)<br/>[<span data-ttu-id="96d3a-252">Описания служб</span><span class="sxs-lookup"><span data-stu-id="96d3a-252">Service Descriptions</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|
