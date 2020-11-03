---
title: Безопасные документы в защитнике Майкрософт для Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Сведения о надежных документах в Microsoft 365 и Microsoft 365 для обеспечения безопасности.
ms.openlocfilehash: 7fbee440298aea3609665b62a946ae3ce2857e37
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845484"
---
# <a name="safe-documents-in-microsoft-365-e5"></a><span data-ttu-id="6d731-103">Безопасные документы в Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="6d731-103">Safe Documents in Microsoft 365 E5</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="6d731-104">Безопасные документы — это функция Microsoft 365, а также безопасность Microsoft 365, которая использует [защитник Майкрософт для конечной точки](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) для сканирования документов и файлов, которые открываются в [режиме защищенного просмотра](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span><span class="sxs-lookup"><span data-stu-id="6d731-104">Safe Documents is a feature in Microsoft 365 E5 or Microsoft 365 E5 Security that uses [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6d731-105">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="6d731-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6d731-106">Безопасные документы доступны только пользователям, у которых есть лицензии на системы безопасности *microsoft 365* и *Microsoft 365* .</span><span class="sxs-lookup"><span data-stu-id="6d731-106">Safe Documents is available only to users with *Microsoft 365 E5* or *Microsoft 365 E5 Security* licenses.</span></span> <span data-ttu-id="6d731-107">Эти лицензии не включены в планах Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="6d731-107">These licenses are not included in Microsoft Defender for Office 365 plans.</span></span>

- <span data-ttu-id="6d731-108">Безопасные документы поддерживаются в приложениях Microsoft 365 для предприятий (прежнее название — Office 365 профессиональный плюс) версии 2004 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="6d731-108">Safe Documents is supported in Microsoft 365 Apps for enterprise (formerly known as Office 365 ProPlus) version 2004 or later.</span></span>

- <span data-ttu-id="6d731-109">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="6d731-109">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="6d731-110">Чтобы перейти непосредственно к странице **безопасных вложений ATP** , откройте <https://protection.office.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="6d731-110">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="6d731-111">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="6d731-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="6d731-112">Перед выполнением процедур, описанных в этом разделе, необходимо назначить разрешения.</span><span class="sxs-lookup"><span data-stu-id="6d731-112">You need to be assigned permissions before you can perform the procedures in this topic.</span></span> <span data-ttu-id="6d731-113">Чтобы включить и настроить безопасные документы, необходимо быть участником группы ролей " **Управление организацией** " или " **администратор безопасности** ".</span><span class="sxs-lookup"><span data-stu-id="6d731-113">To enable and configure Safe Documents, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="6d731-114">Дополнительные сведения о группах ролей в Центре безопасности и соответствия требованиям см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="6d731-114">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="how-does-microsoft-handle-your-data"></a><span data-ttu-id="6d731-115">Как Майкрософт обрабатывает ваши данные?</span><span class="sxs-lookup"><span data-stu-id="6d731-115">How does Microsoft handle your data?</span></span>

