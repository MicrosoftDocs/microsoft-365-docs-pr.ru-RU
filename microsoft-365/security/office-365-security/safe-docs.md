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
ms.openlocfilehash: a1dc6c5dc54acd73b68fcd6241a270d2abdcc5c1
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205672"
---
# <a name="safe-documents-in-microsoft-365-e5"></a><span data-ttu-id="97f41-103">Безопасные документы в Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="97f41-103">Safe Documents in Microsoft 365 E5</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="97f41-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="97f41-104">**Applies to**</span></span>
- [<span data-ttu-id="97f41-105">Microsoft Defender для Office 365 (план 2)</span><span class="sxs-lookup"><span data-stu-id="97f41-105">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="97f41-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="97f41-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="97f41-107">Безопасные документы — это функция в Microsoft 365 E5 или Microsoft 365 E5 Security, которая использует [Microsoft Defender для](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) конечной точки для сканирования документов и файлов, открытых в защищенной точке [зрения.](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)</span><span class="sxs-lookup"><span data-stu-id="97f41-107">Safe Documents is a feature in Microsoft 365 E5 or Microsoft 365 E5 Security that uses [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="97f41-108">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="97f41-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="97f41-109">Безопасные документы доступны только пользователям с лицензиями *microsoft 365 E5* или *Microsoft 365 E5 Security.*</span><span class="sxs-lookup"><span data-stu-id="97f41-109">Safe Documents is available only to users with *Microsoft 365 E5* or *Microsoft 365 E5 Security* licenses.</span></span> <span data-ttu-id="97f41-110">Эти лицензии не включены в планы Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="97f41-110">These licenses are not included in Microsoft Defender for Office 365 plans.</span></span>

- <span data-ttu-id="97f41-111">Безопасные документы поддерживаются в Microsoft 365 Apps для предприятия (ранее известная как Office 365 ProPlus) версии 2004 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="97f41-111">Safe Documents is supported in Microsoft 365 Apps for enterprise (formerly known as Office 365 ProPlus) version 2004 or later.</span></span>

- <span data-ttu-id="97f41-112">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="97f41-112">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="97f41-113">Чтобы перейти непосредственно на страницу БЕЗОПАСНЫЕ вложения **ATP,** откройте <https://protection.office.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="97f41-113">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="97f41-114">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="97f41-114">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="97f41-115">Для выполнения процедур, описанных в этой статье, вам должны быть назначены разрешения в **Exchange Online**:</span><span class="sxs-lookup"><span data-stu-id="97f41-115">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="97f41-116">Чтобы настроить параметры "Безопасные документы", необходимо быть членом группы ролей **"Управление** организацией" или **"Администратор** безопасности".</span><span class="sxs-lookup"><span data-stu-id="97f41-116">To configure Safe Documents settings, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="97f41-117">Для доступа только для чтения к настройкам безопасных документов необходимо быть членом групп ролей **Global Reader** или **Security Reader.**</span><span class="sxs-lookup"><span data-stu-id="97f41-117">For read-only access to Safe Documents settings, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="97f41-118">Дополнительные сведения см. в статье [Разрешения в Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="97f41-118">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="97f41-119">Добавление пользователей в соответствующую роль Azure Active Directory в Центре безопасности Microsoft 365 предоставляет пользователям необходимые разрешения _и_ разрешения для других функций в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="97f41-119">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="97f41-120">Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="97f41-120">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="97f41-121">Группа ролей **Управление организацией с правами только на просмотр** в [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) также предоставляет доступ только для чтения к этой функции.</span><span class="sxs-lookup"><span data-stu-id="97f41-121">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

### <a name="how-does-microsoft-handle-your-data"></a><span data-ttu-id="97f41-122">Как Корпорация Майкрософт обрабатывает ваши данные?</span><span class="sxs-lookup"><span data-stu-id="97f41-122">How does Microsoft handle your data?</span></span>

<span data-ttu-id="97f41-123">Чтобы защититься, safe Documents отправляет файлы в [облако Microsoft Defender для конечной](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) точки для анализа.</span><span class="sxs-lookup"><span data-stu-id="97f41-123">To keep you protected, Safe Documents sends files to the [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span> <span data-ttu-id="97f41-124">Сведения о том, как Microsoft Defender для конечной точки обрабатывает данные, можно найти здесь: Microsoft Defender для хранения и конфиденциальности данных [конечных точек.](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)</span><span class="sxs-lookup"><span data-stu-id="97f41-124">Details on how Microsoft Defender for Endpoint handles your data can be found here: [Microsoft Defender for Endpoint data storage and privacy](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span>

<span data-ttu-id="97f41-125">Файлы, отправленные безопасными документами, не сохраняются в Defender после времени, необходимого для анализа (как правило, менее 24 часов).</span><span class="sxs-lookup"><span data-stu-id="97f41-125">Files sent by Safe Documents are not retained in Defender beyond the time needed for analysis (typically, less than 24 hours).</span></span>

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="97f41-126">Используйте Центр & безопасности для настройки безопасных документов</span><span class="sxs-lookup"><span data-stu-id="97f41-126">Use the Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="97f41-127">В Центре обеспечения & безопасности перейдите к политике управления угрозами  \>  \> **ATP Safe Attachments,** а затем щелкните **глобальные параметры.**</span><span class="sxs-lookup"><span data-stu-id="97f41-127">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="97f41-128">В **глобальных параметрах** вылет, который появляется, настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="97f41-128">In the **Global settings** fly out that appears, configure the following settings:</span></span>

   - <span data-ttu-id="97f41-129">**Включим безопасные** документы для клиентов Office: переместите переключеть вправо, чтобы включить функцию: ![ ](../../media/scc-toggle-on.png) Включить.</span><span class="sxs-lookup"><span data-stu-id="97f41-129">**Turn on Safe Documents for Office clients**: Move the toggle to the right to turn on the feature: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   - <span data-ttu-id="97f41-130">**Разрешить** пользователям щелкнуть защищенный просмотр, даже если "Безопасные документы" идентифицируют файл как вредоносный. Рекомендуется оставить этот параметр отключенным (оставьте переключенку слева: отключите). ![ ](../../media/scc-toggle-off.png)</span><span class="sxs-lookup"><span data-stu-id="97f41-130">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious**: We recommend that you leave this option turned off (leave the toggle to the left: ![Toggle off](../../media/scc-toggle-off.png)).</span></span>

   <span data-ttu-id="97f41-131">Когда закончите, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="97f41-131">When you're finished, click **Save**.</span></span>

   ![Параметры Безопасные документы после выбора глобальных параметров на странице Безопасные вложения.](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a><span data-ttu-id="97f41-133">Использование Exchange Online PowerShell для настройки безопасных документов</span><span class="sxs-lookup"><span data-stu-id="97f41-133">Use Exchange Online PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="97f41-134">Используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="97f41-134">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- <span data-ttu-id="97f41-135">Параметр _EnableSafeDocs_ включает или отключает безопасные документы для всей организации.</span><span class="sxs-lookup"><span data-stu-id="97f41-135">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>
- <span data-ttu-id="97f41-136">Параметр _AllowSafeDocsOpen_ позволяет пользователям покидать защищенный вид (т. е. открывать документ), если документ был идентифицирован как вредоносный.</span><span class="sxs-lookup"><span data-stu-id="97f41-136">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="97f41-137">В этом примере можно включить безопасные документы для всей организации и запретить пользователям открывать документы, которые были идентифицированы как вредоносные из защищенного представления.</span><span class="sxs-lookup"><span data-stu-id="97f41-137">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="97f41-138">Подробные сведения о синтаксисах и параметрах см. в [инструкции Set-AtpPolicyForO365.](/powershell/module/exchange/set-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="97f41-138">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="97f41-139">Как проверить, что это работает?</span><span class="sxs-lookup"><span data-stu-id="97f41-139">How do I know this worked?</span></span>

<span data-ttu-id="97f41-140">Чтобы убедиться, что вы включили и настроили безопасные документы, сделайте все следующие действия:</span><span class="sxs-lookup"><span data-stu-id="97f41-140">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="97f41-141">В Центре обеспечения & безопасности перейдите к политике управления угрозами ATP Safe  \>  \> **Attachments,**   щелкните Глобальные параметры и убедитесь, что включите безопасные документы для клиентов **Office** и разрешите пользователям щелкнуть защищенный просмотр, даже если "Безопасные документы" идентифицируют файл как вредоносные параметры.</span><span class="sxs-lookup"><span data-stu-id="97f41-141">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, click **Global settings**, and verify the **Turn on Safe Documents for Office clients** and **Allow people to click through Protected View even if Safe Documents identifies the file as malicious** settings.</span></span>

- <span data-ttu-id="97f41-142">Запустите следующую команду в Exchange Online PowerShell и проверьте значения свойств:</span><span class="sxs-lookup"><span data-stu-id="97f41-142">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- <span data-ttu-id="97f41-143">Следующие файлы доступны для тестирования защиты безопасных документов.</span><span class="sxs-lookup"><span data-stu-id="97f41-143">The following files are available to test Safe Documents protection.</span></span> <span data-ttu-id="97f41-144">Эти документы похожи на файл EICAR.TXT для тестирования решений по борьбе с вредоносными программами и антивирусами.</span><span class="sxs-lookup"><span data-stu-id="97f41-144">These documents are similar to the EICAR.TXT file for testing anti-malware and anti-virus solutions.</span></span> <span data-ttu-id="97f41-145">Файлы не являются вредными, но они будут запускать защиту безопасных документов.</span><span class="sxs-lookup"><span data-stu-id="97f41-145">The files are not harmful, but they will trigger Safe Documents protection.</span></span>

  - [<span data-ttu-id="97f41-146">SafeDocsDemo.docx</span><span class="sxs-lookup"><span data-stu-id="97f41-146">SafeDocsDemo.docx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [<span data-ttu-id="97f41-147">SafeDocsDemo.pptx</span><span class="sxs-lookup"><span data-stu-id="97f41-147">SafeDocsDemo.pptx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [<span data-ttu-id="97f41-148">SafeDocsDemo.xlsx</span><span class="sxs-lookup"><span data-stu-id="97f41-148">SafeDocsDemo.xlsx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)