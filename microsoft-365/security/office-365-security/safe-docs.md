---
title: Безопасные документы в Microsoft Defender для Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Узнайте о безопасных документах в Microsoft 365 E5 или Microsoft 365 E5 Security.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1186c7856d0b979c483cf6dd1c0a010ab582e2ce
ms.sourcegitcommit: 437bdbf3f99610869811e80432a59b5f244f7a87
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2021
ms.locfileid: "51644756"
---
# <a name="safe-documents-in-microsoft-365-e5"></a><span data-ttu-id="95601-103">Безопасные документы в Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="95601-103">Safe Documents in Microsoft 365 E5</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="95601-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="95601-104">**Applies to**</span></span>
- [<span data-ttu-id="95601-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="95601-105">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="95601-106">Безопасные документы — это функция в Microsoft 365 E5 или Microsoft 365 E5 Security, которая использует [](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653) [Microsoft Defender для](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) конечной точки для сканирования документов и файлов, открытых в защищенном представлении или в Службе безопасности приложений [для Office.](https://support.microsoft.com/topic/9e0fb9c2-ffad-43bf-8ba3-78f785fdba46)</span><span class="sxs-lookup"><span data-stu-id="95601-106">Safe Documents is a feature in Microsoft 365 E5 or Microsoft 365 E5 Security that uses [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653) or [Application Guard for Office](https://support.microsoft.com/topic/9e0fb9c2-ffad-43bf-8ba3-78f785fdba46).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="95601-107">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="95601-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="95601-108">Безопасные документы доступны только пользователям с лицензиями *microsoft 365 E5* или *Microsoft 365 E5 Security.*</span><span class="sxs-lookup"><span data-stu-id="95601-108">Safe Documents is available only to users with *Microsoft 365 E5* or *Microsoft 365 E5 Security* licenses.</span></span> <span data-ttu-id="95601-109">Эти лицензии не включены в планы Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="95601-109">These licenses are not included in Microsoft Defender for Office 365 plans.</span></span>

- <span data-ttu-id="95601-110">Безопасные документы поддерживаются в Microsoft 365 Apps для предприятия (ранее известная как Office 365 ProPlus) версии 2004 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="95601-110">Safe Documents is supported in Microsoft 365 Apps for enterprise (formerly known as Office 365 ProPlus) version 2004 or later.</span></span>

- <span data-ttu-id="95601-111">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="95601-111">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="95601-112">Чтобы перейти непосредственно на страницу БЕЗОПАСНЫЕ вложения **ATP,** откройте <https://protection.office.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="95601-112">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="95601-113">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="95601-113">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="95601-114">Для выполнения процедур, описанных в этой статье, вам должны быть назначены разрешения в **Exchange Online**:</span><span class="sxs-lookup"><span data-stu-id="95601-114">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="95601-115">Чтобы настроить параметры "Безопасные документы", необходимо быть членом группы ролей **"Управление** организацией" или **"Администратор** безопасности".</span><span class="sxs-lookup"><span data-stu-id="95601-115">To configure Safe Documents settings, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="95601-116">Для доступа только для чтения к настройкам безопасных документов необходимо быть членом групп ролей **Global Reader** или **Security Reader.**</span><span class="sxs-lookup"><span data-stu-id="95601-116">For read-only access to Safe Documents settings, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="95601-117">Дополнительные сведения см. в статье [Разрешения в Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="95601-117">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="95601-118">Добавление пользователей в соответствующую роль Azure Active Directory в Центре безопасности Microsoft 365 предоставляет пользователям необходимые разрешения _и_ разрешения для других функций в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="95601-118">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="95601-119">Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="95601-119">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="95601-120">Группа ролей **Управление организацией с правами только на просмотр** в [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) также предоставляет доступ только для чтения к этой функции.</span><span class="sxs-lookup"><span data-stu-id="95601-120">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

### <a name="how-does-microsoft-handle-your-data"></a><span data-ttu-id="95601-121">Как Корпорация Майкрософт обрабатывает ваши данные?</span><span class="sxs-lookup"><span data-stu-id="95601-121">How does Microsoft handle your data?</span></span>

<span data-ttu-id="95601-122">Чтобы защититься, safe Documents отправляет файлы в [облако Microsoft Defender для конечной](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) точки для анализа.</span><span class="sxs-lookup"><span data-stu-id="95601-122">To keep you protected, Safe Documents sends files to the [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span> <span data-ttu-id="95601-123">Сведения о том, как Microsoft Defender для конечной точки обрабатывает данные, можно найти здесь: Microsoft Defender для хранения и конфиденциальности данных [конечных точек.](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)</span><span class="sxs-lookup"><span data-stu-id="95601-123">Details on how Microsoft Defender for Endpoint handles your data can be found here: [Microsoft Defender for Endpoint data storage and privacy](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span>

<span data-ttu-id="95601-124">Файлы, отправленные безопасными документами, не сохраняются в Defender после времени, необходимого для анализа (как правило, менее 24 часов).</span><span class="sxs-lookup"><span data-stu-id="95601-124">Files sent by Safe Documents are not retained in Defender beyond the time needed for analysis (typically, less than 24 hours).</span></span>

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="95601-125">Используйте Центр & безопасности для настройки безопасных документов</span><span class="sxs-lookup"><span data-stu-id="95601-125">Use the Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="95601-126">В Центре обеспечения & безопасности перейдите к политике управления угрозами  \>  \> **ATP Safe Attachments,** а затем щелкните **глобальные параметры.**</span><span class="sxs-lookup"><span data-stu-id="95601-126">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="95601-127">В **глобальных параметрах** вылет, который появляется, настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="95601-127">In the **Global settings** fly out that appears, configure the following settings:</span></span>

   - <span data-ttu-id="95601-128">**Включим безопасные** документы для клиентов Office: переместите переключеть вправо, чтобы включить функцию: ![ ](../../media/scc-toggle-on.png) Включить.</span><span class="sxs-lookup"><span data-stu-id="95601-128">**Turn on Safe Documents for Office clients**: Move the toggle to the right to turn on the feature: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   - <span data-ttu-id="95601-129">**Разрешить** пользователям щелкнуть защищенный просмотр, даже если "Безопасные документы" идентифицируют файл как вредоносный. Рекомендуется оставить этот параметр отключенным (оставьте переключенку слева: отключите). ![ ](../../media/scc-toggle-off.png)</span><span class="sxs-lookup"><span data-stu-id="95601-129">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious**: We recommend that you leave this option turned off (leave the toggle to the left: ![Toggle off](../../media/scc-toggle-off.png)).</span></span>

   <span data-ttu-id="95601-130">По завершении нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="95601-130">When you're finished, click **Save**.</span></span>

   ![Параметры Безопасные документы после выбора глобальных параметров на странице Безопасные вложения.](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a><span data-ttu-id="95601-132">Использование Exchange Online PowerShell для настройки безопасных документов</span><span class="sxs-lookup"><span data-stu-id="95601-132">Use Exchange Online PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="95601-133">Используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="95601-133">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- <span data-ttu-id="95601-134">Параметр _EnableSafeDocs_ включает или отключает безопасные документы для всей организации.</span><span class="sxs-lookup"><span data-stu-id="95601-134">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>
- <span data-ttu-id="95601-135">Параметр _AllowSafeDocsOpen_ позволяет пользователям покидать защищенный вид (т. е. открывать документ), если документ был идентифицирован как вредоносный.</span><span class="sxs-lookup"><span data-stu-id="95601-135">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="95601-136">В этом примере можно включить безопасные документы для всей организации и запретить пользователям открывать документы, которые были идентифицированы как вредоносные из защищенного представления.</span><span class="sxs-lookup"><span data-stu-id="95601-136">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="95601-137">Подробные сведения о синтаксисах и параметрах см. в [инструкции Set-AtpPolicyForO365.](/powershell/module/exchange/set-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="95601-137">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="onboard-to-the-microsoft-defender-for-endpoint-service-to-enable-auditing-capabilities"></a><span data-ttu-id="95601-138">На борту службы Microsoft Defender для конечных точек, чтобы включить возможности аудита</span><span class="sxs-lookup"><span data-stu-id="95601-138">Onboard to the Microsoft Defender for Endpoint Service to enable auditing capabilities</span></span>

<span data-ttu-id="95601-139">Чтобы развернуть Microsoft Defender для конечной точки, необходимо пройти различные этапы развертывания.</span><span class="sxs-lookup"><span data-stu-id="95601-139">To deploy Microsoft Defender for Endpoint, you need to go through the various phases of deployment.</span></span> <span data-ttu-id="95601-140">После взбора можно настроить возможности аудита в Центре & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="95601-140">After onboarding, you can configure auditing capabilities in the Security & Compliance Center.</span></span>

<span data-ttu-id="95601-141">Дополнительные дополнительные информации см. в таблице [Onboard в службе Microsoft Defender for Endpoint.](/microsoft-365/security/defender-endpoint/onboarding)</span><span class="sxs-lookup"><span data-stu-id="95601-141">To learn more, see [Onboard to the Microsoft Defender for Endpoint service](/microsoft-365/security/defender-endpoint/onboarding).</span></span> <span data-ttu-id="95601-142">Если вам нужна дополнительная помощь, обратитесь к проблеме устранения неполадок [Microsoft Defender для конечной](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding)точки.</span><span class="sxs-lookup"><span data-stu-id="95601-142">If you need additional help, please refer to [Troubleshoot Microsoft Defender for Endpoint onboarding issues](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="95601-143">Как проверить, что это работает?</span><span class="sxs-lookup"><span data-stu-id="95601-143">How do I know this worked?</span></span>

<span data-ttu-id="95601-144">Чтобы убедиться, что вы включили и настроили безопасные документы, сделайте все следующие действия:</span><span class="sxs-lookup"><span data-stu-id="95601-144">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="95601-145">В Центре обеспечения & безопасности перейдите к политике управления угрозами ATP Safe  \>  \> **Attachments,**   щелкните Глобальные параметры и убедитесь, что включите безопасные документы для клиентов **Office** и разрешите пользователям щелкнуть защищенный просмотр, даже если "Безопасные документы" идентифицируют файл как вредоносные параметры.</span><span class="sxs-lookup"><span data-stu-id="95601-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, click **Global settings**, and verify the **Turn on Safe Documents for Office clients** and **Allow people to click through Protected View even if Safe Documents identifies the file as malicious** settings.</span></span>

- <span data-ttu-id="95601-146">Запустите следующую команду в Exchange Online PowerShell и проверьте значения свойств:</span><span class="sxs-lookup"><span data-stu-id="95601-146">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- <span data-ttu-id="95601-147">Следующие файлы доступны для тестирования защиты безопасных документов.</span><span class="sxs-lookup"><span data-stu-id="95601-147">The following files are available to test Safe Documents protection.</span></span> <span data-ttu-id="95601-148">Эти документы похожи на файл EICAR.TXT для тестирования решений по борьбе с вредоносными программами и антивирусами.</span><span class="sxs-lookup"><span data-stu-id="95601-148">These documents are similar to the EICAR.TXT file for testing anti-malware and anti-virus solutions.</span></span> <span data-ttu-id="95601-149">Файлы не являются вредными, но они будут запускать защиту безопасных документов.</span><span class="sxs-lookup"><span data-stu-id="95601-149">The files are not harmful, but they will trigger Safe Documents protection.</span></span>

  - [<span data-ttu-id="95601-150">SafeDocsDemo.docx</span><span class="sxs-lookup"><span data-stu-id="95601-150">SafeDocsDemo.docx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [<span data-ttu-id="95601-151">SafeDocsDemo.pptx</span><span class="sxs-lookup"><span data-stu-id="95601-151">SafeDocsDemo.pptx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [<span data-ttu-id="95601-152">SafeDocsDemo.xlsx</span><span class="sxs-lookup"><span data-stu-id="95601-152">SafeDocsDemo.xlsx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
