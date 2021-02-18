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
ms.openlocfilehash: a3f4ed3535c7e53774b9b567b50f7c06e99cef9d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288589"
---
# <a name="safe-documents-in-microsoft-365-e5"></a><span data-ttu-id="63e9e-103">Безопасные документы в Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="63e9e-103">Safe Documents in Microsoft 365 E5</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="63e9e-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="63e9e-104">**Applies to**</span></span>
- [<span data-ttu-id="63e9e-105">Microsoft Defender для Office 365 (план 2)</span><span class="sxs-lookup"><span data-stu-id="63e9e-105">Microsoft Defender for Office 365 plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="63e9e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="63e9e-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="63e9e-107">Безопасные документы — это функция в Microsoft 365 E5 или Microsoft 365 E5 Security, которая использует [Microsoft Defender для](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) конечной точки для сканирования документов и файлов, открытых в защищеном представлении. [](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)</span><span class="sxs-lookup"><span data-stu-id="63e9e-107">Safe Documents is a feature in Microsoft 365 E5 or Microsoft 365 E5 Security that uses [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="63e9e-108">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="63e9e-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="63e9e-109">Безопасные документы доступны только пользователям с лицензиями *microsoft 365 E5* или *Microsoft 365 E5 Security.*</span><span class="sxs-lookup"><span data-stu-id="63e9e-109">Safe Documents is available only to users with *Microsoft 365 E5* or *Microsoft 365 E5 Security* licenses.</span></span> <span data-ttu-id="63e9e-110">Эти лицензии не включены в планы Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="63e9e-110">These licenses are not included in Microsoft Defender for Office 365 plans.</span></span>

- <span data-ttu-id="63e9e-111">Безопасные документы поддерживаются в приложениях Microsoft 365 для предприятий (прежнее название — Office 365 профессиональныйplus) версии 2004 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="63e9e-111">Safe Documents is supported in Microsoft 365 Apps for enterprise (formerly known as Office 365 ProPlus) version 2004 or later.</span></span>

- <span data-ttu-id="63e9e-112">Откройте Центр безопасности и соответствия требованиям по ссылке <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="63e9e-112">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="63e9e-113">Чтобы перейти непосредственно на страницу безопасных **вложений ATP,** откройте <https://protection.office.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="63e9e-113">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="63e9e-114">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="63e9e-114">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="63e9e-115">Для выполнения процедур, описанных в этой статье, вам должны быть назначены разрешения в Центре безопасности и соответствия требованиям:</span><span class="sxs-lookup"><span data-stu-id="63e9e-115">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="63e9e-116">Чтобы настроить параметры безопасных документов, необходимо быть  членом группы ролей "Управление организацией" или "Администратор **безопасности".**</span><span class="sxs-lookup"><span data-stu-id="63e9e-116">To configure Safe Documents settings, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="63e9e-117">Для доступа только для чтения к параметрам безопасных документов необходимо  быть членом группы ролей **"Глобальный** читатель" или "Читатель безопасности".</span><span class="sxs-lookup"><span data-stu-id="63e9e-117">For read-only access to Safe Documents settings, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="63e9e-118">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="63e9e-118">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="63e9e-119">Добавление пользователей в соответствующую роль Azure Active Directory в Центре безопасности Microsoft 365 предоставляет пользователям необходимые разрешения в Центре безопасности и соответствия требованиям _и_ разрешения для других функций в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="63e9e-119">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="63e9e-120">Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="63e9e-120">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="63e9e-121">Группа ролей **Управление организацией с правами только на просмотр** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) также предоставляет доступ только для чтения к этой функции.</span><span class="sxs-lookup"><span data-stu-id="63e9e-121">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

### <a name="how-does-microsoft-handle-your-data"></a><span data-ttu-id="63e9e-122">Как Майкрософт обрабатывает ваши данные?</span><span class="sxs-lookup"><span data-stu-id="63e9e-122">How does Microsoft handle your data?</span></span>

<span data-ttu-id="63e9e-123">Для защиты безопасные документы отправляют файлы в [облако Microsoft Defender для конечных](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) точек для анализа.</span><span class="sxs-lookup"><span data-stu-id="63e9e-123">To keep you protected, Safe Documents sends files to the [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span> <span data-ttu-id="63e9e-124">Подробные сведения о том, как Microsoft Defender для конечной точки обрабатывает ваши данные, можно найти здесь: [Microsoft Defender for Endpoint data storage and privacy](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span><span class="sxs-lookup"><span data-stu-id="63e9e-124">Details on how Microsoft Defender for Endpoint handles your data can be found here: [Microsoft Defender for Endpoint data storage and privacy](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span>

<span data-ttu-id="63e9e-125">Файлы, отправленные с помощью безопасных документов, не сохраняются в Защитнике после времени, необходимого для анализа (обычно менее 24 часов).</span><span class="sxs-lookup"><span data-stu-id="63e9e-125">Files sent by Safe Documents are not retained in Defender beyond the time needed for analysis (typically, less than 24 hours).</span></span>

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="63e9e-126">Использование Центра безопасности & соответствия требованиям для настройки безопасных документов</span><span class="sxs-lookup"><span data-stu-id="63e9e-126">Use the Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="63e9e-127">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments,** and then click **Global settings**.</span><span class="sxs-lookup"><span data-stu-id="63e9e-127">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="63e9e-128">Во время **отлета "Глобальные** параметры" настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="63e9e-128">In the **Global settings** fly out that appears, configure the following settings:</span></span>

   - <span data-ttu-id="63e9e-129">**Включив функцию**"Безопасные документы" для клиентов Office: переместите выключаель вправо, чтобы включить функцию: ![ "Включить". ](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="63e9e-129">**Turn on Safe Documents for Office clients**: Move the toggle to the right to turn on the feature: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   - <span data-ttu-id="63e9e-130">Разрешите пользователям переходить через защищенный просмотр, даже если "Безопасные документы" идентифицируют файл как вредоносный. Рекомендуется оставить этот параметр отключенным (оставьте этот параметр выключенным (оставьте этот параметр слева: "Отключить"). ![ ](../../media/scc-toggle-off.png)</span><span class="sxs-lookup"><span data-stu-id="63e9e-130">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious**: We recommend that you leave this option turned off (leave the toggle to the left: ![Toggle off](../../media/scc-toggle-off.png)).</span></span>

   <span data-ttu-id="63e9e-131">По завершении нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="63e9e-131">When you're finished, click **Save**.</span></span>

   ![Параметры безопасных документов после выбора глобальных параметров на странице "Безопасные вложения".](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a><span data-ttu-id="63e9e-133">Настройка безопасных документов с помощью Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="63e9e-133">Use Exchange Online PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="63e9e-134">Используйте указанный ниже синтаксис.</span><span class="sxs-lookup"><span data-stu-id="63e9e-134">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- <span data-ttu-id="63e9e-135">Параметр _EnableSafeDocs_ включает или отключает безопасные документы для всей организации.</span><span class="sxs-lookup"><span data-stu-id="63e9e-135">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>
- <span data-ttu-id="63e9e-136">Параметр _AllowSafeDocsOpen_ разрешает или предотвращает выход пользователей из защищенного просмотра (т. е. открытие документа), если документ был определен как вредоносный.</span><span class="sxs-lookup"><span data-stu-id="63e9e-136">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="63e9e-137">Этот пример включает безопасные документы для всей организации и предотвращает открытие пользователями документов, которые были определены как вредоносные, из защищенного просмотра.</span><span class="sxs-lookup"><span data-stu-id="63e9e-137">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="63e9e-138">Подробные сведения о синтаксисах и параметрах см. в описании [set-AtpPolicyForO365.](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="63e9e-138">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="63e9e-139">Как проверить, что это работает?</span><span class="sxs-lookup"><span data-stu-id="63e9e-139">How do I know this worked?</span></span>

<span data-ttu-id="63e9e-140">Чтобы убедиться, что вы включили и настроили безопасные документы, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="63e9e-140">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="63e9e-141">В Центре безопасности & соответствия требованиям  перейдите к политике управления угрозами "Безопасные вложения" \>  \> **ATP,**   щелкните "Глобальные параметры" и проверьте, включите ли безопасные документы для клиентов Office и разрешите пользователям переходить через защищенный **просмотр,** даже если "Безопасные документы" идентифицируют файл как вредоносные параметры.</span><span class="sxs-lookup"><span data-stu-id="63e9e-141">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, click **Global settings**, and verify the **Turn on Safe Documents for Office clients** and **Allow people to click through Protected View even if Safe Documents identifies the file as malicious** settings.</span></span>

- <span data-ttu-id="63e9e-142">Запустите следующую команду в Exchange Online PowerShell и проверьте значения свойств:</span><span class="sxs-lookup"><span data-stu-id="63e9e-142">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- <span data-ttu-id="63e9e-143">Для проверки защиты безопасных документов доступны следующие файлы.</span><span class="sxs-lookup"><span data-stu-id="63e9e-143">The following files are available to test Safe Documents protection.</span></span> <span data-ttu-id="63e9e-144">Эти документы похожи на EICAR.TXT для тестирования антивирусных и антивирусных решений.</span><span class="sxs-lookup"><span data-stu-id="63e9e-144">These documents are similar to the EICAR.TXT file for testing anti-malware and anti-virus solutions.</span></span> <span data-ttu-id="63e9e-145">Файлы не являются вредоносными, но они запускают защиту безопасных документов.</span><span class="sxs-lookup"><span data-stu-id="63e9e-145">The files are not harmful, but they will trigger Safe Documents protection.</span></span>

  - [<span data-ttu-id="63e9e-146">SafeDocsDemo.docx</span><span class="sxs-lookup"><span data-stu-id="63e9e-146">SafeDocsDemo.docx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [<span data-ttu-id="63e9e-147">SafeDocsDemo.pptx</span><span class="sxs-lookup"><span data-stu-id="63e9e-147">SafeDocsDemo.pptx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [<span data-ttu-id="63e9e-148">SafeDocsDemo.xlsx</span><span class="sxs-lookup"><span data-stu-id="63e9e-148">SafeDocsDemo.xlsx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