<span data-ttu-id="6d731-116">Чтобы защитить паролем, безопасные документы отправляют файлы в [защитник Майкрософт для](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) облачного облака для анализа.</span><span class="sxs-lookup"><span data-stu-id="6d731-116">To keep you protected, Safe Documents sends files to the [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span> <span data-ttu-id="6d731-117">Сведения о том, как защитник Майкрософт для обработки конечных точек ваши данные можно найти здесь: [защитник Майкрософт для хранения и конфиденциальности данных конечной точки](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span><span class="sxs-lookup"><span data-stu-id="6d731-117">Details on how Microsoft Defender for Endpoint handles your data can be found here: [Microsoft Defender for Endpoint data storage and privacy](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span>

<span data-ttu-id="6d731-118">Файлы, отправленные безопасными документами, не поддерживаются в защитнике за пределами времени, необходимого для анализа (как правило, меньше 24 часов).</span><span class="sxs-lookup"><span data-stu-id="6d731-118">Files sent by Safe Documents are not retained in Defender beyond the time needed for analysis (typically, less than 24 hours).</span></span>

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="6d731-119">Использование центра безопасности & соответствия требованиям для настройки безопасных документов</span><span class="sxs-lookup"><span data-stu-id="6d731-119">Use the Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="6d731-120">В центре безопасности & соответствия требованиям перейдите к разделу политика **управления угрозами** \> **Policy** \> **ATP: безопасные вложения** , а затем щелкните **глобальные параметры**.</span><span class="sxs-lookup"><span data-stu-id="6d731-120">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments** , and then click **Global settings**.</span></span>

2. <span data-ttu-id="6d731-121">В открывшемся окне **глобальные параметры** настройте указанные ниже параметры.</span><span class="sxs-lookup"><span data-stu-id="6d731-121">In the **Global settings** fly out that appears, configure the following settings:</span></span>

   - <span data-ttu-id="6d731-122">**Включите безопасные документы для клиентов Office** : установите переключатель вправо, чтобы включить компонент: включен ![ ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) .</span><span class="sxs-lookup"><span data-stu-id="6d731-122">**Turn on Safe Documents for Office clients** : Move the toggle to the right to turn on the feature: ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span></span>

   - <span data-ttu-id="6d731-123">**Разрешить пользователям переход по защищенному просмотру даже в том случае, если безопасные документы определяют файл как вредоносный** : Мы рекомендуем оставить этот параметр отключенным (не устанавливая флажок слева: выключено ![ ](../../media/scc-toggle-off.png) ).</span><span class="sxs-lookup"><span data-stu-id="6d731-123">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious** : We recommend that you leave this option turned off (leave the toggle to the left: ![Toggle off](../../media/scc-toggle-off.png)).</span></span>

   <span data-ttu-id="6d731-124">Выполнив необходимые действия, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="6d731-124">When you're finished, click **Save**.</span></span>

   ![Параметры безопасных документов после выбора глобальных параметров на странице безопасные вложения.](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a><span data-ttu-id="6d731-126">Настройка безопасных документов с помощью Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="6d731-126">Use Exchange Online PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="6d731-127">Используйте указанный ниже синтаксис.</span><span class="sxs-lookup"><span data-stu-id="6d731-127">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- <span data-ttu-id="6d731-128">Параметр _енаблесафедокс_ включает или отключает безопасные документы для всей Организации.</span><span class="sxs-lookup"><span data-stu-id="6d731-128">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>
- <span data-ttu-id="6d731-129">Параметр _алловсафедоксопен_ разрешает или запрещает пользователям оставлять защищенный просмотр (то есть открывать документ), если документ был определен как вредоносный.</span><span class="sxs-lookup"><span data-stu-id="6d731-129">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="6d731-130">В этом примере показано, как включить безопасные документы для всей Организации и запретить пользователям открывать документы, которые были определены как вредоносные из защищенного просмотра.</span><span class="sxs-lookup"><span data-stu-id="6d731-130">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="6d731-131">Подробные сведения о синтаксисе и параметрах можно найти в статье [Set – AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="6d731-131">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="6d731-132">Как проверить, что это работает?</span><span class="sxs-lookup"><span data-stu-id="6d731-132">How do I know this worked?</span></span>

<span data-ttu-id="6d731-133">Чтобы убедиться, что вы включили и настроили безопасные документы, выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="6d731-133">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="6d731-134">В центре безопасности & соответствия требованиям перейдите к разделу политика **управления угрозами** \> **Policy** \> **ATP: безопасные вложения** , щелкните **глобальные параметры** и проверьте, **включены ли безопасные документы для клиентов Office** , и **разрешите пользователям перейти по защищенному просмотру даже в том случае, если они идентифицируют файл как вредоносные** параметры.</span><span class="sxs-lookup"><span data-stu-id="6d731-134">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments** , click **Global settings** , and verify the **Turn on Safe Documents for Office clients** and **Allow people to click through Protected View even if Safe Documents identifies the file as malicious** settings.</span></span>

- <span data-ttu-id="6d731-135">Выполните следующую команду в Exchange Online PowerShell и проверьте значения свойств:</span><span class="sxs-lookup"><span data-stu-id="6d731-135">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- <span data-ttu-id="6d731-136">Ниже приведены файлы, которые можно использовать для тестирования безопасности защищенных документов.</span><span class="sxs-lookup"><span data-stu-id="6d731-136">The following files are available to test Safe Documents protection.</span></span> <span data-ttu-id="6d731-137">Эти документы аналогичны файлу EICAR.TXT для тестирования антивредоносных и антивирусных решений.</span><span class="sxs-lookup"><span data-stu-id="6d731-137">These documents are similar to the EICAR.TXT file for testing anti-malware and anti-virus solutions.</span></span> <span data-ttu-id="6d731-138">Файлы не являются вредоносными, но они активируют безопасную защиту документов.</span><span class="sxs-lookup"><span data-stu-id="6d731-138">The files are not harmful, but they will trigger Safe Documents protection.</span></span>

  - [<span data-ttu-id="6d731-139">SafeDocsDemo.docx</span><span class="sxs-lookup"><span data-stu-id="6d731-139">SafeDocsDemo.docx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [<span data-ttu-id="6d731-140">SafeDocsDemo.pptx</span><span class="sxs-lookup"><span data-stu-id="6d731-140">SafeDocsDemo.pptx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [<span data-ttu-id="6d731-141">SafeDocsDemo.xlsx</span><span class="sxs-lookup"><span data-stu-id="6d731-141">SafeDocsDemo.xlsx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
