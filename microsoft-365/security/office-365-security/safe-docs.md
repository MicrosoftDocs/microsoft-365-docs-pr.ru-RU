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
description: Узнайте о Сейф документах в Microsoft 365 E5 или Безопасность Microsoft 365 E5.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1186c7856d0b979c483cf6dd1c0a010ab582e2ce
ms.sourcegitcommit: 437bdbf3f99610869811e80432a59b5f244f7a87
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2021
ms.locfileid: "51644756"
---
# <a name="safe-documents-in-microsoft-365-e5"></a><span data-ttu-id="ddbca-103">Безопасные документы в Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="ddbca-103">Safe Documents in Microsoft 365 E5</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ddbca-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="ddbca-104">**Applies to**</span></span>
- [<span data-ttu-id="ddbca-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ddbca-105">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="ddbca-106">Сейф Документы — это функция в Microsoft 365 E5 или Безопасность Microsoft 365 E5, которая использует [Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) для конечной точки [](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653) для сканирования документов и файлов, открытых в защищенных представлениях или в службе безопасности приложений [для Office](https://support.microsoft.com/topic/9e0fb9c2-ffad-43bf-8ba3-78f785fdba46).</span><span class="sxs-lookup"><span data-stu-id="ddbca-106">Safe Documents is a feature in Microsoft 365 E5 or Microsoft 365 E5 Security that uses [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653) or [Application Guard for Office](https://support.microsoft.com/topic/9e0fb9c2-ffad-43bf-8ba3-78f785fdba46).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ddbca-107">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="ddbca-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ddbca-108">Сейф Документы доступны только пользователям  с Microsoft 365 E5 *или Безопасность Microsoft 365 E5* лицензиями.</span><span class="sxs-lookup"><span data-stu-id="ddbca-108">Safe Documents is available only to users with *Microsoft 365 E5* or *Microsoft 365 E5 Security* licenses.</span></span> <span data-ttu-id="ddbca-109">Эти лицензии не включены в Microsoft Defender для Office 365 планов.</span><span class="sxs-lookup"><span data-stu-id="ddbca-109">These licenses are not included in Microsoft Defender for Office 365 plans.</span></span>

- <span data-ttu-id="ddbca-110">Сейф Документы поддерживаются в Приложения Microsoft 365 для предприятий версии 2004 Office 365 профессиональный плюс версии 2004 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="ddbca-110">Safe Documents is supported in Microsoft 365 Apps for enterprise (formerly known as Office 365 ProPlus) version 2004 or later.</span></span>

- <span data-ttu-id="ddbca-111">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="ddbca-111">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="ddbca-112">Чтобы перейти непосредственно на **страницу ATP Сейф вложения,** откройте <https://protection.office.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="ddbca-112">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="ddbca-113">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="ddbca-113">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="ddbca-114">Для выполнения процедур, описанных в этой статье, вам должны быть назначены разрешения в **Exchange Online**:</span><span class="sxs-lookup"><span data-stu-id="ddbca-114">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="ddbca-115">Чтобы настроить Сейф документов, необходимо быть членом групп ролей **администратора** организации или **администратора** безопасности.</span><span class="sxs-lookup"><span data-stu-id="ddbca-115">To configure Safe Documents settings, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="ddbca-116">Для доступа только для чтения Сейф параметров документов необходимо быть членом групп ролей **Global Reader** или **Security Reader.**</span><span class="sxs-lookup"><span data-stu-id="ddbca-116">For read-only access to Safe Documents settings, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="ddbca-117">Дополнительные сведения см. в статье [Разрешения в Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="ddbca-117">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="ddbca-118">Добавление пользователей в соответствующую роль Azure Active Directory в Центре безопасности Microsoft 365 предоставляет пользователям необходимые разрешения _и_ разрешения для других функций в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ddbca-118">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="ddbca-119">Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="ddbca-119">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="ddbca-120">Группа ролей **Управление организацией с правами только на просмотр** в [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) также предоставляет доступ только для чтения к этой функции.</span><span class="sxs-lookup"><span data-stu-id="ddbca-120">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

### <a name="how-does-microsoft-handle-your-data"></a><span data-ttu-id="ddbca-121">Как Корпорация Майкрософт обрабатывает ваши данные?</span><span class="sxs-lookup"><span data-stu-id="ddbca-121">How does Microsoft handle your data?</span></span>

<span data-ttu-id="ddbca-122">Чтобы защититься, Сейф документы отправляют файлы в [облако Microsoft Defender для конечных](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) точек для анализа.</span><span class="sxs-lookup"><span data-stu-id="ddbca-122">To keep you protected, Safe Documents sends files to the [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span> <span data-ttu-id="ddbca-123">Сведения о том, как Microsoft Defender для конечной точки обрабатывает данные, можно найти здесь: Microsoft Defender для хранения и конфиденциальности данных [конечных точек.](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)</span><span class="sxs-lookup"><span data-stu-id="ddbca-123">Details on how Microsoft Defender for Endpoint handles your data can be found here: [Microsoft Defender for Endpoint data storage and privacy](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span>

<span data-ttu-id="ddbca-124">Файлы, отправленные Сейф документов, не сохраняются в Defender после времени, необходимого для анализа (как правило, менее 24 часов).</span><span class="sxs-lookup"><span data-stu-id="ddbca-124">Files sent by Safe Documents are not retained in Defender beyond the time needed for analysis (typically, less than 24 hours).</span></span>

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="ddbca-125">Используйте Центр & безопасности для настройки Сейф документов</span><span class="sxs-lookup"><span data-stu-id="ddbca-125">Use the Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="ddbca-126">В Центре & безопасности перейдите в  центр политики управления угрозами \>  \> **ATP Сейф** вложения, а затем нажмите **параметры Global**.</span><span class="sxs-lookup"><span data-stu-id="ddbca-126">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="ddbca-127">В **глобальных параметрах** вылет, который появляется, настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="ddbca-127">In the **Global settings** fly out that appears, configure the following settings:</span></span>

   - <span data-ttu-id="ddbca-128">**Включаем Сейф** документы для Office клиентов: переместите очки вправо, чтобы включить функцию: включить . ![ ](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="ddbca-128">**Turn on Safe Documents for Office clients**: Move the toggle to the right to turn on the feature: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   - <span data-ttu-id="ddbca-129">Разрешить пользователям щелкнуть защищенный просмотр, даже **если Сейф documents** идентифицирует файл как вредоносный. Рекомендуется оставить этот параметр отключенным (оставьте левое окантовку: отключите). ![ ](../../media/scc-toggle-off.png)</span><span class="sxs-lookup"><span data-stu-id="ddbca-129">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious**: We recommend that you leave this option turned off (leave the toggle to the left: ![Toggle off](../../media/scc-toggle-off.png)).</span></span>

   <span data-ttu-id="ddbca-130">Выполнив необходимые действия, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="ddbca-130">When you're finished, click **Save**.</span></span>

   ![Сейф Параметры документов после выбора глобальных параметров на странице Сейф вложения.](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a><span data-ttu-id="ddbca-132">Используйте Exchange Online PowerShell для настройки Сейф документов</span><span class="sxs-lookup"><span data-stu-id="ddbca-132">Use Exchange Online PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="ddbca-133">Используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="ddbca-133">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- <span data-ttu-id="ddbca-134">Параметр _EnableSafeDocs_ включает или отключает Сейф документов для всей организации.</span><span class="sxs-lookup"><span data-stu-id="ddbca-134">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>
- <span data-ttu-id="ddbca-135">Параметр _AllowSafeDocsOpen_ позволяет пользователям покидать защищенный вид (т. е. открывать документ), если документ был идентифицирован как вредоносный.</span><span class="sxs-lookup"><span data-stu-id="ddbca-135">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="ddbca-136">В этом примере Сейф документов для всей организации и не позволяет пользователям открывать документы, которые были идентифицированы как вредоносные из защищенного представления.</span><span class="sxs-lookup"><span data-stu-id="ddbca-136">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="ddbca-137">Подробные сведения о синтаксисах и параметрах см. в [инструкции Set-AtpPolicyForO365.](/powershell/module/exchange/set-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="ddbca-137">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="onboard-to-the-microsoft-defender-for-endpoint-service-to-enable-auditing-capabilities"></a><span data-ttu-id="ddbca-138">На борту службы Microsoft Defender для конечных точек, чтобы включить возможности аудита</span><span class="sxs-lookup"><span data-stu-id="ddbca-138">Onboard to the Microsoft Defender for Endpoint Service to enable auditing capabilities</span></span>

<span data-ttu-id="ddbca-139">Чтобы развернуть Microsoft Defender для конечной точки, необходимо пройти различные этапы развертывания.</span><span class="sxs-lookup"><span data-stu-id="ddbca-139">To deploy Microsoft Defender for Endpoint, you need to go through the various phases of deployment.</span></span> <span data-ttu-id="ddbca-140">После взбора можно настроить возможности аудита в Центре & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="ddbca-140">After onboarding, you can configure auditing capabilities in the Security & Compliance Center.</span></span>

<span data-ttu-id="ddbca-141">Дополнительные дополнительные информации см. в таблице [Onboard в службе Microsoft Defender for Endpoint.](/microsoft-365/security/defender-endpoint/onboarding)</span><span class="sxs-lookup"><span data-stu-id="ddbca-141">To learn more, see [Onboard to the Microsoft Defender for Endpoint service](/microsoft-365/security/defender-endpoint/onboarding).</span></span> <span data-ttu-id="ddbca-142">Если вам нужна дополнительная помощь, обратитесь к проблеме устранения неполадок [Microsoft Defender для конечной](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding)точки.</span><span class="sxs-lookup"><span data-stu-id="ddbca-142">If you need additional help, please refer to [Troubleshoot Microsoft Defender for Endpoint onboarding issues](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="ddbca-143">Как проверить, что это работает?</span><span class="sxs-lookup"><span data-stu-id="ddbca-143">How do I know this worked?</span></span>

<span data-ttu-id="ddbca-144">Чтобы убедиться, что вы включили Сейф документы, сделайте все следующие действия:</span><span class="sxs-lookup"><span data-stu-id="ddbca-144">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="ddbca-145">В Центре обеспечения & безопасности перейдите  в центр политики управления угрозами \>  \> **ATP Сейф Вложения,**   щелкните параметры Global и убедитесь, что включите документы Сейф для Office клиентов и разрешите пользователям щелкнуть защищенный просмотр, даже если **Сейф Documents** идентифицирует файл как вредоносные параметры.</span><span class="sxs-lookup"><span data-stu-id="ddbca-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, click **Global settings**, and verify the **Turn on Safe Documents for Office clients** and **Allow people to click through Protected View even if Safe Documents identifies the file as malicious** settings.</span></span>

- <span data-ttu-id="ddbca-146">Запустите следующую команду в Exchange Online PowerShell и проверьте значения свойств:</span><span class="sxs-lookup"><span data-stu-id="ddbca-146">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- <span data-ttu-id="ddbca-147">Следующие файлы доступны для проверки Сейф документов.</span><span class="sxs-lookup"><span data-stu-id="ddbca-147">The following files are available to test Safe Documents protection.</span></span> <span data-ttu-id="ddbca-148">Эти документы похожи на файл EICAR.TXT для тестирования решений по борьбе с вредоносными программами и антивирусами.</span><span class="sxs-lookup"><span data-stu-id="ddbca-148">These documents are similar to the EICAR.TXT file for testing anti-malware and anti-virus solutions.</span></span> <span data-ttu-id="ddbca-149">Файлы не являются вредными, но они запускают защиту Сейф документов.</span><span class="sxs-lookup"><span data-stu-id="ddbca-149">The files are not harmful, but they will trigger Safe Documents protection.</span></span>

  - [<span data-ttu-id="ddbca-150">SafeDocsDemo.docx</span><span class="sxs-lookup"><span data-stu-id="ddbca-150">SafeDocsDemo.docx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [<span data-ttu-id="ddbca-151">SafeDocsDemo.pptx</span><span class="sxs-lookup"><span data-stu-id="ddbca-151">SafeDocsDemo.pptx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [<span data-ttu-id="ddbca-152">SafeDocsDemo.xlsx</span><span class="sxs-lookup"><span data-stu-id="ddbca-152">SafeDocsDemo.xlsx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
