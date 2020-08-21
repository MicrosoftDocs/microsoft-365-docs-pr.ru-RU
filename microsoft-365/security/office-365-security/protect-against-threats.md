---
title: Защита от угроз
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.date: ''
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
description: Администраторы могут узнать о защите от угроз в Microsoft 365 и о том, как ее использовать в организации.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8f1cecbb3141b4751778212025e5aad582707e12
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826829"
---
# <a name="protect-against-threats"></a><span data-ttu-id="69e05-103">Защита от угроз</span><span class="sxs-lookup"><span data-stu-id="69e05-103">Protect against threats</span></span>

<span data-ttu-id="69e05-104">В Microsoft 365 есть различные функции защиты от угроз.</span><span class="sxs-lookup"><span data-stu-id="69e05-104">Microsoft 365 includes a variety of threat protection features.</span></span> <span data-ttu-id="69e05-105">Ниже приведено краткое руководство для начала работы с exchange, с помощью которого можно выполнить настройку функций защиты от угроз в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="69e05-105">Here's a quick-start guide you can use as a checklist to make sure your threat protection features are set up for your organization.</span></span> <span data-ttu-id="69e05-106">Если вы не знаете, с того, на каком этапе вы не знакомы с функциями защиты от угроз в Office 365 или незовыскаете, вы не знаете, с чего начать, используйте следующие рекомендации.</span><span class="sxs-lookup"><span data-stu-id="69e05-106">If you're new to threat protection features in Office 365, or you're just not sure where to begin, use the following guidance as a starting point.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="69e05-107">**Начальные рекомендуемые параметры включаются для каждого типа политики. Однако доступны многие параметры,** и вы можете настроить параметры в соответствии с потребностями вашей организации.</span><span class="sxs-lookup"><span data-stu-id="69e05-107">**Initial recommended settings are included for each kind of policy; however, many options are available, and you can adjust your settings to meet your specific organization's needs**.</span></span> <span data-ttu-id="69e05-108">Дайте возможность пользователям работать с политиками или изменениями в центре обработки данных приблизительно через 30 минут.</span><span class="sxs-lookup"><span data-stu-id="69e05-108">Allow approximately 30 minutes for your policies or changes to work their way through your datacenter.</span></span>

## <a name="requirements"></a><span data-ttu-id="69e05-109">Requirements</span><span class="sxs-lookup"><span data-stu-id="69e05-109">Requirements</span></span>

### <a name="subscriptions"></a><span data-ttu-id="69e05-110">Подписки</span><span class="sxs-lookup"><span data-stu-id="69e05-110">Subscriptions</span></span>

<span data-ttu-id="69e05-111">Функции защиты от угроз включены во все подписки на Microsoft 365. Однако некоторые подписки включают более расширенные функции.</span><span class="sxs-lookup"><span data-stu-id="69e05-111">Threat protection features are included in all Microsoft 365 subscriptions; however, some subscriptions include more advanced features.</span></span> <span data-ttu-id="69e05-112">В приведенной ниже таблице перечислены функции защиты, включенные в данную статью, а также минимальные требования к подписке.</span><span class="sxs-lookup"><span data-stu-id="69e05-112">The following table lists the protection features included in this article together with the minimum subscription requirements.</span></span>

****

