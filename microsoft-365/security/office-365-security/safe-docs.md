---
title: Безопасные документы в Office 365 ATP
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
description: Сведения о безопасных документах в Microsoft 365 E5 или Microsoft 365 E5.
ms.openlocfilehash: cd689099fc6a6caa1e0e649c3f152f1de123bf12
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827473"
---
# <a name="safe-documents-in-microsoft-365-e5"></a><span data-ttu-id="9d29b-103">Безопасные документы в Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="9d29b-103">Safe Documents in Microsoft 365 E5</span></span>

<span data-ttu-id="9d29b-104">Безопасные документы — это функция в Microsoft 365 E5 или Microsoft 365 E5, использующая [Advanced Threat Protection в Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) для проверки документов и файлов, открытых в [режиме защищенного просмотра.](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)</span><span class="sxs-lookup"><span data-stu-id="9d29b-104">Safe Documents is a feature in Microsoft 365 E5 or Microsoft 365 E5 Security that uses [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9d29b-105">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="9d29b-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="9d29b-106">Теперь функция "Безопасные документы" общедоступна пользователям Office версии 2004 (12730.x) или более поздней версии!</span><span class="sxs-lookup"><span data-stu-id="9d29b-106">Safe Documents is now generally available to users with Office Version 2004 (12730.x) or greater!</span></span> <span data-ttu-id="9d29b-107">Эта функция отключена по умолчанию, и ее должен включить администратор безопасности.</span><span class="sxs-lookup"><span data-stu-id="9d29b-107">This feature is off by default and will need to be enabled by the Security Administrator.</span></span>

- <span data-ttu-id="9d29b-108">Эта функция доступна только пользователям, у которых имеется *лицензия microsoft 365 E5* *или Microsoft 365 E5 Security* (не включена в планы Office 365 ATP).</span><span class="sxs-lookup"><span data-stu-id="9d29b-108">This feature is only available to users with the *Microsoft 365 E5* or *Microsoft 365 E5 Security* license (not included in Office 365 ATP plans).</span></span>

- <span data-ttu-id="9d29b-109">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="9d29b-109">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="9d29b-110">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="9d29b-110">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="9d29b-111">Для выполнения процедур, описанных в этом разделе, необходимы права.</span><span class="sxs-lookup"><span data-stu-id="9d29b-111">You need to be assigned permissions before you can perform the procedures in this topic.</span></span> <span data-ttu-id="9d29b-112">Чтобы включить и настроить безопасные документы, вы должны быть членом **группы ролей "Управление организацией"** **или "Администратор** безопасности".</span><span class="sxs-lookup"><span data-stu-id="9d29b-112">To enable and configure Safe Documents, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="9d29b-113">Дополнительные сведения о группах ролей в Центре безопасности и соответствия требованиям см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="9d29b-113">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="how-does-microsoft-handle-your-data"></a><span data-ttu-id="9d29b-114">Как Корпорация Майкрософт обрабатывает ваши данные?</span><span class="sxs-lookup"><span data-stu-id="9d29b-114">How does Microsoft handle your data?</span></span>

<span data-ttu-id="9d29b-115">Чтобы защитить документы, безопасные документы отправляются в [облако Advanced Threat Protection в Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) для анализа.</span><span class="sxs-lookup"><span data-stu-id="9d29b-115">To keep you protected, Safe Documents sends files to the [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span>

- <span data-ttu-id="9d29b-116">Сведения о том, как Advanced Threat Protection обрабатывает ваши данные в Microsoft Defender, можно найти [здесь](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)</span><span class="sxs-lookup"><span data-stu-id="9d29b-116">Details on how Microsoft Defender Advanced Threat Protection handles your data can be found [here](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)</span></span>
- <span data-ttu-id="9d29b-117">Кроме приведенных выше рекомендаций файлы, отправляемые функциями "Безопасные документы", не сохраняются в Защитнике, пока не достает времени, необходимого для анализа , что превышает 24 часа</span><span class="sxs-lookup"><span data-stu-id="9d29b-117">In addition to the guidelines above, files sent by Safe Documents are not retained in Defender beyond the time needed for analysis, which is typically less than 24 hours</span></span>

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="9d29b-118">Настройка безопасных документов с помощью & Центра безопасности</span><span class="sxs-lookup"><span data-stu-id="9d29b-118">Use the Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="9d29b-119">Откройте Центр безопасности & соответствия требованиям на <https://protection.office.com> сайте.</span><span class="sxs-lookup"><span data-stu-id="9d29b-119">Open the Security & Compliance Center at <https://protection.office.com>.</span></span>

2. <span data-ttu-id="9d29b-120">Перейдите в **раздел "Безопасные** \> **Policy** \> **вложения ATP" в разделе "Политика управления угрозами".**</span><span class="sxs-lookup"><span data-stu-id="9d29b-120">Go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

3. <span data-ttu-id="9d29b-121">Настройте следующие параметры **в** разделе справки для пользователей.</span><span class="sxs-lookup"><span data-stu-id="9d29b-121">In the **Help people stay safe when trusting a file to open outside Protected View in Office applications** section, configure either of the following settings:</span></span>

   - <span data-ttu-id="9d29b-122">**Включение безопасных документов для клиентов Office**</span><span class="sxs-lookup"><span data-stu-id="9d29b-122">**Turn on Safe Documents for Office clients**</span></span>

   - <span data-ttu-id="9d29b-123">**Разрешить пользователям переходить в режиме защищенного просмотра, даже если система безопасных**документов определяет файл вредоносным. Мы не рекомендуем включать этот параметр.</span><span class="sxs-lookup"><span data-stu-id="9d29b-123">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious**: We recommend that you don't enable this option.</span></span>

4. <span data-ttu-id="9d29b-124">Выполнив необходимые действия, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9d29b-124">When you're finished, click **Save**.</span></span>

![Страница "Безопасные вложения ATP"](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-documents"></a><span data-ttu-id="9d29b-126">Настройка безопасных документов с помощью Exchange Online PowerShell или автономной службы EOP PowerShell</span><span class="sxs-lookup"><span data-stu-id="9d29b-126">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="9d29b-127">Используйте указанный ниже синтаксис.</span><span class="sxs-lookup"><span data-stu-id="9d29b-127">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- <span data-ttu-id="9d29b-128">Параметр _EnableSafeDocs включает_ или отключает функцию "Безопасные документы" для всей организации.</span><span class="sxs-lookup"><span data-stu-id="9d29b-128">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>

- <span data-ttu-id="9d29b-129">Параметр _AllowSafeDocsOpen_ позволяет или запрещает пользователям выгрузить документ в режиме защищенного просмотра (то есть открывать документ), если он был определен как вредоносный.</span><span class="sxs-lookup"><span data-stu-id="9d29b-129">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="9d29b-130">В этом примере функцию "Безопасные документы" включается для всей организации и запрет открытия документов, определенных как вредоносные, от режима защищенного просмотра.</span><span class="sxs-lookup"><span data-stu-id="9d29b-130">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="9d29b-131">Дополнительные сведения о синтаксисе и параметрах см. в [описании Set-AtpPolicyForO365.](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="9d29b-131">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="9d29b-132">Как проверить, что это работает?</span><span class="sxs-lookup"><span data-stu-id="9d29b-132">How do I know this worked?</span></span>

<span data-ttu-id="9d29b-133">Чтобы убедиться, что вы включили и настроили безопасные документы, выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="9d29b-133">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="9d29b-134">В Центре безопасности & соответствия требованиям откройте **"Безопасные** вложения \> **Policy** \> **ATP"** и проверьте параметры, выбранные в параметрах безопасности, чтобы пользователи не **стали безопасными,** если файл открываться вне раздела приложений Office.</span><span class="sxs-lookup"><span data-stu-id="9d29b-134">In the Security & Compliance Center go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and verify the selections in the **Help people stay safe when trusting a file to open outside Protected View in Office applications** section.</span></span>

- <span data-ttu-id="9d29b-135">Выполните следующую команду в Exchange Online PowerShell и проверьте значения свойств:</span><span class="sxs-lookup"><span data-stu-id="9d29b-135">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```
