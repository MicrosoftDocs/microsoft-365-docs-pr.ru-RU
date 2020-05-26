---
title: Безопасные документы в Office 365 ATP
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Сведения о безопасных документах в Office 365 ATP.
ms.openlocfilehash: f792b1acbdacfd29db5bbbf377f41396c35e3f17
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2020
ms.locfileid: "44350955"
---
# <a name="safe-documents-in-office-365-advanced-threat-protection"></a><span data-ttu-id="2d739-103">Безопасные документы в Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="2d739-103">Safe Documents in Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="2d739-104">Безопасные документы — это функция в Office 365 Advanced Threat protection (Office 365 ATP), использующая [Advanced Threat Protection в защитнике Microsoft](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) для сканирования документов и файлов, открытых в [режиме защищенного просмотра](https://support.office.com/article/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span><span class="sxs-lookup"><span data-stu-id="2d739-104">Safe Documents is a feature in Office 365 Advanced Threat Protection (Office 365 ATP) that uses [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.office.com/article/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2d739-105">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="2d739-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2d739-106">Эта функция доступна только пользователям, у которых есть лицензия на систему безопасности Microsoft 365 и Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2d739-106">This feature is only available to users with the Microsoft 365 E5 or Microsoft 365 E5 Security license.</span></span>

- <span data-ttu-id="2d739-107">Безопасные документы в настоящее время доступны для общедоступной предварительной версии, доступной для пользователей, которые входят в состав [программы предварительной оценки Office](https://insider.office.com/en-us/join) на странице "ежемесячный канал (целевой)" с Office версии 2002 (12527,20092) или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="2d739-107">Safe Documents is currently available for public preview, available to users that are part of the [Office Insider Program](https://insider.office.com/en-us/join) on the 'Monthly Channel (Targeted)' with Office Version 2002 (12527.20092) or greater.</span></span> <span data-ttu-id="2d739-108">Эта функция отключена по умолчанию и должна быть включена администратором безопасности.</span><span class="sxs-lookup"><span data-stu-id="2d739-108">This feature is off by default and will need to be enabled by the Security Administrator.</span></span>

- <span data-ttu-id="2d739-109">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="2d739-109">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="2d739-110">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="2d739-110">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="2d739-111">Перед выполнением процедур, описанных в этом разделе, необходимо назначить разрешения.</span><span class="sxs-lookup"><span data-stu-id="2d739-111">You need to be assigned permissions before you can perform the procedures in this topic.</span></span> <span data-ttu-id="2d739-112">Чтобы включить и настроить безопасные документы, необходимо быть участником группы ролей " **Управление организацией** " или " **администратор безопасности** ".</span><span class="sxs-lookup"><span data-stu-id="2d739-112">To enable and configure Safe Documents, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="2d739-113">Дополнительные сведения о группах ролей в Центре безопасности и соответствия требованиям см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="2d739-113">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="how-does-microsoft-handle-your-data"></a><span data-ttu-id="2d739-114">Как Майкрософт обрабатывает ваши данные?</span><span class="sxs-lookup"><span data-stu-id="2d739-114">How does Microsoft handle your data?</span></span>

<span data-ttu-id="2d739-115">Чтобы защититься от вирусов, безопасные документы отправляют файлы в облако [Microsoft Defender Advanced Threat protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) для анализа.</span><span class="sxs-lookup"><span data-stu-id="2d739-115">To keep you protected, Safe Documents sends files to the [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span>

- <span data-ttu-id="2d739-116">Сведения о том, как служба защитника (Advanced Thread Protection) отвечает [за поиск данных](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)</span><span class="sxs-lookup"><span data-stu-id="2d739-116">Details on how Microsoft Defender Advanced Thread Protection handles your data can be found [here](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)</span></span>
- <span data-ttu-id="2d739-117">В дополнение к рекомендациям, описанным выше, файлы, отправленные безопасными документами, не сохраняются в защитнике за пределами времени, необходимого для анализа, что обычно составляет менее 24 часов.</span><span class="sxs-lookup"><span data-stu-id="2d739-117">In addition to the guidelines above, files sent by Safe Documents are not retained in Defender beyond the time needed for analysis, which is typically less than 24 hours</span></span>

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="2d739-118">Использование центра безопасности & соответствия требованиям для настройки безопасных документов</span><span class="sxs-lookup"><span data-stu-id="2d739-118">Use the Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="2d739-119">Откройте центр соответствия требованиям по безопасности & по адресу <https://protection.office.com> .</span><span class="sxs-lookup"><span data-stu-id="2d739-119">Open the Security & Compliance Center at <https://protection.office.com>.</span></span>

2. <span data-ttu-id="2d739-120">Перейдите к разделу политика **управления угрозой** \> **Policy** \> **безопасные вложения ATP**.</span><span class="sxs-lookup"><span data-stu-id="2d739-120">Go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

3. <span data-ttu-id="2d739-121">В разделе **Помогите людям безопасно оставаться безопасными, когда вы доверяете файлу для открытия раздела "защищенный просмотр в приложениях Office** ", настройте один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="2d739-121">In the **Help people stay safe when trusting a file to open outside Protected View in Office applications** section, configure either of the following settings:</span></span>

   - <span data-ttu-id="2d739-122">**Включение безопасных документов для клиентов Office (файлы также будут отправляться в облако Майкрософт для глубокого анализа)**</span><span class="sxs-lookup"><span data-stu-id="2d739-122">**Turn on Safe Documents for Office clients (Files will also be sent to Microsoft Cloud for deep analyses)**</span></span>

   - <span data-ttu-id="2d739-123">**Разрешить пользователям щелкать в режиме защищенного просмотра, даже если документы распознает файл как вредоносный**: не рекомендуется включать этот параметр.</span><span class="sxs-lookup"><span data-stu-id="2d739-123">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious**: We recommend that you don't enable this option.</span></span>

4. <span data-ttu-id="2d739-124">По завершении нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="2d739-124">When you're finished, click **Save**.</span></span>

![Страница безопасных вложений ATP](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-documents"></a><span data-ttu-id="2d739-126">Настройка безопасных документов с помощью Exchange Online PowerShell или отдельного EOP PowerShell</span><span class="sxs-lookup"><span data-stu-id="2d739-126">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="2d739-127">Используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="2d739-127">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true|$false> -AllowSafeDocsOpen <$true|$false>
```

- <span data-ttu-id="2d739-128">Параметр _енаблесафедокс_ включает или отключает безопасные документы для всей Организации.</span><span class="sxs-lookup"><span data-stu-id="2d739-128">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>

- <span data-ttu-id="2d739-129">Параметр _алловсафедоксопен_ разрешает или запрещает пользователям оставлять защищенный просмотр (то есть открывать документ), если документ был определен как вредоносный.</span><span class="sxs-lookup"><span data-stu-id="2d739-129">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="2d739-130">В этом примере показано, как включить безопасные документы для всей Организации и запретить пользователям открывать документы, которые были определены как вредоносные из защищенного просмотра.</span><span class="sxs-lookup"><span data-stu-id="2d739-130">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="2d739-131">Подробные сведения о синтаксисе и параметрах можно найти в статье [Set – AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="2d739-131">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="2d739-132">Как проверить, что это работает?</span><span class="sxs-lookup"><span data-stu-id="2d739-132">How do I know this worked?</span></span>

<span data-ttu-id="2d739-133">Чтобы убедиться, что вы включили и настроили безопасные документы, выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="2d739-133">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="2d739-134">В центре безопасности & соответствия требованиям перейдите к разделу политика **управления угрозами** для \> **Policy** \> **безопасных вложений ATP**и убедитесь, что параметры, выбранные в **справке, остаются безопасными при доверии файлу для открытия в разделе "защищенный просмотр в приложениях Office** ".</span><span class="sxs-lookup"><span data-stu-id="2d739-134">In the Security & Compliance Center go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and verify the selections in the **Help people stay safe when trusting a file to open outside Protected View in Office applications** section.</span></span>

- <span data-ttu-id="2d739-135">Выполните следующую команду в Exchange Online PowerShell и проверьте значения свойств:</span><span class="sxs-lookup"><span data-stu-id="2d739-135">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```