|<span data-ttu-id="69e05-113">Тип защиты</span><span class="sxs-lookup"><span data-stu-id="69e05-113">Protection type</span></span>|<span data-ttu-id="69e05-114">Требование подписки</span><span class="sxs-lookup"><span data-stu-id="69e05-114">Subscription requirement</span></span>|
|---|---|
|<span data-ttu-id="69e05-115">Защита от вредоносных программ</span><span class="sxs-lookup"><span data-stu-id="69e05-115">Anti-malware protection</span></span>|<span data-ttu-id="69e05-116">[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (EOP)</span><span class="sxs-lookup"><span data-stu-id="69e05-116">[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (EOP)</span></span>|
|<span data-ttu-id="69e05-117">Защита от вредоносных URL-адресов и файлов в электронных письмах и документах Office</span><span class="sxs-lookup"><span data-stu-id="69e05-117">Protection from malicious URLs and files in email and Office documents</span></span>|<span data-ttu-id="69e05-118">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP)</span><span class="sxs-lookup"><span data-stu-id="69e05-118">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP)</span></span>|
|<span data-ttu-id="69e05-119">Защита от фишинга</span><span class="sxs-lookup"><span data-stu-id="69e05-119">Anti-phishing protection</span></span>|[<span data-ttu-id="69e05-120">EOP</span><span class="sxs-lookup"><span data-stu-id="69e05-120">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="69e05-121">Расширенная защита от фишинга</span><span class="sxs-lookup"><span data-stu-id="69e05-121">Advanced anti-phishing protection</span></span>|[<span data-ttu-id="69e05-122">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="69e05-122">Office 365 ATP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|<span data-ttu-id="69e05-123">Защита от нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="69e05-123">Anti-spam protection</span></span>|[<span data-ttu-id="69e05-124">EOP</span><span class="sxs-lookup"><span data-stu-id="69e05-124">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="69e05-125">Автоматическая очистка (для электронной почты)</span><span class="sxs-lookup"><span data-stu-id="69e05-125">Zero-hour auto purge (for email)</span></span>|[<span data-ttu-id="69e05-126">EOP</span><span class="sxs-lookup"><span data-stu-id="69e05-126">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="69e05-127">Ведение журнала аудита (используется для создания отчетов)</span><span class="sxs-lookup"><span data-stu-id="69e05-127">Audit logging (this is used for reporting purposes)</span></span>|[<span data-ttu-id="69e05-128">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="69e05-128">Exchange Online</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|

### <a name="roles-and-permissions"></a><span data-ttu-id="69e05-129">Роли и разрешения</span><span class="sxs-lookup"><span data-stu-id="69e05-129">Roles and permissions</span></span>

<span data-ttu-id="69e05-130">Вам должна быть назначена соответствующая роль для настройки политик в [Центре безопасности & соответствия требованиям.](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)</span><span class="sxs-lookup"><span data-stu-id="69e05-130">You must be assigned an appropriate role to configure policies in the [Security & Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span></span> <span data-ttu-id="69e05-131">В таблице приведено несколько примеров.</span><span class="sxs-lookup"><span data-stu-id="69e05-131">The following table includes some examples:</span></span>

****

|<span data-ttu-id="69e05-132">Роль или группа ролей</span><span class="sxs-lookup"><span data-stu-id="69e05-132">Role or role group</span></span>|<span data-ttu-id="69e05-133">Where to learn more</span><span class="sxs-lookup"><span data-stu-id="69e05-133">Where to learn more</span></span>|
|---|---|
|<span data-ttu-id="69e05-134">глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="69e05-134">global administrator</span></span>|[<span data-ttu-id="69e05-135">О ролях администратора Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="69e05-135">About Microsoft 365 admin roles</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|<span data-ttu-id="69e05-136">Администратор безопасности</span><span class="sxs-lookup"><span data-stu-id="69e05-136">Security Administrator</span></span>|[<span data-ttu-id="69e05-137">Разрешения роли администратора в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="69e05-137">Administrator role permissions in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|<span data-ttu-id="69e05-138">Управление организациями в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="69e05-138">Exchange Online Organization Management</span></span>|[<span data-ttu-id="69e05-139">Разрешения в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="69e05-139">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <br><span data-ttu-id="69e05-140">и</span><span class="sxs-lookup"><span data-stu-id="69e05-140">and</span></span><br> [<span data-ttu-id="69e05-141">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="69e05-141">Exchange Online PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|

<span data-ttu-id="69e05-142">Дополнительные сведения см. в разделе ["Разрешения" в Центре &amp; соответствия требованиям безопасности.](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="69e05-142">To learn more, see [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="part-1---anti-malware-protection"></a><span data-ttu-id="69e05-143">Часть 1. Защита от вредоносных программ</span><span class="sxs-lookup"><span data-stu-id="69e05-143">Part 1 - Anti-malware protection</span></span>

<span data-ttu-id="69e05-144">[Защита от вредоносных](anti-malware-protection.md) программ доступна в подписках, включающих [EOP.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)</span><span class="sxs-lookup"><span data-stu-id="69e05-144">[Anti-malware protection](anti-malware-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="69e05-145">В Центре [безопасности & соответствия требованиям выберите](https://protection.office.com)пункт **"Защита от**  >  **вредоносных**  >  **программ" политики управления угрозами.**</span><span class="sxs-lookup"><span data-stu-id="69e05-145">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-malware**.</span></span>

2. <span data-ttu-id="69e05-146">Дважды щелкните **политику по** умолчанию и выберите **параметры.**</span><span class="sxs-lookup"><span data-stu-id="69e05-146">Double-click the **Default** policy, and then choose **settings**.</span></span>

3. <span data-ttu-id="69e05-147">Укажите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="69e05-147">Specify the following settings:</span></span>

    - <span data-ttu-id="69e05-148">В разделе **реагирования при обнаружении** вредоносных программ оставьте значение **"Нет" по умолчанию.**</span><span class="sxs-lookup"><span data-stu-id="69e05-148">In the **Malware Detection Response** section, keep the default setting of **No**.</span></span>

    - <span data-ttu-id="69e05-149">В разделе **"Фильтр распространенных типов вложений"** выберите значение **"Включено".**</span><span class="sxs-lookup"><span data-stu-id="69e05-149">In the **Common Attachment Types Filter** section, choose **On**.</span></span>

4. <span data-ttu-id="69e05-150">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="69e05-150">Click **Save**.</span></span>

<span data-ttu-id="69e05-151">Дополнительные сведения о параметрах политикзащиты от вредоносных программ см. в статье ["Настройка политик защиты от вредоносных программ".](configure-anti-malware-policies.md)</span><span class="sxs-lookup"><span data-stu-id="69e05-151">To learn more about anti-malware policy options, see [Configure anti-malware policies](configure-anti-malware-policies.md).</span></span>

## <a name="part-2---protection-from-malicious-urls-and-files"></a><span data-ttu-id="69e05-152">Часть 2. Защита от вредоносных URL-адресов и файлов</span><span class="sxs-lookup"><span data-stu-id="69e05-152">Part 2 - Protection from malicious URLs and files</span></span>

<span data-ttu-id="69e05-153">Защита от щелчка по вредоносным URL-адресам и файлам доступна в подписках, [включающих Office 365 ATP (ATP),](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) и устанавливается с помощью [политик безопасных](atp-safe-attachments.md) вложений [и безопасных ссылок ATP.](atp-safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="69e05-153">Time-of-click protection from malicious URLs and files is available in subscriptions that include [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP), and is set up through [ATP Safe Attachments](atp-safe-attachments.md) and [ATP Safe Links](atp-safe-links.md) policies.</span></span>

### <a name="atp-safe-attachments-policies"></a><span data-ttu-id="69e05-154">Политики безопасных вложений ATP</span><span class="sxs-lookup"><span data-stu-id="69e05-154">ATP Safe Attachments policies</span></span>

<span data-ttu-id="69e05-155">Чтобы настроить [безопасные вложения ATP,](atp-safe-attachments.md)необходимо определить по крайней мере одну политику безопасных вложений ATP.</span><span class="sxs-lookup"><span data-stu-id="69e05-155">To set up [ATP Safe Attachments](atp-safe-attachments.md), you must define at least one ATP Safe Attachments policy.</span></span>

1. <span data-ttu-id="69e05-156">В Центре [безопасности & выберите](https://protection.office.com) **безопасные**  >  **вложения**  >  **ATP с политикой управления угрозами.**</span><span class="sxs-lookup"><span data-stu-id="69e05-156">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP safe attachments**.</span></span>

2. <span data-ttu-id="69e05-157">Выберите параметр **"Включить ATP для SharePoint, OneDrive и Microsoft Teams".**</span><span class="sxs-lookup"><span data-stu-id="69e05-157">Select the option **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

3. <span data-ttu-id="69e05-158">В разделе **"Защита вложений электронной почты"** выберите знак "плюс" ( **+**</span><span class="sxs-lookup"><span data-stu-id="69e05-158">In the **Protect email attachments** section, click the plus sign (**+**).</span></span>

4. <span data-ttu-id="69e05-159">Укажите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="69e05-159">Specify the following settings:</span></span>

   - <span data-ttu-id="69e05-160">В поле **"Имя"** введите `Block malware` .</span><span class="sxs-lookup"><span data-stu-id="69e05-160">In the **Name** box, type `Block malware`.</span></span>

   - <span data-ttu-id="69e05-161">В разделе ответа выберите **"Блокировать".**</span><span class="sxs-lookup"><span data-stu-id="69e05-161">In the response section, choose **Block**.</span></span>

   - <span data-ttu-id="69e05-162">В разделе **"Перенаправление вложений"** выберите параметр **"Включить перенаправление"** и укажите адрес электронной почты администратора безопасности вашей организации или оператора, который будет проверять обнаруженные файлы.</span><span class="sxs-lookup"><span data-stu-id="69e05-162">In the **Redirect attachment** section, select the option **Enable redirect**, and then specify the email address for your organization's security administrator or operator who will review detected files.</span></span>

   - <span data-ttu-id="69e05-163">В разделе **"Применяется** к **разделу" выберите домен получателя.**</span><span class="sxs-lookup"><span data-stu-id="69e05-163">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="69e05-164">Затем выберите домен, нажмите кнопку **"Добавить",** а затем нажмите кнопку **ОК.**</span><span class="sxs-lookup"><span data-stu-id="69e05-164">Then, select your domain, choose **Add**, and then click **OK**.</span></span>

5. <span data-ttu-id="69e05-165">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="69e05-165">Click **Save**.</span></span>

6. <span data-ttu-id="69e05-166">**(Рекомендуется дополнительного шага)** Как глобальный администратор или администратор SharePoint Online выполните **[командлет Set-SPOTenant,](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** у которого **для параметра DisallowInfectedFileDownload** *установлено* значение true для вашей среды Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="69e05-166">(**Recommended additional step**) As a global administrator or a SharePoint Online administrator run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet with the **DisallowInfectedFileDownload** parameter set to  *true* for your Microsoft 365 environment.</span></span> <span data-ttu-id="69e05-167">(Это не позволяет открывать, перемещать, копировать и совместно использовать файлы, которые станут вредоносными.)</span><span class="sxs-lookup"><span data-stu-id="69e05-167">(This prevents people from opening, moving, copying, or sharing files that are detected as malicious.)</span></span>

<span data-ttu-id="69e05-168">Дополнительные сведения см. в статье ["Настройка политик безопасных вложений ATP Office 365"](set-up-atp-safe-attachments-policies.md) и включение [Office 365 ATP для SharePoint, OneDrive и Microsoft Teams.](turn-on-atp-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="69e05-168">To learn more, see [Set up Office 365 ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="atp-safe-links-policies"></a><span data-ttu-id="69e05-169">Политики безопасных ссылок ATP</span><span class="sxs-lookup"><span data-stu-id="69e05-169">ATP Safe Links policies</span></span>

<span data-ttu-id="69e05-170">Чтобы настроить [безопасные ссылки ATP,](atp-safe-links.md)проверьте и измените политику по умолчанию, а также добавьте политику для определенных пользователей.</span><span class="sxs-lookup"><span data-stu-id="69e05-170">To set up [ATP Safe Links](atp-safe-links.md), review and edit your default policy, and add a policy for specific users.</span></span>

1. <span data-ttu-id="69e05-171">В Центре [безопасности & выберите](https://protection.office.com)пункт **"Безопасные**  >  **ссылки**  >  **ATP" в "Политика управления угрозами".**</span><span class="sxs-lookup"><span data-stu-id="69e05-171">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP Safe Links**.</span></span>

2. <span data-ttu-id="69e05-172">Дважды щелкните **политику по умолчанию.**</span><span class="sxs-lookup"><span data-stu-id="69e05-172">Double-click the **Default** policy.</span></span>

3. <span data-ttu-id="69e05-173">В разделе **"Использование безопасных ссылок"** выберите вариант **"Приложения Microsoft 365 для предприятий", "Office для iOS и Android"** и нажмите кнопку **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="69e05-173">In the **Use safe links in** section, select the option **Microsoft 365 Apps for enterprise, Office for iOS and Android**, and then click **Save**.</span></span>

4. <span data-ttu-id="69e05-174">В разделе **"Политики", применяемые к определенным получателям,** щелкните знак "плюс" **+** ().).</span><span class="sxs-lookup"><span data-stu-id="69e05-174">In the **Policies that apply to specific recipients** section, click the plus sign (**+**).</span></span>

5. <span data-ttu-id="69e05-175">Укажите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="69e05-175">Specify the following settings:</span></span>

   - <span data-ttu-id="69e05-176">В поле **"Имя"** введите имя, `Safe Links` например.</span><span class="sxs-lookup"><span data-stu-id="69e05-176">In the **Name** box, type a name, such as `Safe Links`.</span></span>

   - <span data-ttu-id="69e05-177">В разделе **выбора действия** выберите **"Вкл.".**</span><span class="sxs-lookup"><span data-stu-id="69e05-177">In the **Select the action** section, choose **On**.</span></span>

   - <span data-ttu-id="69e05-178">Выберите эти параметры:</span><span class="sxs-lookup"><span data-stu-id="69e05-178">Select these options:</span></span>

     - <span data-ttu-id="69e05-179">**Использование безопасных вложений для проверки загружаемого содержимого**</span><span class="sxs-lookup"><span data-stu-id="69e05-179">**Use safe attachments to scan downloadable content**</span></span>

     - <span data-ttu-id="69e05-180">**Применение безопасных ссылок к сообщениям электронной почты, отправляемым в пределах организации**</span><span class="sxs-lookup"><span data-stu-id="69e05-180">**Apply safe links to email messages sent within the organization**</span></span>

     - <span data-ttu-id="69e05-181">**Не разрешать пользователям переходить по безопасным ссылкам на исходный URL-адрес**</span><span class="sxs-lookup"><span data-stu-id="69e05-181">**Do not let users click through safe links to original URL**</span></span>

   - <span data-ttu-id="69e05-182">В разделе **"Применяется** к **разделу" выберите домен получателя.**</span><span class="sxs-lookup"><span data-stu-id="69e05-182">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="69e05-183">Затем выберите домен, нажмите кнопку **"Добавить",** а затем нажмите кнопку **ОК.**</span><span class="sxs-lookup"><span data-stu-id="69e05-183">Then, select your domain, choose **Add**, and then click **OK**.</span></span>

6. <span data-ttu-id="69e05-184">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="69e05-184">Click **Save**.</span></span>

<span data-ttu-id="69e05-185">Дополнительные сведения см. в статье [Настройка политик безопасных ссылок ATP в Office 365](set-up-atp-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="69e05-185">To learn more, see [Set up Office 365 ATP Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

## <a name="part-3---anti-phishing-protection"></a><span data-ttu-id="69e05-186">Часть 3. Защита от фишинга</span><span class="sxs-lookup"><span data-stu-id="69e05-186">Part 3 - Anti-phishing protection</span></span>

<span data-ttu-id="69e05-187">[Защита от фишинга]</span><span class="sxs-lookup"><span data-stu-id="69e05-187">[Anti-phishing]</span></span>

<span data-ttu-id="69e05-188">[Защита от фишинга доступна](anti-phishing-protection.md) в подписках, включающих [EOP.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)</span><span class="sxs-lookup"><span data-stu-id="69e05-188">[Anti-phishing protection](anti-phishing-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span> <span data-ttu-id="69e05-189">Расширенная защита от фишинга доступна [в ATP.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)</span><span class="sxs-lookup"><span data-stu-id="69e05-189">Advanced anti-phishing protection is available in [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

<span data-ttu-id="69e05-190">Ниже описана настройка политики защиты от фишинга ATP.</span><span class="sxs-lookup"><span data-stu-id="69e05-190">The following procedure describes how to configure an ATP anti-phishing policy.</span></span> <span data-ttu-id="69e05-191">Действия аналогичны настройке политики защиты от фишинга (без ATP).</span><span class="sxs-lookup"><span data-stu-id="69e05-191">The steps are similar for configuring an anti-phishing policy (without ATP).</span></span>

1. <span data-ttu-id="69e05-192">В [Центре безопасности & выберите](https://protection.office.com) **защиту от фишинга**политики  >  **Policy**  >  **управления угрозами ATP.**</span><span class="sxs-lookup"><span data-stu-id="69e05-192">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="69e05-193">Щелкните **"Политика по умолчанию".**</span><span class="sxs-lookup"><span data-stu-id="69e05-193">Click **Default policy**.</span></span>

3. <span data-ttu-id="69e05-194">В разделе **олицетворения** нажмите **кнопку "Изменить"** и укажите следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="69e05-194">In the **Impersonation** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="69e05-195">На вкладке **"Добавить пользователей для защиты"** включите защиту.</span><span class="sxs-lookup"><span data-stu-id="69e05-195">On the **Add users to protect** tab, turn protection on.</span></span> <span data-ttu-id="69e05-196">Затем добавьте пользователей, например членов доски вашей организации, исследовательский директор, использованный директор и другие старшего входящего директора.</span><span class="sxs-lookup"><span data-stu-id="69e05-196">Then add users, such as your organization's board members, your CEO, CFO, and other senior leaders.</span></span> <span data-ttu-id="69e05-197">(Можно ввести отдельный адрес электронной почты или щелкнуть для отображения списка.)</span><span class="sxs-lookup"><span data-stu-id="69e05-197">(You can type an individual email address, or click to display a list.)</span></span>

   - <span data-ttu-id="69e05-198">На вкладке **"Добавить домены для защиты"** включите параметр "Автоматически включить **в ключ и домены, принадлежащие мне"**</span><span class="sxs-lookup"><span data-stu-id="69e05-198">On the **Add domains to protect** tab, turn on **Automatically include the domains I own**.</span></span> <span data-ttu-id="69e05-199">Если у вас есть пользовательские домены, добавьте их и для них.</span><span class="sxs-lookup"><span data-stu-id="69e05-199">If you have custom domains, add those as well.</span></span>

   - <span data-ttu-id="69e05-200">На вкладке **"Действия"** выберите **"Поместить сообщение на** карантин" для **олицетворенного** пользователя и **олицетворенного** домена.</span><span class="sxs-lookup"><span data-stu-id="69e05-200">On the **Actions** tab, select **Quarantine the message** for both the **impersonated user** and **impersonated domain** options.</span></span> <span data-ttu-id="69e05-201">Кроме того, включите советы по безопасности олицетворения.</span><span class="sxs-lookup"><span data-stu-id="69e05-201">In addition, turn on impersonation safety tips.</span></span>

   - <span data-ttu-id="69e05-202">На **вкладке "Аналитика почтовых ящиков"** убедитесь, что аналитика почтового ящика включена.</span><span class="sxs-lookup"><span data-stu-id="69e05-202">On the **Mailbox intelligence** tab, make sure mailbox intelligence is turned on.</span></span> <span data-ttu-id="69e05-203">Кроме того, включите защиту от олицетворения на основе аналитики почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="69e05-203">In addition, turn on mailbox intelligence based impersonation protection.</span></span> <span data-ttu-id="69e05-204">Если сообщение **отправляется из олицетворенного** списка пользователей, выберите команду **"Поместить сообщение в карантин".**</span><span class="sxs-lookup"><span data-stu-id="69e05-204">In the **If email is sent by an impersonated user** list, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="69e05-205">На **вкладке "Добавление надежных отправителей и доменов"** укажите надежных отправителей или домены для добавления.</span><span class="sxs-lookup"><span data-stu-id="69e05-205">On the **Add trusted senders and domains** tab, specify any trusted senders or domains that you want to add.</span></span>

   - <span data-ttu-id="69e05-206">На **вкладке "Проверьте параметры"** после проверки параметров нажмите кнопку **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="69e05-206">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span>

4. <span data-ttu-id="69e05-207">В разделе **"Подделка"** щелкните **"Изменить"** и укажите следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="69e05-207">In the **Spoof** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="69e05-208">На **вкладке параметров фильтра подделок** убедитесь, что защита от спуфинга включена.</span><span class="sxs-lookup"><span data-stu-id="69e05-208">On the **Spoofing filter settings** tab, make sure anti-spoofing protection is turned on.</span></span>

   - <span data-ttu-id="69e05-209">На вкладке **"Действия" выберите** пункт **"Поместить сообщение в карантин".**</span><span class="sxs-lookup"><span data-stu-id="69e05-209">On the **Actions** tab, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="69e05-210">На **вкладке "Проверьте параметры"** после проверки параметров нажмите кнопку **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="69e05-210">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span> <span data-ttu-id="69e05-211">(Если вы не вносили никаких изменений, нажмите кнопку **Отмена.**</span><span class="sxs-lookup"><span data-stu-id="69e05-211">(If you didn't make any changes, click **Cancel**.)</span></span>

5. <span data-ttu-id="69e05-212">Закройте страницу параметров политики по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="69e05-212">Close the default policy settings page.</span></span>

<span data-ttu-id="69e05-213">Дополнительные сведения о параметрах политики защиты от фишинга см. в статье ["Настройка политик защиты от фишинга" ATP.](configure-atp-anti-phishing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="69e05-213">To learn more about your anti-phishing policy options, see [Configure ATP anti-phishing policies](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="part-4---anti-spam-protection"></a><span data-ttu-id="69e05-214">Часть 4. Защита от нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="69e05-214">Part 4 - Anti-spam protection</span></span>

<span data-ttu-id="69e05-215">[Защита от нежелательной](anti-spam-protection.md) почты доступна в подписках, включающих [EOP.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)</span><span class="sxs-lookup"><span data-stu-id="69e05-215">[Anti-spam protection](anti-spam-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="69e05-216">В Центре [безопасности & выберите защиту](https://protection.office.com) **от**  >  **Policy**  >  **политики управления угрозами.**</span><span class="sxs-lookup"><span data-stu-id="69e05-216">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-spam**.</span></span>

2. <span data-ttu-id="69e05-217">На вкладке **Custom (Настраиваемые)** включите **независимые** параметры.</span><span class="sxs-lookup"><span data-stu-id="69e05-217">On the **Custom** tab, turn **Custom settings** on.</span></span>

3. <span data-ttu-id="69e05-218">Разверните **"Политика фильтрации нежелательной почты по**умолчанию", **щелкните**"Изменить политику" и укажите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="69e05-218">Expand **Default spam filter policy**, click **Edit policy**, and then specify the following settings:</span></span>

   - <span data-ttu-id="69e05-219">В разделе **"Нежелательная почта и** массовые действия" установите для порога значение 5 или 6.</span><span class="sxs-lookup"><span data-stu-id="69e05-219">In the **Spam and bulk actions** section, set the threshold to a value of 5 or 6.</span></span>

   - <span data-ttu-id="69e05-220">В разделе **списков разрешений** просмотрите (и, при необходимости, измените список разрешенных отправителей и доменов).</span><span class="sxs-lookup"><span data-stu-id="69e05-220">In the **Allow lists** section, review (and if necessary, edit) your allowed senders and domains.</span></span>

4. <span data-ttu-id="69e05-221">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="69e05-221">Click **Save**.</span></span>

<span data-ttu-id="69e05-222">Дополнительные сведения о параметрах политики защиты от нежелательной почты см. в статье ["Настройка политик защиты от нежелательной почты" в EOP.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="69e05-222">To learn more about your anti-spam policy options, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="part-5---additional-settings-to-configure"></a><span data-ttu-id="69e05-223">Часть 5. Дополнительные параметры, которые необходимо настроить</span><span class="sxs-lookup"><span data-stu-id="69e05-223">Part 5 - Additional settings to configure</span></span>

<span data-ttu-id="69e05-224">Помимо настройки защиты от вредоносных, вредоносных URL-адресов и файлов, фишинговых сообщений и спама рекомендуется настроить параметры автоматической очистки и ведения журнала аудита.</span><span class="sxs-lookup"><span data-stu-id="69e05-224">In addition to configuring protection from malware, malicious URLs and files, phishing, and spam, we recommend that you configure your zero-hour auto purge and audit logging settings.</span></span>

### <a name="zero-hour-auto-purge-for-email"></a><span data-ttu-id="69e05-225">Автоматическая очистка электронной почты</span><span class="sxs-lookup"><span data-stu-id="69e05-225">Zero-hour auto purge for email</span></span>

<span data-ttu-id="69e05-226">[Автоматическая очистка](zero-hour-auto-purge.md) (ZAP) доступна в подписках, включающих [EOP.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)</span><span class="sxs-lookup"><span data-stu-id="69e05-226">[Zero-hour auto purge](zero-hour-auto-purge.md) (ZAP) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span> <span data-ttu-id="69e05-227">Защита включена по умолчанию; Однако для обеспечения их защиты необходимо соблюдать следующие условия:</span><span class="sxs-lookup"><span data-stu-id="69e05-227">This protection is turned on by default; however, the following conditions must be met for protection to be in effect:</span></span>

- <span data-ttu-id="69e05-228">Действия с нежелательной почтой настроены на **перемещение сообщений в папку нежелательной почты в** [политиках защиты от нежелательной почты.](anti-spam-protection.md)</span><span class="sxs-lookup"><span data-stu-id="69e05-228">Spam actions are set to **Move message to Junk Email folder** in [anti-spam policies](anti-spam-protection.md).</span></span>

- <span data-ttu-id="69e05-229">Пользователи сохращают параметры [нежелательной почты](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)по умолчанию и не отключили защиту от нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="69e05-229">Users have kept their default [junk email settings](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md), and have not turned off junk email protection.</span></span>

<span data-ttu-id="69e05-230">Дополнительные сведения см. в статье ["Автоматическая очистка" для защиты от спама и вредоносных программ.](zero-hour-auto-purge.md)</span><span class="sxs-lookup"><span data-stu-id="69e05-230">To learn more, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

### <a name="audit-logging-for-reporting-and-investigation"></a><span data-ttu-id="69e05-231">Ведение журнала аудита для отчетности и исследования</span><span class="sxs-lookup"><span data-stu-id="69e05-231">Audit logging for reporting and investigation</span></span>

<span data-ttu-id="69e05-232">Ведение журнала аудита доступно в подписках, включающих [Exchange Online.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)</span><span class="sxs-lookup"><span data-stu-id="69e05-232">Audit logging is available in subscriptions that include [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description).</span></span> <span data-ttu-id="69e05-233">Чтобы просматривать данные в отчетах о защите от угроз, таких как [информационная](security-dashboard.md)панель безопасности, [отчеты о безопасности](view-email-security-reports.md)электронных писем и [проводник,](threat-explorer.md)необходимо включить ведение журнала аудита для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="69e05-233">In order to view data in threat protection reports, such as the [Security Dashboard](security-dashboard.md), [email security reports](view-email-security-reports.md), and [Explorer](threat-explorer.md), audit logging must be turned on for your organization.</span></span> <span data-ttu-id="69e05-234">Дополнительные сведения см. в разделе ["Включение и отключение поиска в журнале аудита".](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="69e05-234">To learn more, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="post-setup-tasks"></a><span data-ttu-id="69e05-235">Задачи, выполняемые после установки</span><span class="sxs-lookup"><span data-stu-id="69e05-235">Post-setup tasks</span></span>

<span data-ttu-id="69e05-236">После настройки функций защиты от угроз обязательно отслеживайте работу этих функций, проверяйте и вносите изменения в свои политики при необходимости, а также просматривайте новые функции и обновления служб.</span><span class="sxs-lookup"><span data-stu-id="69e05-236">After you have configured your threat protection features, make sure to monitor how those features are working, review and revise your policies as needed, and watch for new features and service updates.</span></span>

****

|<span data-ttu-id="69e05-237">Действия</span><span class="sxs-lookup"><span data-stu-id="69e05-237">What to do</span></span>|<span data-ttu-id="69e05-238">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="69e05-238">Resources to learn more</span></span>|
|---|---|
|<span data-ttu-id="69e05-239">Узнайте, как функции защиты от угроз работают в вашей организации путем просмотра отчетов</span><span class="sxs-lookup"><span data-stu-id="69e05-239">See how threat protection features are working for your organization by viewing reports</span></span>|[<span data-ttu-id="69e05-240">Информационная панель безопасности</span><span class="sxs-lookup"><span data-stu-id="69e05-240">Security dashboard</span></span>](security-dashboard.md)<br/>[<span data-ttu-id="69e05-241">Отчеты о безопасности электронной почты</span><span class="sxs-lookup"><span data-stu-id="69e05-241">Email security reports</span></span>](view-email-security-reports.md)<br/>[<span data-ttu-id="69e05-242">Отчеты для Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="69e05-242">Reports for Office 365 ATP</span></span>](view-reports-for-atp.md)<br/>[<span data-ttu-id="69e05-243">Обозреватель угроз</span><span class="sxs-lookup"><span data-stu-id="69e05-243">Threat Explorer</span></span>](threat-explorer.md)|
|<span data-ttu-id="69e05-244">Периодический просмотр и изменение политик защиты от угроз по мере необходимости</span><span class="sxs-lookup"><span data-stu-id="69e05-244">Periodically review and revise your threat protection policies as needed</span></span>|[<span data-ttu-id="69e05-245">Оценка безопасности</span><span class="sxs-lookup"><span data-stu-id="69e05-245">Secure Score</span></span>](../mtp/microsoft-secure-score.md)<br/>[<span data-ttu-id="69e05-246">Интеллектуальная аналитика и аналитика</span><span class="sxs-lookup"><span data-stu-id="69e05-246">Smart reports and insights</span></span>](reports-and-insights-in-security-and-compliance.md)<br/>[<span data-ttu-id="69e05-247">Функции анализа угроз и реагирования на них в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="69e05-247">Microsoft 365 threat investigation and response features</span></span>](keep-users-safe-with-office-365-ti.md)|
|<span data-ttu-id="69e05-248">Смотрите на наличие новых функций и обновлений служб</span><span class="sxs-lookup"><span data-stu-id="69e05-248">Watch for new features and service updates</span></span>|[<span data-ttu-id="69e05-249">Варианты выпусков стандартных и целевых версий</span><span class="sxs-lookup"><span data-stu-id="69e05-249">Standard and Targeted release options</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365)<br/>[<span data-ttu-id="69e05-250">Центр сообщений</span><span class="sxs-lookup"><span data-stu-id="69e05-250">Message Center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/message-center)<br/>[<span data-ttu-id="69e05-251">План развития Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="69e05-251">Microsoft 365 Roadmap</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)<br/>[<span data-ttu-id="69e05-252">Описания служб</span><span class="sxs-lookup"><span data-stu-id="69e05-252">Service Descriptions</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|
