---
title: Настройка политик безопасных вложений в Microsoft Defender для Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: Узнайте, как определить политики безопасных вложений для защиты организации от вредоносных файлов в электронной почте.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e96babff19ea981b953d35929813b1e08c000e32
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071198"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="9f9da-103">Настройка политик безопасных вложений в Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="9f9da-103">Set up Safe Attachments policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="9f9da-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="9f9da-104">**Applies to**</span></span>
- [<span data-ttu-id="9f9da-105">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="9f9da-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="9f9da-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9f9da-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="9f9da-107">Эта статья предназначена для бизнес-клиентов, использующих [Microsoft Defender для Office 365](whats-new-in-defender-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="9f9da-107">This article is intended for business customers who have [Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md).</span></span> <span data-ttu-id="9f9da-108">Если вы домашний пользователь, который ищет сведения о сканировании вложений в Outlook, см. в Outlook.com [безопасности.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)</span><span class="sxs-lookup"><span data-stu-id="9f9da-108">If you're a home user looking for information about attachment scanning in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="9f9da-109">Безопасные вложения — это функция [в Microsoft Defender для Office 365,](whats-new-in-defender-for-office-365.md) которая использует виртуальную среду для проверки вложений в входящие сообщения электронной почты после проверки защиты от вредоносных программ в Exchange Online Protection [(EOP),](anti-malware-protection.md)но перед доставкой получателям.</span><span class="sxs-lookup"><span data-stu-id="9f9da-109">Safe Attachments is a feature in [Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md) that uses a virtual environment to check attachments in inbound email messages after they've been scanned by [anti-malware protection in Exchange Online Protection (EOP)](anti-malware-protection.md), but before delivery to recipients.</span></span> <span data-ttu-id="9f9da-110">Дополнительные сведения см. в [веб-сайте Безопасные вложения в Microsoft Defender для Office 365.](safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="9f9da-110">For more information, see [Safe Attachments in Microsoft Defender for Office 365](safe-attachments.md).</span></span>

<span data-ttu-id="9f9da-111">Не существует встроенной или по умолчанию политики безопасных вложений.</span><span class="sxs-lookup"><span data-stu-id="9f9da-111">There's no built-in or default Safe Attachments policy.</span></span> <span data-ttu-id="9f9da-112">Чтобы получить сканирование безопасных вложений для вложений сообщений электронной почты, необходимо создать одну или несколько политик безопасных вложений, как описано в этой статье.</span><span class="sxs-lookup"><span data-stu-id="9f9da-112">To get Safe Attachments scanning of email message attachments, you need to create one or more Safe Attachments policies as described in this article.</span></span>

<span data-ttu-id="9f9da-113">Политики безопасных вложений можно настроить в Центре соответствия требованиям & безопасности или в PowerShell (Exchange Online PowerShell для организаций Microsoft 365 с почтовыми ящиками в Exchange Online; автономных EOP PowerShell для организаций без почтовых ящиков Exchange Online, но с надстройкой Defender для Office 365).</span><span class="sxs-lookup"><span data-stu-id="9f9da-113">You can configure Safe Attachments policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="9f9da-114">Основные элементы политики безопасных вложений:</span><span class="sxs-lookup"><span data-stu-id="9f9da-114">The basic elements of a Safe Attachments policy are:</span></span>

- <span data-ttu-id="9f9da-115">**Политика** безопасного вложения: указывает действия для обнаружения неизвестных вредоносных программ, отправку сообщений с вложениями вредоносных программ на указанный адрес электронной почты и отправку сообщений, если сканирование безопасных вложений не может завершиться.</span><span class="sxs-lookup"><span data-stu-id="9f9da-115">**The safe attachment policy**: Specifies the actions for unknown malware detections, whether to send messages with malware attachments to a specified email address, and whether to deliver messages if Safe Attachments scanning can't complete.</span></span>
- <span data-ttu-id="9f9da-116">**Правило безопасного вложения:** указывает фильтры приоритета и получателя (к кому применяется политика).</span><span class="sxs-lookup"><span data-stu-id="9f9da-116">**The safe attachment rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="9f9da-117">Разница между этими двумя элементами не очевидна при управлении полициями безопасных вложений в Центре & безопасности:</span><span class="sxs-lookup"><span data-stu-id="9f9da-117">The difference between these two elements isn't obvious when you manage Safe Attachments polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="9f9da-118">При создании политики безопасных вложений создается правило безопасного вложения и связанная политика безопасного вложения одновременно с тем же именем для обоих.</span><span class="sxs-lookup"><span data-stu-id="9f9da-118">When you create a Safe Attachments policy, you're actually creating a safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="9f9da-119">При изменении политики безопасных вложений параметры, связанные с именем, приоритетом, включенной или отключенной, и фильтры получателей изменяют правило безопасного вложения.</span><span class="sxs-lookup"><span data-stu-id="9f9da-119">When you modify a Safe Attachments policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe attachment rule.</span></span> <span data-ttu-id="9f9da-120">Все остальные параметры изменяют связанную политику безопасного вложения.</span><span class="sxs-lookup"><span data-stu-id="9f9da-120">All other settings modify the associated safe attachment policy.</span></span>
- <span data-ttu-id="9f9da-121">При удалении политики безопасных вложений правило безопасного вложения и связанная политика безопасного вложения удаляются.</span><span class="sxs-lookup"><span data-stu-id="9f9da-121">When you remove a Safe Attachments policy, the safe attachment rule and the associated safe attachment policy are removed.</span></span>

<span data-ttu-id="9f9da-122">В Exchange Online PowerShell или автономном EOP PowerShell вы управляете политикой и правилом отдельно.</span><span class="sxs-lookup"><span data-stu-id="9f9da-122">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="9f9da-123">Дополнительные сведения см. в разделе Use Exchange Online PowerShell или автономный [EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) для настройки политики безопасных вложений в дальнейшем в этой статье.</span><span class="sxs-lookup"><span data-stu-id="9f9da-123">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) section later in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="9f9da-124">В области глобальных параметров параметров безопасных вложений настраиваются функции, не зависящие от политик безопасных вложений.</span><span class="sxs-lookup"><span data-stu-id="9f9da-124">In the global settings area of Safe Attachments settings, you configure features that are not dependent on Safe Attachments policies.</span></span> <span data-ttu-id="9f9da-125">Инструкции см. в раздел Включить безопасные вложения [для SharePoint, OneDrive и Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md) и безопасные документы в Microsoft [365 E5.](safe-docs.md)</span><span class="sxs-lookup"><span data-stu-id="9f9da-125">For instructions see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md) and [Safe Documents in Microsoft 365 E5](safe-docs.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9f9da-126">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="9f9da-126">What do you need to know before you begin?</span></span>

- <span data-ttu-id="9f9da-127">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="9f9da-127">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="9f9da-128">Чтобы перейти непосредственно на страницу **Безопасные вложения,** используйте <https://protection.office.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="9f9da-128">To go directly to the **Safe Attachments** page, use <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="9f9da-129">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="9f9da-129">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="9f9da-130">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="9f9da-130">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="9f9da-131">Прежде чем делать процедуры в этой статье, необходимо получить соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="9f9da-131">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="9f9da-132">Чтобы создать, изменить и удалить политики безопасных вложений, необходимо быть членом групп ролей управления организацией или  администратором безопасности  в Центре обеспечения безопасности & соответствия требованиям и членом группы ролей управления организацией в Exchange Online.  </span><span class="sxs-lookup"><span data-stu-id="9f9da-132">To create, modify, and delete Safe Attachments policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="9f9da-133">Для доступа только для чтения к политикам безопасных вложений необходимо быть членом групп ролей **Global Reader** или **Security Reader** в Центре & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="9f9da-133">For read-only access to Safe Attachments policies, you need to be a member of the **Global Reader** or **Security Reader** role groups in the Security & Compliance Center.</span></span>

  <span data-ttu-id="9f9da-134">Дополнительные сведения см. [в веб-сайте Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online.](/exchange/permissions-exo/permissions-exo)</span><span class="sxs-lookup"><span data-stu-id="9f9da-134">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="9f9da-135">**Примечания**.</span><span class="sxs-lookup"><span data-stu-id="9f9da-135">**Notes**:</span></span>

  - <span data-ttu-id="9f9da-136">Добавление пользователей в соответствующую роль Azure Active Directory в Центре безопасности Microsoft 365 предоставляет пользователям необходимые разрешения в Центре безопасности и соответствия требованиям _и_ разрешения для других функций в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9f9da-136">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="9f9da-137">Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="9f9da-137">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="9f9da-138">Группа ролей **Управление организацией с правами только на просмотр** в [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) также предоставляет доступ только для чтения к этой функции.</span><span class="sxs-lookup"><span data-stu-id="9f9da-138">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="9f9da-139">Рекомендуемые параметры для политик безопасных вложений см. в приложении ["Безопасные вложения".](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)</span><span class="sxs-lookup"><span data-stu-id="9f9da-139">For our recommended settings for Safe Attachments policies, see [Safe Attachments settings](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).</span></span>

- <span data-ttu-id="9f9da-140">Разрешить до 30 минут для новой или обновленной политики, которая будет применяться.</span><span class="sxs-lookup"><span data-stu-id="9f9da-140">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-attachments-policies"></a><span data-ttu-id="9f9da-141">Используйте Центр & безопасности для создания политик безопасных вложений</span><span class="sxs-lookup"><span data-stu-id="9f9da-141">Use the Security & Compliance Center to create Safe Attachments policies</span></span>

<span data-ttu-id="9f9da-142">Создание настраиваемой политики безопасных вложений в Центре & безопасности создает правило безопасного вложения и связанную политику безопасного вложения одновременно с использованием одного и того же имени для обоих.</span><span class="sxs-lookup"><span data-stu-id="9f9da-142">Creating a custom Safe Attachments policy in the Security & Compliance Center creates the safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="9f9da-143">В Центре обеспечения & безопасности перейдите к **политике** управления угрозами \>  \> **ATP Safe Attachments**.</span><span class="sxs-lookup"><span data-stu-id="9f9da-143">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="9f9da-144">На странице **Безопасные вложения** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="9f9da-144">On the **Safe Attachments** page, click **Create**.</span></span>

3. <span data-ttu-id="9f9da-145">Откроется **мастер** политики политики "Новые безопасные вложения".</span><span class="sxs-lookup"><span data-stu-id="9f9da-145">The **New Safe Attachments policy** wizard opens.</span></span> <span data-ttu-id="9f9da-146">На странице **Имя политики** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="9f9da-146">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="9f9da-147">**Имя**. Укажите уникальное, понятное имя политики.</span><span class="sxs-lookup"><span data-stu-id="9f9da-147">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="9f9da-148">**Описание**. Укажите необязательное описание политики.</span><span class="sxs-lookup"><span data-stu-id="9f9da-148">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="9f9da-149">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9f9da-149">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="9f9da-150">На **странице Параметры,** которая появится, настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="9f9da-150">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="9f9da-151">**Безопасные вложения неизвестный ответ вредоносных** программ: Выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="9f9da-151">**Safe Attachments unknown malware response**: Select one of the following values:</span></span>

     - <span data-ttu-id="9f9da-152">**Off.** Как правило, мы не рекомендуем это значение.</span><span class="sxs-lookup"><span data-stu-id="9f9da-152">**Off**: Typically, we don't recommend this value.</span></span>
     - <span data-ttu-id="9f9da-153">**Монитор**</span><span class="sxs-lookup"><span data-stu-id="9f9da-153">**Monitor**</span></span>
     - <span data-ttu-id="9f9da-154">**Блок.** Это значение по умолчанию и рекомендуемое значение в стандартных и строгих [предустановленных политиках безопасности.](preset-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="9f9da-154">**Block**: This is the default value, and the recommended value in Standard and Strict [preset security policies](preset-security-policies.md).</span></span>
     - <span data-ttu-id="9f9da-155">**Замена**</span><span class="sxs-lookup"><span data-stu-id="9f9da-155">**Replace**</span></span>
     - <span data-ttu-id="9f9da-156">**Динамическая доставка (функция предварительного просмотра)**</span><span class="sxs-lookup"><span data-stu-id="9f9da-156">**Dynamic Delivery (Preview Feature)**</span></span>

     <span data-ttu-id="9f9da-157">Эти значения объясняются в параметрах политики [безопасных вложений.](safe-attachments.md#safe-attachments-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="9f9da-157">These values are explained in [Safe Attachments policy settings](safe-attachments.md#safe-attachments-policy-settings).</span></span>

   - <span data-ttu-id="9f9da-158">Отправьте вложение на следующий адрес **электронной** почты: Для значений действия  **Block**, **Monitor** или **Replace** можно выбрать Включить перенаправление для отправки сообщений, содержащих вложения вредоносных программ, на указанный внутренний или внешний адрес электронной почты для анализа и исследования.</span><span class="sxs-lookup"><span data-stu-id="9f9da-158">**Send the attachment to the following email address**: For the action values **Block**, **Monitor**, or **Replace**, you can select **Enable redirect** to send messages that contain malware attachments to the specified internal or external email address for analysis and investigation.</span></span>

     <span data-ttu-id="9f9da-159">Рекомендация для параметров стандартных и строгих политик — включить перенаправление.</span><span class="sxs-lookup"><span data-stu-id="9f9da-159">The recommendation for Standard and Strict policy settings is to enable redirection.</span></span> <span data-ttu-id="9f9da-160">Дополнительные сведения см. в [приложении "Безопасные вложения".](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)</span><span class="sxs-lookup"><span data-stu-id="9f9da-160">For more information, see [Safe Attachments settings](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).</span></span>

   - <span data-ttu-id="9f9da-161">Применив указанный выше выбор, если при сканировании вредоносных программ для вложений происходит время или возникает **ошибка:** действие, указанное в безопасных вложениях, неизвестное вредоносное по ответам, будет приниматься в сообщениях даже в тех случаях, когда сканирование безопасных вложений не может завершиться. </span><span class="sxs-lookup"><span data-stu-id="9f9da-161">**Apply the above selection if malware scanning for attachments times out or error occurs**: The action specified by **Safe Attachments unknown malware response** is taken on messages even when Safe Attachments scanning can't complete.</span></span> <span data-ttu-id="9f9da-162">Если выбран этот параметр, всегда выберите перенаправление **с включенной поддержкой.**</span><span class="sxs-lookup"><span data-stu-id="9f9da-162">If you selected this option, always select **Enabled redirect**.</span></span> <span data-ttu-id="9f9da-163">В противном случае сообщения могут быть потеряны.</span><span class="sxs-lookup"><span data-stu-id="9f9da-163">Otherwise, messages might be lost.</span></span>

   <span data-ttu-id="9f9da-164">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9f9da-164">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="9f9da-165">На странице **Applied to** page, которая появится, определите внутренних получателей, к которые применяется политика.</span><span class="sxs-lookup"><span data-stu-id="9f9da-165">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="9f9da-166">Условие или исключение можно использовать только один раз, но можно указать для них несколько значений.</span><span class="sxs-lookup"><span data-stu-id="9f9da-166">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="9f9da-167">Указать несколько значений в одном условии или исключении можно с помощью оператора OR (например, _\<recipient1\>_ or _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="9f9da-167">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="9f9da-168">Между разными условиями и исключениями используется оператор AND (например, _\<recipient1\>_ and _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="9f9da-168">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="9f9da-169">Нажмите **кнопку Добавить условие**.</span><span class="sxs-lookup"><span data-stu-id="9f9da-169">Click **Add a condition**.</span></span> <span data-ttu-id="9f9da-170">В отсеве, которое появится, выберите условие в **applied, если**:</span><span class="sxs-lookup"><span data-stu-id="9f9da-170">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="9f9da-171">**Получатель:** указывает один или несколько почтовых ящиков, пользователей почты или почтовых контактов в организации.</span><span class="sxs-lookup"><span data-stu-id="9f9da-171">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="9f9da-172">**Получатель является членом**: указывает одну или несколько групп в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="9f9da-172">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="9f9da-173">**Домен получателя**: Указывает получателей в одном или нескольких настроенных принятых доменов в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="9f9da-173">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="9f9da-174">После выбора условия в любом из этих поле появится соответствующее **отсев.**</span><span class="sxs-lookup"><span data-stu-id="9f9da-174">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="9f9da-175">Щелкните в поле и прокрутите список значений для выбора.</span><span class="sxs-lookup"><span data-stu-id="9f9da-175">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="9f9da-176">Щелкните в поле и начните печатать, чтобы отфильтровать список и выбрать значение.</span><span class="sxs-lookup"><span data-stu-id="9f9da-176">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="9f9da-177">Чтобы добавить дополнительные значения, щелкните в пустой области в поле.</span><span class="sxs-lookup"><span data-stu-id="9f9da-177">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="9f9da-178">Чтобы удалить отдельные записи, **нажмите кнопку Удалить** ![ значок Удалить ](../../media/scc-remove-icon.png) значение.</span><span class="sxs-lookup"><span data-stu-id="9f9da-178">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="9f9da-179">Чтобы удалить все условие, нажмите **кнопку Удалить значок Удалить** ![ в ](../../media/scc-remove-icon.png) состоянии.</span><span class="sxs-lookup"><span data-stu-id="9f9da-179">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="9f9da-180">Чтобы добавить дополнительное условие, нажмите **кнопку Добавить условие** и выберите оставшееся значение **в applied if**.</span><span class="sxs-lookup"><span data-stu-id="9f9da-180">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="9f9da-181">Чтобы добавить исключения, нажмите **кнопку Добавить условие** и выберите исключение в соответствии **с исключением, если**.</span><span class="sxs-lookup"><span data-stu-id="9f9da-181">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="9f9da-182">Параметры и поведение полностью идентичны условиям.</span><span class="sxs-lookup"><span data-stu-id="9f9da-182">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="9f9da-183">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9f9da-183">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="9f9da-184">На странице **Обзор параметров,** которая отображается, просмотрите параметры.</span><span class="sxs-lookup"><span data-stu-id="9f9da-184">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="9f9da-185">Чтобы изменить его, можно нажать **кнопку Изменить** каждый параметр.</span><span class="sxs-lookup"><span data-stu-id="9f9da-185">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="9f9da-186">Закончив, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="9f9da-186">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-attachments-policies"></a><span data-ttu-id="9f9da-187">Используйте Центр & безопасности для просмотра политик безопасных вложений</span><span class="sxs-lookup"><span data-stu-id="9f9da-187">Use the Security & Compliance Center to view Safe Attachments policies</span></span>

1. <span data-ttu-id="9f9da-188">В Центре обеспечения & безопасности перейдите к **политике** управления угрозами \>  \> **ATP Safe Attachments**.</span><span class="sxs-lookup"><span data-stu-id="9f9da-188">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="9f9da-189">На странице **Безопасные вложения** выберите политику из списка и нажмите на нее (не выберите поле).</span><span class="sxs-lookup"><span data-stu-id="9f9da-189">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="9f9da-190">Сведения о политике отображаются в вылете</span><span class="sxs-lookup"><span data-stu-id="9f9da-190">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-attachments-policies"></a><span data-ttu-id="9f9da-191">Используйте Центр & безопасности для изменения политик безопасных вложений</span><span class="sxs-lookup"><span data-stu-id="9f9da-191">Use the Security & Compliance Center to modify Safe Attachments policies</span></span>

1. <span data-ttu-id="9f9da-192">В Центре обеспечения & безопасности перейдите к **политике** управления угрозами \>  \> **ATP Safe Attachments**.</span><span class="sxs-lookup"><span data-stu-id="9f9da-192">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="9f9da-193">На странице **Безопасные вложения** выберите политику из списка и нажмите на нее (не выберите поле).</span><span class="sxs-lookup"><span data-stu-id="9f9da-193">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="9f9da-194">В появились сведения о политике, нажмите **кнопку Изменить политику**.</span><span class="sxs-lookup"><span data-stu-id="9f9da-194">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="9f9da-195">Доступные параметры в вылете, которые появляются, идентичны тем, которые описаны в разделе Use the Security & Compliance Center для создания политик безопасных [вложений.](#use-the-security--compliance-center-to-create-safe-attachments-policies)</span><span class="sxs-lookup"><span data-stu-id="9f9da-195">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Attachments policies](#use-the-security--compliance-center-to-create-safe-attachments-policies) section.</span></span>

<span data-ttu-id="9f9da-196">Чтобы включить или отключить политику или установить порядок приоритета политики, см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="9f9da-196">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-attachments-policies"></a><span data-ttu-id="9f9da-197">Включить или отключить политики безопасных вложений</span><span class="sxs-lookup"><span data-stu-id="9f9da-197">Enable or disable Safe Attachments policies</span></span>

1. <span data-ttu-id="9f9da-198">В Центре обеспечения & безопасности перейдите к **политике** управления угрозами \>  \> **ATP Safe Attachments**.</span><span class="sxs-lookup"><span data-stu-id="9f9da-198">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="9f9da-199">Обратите внимание на значение в **столбце Состояние:**</span><span class="sxs-lookup"><span data-stu-id="9f9da-199">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="9f9da-200">Перемещение перемежа влево</span><span class="sxs-lookup"><span data-stu-id="9f9da-200">Move the toggle to the left</span></span> ![Отключение политики](../../media/scc-toggle-off.png) <span data-ttu-id="9f9da-202">отключение политики.</span><span class="sxs-lookup"><span data-stu-id="9f9da-202">to disable the policy.</span></span>

   - <span data-ttu-id="9f9da-203">Перемещение перемыкать вправо</span><span class="sxs-lookup"><span data-stu-id="9f9da-203">Move the toggle to the right</span></span> ![Включаем политику](../../media/scc-toggle-on.png) <span data-ttu-id="9f9da-205">включить политику.</span><span class="sxs-lookup"><span data-stu-id="9f9da-205">to enable the policy.</span></span>

### <a name="set-the-priority-of-safe-attachments-policies"></a><span data-ttu-id="9f9da-206">Заорит приоритет политик безопасных вложений</span><span class="sxs-lookup"><span data-stu-id="9f9da-206">Set the priority of Safe Attachments policies</span></span>

<span data-ttu-id="9f9da-207">По умолчанию политикам безопасных вложений предоставляется приоритет, основанный на порядке, в который они были созданы (более новые политики имеют более низкий приоритет по сравнению с более старыми политиками).</span><span class="sxs-lookup"><span data-stu-id="9f9da-207">By default, Safe Attachments policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="9f9da-208">Чем ниже значение, тем выше приоритет политики (0 — наивысший приоритет), а порядок обработки политик зависит от их приоритетов (политики с высоким приоритетом обрабатываются раньше, чем политики с низким приоритетом).</span><span class="sxs-lookup"><span data-stu-id="9f9da-208">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="9f9da-209">Никакие две политики не могут иметь одинаковый приоритет, и обработка политики прекращается после применения первой политики.</span><span class="sxs-lookup"><span data-stu-id="9f9da-209">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="9f9da-210">Дополнительные сведения о приоритетах, а также оценке и применении нескольких политик см. в статье [Порядок и приоритет защиты электронной почты](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="9f9da-210">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="9f9da-211">Политики безопасных вложений отображаются в порядке их обработки (первая политика имеет значение **Priority** 0).</span><span class="sxs-lookup"><span data-stu-id="9f9da-211">Safe Attachments policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

<span data-ttu-id="9f9da-212">**Примечание.** В Центре & безопасности можно изменить приоритет политики безопасных вложений только после ее создания.</span><span class="sxs-lookup"><span data-stu-id="9f9da-212">**Note**: In the Security & Compliance Center, you can only change the priority of the Safe Attachments policy after you create it.</span></span> <span data-ttu-id="9f9da-213">В PowerShell можно переопредить приоритет по умолчанию при создании правила безопасного вложения (которое может повлиять на приоритет существующих правил).</span><span class="sxs-lookup"><span data-stu-id="9f9da-213">In PowerShell, you can override the default priority when you create the safe attachment rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="9f9da-214">Чтобы изменить приоритет политики, переместите ее вверх или вниз в списке (в Центре безопасности и соответствия требованиям невозможно напрямую изменить значение свойства **Приоритет**).</span><span class="sxs-lookup"><span data-stu-id="9f9da-214">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="9f9da-215">В Центре обеспечения & безопасности перейдите к **политике** управления угрозами \>  \> **ATP Safe Attachments**.</span><span class="sxs-lookup"><span data-stu-id="9f9da-215">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="9f9da-216">На странице **Безопасные вложения** выберите политику из списка и нажмите на нее (не выберите поле).</span><span class="sxs-lookup"><span data-stu-id="9f9da-216">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="9f9da-217">В появились сведения о политике, щелкните доступную кнопку приоритета.</span><span class="sxs-lookup"><span data-stu-id="9f9da-217">In the policy details fly out that appears, click the available priority button.</span></span>

   - <span data-ttu-id="9f9da-218">Политика безопасных вложений со **значением Приоритет** **0** имеет только доступную кнопку **Приоритет уменьшения.**</span><span class="sxs-lookup"><span data-stu-id="9f9da-218">The Safe Attachments policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="9f9da-219">Политика безопасных вложений  с наименьшим значением приоритета (например, **3)** имеет только доступную кнопку **"Увеличение приоритета".**</span><span class="sxs-lookup"><span data-stu-id="9f9da-219">The Safe Attachments policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="9f9da-220">Если у вас есть три или более политик безопасных вложений, политики между самыми высокими и самыми низкими значениями приоритетов имеют доступные кнопки **Приоритеты** повышения и Уменьшения приоритетов. </span><span class="sxs-lookup"><span data-stu-id="9f9da-220">If you have three or more Safe Attachments policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="9f9da-221">Щелкните **Увеличить приоритет или** уменьшить **приоритет,** чтобы изменить **значение Priority.**</span><span class="sxs-lookup"><span data-stu-id="9f9da-221">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="9f9da-222">Когда закончите, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="9f9da-222">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-attachments-policies"></a><span data-ttu-id="9f9da-223">С помощью Центра & безопасности для удаления политик безопасных вложений</span><span class="sxs-lookup"><span data-stu-id="9f9da-223">Use the Security & Compliance Center to remove Safe Attachments policies</span></span>

1. <span data-ttu-id="9f9da-224">В Центре обеспечения & безопасности перейдите к **политике** управления угрозами \>  \> **ATP Safe Attachments**.</span><span class="sxs-lookup"><span data-stu-id="9f9da-224">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="9f9da-225">На странице **Безопасные вложения** выберите политику из списка и нажмите на нее (не выберите поле).</span><span class="sxs-lookup"><span data-stu-id="9f9da-225">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="9f9da-226">В появились сведения о политике, нажмите кнопку **Удалить** политику, а затем нажмите **кнопку Да** в диалоговом окте предупреждения, который появится.</span><span class="sxs-lookup"><span data-stu-id="9f9da-226">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a><span data-ttu-id="9f9da-227">Используйте Exchange Online PowerShell или автономный EOP PowerShell для настройки политик безопасных вложений</span><span class="sxs-lookup"><span data-stu-id="9f9da-227">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies</span></span>

<span data-ttu-id="9f9da-228">Как описано выше, политика безопасных вложений состоит из политики безопасного вложения и правила безопасного вложения.</span><span class="sxs-lookup"><span data-stu-id="9f9da-228">As previously described, a Safe Attachments policy consists of a safe attachment policy and a safe attachment rule.</span></span>

<span data-ttu-id="9f9da-229">В PowerShell разница между политиками безопасного вложения и правилами безопасного вложения очевидна.</span><span class="sxs-lookup"><span data-stu-id="9f9da-229">In PowerShell, the difference between safe attachment policies and safe attachment rules is apparent.</span></span> <span data-ttu-id="9f9da-230">Вы управляете политиками безопасного вложения с помощью **\* кодлетов -SafeAttachmentPolicy** и управляете правилами безопасного вложения с помощью cmdlets **\* -SafeAttachmentRule.**</span><span class="sxs-lookup"><span data-stu-id="9f9da-230">You manage safe attachment policies by using the **\*-SafeAttachmentPolicy** cmdlets, and you manage safe attachment rules by using the **\*-SafeAttachmentRule** cmdlets.</span></span>

- <span data-ttu-id="9f9da-231">В PowerShell сначала создается политика безопасного вложения, а затем создается правило безопасного вложения, которое определяет политику, к которую применяется правило.</span><span class="sxs-lookup"><span data-stu-id="9f9da-231">In PowerShell, you create the safe attachment policy first, then you create the safe attachment rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="9f9da-232">В PowerShell параметры политики безопасного вложения и правила безопасного вложения изменяются отдельно.</span><span class="sxs-lookup"><span data-stu-id="9f9da-232">In PowerShell, you modify the settings in the safe attachment policy and the safe attachment rule separately.</span></span>
- <span data-ttu-id="9f9da-233">При удалении политики безопасного вложения из PowerShell соответствующее правило безопасного вложения не удаляется автоматически, и наоборот.</span><span class="sxs-lookup"><span data-stu-id="9f9da-233">When you remove a safe attachment policy from PowerShell, the corresponding safe attachment rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-attachments-policies"></a><span data-ttu-id="9f9da-234">Использование PowerShell для создания политик безопасных вложений</span><span class="sxs-lookup"><span data-stu-id="9f9da-234">Use PowerShell to create Safe Attachments policies</span></span>

<span data-ttu-id="9f9da-235">Создание политики безопасных вложений в PowerShell — это двухшаговая процедура:</span><span class="sxs-lookup"><span data-stu-id="9f9da-235">Creating a Safe Attachments policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="9f9da-236">Создание политики безопасного вложения.</span><span class="sxs-lookup"><span data-stu-id="9f9da-236">Create the safe attachment policy.</span></span>
2. <span data-ttu-id="9f9da-237">Создайте правило безопасного вложения, которое указывает политику безопасного вложения, которая применяется к этому правилу.</span><span class="sxs-lookup"><span data-stu-id="9f9da-237">Create the safe attachment rule that specifies the safe attachment policy that the rule applies to.</span></span>

 <span data-ttu-id="9f9da-238">**Примечания.**</span><span class="sxs-lookup"><span data-stu-id="9f9da-238">**Notes**:</span></span>

- <span data-ttu-id="9f9da-239">Можно создать новое правило безопасного вложения и назначить ему существующую, неассоциированную политику безопасного вложения.</span><span class="sxs-lookup"><span data-stu-id="9f9da-239">You can create a new safe attachment rule and assign an existing, unassociated safe attachment policy to it.</span></span> <span data-ttu-id="9f9da-240">Правило безопасного вложения не может быть связано с более чем одной политикой безопасного вложения.</span><span class="sxs-lookup"><span data-stu-id="9f9da-240">A safe attachment rule can't be associated with more than one safe attachment policy.</span></span>

- <span data-ttu-id="9f9da-241">Вы можете настроить следующие параметры для новых политик безопасного вложения в PowerShell, которые недоступны в Центре & безопасности до момента создания политики:</span><span class="sxs-lookup"><span data-stu-id="9f9da-241">You can configure the following settings on new safe attachment policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>
  - <span data-ttu-id="9f9da-242">Создайте новую политику как отключенную _(включена_ `$false` в **кодлете New-SafeAttachmentRule).**</span><span class="sxs-lookup"><span data-stu-id="9f9da-242">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeAttachmentRule** cmdlet).</span></span>
  - <span data-ttu-id="9f9da-243">Задай приоритет политики во время создания _(приоритет)_ в _\<Number\>_ **кодлете New-SafeAttachmentRule.**</span><span class="sxs-lookup"><span data-stu-id="9f9da-243">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeAttachmentRule** cmdlet).</span></span>

- <span data-ttu-id="9f9da-244">Новая политика безопасного вложения, которую вы создаете в PowerShell, не отображается в Центре & безопасности, пока не назначите политику правилу безопасного вложения.</span><span class="sxs-lookup"><span data-stu-id="9f9da-244">A new safe attachment policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe attachment rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a><span data-ttu-id="9f9da-245">Шаг 1. Использование PowerShell для создания политики безопасного вложения</span><span class="sxs-lookup"><span data-stu-id="9f9da-245">Step 1: Use PowerShell to create a safe attachment policy</span></span>

<span data-ttu-id="9f9da-246">Чтобы создать безопасную политику вложений, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="9f9da-246">To create a safe attachment policy, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

<span data-ttu-id="9f9da-247">В этом примере создается политика безопасного вложения с именем Contoso All со следующими значениями:</span><span class="sxs-lookup"><span data-stu-id="9f9da-247">This example creates a safe attachment policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="9f9da-248">Блокируют сообщения, содержащие вредоносные программы при сканировании безопасных документов (мы не используем параметр _Action,_ а значение по `Block` умолчанию).</span><span class="sxs-lookup"><span data-stu-id="9f9da-248">Block messages that are found to contain malware by Safe Documents scanning (we aren't using the _Action_ parameter, and the default value is `Block`).</span></span>
- <span data-ttu-id="9f9da-249">Перенаправление включено, и сообщения, содержащие вредоносные программы, отправляются в sec-ops@contoso.com для анализа и исследования.</span><span class="sxs-lookup"><span data-stu-id="9f9da-249">Redirection is enabled, and messages that are found to contain malware are sent to sec-ops@contoso.com for analysis and investigation.</span></span>
- <span data-ttu-id="9f9da-250">Если проверка безопасных вложений недоступна или встречаются ошибки, не доставляйте сообщение (мы не используем параметр _ActionOnError,_ а значение по `$true` умолчанию).</span><span class="sxs-lookup"><span data-stu-id="9f9da-250">If Safe Attachments scanning isn't available or encounters errors, don't deliver the message (we aren't using the _ActionOnError_ parameter, and the default value is `$true`).</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

<span data-ttu-id="9f9da-251">Подробные сведения о синтаксисах и параметрах см. в [обзоре New-SafeAttachmentPolicy.](/powershell/module/exchange/new-safeattachmentpolicy)</span><span class="sxs-lookup"><span data-stu-id="9f9da-251">For detailed syntax and parameter information, see [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a><span data-ttu-id="9f9da-252">Шаг 2. Использование PowerShell для создания правила безопасного вложения</span><span class="sxs-lookup"><span data-stu-id="9f9da-252">Step 2: Use PowerShell to create a safe attachment rule</span></span>

<span data-ttu-id="9f9da-253">Чтобы создать правило безопасного вложения, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="9f9da-253">To create a safe attachment rule, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="9f9da-254">В этом примере создается правило безопасного вложения с именем Contoso All со следующими условиями:</span><span class="sxs-lookup"><span data-stu-id="9f9da-254">This example creates a safe attachment rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="9f9da-255">Это правило связано с политикой безопасного вложения с именем Contoso All.</span><span class="sxs-lookup"><span data-stu-id="9f9da-255">The rule is associated with the safe attachment policy named Contoso All.</span></span>
- <span data-ttu-id="9f9da-256">Правило применяется ко всем получателям в contoso.com домене.</span><span class="sxs-lookup"><span data-stu-id="9f9da-256">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="9f9da-257">Так как мы не используем параметр _Priority,_ используется приоритет по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9f9da-257">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="9f9da-258">Правило включено (мы не используем параметр _Включен,_ а значение по `$true` умолчанию).</span><span class="sxs-lookup"><span data-stu-id="9f9da-258">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="9f9da-259">Подробные сведения о синтаксисах и параметрах см. [в обзоре New-SafeAttachmentRule.](/powershell/module/exchange/new-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="9f9da-259">For detailed syntax and parameter information, see [New-SafeAttachmentRule](/powershell/module/exchange/new-safeattachmentrule).</span></span>

### <a name="use-powershell-to-view-safe-attachment-policies"></a><span data-ttu-id="9f9da-260">Использование PowerShell для просмотра политик безопасного вложения</span><span class="sxs-lookup"><span data-stu-id="9f9da-260">Use PowerShell to view safe attachment policies</span></span>

<span data-ttu-id="9f9da-261">Чтобы просмотреть существующие политики безопасного вложения, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="9f9da-261">To view existing safe attachment policies, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="9f9da-262">В этом примере возвращается сводный список всех политик безопасного вложения.</span><span class="sxs-lookup"><span data-stu-id="9f9da-262">This example returns a summary list of all safe attachment policies.</span></span>

```PowerShell
Get-SafeAttachmentPolicy
```

<span data-ttu-id="9f9da-263">В этом примере возвращаются подробные сведения о политике безопасного вложения с именем Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="9f9da-263">This example returns detailed information for the safe attachment policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="9f9da-264">Подробные сведения о синтаксисах и параметрах см. в [обзоре Get-SafeAttachmentPolicy.](/powershell/module/exchange/get-safeattachmentpolicy)</span><span class="sxs-lookup"><span data-stu-id="9f9da-264">For detailed syntax and parameter information, see [Get-SafeAttachmentPolicy](/powershell/module/exchange/get-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-view-safe-attachment-rules"></a><span data-ttu-id="9f9da-265">Использование PowerShell для просмотра правил безопасного вложения</span><span class="sxs-lookup"><span data-stu-id="9f9da-265">Use PowerShell to view safe attachment rules</span></span>

<span data-ttu-id="9f9da-266">Чтобы просмотреть существующие правила безопасного вложения, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="9f9da-266">To view existing safe attachment rules, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="9f9da-267">В этом примере возвращается сводный список всех правил безопасного вложения.</span><span class="sxs-lookup"><span data-stu-id="9f9da-267">This example returns a summary list of all safe attachment rules.</span></span>

```PowerShell
Get-SafeAttachmentRule
```

<span data-ttu-id="9f9da-268">Чтобы отфильтровать список по включенным или отключенным правилам, выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="9f9da-268">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeAttachmentRule -State Disabled
```

```PowerShell
Get-SafeAttachmentRule -State Enabled
```

<span data-ttu-id="9f9da-269">В этом примере возвращается подробная информация для правила безопасного вложения с именем Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="9f9da-269">This example returns detailed information for the safe attachment rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="9f9da-270">Подробные сведения о синтаксисах и параметрах см. в [ссылке Get-SafeAttachmentRule.](/powershell/module/exchange/get-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="9f9da-270">For detailed syntax and parameter information, see [Get-SafeAttachmentRule](/powershell/module/exchange/get-safeattachmentrule).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-policies"></a><span data-ttu-id="9f9da-271">Использование PowerShell для изменения политик безопасного вложения</span><span class="sxs-lookup"><span data-stu-id="9f9da-271">Use PowerShell to modify safe attachment policies</span></span>

<span data-ttu-id="9f9da-272">Нельзя переименовать политику безопасного вложения в PowerShell (в **комлете Set-SafeAttachmentPolicy** нет _параметра Name)._</span><span class="sxs-lookup"><span data-stu-id="9f9da-272">You can't rename a safe attachment policy in PowerShell (the **Set-SafeAttachmentPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="9f9da-273">При переименовании политики безопасных вложений в Центре & соответствия требованиям необходимо только переименовать правило безопасного _вложения._</span><span class="sxs-lookup"><span data-stu-id="9f9da-273">When you rename a Safe Attachments policy in the Security & Compliance Center, you're only renaming the safe attachment _rule_.</span></span>

<span data-ttu-id="9f9da-274">В противном случае те же параметры доступны при создании политики безопасного вложения, как описано в шаге [1: Использование PowerShell](#step-1-use-powershell-to-create-a-safe-attachment-policy) для создания безопасного раздела политики вложений в начале этой статьи.</span><span class="sxs-lookup"><span data-stu-id="9f9da-274">Otherwise, the same settings are available when you create a safe attachment policy as described in the [Step 1: Use PowerShell to create a safe attachment policy](#step-1-use-powershell-to-create-a-safe-attachment-policy) section earlier in this article.</span></span>

<span data-ttu-id="9f9da-275">Чтобы изменить политику безопасного вложения, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="9f9da-275">To modify a safe attachment policy, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="9f9da-276">Подробные сведения о синтаксисах и параметрах см. в [инструкции Set-SafeAttachmentPolicy.](/powershell/module/exchange/set-safeattachmentpolicy)</span><span class="sxs-lookup"><span data-stu-id="9f9da-276">For detailed syntax and parameter information, see [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-rules"></a><span data-ttu-id="9f9da-277">Использование PowerShell для изменения правил безопасного вложения</span><span class="sxs-lookup"><span data-stu-id="9f9da-277">Use PowerShell to modify safe attachment rules</span></span>

<span data-ttu-id="9f9da-278">Единственный параметр, недоступный при изменении правила безопасного вложения  в PowerShell, — это параметр Включен, который позволяет создать правило отключения.</span><span class="sxs-lookup"><span data-stu-id="9f9da-278">The only setting that's not available when you modify a safe attachment rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="9f9da-279">Чтобы включить или отключить существующие правила безопасного вложения, см. в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="9f9da-279">To enable or disable existing safe attachment rules, see the next section.</span></span>

<span data-ttu-id="9f9da-280">В противном случае те же параметры доступны при создании правила, описанного в разделе [Шаг 2. Использование PowerShell](#step-2-use-powershell-to-create-a-safe-attachment-rule) для создания раздела правила безопасного вложения в начале этой статьи.</span><span class="sxs-lookup"><span data-stu-id="9f9da-280">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe attachment rule](#step-2-use-powershell-to-create-a-safe-attachment-rule) section earlier in this article.</span></span>

<span data-ttu-id="9f9da-281">Чтобы изменить правило безопасного вложения, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="9f9da-281">To modify a safe attachment rule, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="9f9da-282">Подробные сведения о синтаксисах и параметрах см. в [инструкции Set-SafeAttachmentRule.](/powershell/module/exchange/set-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="9f9da-282">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a><span data-ttu-id="9f9da-283">Использование PowerShell, чтобы включить или отключить правила безопасного вложения</span><span class="sxs-lookup"><span data-stu-id="9f9da-283">Use PowerShell to enable or disable safe attachment rules</span></span>

<span data-ttu-id="9f9da-284">Включение или отключение правила безопасного вложения в PowerShell включает или отключает всю политику безопасных вложений (правило безопасного вложения и назначенную политику безопасного вложения).</span><span class="sxs-lookup"><span data-stu-id="9f9da-284">Enabling or disabling a safe attachment rule in PowerShell enables or disables the whole Safe Attachments policy (the safe attachment rule and the assigned safe attachment policy).</span></span>

<span data-ttu-id="9f9da-285">Чтобы включить или отключить правило безопасного вложения в PowerShell, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="9f9da-285">To enable or disable a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

<span data-ttu-id="9f9da-286">В этом примере отключает правило безопасного вложения с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="9f9da-286">This example disables the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="9f9da-287">В этом примере включается то же правило.</span><span class="sxs-lookup"><span data-stu-id="9f9da-287">This example enables same rule.</span></span>

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="9f9da-288">Подробные сведения о синтаксисах и параметрах см. в [инструкции Enable-SafeAttachmentRule](/powershell/module/exchange/enable-safeattachmentrule) и [Disable-SafeAttachmentRule.](/powershell/module/exchange/disable-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="9f9da-288">For detailed syntax and parameter information, see [Enable-SafeAttachmentRule](/powershell/module/exchange/enable-safeattachmentrule) and [Disable-SafeAttachmentRule](/powershell/module/exchange/disable-safeattachmentrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a><span data-ttu-id="9f9da-289">Использование PowerShell для набора приоритета правил безопасного вложения</span><span class="sxs-lookup"><span data-stu-id="9f9da-289">Use PowerShell to set the priority of safe attachment rules</span></span>

<span data-ttu-id="9f9da-290">Максимальный приоритет, который можно задать для правила, — 0.</span><span class="sxs-lookup"><span data-stu-id="9f9da-290">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="9f9da-291">Минимальное значение зависит от количества правил.</span><span class="sxs-lookup"><span data-stu-id="9f9da-291">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="9f9da-292">Например, если у вас есть пять правил, вы можете использовать значения 0–4.</span><span class="sxs-lookup"><span data-stu-id="9f9da-292">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="9f9da-293">Изменение приоритета существующего правила оказывает каскадное влияние на другие правила.</span><span class="sxs-lookup"><span data-stu-id="9f9da-293">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="9f9da-294">Например, если вы измените приоритет правила на 2, когда у вас есть пять настраиваемых правил (с приоритетами от 0 до 4), то для существующего правила с приоритетом 2 будет задан приоритет 3, а для правила с приоритетом 3 будет задан приоритет 4.</span><span class="sxs-lookup"><span data-stu-id="9f9da-294">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="9f9da-295">Чтобы установить приоритет правила безопасного вложения в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="9f9da-295">To set the priority of a safe attachment rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="9f9da-p124">В этом примере для правила Marketing Department задается приоритет 2. Все правила с приоритетом не больше 2 понижаются на один ранг (значения приоритета увеличиваются на 1).</span><span class="sxs-lookup"><span data-stu-id="9f9da-p124">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="9f9da-298">**Примечание.** Чтобы установить приоритет нового правила при его создании, используйте параметр _Priority_ в **комлете New-SafeAttachmentRule.**</span><span class="sxs-lookup"><span data-stu-id="9f9da-298">**Note**: To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeAttachmentRule** cmdlet instead.</span></span>

<span data-ttu-id="9f9da-299">Подробные сведения о синтаксисах и параметрах см. в [инструкции Set-SafeAttachmentRule.](/powershell/module/exchange/set-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="9f9da-299">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-policies"></a><span data-ttu-id="9f9da-300">Использование PowerShell для удаления политик безопасного вложения</span><span class="sxs-lookup"><span data-stu-id="9f9da-300">Use PowerShell to remove safe attachment policies</span></span>

<span data-ttu-id="9f9da-301">При удалении политики безопасного вложения с помощью PowerShell соответствующее правило безопасного вложения не удаляется.</span><span class="sxs-lookup"><span data-stu-id="9f9da-301">When you use PowerShell to remove a safe attachment policy, the corresponding safe attachment rule isn't removed.</span></span>

<span data-ttu-id="9f9da-302">Чтобы удалить политику безопасного вложения в PowerShell, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="9f9da-302">To remove a safe attachment policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="9f9da-303">В этом примере удаляется политика безопасного вложения с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="9f9da-303">This example removes the safe attachment policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

<span data-ttu-id="9f9da-304">Подробные сведения о синтаксисах и параметрах см. в [обзоре Remove-SafeAttachmentPolicy.](/powershell/module/exchange/remove-safeattachmentpolicy)</span><span class="sxs-lookup"><span data-stu-id="9f9da-304">For detailed syntax and parameter information, see [Remove-SafeAttachmentPolicy](/powershell/module/exchange/remove-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-rules"></a><span data-ttu-id="9f9da-305">Использование PowerShell для удаления правил безопасного вложения</span><span class="sxs-lookup"><span data-stu-id="9f9da-305">Use PowerShell to remove safe attachment rules</span></span>

<span data-ttu-id="9f9da-306">При удалении правила безопасного вложения с помощью PowerShell соответствующая политика безопасного вложения не удаляется.</span><span class="sxs-lookup"><span data-stu-id="9f9da-306">When you use PowerShell to remove a safe attachment rule, the corresponding safe attachment policy isn't removed.</span></span>

<span data-ttu-id="9f9da-307">Чтобы удалить правило безопасного вложения в PowerShell, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="9f9da-307">To remove a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

<span data-ttu-id="9f9da-308">В этом примере удаляется правило безопасного вложения с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="9f9da-308">This example removes the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="9f9da-309">Подробные сведения о синтаксисах и параметрах см. в [ссылке Remove-SafeAttachmentRule.](/powershell/module/exchange/remove-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="9f9da-309">For detailed syntax and parameter information, see [Remove-SafeAttachmentRule](/powershell/module/exchange/remove-safeattachmentrule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="9f9da-310">Как проверить, что эти процедуры выполнены?</span><span class="sxs-lookup"><span data-stu-id="9f9da-310">How do you know these procedures worked?</span></span>

<span data-ttu-id="9f9da-311">Чтобы убедиться, что вы успешно создали, изменили или удалили политики безопасных вложений, сделайте все следующие действия:</span><span class="sxs-lookup"><span data-stu-id="9f9da-311">To verify that you've successfully created, modified, or removed Safe Attachments policies, do any of the following steps:</span></span>

- <span data-ttu-id="9f9da-312">В Центре обеспечения & безопасности перейдите к **политике** управления угрозами \>  \> **ATP Safe Attachments**.</span><span class="sxs-lookup"><span data-stu-id="9f9da-312">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span> <span data-ttu-id="9f9da-313">Проверка списка политик, их значений **состояния** и **их значений приоритета.**</span><span class="sxs-lookup"><span data-stu-id="9f9da-313">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="9f9da-314">Чтобы просмотреть дополнительные сведения, выберите политику из списка и просмотреть сведения в поле вылета.</span><span class="sxs-lookup"><span data-stu-id="9f9da-314">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="9f9da-315">В Exchange Online PowerShell или Exchange Online Protection PowerShell замените имя политики или правила, запустите следующую команду и проверьте \<Name\> параметры:</span><span class="sxs-lookup"><span data-stu-id="9f9da-315">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

<span data-ttu-id="9f9da-316">Чтобы убедиться, что безопасные вложения сканирует сообщения, проверьте доступные отчеты Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="9f9da-316">To verify that Safe Attachments is scanning messages, check the available Defender for Office 365 reports.</span></span> <span data-ttu-id="9f9da-317">Дополнительные сведения см. в обзоре отчетов [для Defender для Office 365](view-reports-for-mdo.md) и Use Explorer в Центре & [безопасности.](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="9f9da-317">For more information, see [View reports for Defender for Office 365](view-reports-for-mdo.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>
