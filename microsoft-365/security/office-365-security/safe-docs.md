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
ms.openlocfilehash: 1049543b11ad14eeeed596367228f025cc8edd65
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054442"
---
# <a name="safe-documents-in-microsoft-365-e5"></a><span data-ttu-id="6916e-103">Безопасные документы в Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="6916e-103">Safe Documents in Microsoft 365 E5</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="6916e-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="6916e-104">**Applies to**</span></span>
- [<span data-ttu-id="6916e-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6916e-105">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="6916e-106">Сейф Документы — это функция в Microsoft 365 E5 или Безопасность Microsoft 365 E5, которая использует [Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) для конечной точки [](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653) для сканирования документов и файлов, открытых в защищенных представлениях или в службе безопасности приложений [для Office](https://support.microsoft.com/topic/9e0fb9c2-ffad-43bf-8ba3-78f785fdba46).</span><span class="sxs-lookup"><span data-stu-id="6916e-106">Safe Documents is a feature in Microsoft 365 E5 or Microsoft 365 E5 Security that uses [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653) or [Application Guard for Office](https://support.microsoft.com/topic/9e0fb9c2-ffad-43bf-8ba3-78f785fdba46).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6916e-107">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="6916e-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6916e-108">Сейф Документы доступны только пользователям  с Microsoft 365 E5 *или Безопасность Microsoft 365 E5* лицензиями.</span><span class="sxs-lookup"><span data-stu-id="6916e-108">Safe Documents is available only to users with *Microsoft 365 E5* or *Microsoft 365 E5 Security* licenses.</span></span> <span data-ttu-id="6916e-109">Эти лицензии не включены в Microsoft Defender для Office 365 планов.</span><span class="sxs-lookup"><span data-stu-id="6916e-109">These licenses are not included in Microsoft Defender for Office 365 plans.</span></span>

- <span data-ttu-id="6916e-110">Сейф Документы поддерживаются в Приложения Microsoft 365 для предприятий версии 2004 Office 365 профессиональный плюс версии 2004 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="6916e-110">Safe Documents is supported in Microsoft 365 Apps for enterprise (formerly known as Office 365 ProPlus) version 2004 or later.</span></span>

- <span data-ttu-id="6916e-111">Чтобы открыть портал Microsoft 365 Defender, перейдите на сайт <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="6916e-111">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="6916e-112">Чтобы перейти непосредственно **на страницу Сейф вложения,** используйте <https://security.microsoft.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="6916e-112">To go directly to the **Safe Attachments** page, use <https://security.microsoft.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="6916e-113">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="6916e-113">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="6916e-114">Вам нужны разрешения в **Exchange Online,** прежде чем вы сможете сделать процедуры в этой статье:</span><span class="sxs-lookup"><span data-stu-id="6916e-114">You need permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="6916e-115">Чтобы настроить Сейф документов, необходимо быть членом групп ролей **администратора** организации или **администратора** безопасности.</span><span class="sxs-lookup"><span data-stu-id="6916e-115">To configure Safe Documents settings, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="6916e-116">Для доступа только для чтения Сейф параметров документов необходимо быть членом групп ролей **Global Reader** или **Security Reader.**</span><span class="sxs-lookup"><span data-stu-id="6916e-116">For read-only access to Safe Documents settings, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="6916e-117">Дополнительные сведения см. в статье [Разрешения в Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="6916e-117">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="6916e-118">Добавление пользователей в соответствующую роль Azure Active Directory в Центре безопасности Microsoft 365 предоставляет пользователям необходимые разрешения _и_ разрешения для других функций в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6916e-118">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="6916e-119">Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="6916e-119">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="6916e-120">Группа ролей **Управление организацией с правами только на просмотр** в [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) также предоставляет доступ только для чтения к этой функции.</span><span class="sxs-lookup"><span data-stu-id="6916e-120">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

### <a name="how-does-microsoft-handle-your-data"></a><span data-ttu-id="6916e-121">Как Корпорация Майкрософт обрабатывает ваши данные?</span><span class="sxs-lookup"><span data-stu-id="6916e-121">How does Microsoft handle your data?</span></span>

<span data-ttu-id="6916e-122">Чтобы защититься, Сейф документы отправляют файлы в [облако Microsoft Defender для конечных](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) точек для анализа.</span><span class="sxs-lookup"><span data-stu-id="6916e-122">To keep you protected, Safe Documents sends files to the [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span> <span data-ttu-id="6916e-123">Сведения о том, как Microsoft Defender для конечной точки обрабатывает данные, можно найти здесь: Microsoft Defender для хранения и конфиденциальности данных [конечных точек.](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)</span><span class="sxs-lookup"><span data-stu-id="6916e-123">Details on how Microsoft Defender for Endpoint handles your data can be found here: [Microsoft Defender for Endpoint data storage and privacy](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span>

<span data-ttu-id="6916e-124">Файлы, отправленные Сейф документов, не сохраняются в Defender после времени, необходимого для анализа (как правило, менее 24 часов).</span><span class="sxs-lookup"><span data-stu-id="6916e-124">Files sent by Safe Documents are not retained in Defender beyond the time needed for analysis (typically, less than 24 hours).</span></span>

## <a name="use-the-microsoft-365-defender-to-configure-safe-documents"></a><span data-ttu-id="6916e-125">Используйте Microsoft 365 Defender для настройки Сейф документов</span><span class="sxs-lookup"><span data-stu-id="6916e-125">Use the Microsoft 365 Defender to configure Safe Documents</span></span>

1. <span data-ttu-id="6916e-126">Откройте портал Microsoft 365 Defender и перейдите в раздел Политики **совместной** & электронной почты & правила политики \>  \>  \>  \> **угрозы Сейф вложения.**</span><span class="sxs-lookup"><span data-stu-id="6916e-126">Open the Microsoft 365 Defender portal and go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="6916e-127">На странице **Сейф вложения нажмите** **глобальные параметры**.</span><span class="sxs-lookup"><span data-stu-id="6916e-127">On the **Safe Attachments** page, click **Global settings**.</span></span>

3. <span data-ttu-id="6916e-128">В **глобальных параметрах** вылет, который появляется, настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="6916e-128">In the **Global settings** fly out that appears, configure the following settings:</span></span>
   - <span data-ttu-id="6916e-129">**Включаем Сейф** документы для Office клиентов: переместите очки вправо, чтобы включить функцию: включить . ![ ](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="6916e-129">**Turn on Safe Documents for Office clients**: Move the toggle to the right to turn on the feature: ![Toggle on](../../media/scc-toggle-on.png).</span></span>
   - <span data-ttu-id="6916e-130">Разрешить пользователям щелкнуть защищенный **просмотр,** даже если Сейф документы идентифицировали файл как вредоносный. Рекомендуется оставить этот параметр отключенным (оставьте переключенку слева: отключите). ![ ](../../media/scc-toggle-off.png)</span><span class="sxs-lookup"><span data-stu-id="6916e-130">**Allow people to click through Protected View even if Safe Documents identified the file as malicious**: We recommend that you leave this option turned off (leave the toggle to the left: ![Toggle off](../../media/scc-toggle-off.png)).</span></span>

   <span data-ttu-id="6916e-131">По завершении нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="6916e-131">When you're finished, click **Save**.</span></span>

   ![Сейф Параметры документов после выбора глобальных параметров на странице Сейф вложения.](../../media/safe-docs-global-settings.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a><span data-ttu-id="6916e-133">Используйте Exchange Online PowerShell для настройки Сейф документов</span><span class="sxs-lookup"><span data-stu-id="6916e-133">Use Exchange Online PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="6916e-134">Используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="6916e-134">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- <span data-ttu-id="6916e-135">Параметр _EnableSafeDocs_ включает или отключает Сейф документов для всей организации.</span><span class="sxs-lookup"><span data-stu-id="6916e-135">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>
- <span data-ttu-id="6916e-136">Параметр _AllowSafeDocsOpen_ позволяет пользователям покидать защищенный вид (т. е. открывать документ), если документ был идентифицирован как вредоносный.</span><span class="sxs-lookup"><span data-stu-id="6916e-136">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="6916e-137">В этом примере Сейф документов для всей организации и не позволяет пользователям открывать документы, которые были идентифицированы как вредоносные из защищенного представления.</span><span class="sxs-lookup"><span data-stu-id="6916e-137">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="6916e-138">Подробные сведения о синтаксисах и параметрах см. в [инструкции Set-AtpPolicyForO365.](/powershell/module/exchange/set-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="6916e-138">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="onboard-to-the-microsoft-defender-for-endpoint-service-to-enable-auditing-capabilities"></a><span data-ttu-id="6916e-139">На борту службы Microsoft Defender для конечных точек, чтобы включить возможности аудита</span><span class="sxs-lookup"><span data-stu-id="6916e-139">Onboard to the Microsoft Defender for Endpoint Service to enable auditing capabilities</span></span>

<span data-ttu-id="6916e-140">Чтобы развернуть Microsoft Defender для конечной точки, необходимо пройти различные этапы развертывания.</span><span class="sxs-lookup"><span data-stu-id="6916e-140">To deploy Microsoft Defender for Endpoint, you need to go through the various phases of deployment.</span></span> <span data-ttu-id="6916e-141">После встройки можно настроить возможности аудита на Microsoft 365 Defender портале.</span><span class="sxs-lookup"><span data-stu-id="6916e-141">After onboarding, you can configure auditing capabilities in the Microsoft 365 Defender portal.</span></span>

<span data-ttu-id="6916e-142">Дополнительные дополнительные информации см. в таблице [Onboard в службе Microsoft Defender for Endpoint.](/microsoft-365/security/defender-endpoint/onboarding)</span><span class="sxs-lookup"><span data-stu-id="6916e-142">To learn more, see [Onboard to the Microsoft Defender for Endpoint service](/microsoft-365/security/defender-endpoint/onboarding).</span></span> <span data-ttu-id="6916e-143">Если вам нужна дополнительная помощь, обратитесь к проблеме устранения неполадок [Microsoft Defender для конечной](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding)точки.</span><span class="sxs-lookup"><span data-stu-id="6916e-143">If you need additional help, refer to [Troubleshoot Microsoft Defender for Endpoint onboarding issues](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="6916e-144">Как проверить, что это работает?</span><span class="sxs-lookup"><span data-stu-id="6916e-144">How do I know this worked?</span></span>

<span data-ttu-id="6916e-145">Чтобы убедиться, что вы включили Сейф документы, сделайте все следующие действия:</span><span class="sxs-lookup"><span data-stu-id="6916e-145">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="6916e-146">На портале Microsoft 365 Defender перейдите на электронную почту **&** Политики совместной работы & правила политики угрозы раздела Сейф Вложения Глобальные параметры, а также проверьте включить документы Сейф для Office клиентов и разрешить пользователям щелкнуть защищенный просмотр, даже если Сейф Documents идентифицирует файл как \>  \>  \>  \>  \> вредоносные параметры.  </span><span class="sxs-lookup"><span data-stu-id="6916e-146">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Policies** section \> **Safe Attachments** \> **Global settings**, and verify the **Turn on Safe Documents for Office clients** and **Allow people to click through Protected View even if Safe Documents identifies the file as malicious** settings.</span></span>

- <span data-ttu-id="6916e-147">Запустите следующую команду в Exchange Online PowerShell и проверьте значения свойств:</span><span class="sxs-lookup"><span data-stu-id="6916e-147">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- <span data-ttu-id="6916e-148">Следующие файлы доступны для проверки Сейф документов.</span><span class="sxs-lookup"><span data-stu-id="6916e-148">The following files are available to test Safe Documents protection.</span></span> <span data-ttu-id="6916e-149">Эти документы похожи на файл EICAR.TXT для тестирования решений по борьбе с вредоносными программами и антивирусами.</span><span class="sxs-lookup"><span data-stu-id="6916e-149">These documents are similar to the EICAR.TXT file for testing anti-malware and anti-virus solutions.</span></span> <span data-ttu-id="6916e-150">Файлы не являются вредными, но они запускают защиту Сейф документов.</span><span class="sxs-lookup"><span data-stu-id="6916e-150">The files are not harmful, but they will trigger Safe Documents protection.</span></span>

  - [<span data-ttu-id="6916e-151">SafeDocsDemo.docx</span><span class="sxs-lookup"><span data-stu-id="6916e-151">SafeDocsDemo.docx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [<span data-ttu-id="6916e-152">SafeDocsDemo.pptx</span><span class="sxs-lookup"><span data-stu-id="6916e-152">SafeDocsDemo.pptx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [<span data-ttu-id="6916e-153">SafeDocsDemo.xlsx</span><span class="sxs-lookup"><span data-stu-id="6916e-153">SafeDocsDemo.xlsx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
