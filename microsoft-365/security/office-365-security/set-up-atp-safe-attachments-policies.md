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
ms.openlocfilehash: 314f7fd882986c22adddd0c4570b4aa9f49a40f3
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166337"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="9287b-103">Настройка политик безопасных вложений в Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="9287b-103">Set up Safe Attachments policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="9287b-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="9287b-104">**Applies to**</span></span>
- [<span data-ttu-id="9287b-105">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="9287b-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="9287b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9287b-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="9287b-107">Эта статья предназначена для бизнес-клиентов, использующих [Microsoft Defender для Office 365](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="9287b-107">This article is intended for business customers who have [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="9287b-108">Если вы домашний пользователь, который ищет сведения о сканировании вложений в Outlook, см. дополнительные Outlook.com [безопасности.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)</span><span class="sxs-lookup"><span data-stu-id="9287b-108">If you're a home user looking for information about attachment scanning in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="9287b-109">Функция "Безопасные вложения" — это функция в Microsoft Defender для [Office 365,](office-365-atp.md) которая использует виртуальную среду для проверки вложений во входящие сообщения электронной почты после сканирования с помощью защиты от вредоносных программ в [Exchange Online Protection (EOP),](anti-malware-protection.md)но перед доставкой получателям.</span><span class="sxs-lookup"><span data-stu-id="9287b-109">Safe Attachments is a feature in [Microsoft Defender for Office 365](office-365-atp.md) that uses a virtual environment to check attachments in inbound email messages after they've been scanned by [anti-malware protection in Exchange Online Protection (EOP)](anti-malware-protection.md), but before delivery to recipients.</span></span> <span data-ttu-id="9287b-110">Дополнительные сведения см. в записи ["Безопасные вложения" в Microsoft Defender для Office 365.](atp-safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="9287b-110">For more information, see [Safe Attachments in Microsoft Defender for Office 365](atp-safe-attachments.md).</span></span>

<span data-ttu-id="9287b-111">Встроенная или стандартная политика безопасных вложений не существует.</span><span class="sxs-lookup"><span data-stu-id="9287b-111">There's no built-in or default Safe Attachments policy.</span></span> <span data-ttu-id="9287b-112">Чтобы получить сканирование безопасных вложений с вложениями электронной почты, необходимо создать одну или несколько политик безопасных вложений, как описано в этой статье.</span><span class="sxs-lookup"><span data-stu-id="9287b-112">To get Safe Attachments scanning of email message attachments, you need to create one or more Safe Attachments policies as described in this article.</span></span>

<span data-ttu-id="9287b-113">Политики безопасных вложений можно настроить в Центре безопасности & и соответствия требованиям или в PowerShell (Exchange Online PowerShell для подходящих организаций Microsoft 365 с почтовыми ящиками в Exchange Online; автономный EOP PowerShell для организаций без почтовых ящиков Exchange Online, но с подписками на надстройки Defender для Office 365).</span><span class="sxs-lookup"><span data-stu-id="9287b-113">You can configure Safe Attachments policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="9287b-114">Основные элементы политики безопасных вложений:</span><span class="sxs-lookup"><span data-stu-id="9287b-114">The basic elements of a Safe Attachments policy are:</span></span>

- <span data-ttu-id="9287b-115">Политика **безопасных** вложений: определяет действия для неизвестных обнаружений вредоносных программ, отправку сообщений с вредоносными вложениями на указанный адрес электронной почты и доставку сообщений, если проверка безопасных вложений не может завершиться.</span><span class="sxs-lookup"><span data-stu-id="9287b-115">**The safe attachment policy**: Specifies the actions for unknown malware detections, whether to send messages with malware attachments to a specified email address, and whether to deliver messages if Safe Attachments scanning can't complete.</span></span>
- <span data-ttu-id="9287b-116">**Правило безопасных вложений:** определяет приоритет и фильтры получателей (к кому применяется политика).</span><span class="sxs-lookup"><span data-stu-id="9287b-116">**The safe attachment rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="9287b-117">Разница между этими двумя элементами не очевидна при управлении политиками безопасных вложений в Центре безопасности & соответствия требованиям:</span><span class="sxs-lookup"><span data-stu-id="9287b-117">The difference between these two elements isn't obvious when you manage Safe Attachments polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="9287b-118">При создании политики безопасных вложений фактически создается правило безопасных вложений и связанная политика безопасных вложений одновременно с использованием одного и того же имени для обоих.</span><span class="sxs-lookup"><span data-stu-id="9287b-118">When you create a Safe Attachments policy, you're actually creating a safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="9287b-119">При изменении политики безопасных вложений параметры, связанные с именем, приоритетом, включенным или отключенным фильтрами получателей, изменяют правило безопасных вложений.</span><span class="sxs-lookup"><span data-stu-id="9287b-119">When you modify a Safe Attachments policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe attachment rule.</span></span> <span data-ttu-id="9287b-120">Все остальные параметры изменяют связанную политику безопасных вложений.</span><span class="sxs-lookup"><span data-stu-id="9287b-120">All other settings modify the associated safe attachment policy.</span></span>
- <span data-ttu-id="9287b-121">При удалении политики безопасных вложений правило безопасных вложений и связанная политика безопасных вложений удаляются.</span><span class="sxs-lookup"><span data-stu-id="9287b-121">When you remove a Safe Attachments policy, the safe attachment rule and the associated safe attachment policy are removed.</span></span>

<span data-ttu-id="9287b-122">В Exchange Online PowerShell или автономном EOP PowerShell вы управляете политикой и правилом отдельно.</span><span class="sxs-lookup"><span data-stu-id="9287b-122">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="9287b-123">Дополнительные сведения см. в разделе "Использование Exchange Online PowerShell или автономный [EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) для настройки политик безопасных вложений" далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="9287b-123">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) section later in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="9287b-124">В области глобальных параметров параметров безопасных вложений настраиваются функции, не зависящие от политик безопасных вложений.</span><span class="sxs-lookup"><span data-stu-id="9287b-124">In the global settings area of Safe Attachments settings, you configure features that are not dependent on Safe Attachments policies.</span></span> <span data-ttu-id="9287b-125">Инструкции см. в документе "Включить безопасные вложения [для SharePoint, OneDrive, Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) и безопасных документов в Microsoft [365 E5".](safe-docs.md)</span><span class="sxs-lookup"><span data-stu-id="9287b-125">For instructions see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) and [Safe Documents in Microsoft 365 E5](safe-docs.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9287b-126">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="9287b-126">What do you need to know before you begin?</span></span>

- <span data-ttu-id="9287b-127">Откройте Центр безопасности и соответствия требованиям по ссылке <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="9287b-127">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="9287b-128">Чтобы перейти непосредственно на страницу **"Безопасные вложения",** используйте <https://protection.office.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="9287b-128">To go directly to the **Safe Attachments** page, use <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="9287b-129">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="9287b-129">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="9287b-130">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="9287b-130">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="9287b-131">Для работы с процедурами, которые данной статьи, вам должны быть назначены разрешения:</span><span class="sxs-lookup"><span data-stu-id="9287b-131">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="9287b-132">Для создания, изменения и удаления политик безопасных вложений необходимо  быть членом группы ролей "Управление организацией" или  "Администратор безопасности" в Центре безопасности и соответствия требованиям & и членом группы ролей "Управление организацией" в Exchange Online.  </span><span class="sxs-lookup"><span data-stu-id="9287b-132">To create, modify, and delete Safe Attachments policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="9287b-133">Для доступа только для чтения к политикам безопасных вложений необходимо  быть участником группы ролей **"Глобальный** читатель" или "Читатель безопасности" в Центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="9287b-133">For read-only access to Safe Attachments policies, you need to be a member of the **Global Reader** or **Security Reader** role groups in the Security & Compliance Center.</span></span>

  <span data-ttu-id="9287b-134">Дополнительные сведения см. в сведениях о разрешениях в Центре [безопасности & соответствия](permissions-in-the-security-and-compliance-center.md) требованиям и [разрешениях в Exchange Online.](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)</span><span class="sxs-lookup"><span data-stu-id="9287b-134">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="9287b-135">**Примечания**.</span><span class="sxs-lookup"><span data-stu-id="9287b-135">**Notes**:</span></span>

  - <span data-ttu-id="9287b-136">Добавление пользователей в соответствующую роль Azure Active Directory в Центре безопасности Microsoft 365 предоставляет пользователям необходимые разрешения в Центре безопасности и соответствия требованиям _и_ разрешения для других функций в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9287b-136">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="9287b-137">Дополнительные сведения см. в статье [О ролях администраторов](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="9287b-137">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="9287b-138">Группа ролей **Управление организацией с правами только на просмотр** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) также предоставляет доступ только для чтения к этой функции.</span><span class="sxs-lookup"><span data-stu-id="9287b-138">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="9287b-139">Рекомендуемые параметры политик безопасных вложений см. в параметрах [безопасных вложений.](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)</span><span class="sxs-lookup"><span data-stu-id="9287b-139">For our recommended settings for Safe Attachments policies, see [Safe Attachments settings](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).</span></span>

- <span data-ttu-id="9287b-140">Позволяет применять новую или обновленную политику в течение 30 минут.</span><span class="sxs-lookup"><span data-stu-id="9287b-140">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-attachments-policies"></a><span data-ttu-id="9287b-141">Использование Центра безопасности & соответствия требованиям для создания политик безопасных вложений</span><span class="sxs-lookup"><span data-stu-id="9287b-141">Use the Security & Compliance Center to create Safe Attachments policies</span></span>

<span data-ttu-id="9287b-142">При создании настраиваемой политики безопасных вложений в Центре безопасности & соответствия требованиям одновременно создаются правило безопасных вложений и связанная политика безопасных вложений с одинаковым именем.</span><span class="sxs-lookup"><span data-stu-id="9287b-142">Creating a custom Safe Attachments policy in the Security & Compliance Center creates the safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="9287b-143">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span><span class="sxs-lookup"><span data-stu-id="9287b-143">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="9287b-144">На странице **"Безопасные вложения"** нажмите кнопку **"Создать".**</span><span class="sxs-lookup"><span data-stu-id="9287b-144">On the **Safe Attachments** page, click **Create**.</span></span>

3. <span data-ttu-id="9287b-145">Откроется **мастер новой политики безопасных** вложений.</span><span class="sxs-lookup"><span data-stu-id="9287b-145">The **New Safe Attachments policy** wizard opens.</span></span> <span data-ttu-id="9287b-146">На странице **"Имя политики"** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="9287b-146">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="9287b-147">**Имя**. Укажите уникальное, понятное имя политики.</span><span class="sxs-lookup"><span data-stu-id="9287b-147">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="9287b-148">**Описание**. Укажите необязательное описание политики.</span><span class="sxs-lookup"><span data-stu-id="9287b-148">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="9287b-149">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9287b-149">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="9287b-150">На странице **"Параметры"** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="9287b-150">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="9287b-151">**Ответ на неизвестные вредоносные программы**"Безопасные вложения": выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="9287b-151">**Safe Attachments unknown malware response**: Select one of the following values:</span></span>

     - <span data-ttu-id="9287b-152">**Off**: Typically, we don't recommend this value.</span><span class="sxs-lookup"><span data-stu-id="9287b-152">**Off**: Typically, we don't recommend this value.</span></span>
     - <span data-ttu-id="9287b-153">**Монитор**</span><span class="sxs-lookup"><span data-stu-id="9287b-153">**Monitor**</span></span>
     - <span data-ttu-id="9287b-154">**Block**: это значение по умолчанию и рекомендуемое значение в стандартных и строгих [предустановленных политиках безопасности.](preset-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="9287b-154">**Block**: This is the default value, and the recommended value in Standard and Strict [preset security policies](preset-security-policies.md).</span></span>
     - <span data-ttu-id="9287b-155">**Replace**</span><span class="sxs-lookup"><span data-stu-id="9287b-155">**Replace**</span></span>
     - <span data-ttu-id="9287b-156">**Динамическая доставка (предварительная версия функции)**</span><span class="sxs-lookup"><span data-stu-id="9287b-156">**Dynamic Delivery (Preview Feature)**</span></span>

     <span data-ttu-id="9287b-157">Эти значения поясняется в параметрах [политики безопасных вложений.](atp-safe-attachments.md#safe-attachments-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="9287b-157">These values are explained in [Safe Attachments policy settings](atp-safe-attachments.md#safe-attachments-policy-settings).</span></span>

   - <span data-ttu-id="9287b-158">Отправьте вложение на следующий адрес электронной почты: для значений действия  **Block**, **Monitor** или **Replace** можно включить перенаправление для отправки сообщений, содержащих вредоносные вложения, на указанный внутренний или внешний адрес электронной почты для анализа и анализа. </span><span class="sxs-lookup"><span data-stu-id="9287b-158">**Send the attachment to the following email address**: For the action values **Block**, **Monitor**, or **Replace**, you can select **Enable redirect** to send messages that contain malware attachments to the specified internal or external email address for analysis and investigation.</span></span>

     <span data-ttu-id="9287b-159">Чтобы включить перенаправление, для параметров политики Standard и Strict необходимо включить перенаправление.</span><span class="sxs-lookup"><span data-stu-id="9287b-159">The recommendation for Standard and Strict policy settings is to enable redirection.</span></span> <span data-ttu-id="9287b-160">Дополнительные сведения см. в [параметрах безопасных вложений.](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)</span><span class="sxs-lookup"><span data-stu-id="9287b-160">For more information, see [Safe Attachments settings](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).</span></span>

   - <span data-ttu-id="9287b-161">Применив указанный выше выбор, если время проверки на  вредоносные программы для вложений не превышает времени или возникает **ошибка:** действие, указанное в ответе на неизвестные вредоносные программы безопасных вложений, применяется к сообщениям, даже если проверка безопасных вложений не может завершиться.</span><span class="sxs-lookup"><span data-stu-id="9287b-161">**Apply the above selection if malware scanning for attachments times out or error occurs**: The action specified by **Safe Attachments unknown malware response** is taken on messages even when Safe Attachments scanning can't complete.</span></span> <span data-ttu-id="9287b-162">Если выбран этот параметр, всегда выбирайте **"Включено перенаправление".**</span><span class="sxs-lookup"><span data-stu-id="9287b-162">If you selected this option, always select **Enabled redirect**.</span></span> <span data-ttu-id="9287b-163">В противном случае сообщения могут быть потеряны.</span><span class="sxs-lookup"><span data-stu-id="9287b-163">Otherwise, messages might be lost.</span></span>

   <span data-ttu-id="9287b-164">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9287b-164">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="9287b-165">На странице **"Применено к"** определите внутренних получателей, к которые применяется политика.</span><span class="sxs-lookup"><span data-stu-id="9287b-165">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="9287b-166">Условие или исключение можно использовать только один раз, но можно указать для них несколько значений.</span><span class="sxs-lookup"><span data-stu-id="9287b-166">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="9287b-167">Указать несколько значений в одном условии или исключении можно с помощью оператора OR (например, _\<recipient1\>_ or _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="9287b-167">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="9287b-168">Между разными условиями и исключениями используется оператор AND (например, _\<recipient1\>_ and _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="9287b-168">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="9287b-169">Нажмите **кнопку "Добавить условие".**</span><span class="sxs-lookup"><span data-stu-id="9287b-169">Click **Add a condition**.</span></span> <span data-ttu-id="9287b-170">В отобраложенном выпадаемом окном выберите условие в области **"Применено", если:**</span><span class="sxs-lookup"><span data-stu-id="9287b-170">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="9287b-171">**Получатель:** указывает один или несколько почтовых ящиков, почтовых пользователей или почтовых контактов в организации.</span><span class="sxs-lookup"><span data-stu-id="9287b-171">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="9287b-172">**Получатель является членом**: указывает одну или несколько групп в организации.</span><span class="sxs-lookup"><span data-stu-id="9287b-172">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="9287b-173">**Домен получателя**: Указывает получателей в одном или нескольких настроенных принятых доменов в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="9287b-173">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="9287b-174">После выбора условия появится соответствующее dropdown с любым **из этих полей.**</span><span class="sxs-lookup"><span data-stu-id="9287b-174">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="9287b-175">Щелкните поле и прокрутите список выбранных значений.</span><span class="sxs-lookup"><span data-stu-id="9287b-175">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="9287b-176">Щелкните поле и начните вводить текст, чтобы отфильтровать список и выбрать значение.</span><span class="sxs-lookup"><span data-stu-id="9287b-176">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="9287b-177">Чтобы добавить дополнительные значения, щелкните пустую область в поле.</span><span class="sxs-lookup"><span data-stu-id="9287b-177">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="9287b-178">Чтобы удалить отдельные записи, **щелкните значок "Удалить** ![ удалить" ](../../media/scc-remove-icon.png) в значении.</span><span class="sxs-lookup"><span data-stu-id="9287b-178">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="9287b-179">Чтобы удалить все условие, щелкните **значок "Удалить** ![ удалить" ](../../media/scc-remove-icon.png) в этом условии.</span><span class="sxs-lookup"><span data-stu-id="9287b-179">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="9287b-180">Чтобы добавить дополнительное условие, нажмите кнопку **"Добавить условие"** и выберите оставшееся значение **в области "Применено", если**.</span><span class="sxs-lookup"><span data-stu-id="9287b-180">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="9287b-181">Чтобы добавить исключения, нажмите **кнопку "Добавить условие"** и выберите исключение в области **"Кроме случаев, когда"**.</span><span class="sxs-lookup"><span data-stu-id="9287b-181">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="9287b-182">Параметры и поведение полностью идентичны условиям.</span><span class="sxs-lookup"><span data-stu-id="9287b-182">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="9287b-183">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9287b-183">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="9287b-184">На странице **"Просмотр параметров"** просмотрите параметры.</span><span class="sxs-lookup"><span data-stu-id="9287b-184">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="9287b-185">Вы можете нажать **кнопку "Изменить"** для каждого параметра, чтобы изменить его.</span><span class="sxs-lookup"><span data-stu-id="9287b-185">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="9287b-186">Закончив, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="9287b-186">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-attachments-policies"></a><span data-ttu-id="9287b-187">Использование Центра безопасности & соответствия требованиям для просмотра политик безопасных вложений</span><span class="sxs-lookup"><span data-stu-id="9287b-187">Use the Security & Compliance Center to view Safe Attachments policies</span></span>

1. <span data-ttu-id="9287b-188">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span><span class="sxs-lookup"><span data-stu-id="9287b-188">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="9287b-189">На странице **"Безопасные вложения"** выберите политику в списке и щелкните ее (не выбирайте этот контроль).</span><span class="sxs-lookup"><span data-stu-id="9287b-189">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="9287b-190">Сведения о политике отображаются во fly out</span><span class="sxs-lookup"><span data-stu-id="9287b-190">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-attachments-policies"></a><span data-ttu-id="9287b-191">Использование Центра безопасности & соответствия требованиям для изменения политик безопасных вложений</span><span class="sxs-lookup"><span data-stu-id="9287b-191">Use the Security & Compliance Center to modify Safe Attachments policies</span></span>

1. <span data-ttu-id="9287b-192">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span><span class="sxs-lookup"><span data-stu-id="9287b-192">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="9287b-193">На странице **"Безопасные вложения"** выберите политику в списке и щелкните ее (не выбирайте этот контроль).</span><span class="sxs-lookup"><span data-stu-id="9287b-193">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="9287b-194">В появились сведения о политике, нажмите кнопку **"Изменить политику".**</span><span class="sxs-lookup"><span data-stu-id="9287b-194">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="9287b-195">Доступные параметры во время выполнения идентичны тем, которые описаны в разделе "Использование центра безопасности & соответствия требованиям для создания политик безопасных [вложений".](#use-the-security--compliance-center-to-create-safe-attachments-policies)</span><span class="sxs-lookup"><span data-stu-id="9287b-195">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Attachments policies](#use-the-security--compliance-center-to-create-safe-attachments-policies) section.</span></span>

<span data-ttu-id="9287b-196">Чтобы включить или отключить политику или установить порядок приоритетов политики, см. следующие разделы.</span><span class="sxs-lookup"><span data-stu-id="9287b-196">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-attachments-policies"></a><span data-ttu-id="9287b-197">Включить или отключить политики безопасных вложений</span><span class="sxs-lookup"><span data-stu-id="9287b-197">Enable or disable Safe Attachments policies</span></span>

1. <span data-ttu-id="9287b-198">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span><span class="sxs-lookup"><span data-stu-id="9287b-198">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="9287b-199">Обратите внимание на значение в **столбце "Состояние":**</span><span class="sxs-lookup"><span data-stu-id="9287b-199">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="9287b-200">Перемещение перегона влево</span><span class="sxs-lookup"><span data-stu-id="9287b-200">Move the toggle to the left</span></span> ![Отключение политики](../../media/scc-toggle-off.png) <span data-ttu-id="9287b-202">чтобы отключить политику.</span><span class="sxs-lookup"><span data-stu-id="9287b-202">to disable the policy.</span></span>

   - <span data-ttu-id="9287b-203">Перемещение передвигаемой области вправо</span><span class="sxs-lookup"><span data-stu-id="9287b-203">Move the toggle to the right</span></span> ![Включить политику](../../media/scc-toggle-on.png) <span data-ttu-id="9287b-205">чтобы включить политику.</span><span class="sxs-lookup"><span data-stu-id="9287b-205">to enable the policy.</span></span>

### <a name="set-the-priority-of-safe-attachments-policies"></a><span data-ttu-id="9287b-206">Настройка приоритета политик безопасных вложений</span><span class="sxs-lookup"><span data-stu-id="9287b-206">Set the priority of Safe Attachments policies</span></span>

<span data-ttu-id="9287b-207">По умолчанию политикам безопасных вложений предоставляется приоритет, основанный на порядке их создания (приоритет новых политик ниже, чем у старых политик).</span><span class="sxs-lookup"><span data-stu-id="9287b-207">By default, Safe Attachments policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="9287b-208">Чем ниже значение, тем выше приоритет политики (0 — наивысший приоритет), а порядок обработки политик зависит от их приоритетов (политики с высоким приоритетом обрабатываются раньше, чем политики с низким приоритетом).</span><span class="sxs-lookup"><span data-stu-id="9287b-208">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="9287b-209">Никакие две политики не могут иметь одинаковый приоритет, и обработка политики прекращается после применения первой политики.</span><span class="sxs-lookup"><span data-stu-id="9287b-209">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="9287b-210">Дополнительные сведения о приоритетах, а также оценке и применении нескольких политик см. в статье [Порядок и приоритет защиты электронной почты](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="9287b-210">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="9287b-211">Политики безопасных вложений отображаются в порядке их обработки (первая политика имеет значение **приоритета** 0).</span><span class="sxs-lookup"><span data-stu-id="9287b-211">Safe Attachments policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

<span data-ttu-id="9287b-212">**Примечание.** В Центре & соответствия требованиям приоритет политики безопасных вложений можно изменить только после ее создания.</span><span class="sxs-lookup"><span data-stu-id="9287b-212">**Note**: In the Security & Compliance Center, you can only change the priority of the Safe Attachments policy after you create it.</span></span> <span data-ttu-id="9287b-213">В PowerShell можно переопредить приоритет по умолчанию при создании правила безопасных вложений (которое может повлиять на приоритет существующих правил).</span><span class="sxs-lookup"><span data-stu-id="9287b-213">In PowerShell, you can override the default priority when you create the safe attachment rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="9287b-214">Чтобы изменить приоритет политики, переместите ее вверх или вниз в списке (в Центре безопасности и соответствия требованиям невозможно напрямую изменить значение свойства **Приоритет**).</span><span class="sxs-lookup"><span data-stu-id="9287b-214">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="9287b-215">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span><span class="sxs-lookup"><span data-stu-id="9287b-215">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="9287b-216">На странице **"Безопасные вложения"** выберите политику в списке и щелкните ее (не выбирайте этот контроль).</span><span class="sxs-lookup"><span data-stu-id="9287b-216">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="9287b-217">В появились сведения о политике, нажмите доступную кнопку приоритета.</span><span class="sxs-lookup"><span data-stu-id="9287b-217">In the policy details fly out that appears, click the available priority button.</span></span>

   - <span data-ttu-id="9287b-218">В политике безопасных вложений со значением **приоритета** **0** доступна только кнопка **"Уменьшить приоритет".**</span><span class="sxs-lookup"><span data-stu-id="9287b-218">The Safe Attachments policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="9287b-219">В политике безопасных вложений с наименьшим значением приоритета (например, **3)** доступна только кнопка "Увеличить  **приоритет".**</span><span class="sxs-lookup"><span data-stu-id="9287b-219">The Safe Attachments policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="9287b-220">Если у вас есть три или более политик безопасных вложений, политики между  самыми высокими и минимальными значениями приоритета имеют доступные кнопки "Увеличить приоритет" и "Уменьшить приоритет". </span><span class="sxs-lookup"><span data-stu-id="9287b-220">If you have three or more Safe Attachments policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="9287b-221">Нажмите **кнопку "Увеличить приоритет"** или **"Уменьшить приоритет",** чтобы изменить **значение приоритета.**</span><span class="sxs-lookup"><span data-stu-id="9287b-221">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="9287b-222">Когда закончите, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="9287b-222">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-attachments-policies"></a><span data-ttu-id="9287b-223">Использование Центра безопасности & соответствия требованиям для удаления политик безопасных вложений</span><span class="sxs-lookup"><span data-stu-id="9287b-223">Use the Security & Compliance Center to remove Safe Attachments policies</span></span>

1. <span data-ttu-id="9287b-224">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span><span class="sxs-lookup"><span data-stu-id="9287b-224">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="9287b-225">На странице **"Безопасные вложения"** выберите политику в списке и щелкните ее (не выбирайте этот контроль).</span><span class="sxs-lookup"><span data-stu-id="9287b-225">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="9287b-226">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span><span class="sxs-lookup"><span data-stu-id="9287b-226">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a><span data-ttu-id="9287b-227">Настройка политик безопасных вложений с помощью Exchange Online PowerShell или автономных EOP PowerShell</span><span class="sxs-lookup"><span data-stu-id="9287b-227">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies</span></span>

<span data-ttu-id="9287b-228">Как было описано выше, политика безопасных вложений состоит из политики безопасных вложений и правила безопасных вложений.</span><span class="sxs-lookup"><span data-stu-id="9287b-228">As previously described, a Safe Attachments policy consists of a safe attachment policy and a safe attachment rule.</span></span>

<span data-ttu-id="9287b-229">В PowerShell разница между политиками безопасных вложений и правилами безопасных вложений очевидна.</span><span class="sxs-lookup"><span data-stu-id="9287b-229">In PowerShell, the difference between safe attachment policies and safe attachment rules is apparent.</span></span> <span data-ttu-id="9287b-230">Вы управляете политиками безопасных вложений с помощью cmdlets **\* -SafeAttachmentPolicy** и управляете правилами безопасных вложений с помощью **\* -SafeAttachmentRule.**</span><span class="sxs-lookup"><span data-stu-id="9287b-230">You manage safe attachment policies by using the **\*-SafeAttachmentPolicy** cmdlets, and you manage safe attachment rules by using the **\*-SafeAttachmentRule** cmdlets.</span></span>

- <span data-ttu-id="9287b-231">В PowerShell сначала создается политика безопасных вложений, а затем создается правило безопасных вложений, которое определяет политику, к которую применяется правило.</span><span class="sxs-lookup"><span data-stu-id="9287b-231">In PowerShell, you create the safe attachment policy first, then you create the safe attachment rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="9287b-232">В PowerShell параметры политики безопасных вложений и правила безопасных вложений изменяются отдельно.</span><span class="sxs-lookup"><span data-stu-id="9287b-232">In PowerShell, you modify the settings in the safe attachment policy and the safe attachment rule separately.</span></span>
- <span data-ttu-id="9287b-233">При удалении политики безопасных вложений из PowerShell соответствующее правило безопасного вложения не удаляется автоматически и наоборот.</span><span class="sxs-lookup"><span data-stu-id="9287b-233">When you remove a safe attachment policy from PowerShell, the corresponding safe attachment rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-attachments-policies"></a><span data-ttu-id="9287b-234">Создание политик безопасных вложений с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="9287b-234">Use PowerShell to create Safe Attachments policies</span></span>

<span data-ttu-id="9287b-235">Создание политики безопасных вложений в PowerShell — это двухшаговая процедура:</span><span class="sxs-lookup"><span data-stu-id="9287b-235">Creating a Safe Attachments policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="9287b-236">Создайте политику безопасных вложений.</span><span class="sxs-lookup"><span data-stu-id="9287b-236">Create the safe attachment policy.</span></span>
2. <span data-ttu-id="9287b-237">Создайте правило безопасных вложений, которое определяет политику безопасных вложений, к которую оно применяется.</span><span class="sxs-lookup"><span data-stu-id="9287b-237">Create the safe attachment rule that specifies the safe attachment policy that the rule applies to.</span></span>

 <span data-ttu-id="9287b-238">**Примечания**.</span><span class="sxs-lookup"><span data-stu-id="9287b-238">**Notes**:</span></span>

- <span data-ttu-id="9287b-239">Вы можете создать новое правило безопасных вложений и назначить ему существующую несвязаную политику безопасных вложений.</span><span class="sxs-lookup"><span data-stu-id="9287b-239">You can create a new safe attachment rule and assign an existing, unassociated safe attachment policy to it.</span></span> <span data-ttu-id="9287b-240">Правило безопасного вложения не может быть связано с более чем одной политикой безопасных вложений.</span><span class="sxs-lookup"><span data-stu-id="9287b-240">A safe attachment rule can't be associated with more than one safe attachment policy.</span></span>

- <span data-ttu-id="9287b-241">Вы можете настроить следующие параметры для новых политик безопасных вложений в PowerShell, которые недоступны в Центре безопасности и соответствия требованиям & до создания политики:</span><span class="sxs-lookup"><span data-stu-id="9287b-241">You can configure the following settings on new safe attachment policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>
  - <span data-ttu-id="9287b-242">Создайте новую политику как отключенную _(включена_ `$false` в **cmdlet New-SafeAttachmentRule).**</span><span class="sxs-lookup"><span data-stu-id="9287b-242">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeAttachmentRule** cmdlet).</span></span>
  - <span data-ttu-id="9287b-243">Установите приоритет политики во время создания _(Priority)_ в _\<Number\>_ **cmdlet New-SafeAttachmentRule).**</span><span class="sxs-lookup"><span data-stu-id="9287b-243">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeAttachmentRule** cmdlet).</span></span>

- <span data-ttu-id="9287b-244">Новая политика безопасных вложений, которую вы создаете в PowerShell, не отображается в Центре безопасности & соответствия требованиям, пока вы не назначите политику правилу безопасных вложений.</span><span class="sxs-lookup"><span data-stu-id="9287b-244">A new safe attachment policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe attachment rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a><span data-ttu-id="9287b-245">Шаг 1. Создание политики безопасных вложений с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="9287b-245">Step 1: Use PowerShell to create a safe attachment policy</span></span>

<span data-ttu-id="9287b-246">Чтобы создать безопасную политику вложений, используйте синтаксис:</span><span class="sxs-lookup"><span data-stu-id="9287b-246">To create a safe attachment policy, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

<span data-ttu-id="9287b-247">В этом примере создается политика безопасных вложений с именем Contoso All со следующими значениями:</span><span class="sxs-lookup"><span data-stu-id="9287b-247">This example creates a safe attachment policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="9287b-248">Блокировать сообщения, которые содержат вредоносные программы при сканировании безопасных документов (мы не используем параметр _Action,_ а значение по умолчанию — `Block` ).</span><span class="sxs-lookup"><span data-stu-id="9287b-248">Block messages that are found to contain malware by Safe Documents scanning (we aren't using the _Action_ parameter, and the default value is `Block`).</span></span>
- <span data-ttu-id="9287b-249">Перенаправление включено, и сообщения, которые содержат вредоносные программы, отправляются в sec-ops@contoso.com для анализа и исследования.</span><span class="sxs-lookup"><span data-stu-id="9287b-249">Redirection is enabled, and messages that are found to contain malware are sent to sec-ops@contoso.com for analysis and investigation.</span></span>
- <span data-ttu-id="9287b-250">Если проверка безопасных вложений недоступна или возникнут ошибки, не доставляйте сообщение (мы не используем параметр _ActionOnError,_ а значение по умолчанию — `$true` ).</span><span class="sxs-lookup"><span data-stu-id="9287b-250">If Safe Attachments scanning isn't available or encounters errors, don't deliver the message (we aren't using the _ActionOnError_ parameter, and the default value is `$true`).</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

<span data-ttu-id="9287b-251">Подробные сведения о синтаксисах и параметрах см. в описании [New-SafeAttachmentPolicy.](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy)</span><span class="sxs-lookup"><span data-stu-id="9287b-251">For detailed syntax and parameter information, see [New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a><span data-ttu-id="9287b-252">Шаг 2. Создание правила безопасного вложения с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="9287b-252">Step 2: Use PowerShell to create a safe attachment rule</span></span>

<span data-ttu-id="9287b-253">Чтобы создать правило безопасного вложения, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="9287b-253">To create a safe attachment rule, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="9287b-254">В этом примере создается правило безопасных вложений с именем Contoso All со следующими условиями:</span><span class="sxs-lookup"><span data-stu-id="9287b-254">This example creates a safe attachment rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="9287b-255">Правило связано с политикой безопасных вложений с именем Contoso All.</span><span class="sxs-lookup"><span data-stu-id="9287b-255">The rule is associated with the safe attachment policy named Contoso All.</span></span>
- <span data-ttu-id="9287b-256">Правило применяется ко всем получателям в contoso.com домене.</span><span class="sxs-lookup"><span data-stu-id="9287b-256">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="9287b-257">Так как мы не используем параметр _Priority,_ используется приоритет по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9287b-257">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="9287b-258">Правило включено (мы не используем параметр _Enabled,_ а по умолчанию используется `$true` значение).</span><span class="sxs-lookup"><span data-stu-id="9287b-258">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="9287b-259">Подробные сведения о синтаксисах и параметрах см. в описании [New-SafeAttachmentRule.](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="9287b-259">For detailed syntax and parameter information, see [New-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentrule).</span></span>

### <a name="use-powershell-to-view-safe-attachment-policies"></a><span data-ttu-id="9287b-260">Просмотр политик безопасных вложений с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="9287b-260">Use PowerShell to view safe attachment policies</span></span>

<span data-ttu-id="9287b-261">Чтобы просмотреть существующие политики безопасных вложений, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="9287b-261">To view existing safe attachment policies, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="9287b-262">В этом примере возвращается сводный список всех политик безопасных вложений.</span><span class="sxs-lookup"><span data-stu-id="9287b-262">This example returns a summary list of all safe attachment policies.</span></span>

```PowerShell
Get-SafeAttachmentPolicy
```

<span data-ttu-id="9287b-263">В этом примере возвращаются подробные сведения о политике безопасных вложений с именем Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="9287b-263">This example returns detailed information for the safe attachment policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="9287b-264">Подробные сведения о синтаксисах и параметрах см. в описании [Get-SafeAttachmentPolicy.](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentpolicy)</span><span class="sxs-lookup"><span data-stu-id="9287b-264">For detailed syntax and parameter information, see [Get-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-view-safe-attachment-rules"></a><span data-ttu-id="9287b-265">Просмотр правил безопасных вложений с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="9287b-265">Use PowerShell to view safe attachment rules</span></span>

<span data-ttu-id="9287b-266">Чтобы просмотреть существующие правила безопасных вложений, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="9287b-266">To view existing safe attachment rules, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="9287b-267">В этом примере возвращается сводный список всех правил безопасных вложений.</span><span class="sxs-lookup"><span data-stu-id="9287b-267">This example returns a summary list of all safe attachment rules.</span></span>

```PowerShell
Get-SafeAttachmentRule
```

<span data-ttu-id="9287b-268">Чтобы отфильтровать список по включенным или отключенным правилам, выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="9287b-268">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeAttachmentRule -State Disabled
```

```PowerShell
Get-SafeAttachmentRule -State Enabled
```

<span data-ttu-id="9287b-269">В этом примере возвращаются подробные сведения о правиле безопасных вложений с именем Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="9287b-269">This example returns detailed information for the safe attachment rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="9287b-270">Подробные сведения о синтаксисах и параметрах см. в описании [Get-SafeAttachmentRule.](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="9287b-270">For detailed syntax and parameter information, see [Get-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentrule).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-policies"></a><span data-ttu-id="9287b-271">Изменение политик безопасных вложений с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="9287b-271">Use PowerShell to modify safe attachment policies</span></span>

<span data-ttu-id="9287b-272">В PowerShell нельзя переименовать политику безопасных вложений (у cmdlet **Set-SafeAttachmentPolicy** нет _параметра Name)._</span><span class="sxs-lookup"><span data-stu-id="9287b-272">You can't rename a safe attachment policy in PowerShell (the **Set-SafeAttachmentPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="9287b-273">При переименовании политики безопасных вложений в Центре безопасности & соответствия требованиям необходимо переименовать только правило безопасных _вложений._</span><span class="sxs-lookup"><span data-stu-id="9287b-273">When you rename a Safe Attachments policy in the Security & Compliance Center, you're only renaming the safe attachment _rule_.</span></span>

<span data-ttu-id="9287b-274">В противном случае те же параметры доступны при создании политики безопасных вложений, как описано в разделе "Шаг 1. Создание политики безопасных вложений с помощью [PowerShell"](#step-1-use-powershell-to-create-a-safe-attachment-policy) ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="9287b-274">Otherwise, the same settings are available when you create a safe attachment policy as described in the [Step 1: Use PowerShell to create a safe attachment policy](#step-1-use-powershell-to-create-a-safe-attachment-policy) section earlier in this article.</span></span>

<span data-ttu-id="9287b-275">Чтобы изменить политику безопасных вложений, используйте синтаксис:</span><span class="sxs-lookup"><span data-stu-id="9287b-275">To modify a safe attachment policy, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="9287b-276">Подробные сведения о синтаксисах и параметрах см. в описании [Set-SafeAttachmentPolicy.](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentpolicy)</span><span class="sxs-lookup"><span data-stu-id="9287b-276">For detailed syntax and parameter information, see [Set-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-rules"></a><span data-ttu-id="9287b-277">Изменение правил безопасных вложений с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="9287b-277">Use PowerShell to modify safe attachment rules</span></span>

<span data-ttu-id="9287b-278">Единственным параметром, недоступным при изменении правила безопасного вложения в PowerShell, является параметр _Enabled,_ позволяющий создать отключенное правило.</span><span class="sxs-lookup"><span data-stu-id="9287b-278">The only setting that's not available when you modify a safe attachment rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="9287b-279">Чтобы включить или отключить существующие правила безопасных вложений, см. следующий раздел.</span><span class="sxs-lookup"><span data-stu-id="9287b-279">To enable or disable existing safe attachment rules, see the next section.</span></span>

<span data-ttu-id="9287b-280">В противном случае те же параметры доступны при создании правила, как описано в разделе "Шаг 2. Создание правила безопасного вложения с помощью [PowerShell"](#step-2-use-powershell-to-create-a-safe-attachment-rule) ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="9287b-280">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe attachment rule](#step-2-use-powershell-to-create-a-safe-attachment-rule) section earlier in this article.</span></span>

<span data-ttu-id="9287b-281">Чтобы изменить правило безопасного вложения, используйте синтаксис:</span><span class="sxs-lookup"><span data-stu-id="9287b-281">To modify a safe attachment rule, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="9287b-282">Подробные сведения о синтаксисах и параметрах см. в описании [Set-SafeAttachmentRule.](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="9287b-282">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a><span data-ttu-id="9287b-283">Использование PowerShell для включить или отключить правила безопасных вложений</span><span class="sxs-lookup"><span data-stu-id="9287b-283">Use PowerShell to enable or disable safe attachment rules</span></span>

<span data-ttu-id="9287b-284">Включение или отключение правила безопасных вложений в PowerShell включает или отключает всю политику безопасных вложений (правило безопасных вложений и назначенную политику безопасных вложений).</span><span class="sxs-lookup"><span data-stu-id="9287b-284">Enabling or disabling a safe attachment rule in PowerShell enables or disables the whole Safe Attachments policy (the safe attachment rule and the assigned safe attachment policy).</span></span>

<span data-ttu-id="9287b-285">Чтобы включить или отключить правило безопасного вложения в PowerShell, используйте синтаксис:</span><span class="sxs-lookup"><span data-stu-id="9287b-285">To enable or disable a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

<span data-ttu-id="9287b-286">В этом примере отключается правило безопасных вложений Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="9287b-286">This example disables the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="9287b-287">В этом примере включается то же правило.</span><span class="sxs-lookup"><span data-stu-id="9287b-287">This example enables same rule.</span></span>

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="9287b-288">Подробные сведения о синтаксисах и параметрах см. в описании [Enable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/enable-safeattachmentrule) и [Disable-SafeAttachmentRule.](https://docs.microsoft.com/powershell/module/exchange/disable-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="9287b-288">For detailed syntax and parameter information, see [Enable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/enable-safeattachmentrule) and [Disable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/disable-safeattachmentrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a><span data-ttu-id="9287b-289">Настройка приоритета правил безопасных вложений с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="9287b-289">Use PowerShell to set the priority of safe attachment rules</span></span>

<span data-ttu-id="9287b-290">Максимальный приоритет, который можно задать для правила, — 0.</span><span class="sxs-lookup"><span data-stu-id="9287b-290">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="9287b-291">Минимальное значение зависит от количества правил.</span><span class="sxs-lookup"><span data-stu-id="9287b-291">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="9287b-292">Например, если у вас есть пять правил, вы можете использовать значения 0–4.</span><span class="sxs-lookup"><span data-stu-id="9287b-292">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="9287b-293">Изменение приоритета существующего правила оказывает каскадное влияние на другие правила.</span><span class="sxs-lookup"><span data-stu-id="9287b-293">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="9287b-294">Например, если вы измените приоритет правила на 2, когда у вас есть пять настраиваемых правил (с приоритетами от 0 до 4), то для существующего правила с приоритетом 2 будет задан приоритет 3, а для правила с приоритетом 3 будет задан приоритет 4.</span><span class="sxs-lookup"><span data-stu-id="9287b-294">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="9287b-295">Чтобы установить приоритет правила безопасного вложения в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="9287b-295">To set the priority of a safe attachment rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="9287b-p124">В этом примере для правила Marketing Department задается приоритет 2. Все правила с приоритетом не больше 2 понижаются на один ранг (значения приоритета увеличиваются на 1).</span><span class="sxs-lookup"><span data-stu-id="9287b-p124">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="9287b-298">**Примечание.** Чтобы установить приоритет нового правила при его создании, используйте параметр _Priority_ в параметре **New-SafeAttachmentRule.**</span><span class="sxs-lookup"><span data-stu-id="9287b-298">**Note**: To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeAttachmentRule** cmdlet instead.</span></span>

<span data-ttu-id="9287b-299">Подробные сведения о синтаксисах и параметрах см. в описании [Set-SafeAttachmentRule.](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="9287b-299">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-policies"></a><span data-ttu-id="9287b-300">Удаление политик безопасных вложений с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="9287b-300">Use PowerShell to remove safe attachment policies</span></span>

<span data-ttu-id="9287b-301">При удалении политики безопасных вложений с помощью PowerShell соответствующее правило безопасных вложений не удаляется.</span><span class="sxs-lookup"><span data-stu-id="9287b-301">When you use PowerShell to remove a safe attachment policy, the corresponding safe attachment rule isn't removed.</span></span>

<span data-ttu-id="9287b-302">Чтобы удалить политику безопасных вложений в PowerShell, используйте синтаксис:</span><span class="sxs-lookup"><span data-stu-id="9287b-302">To remove a safe attachment policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="9287b-303">В этом примере удаляется политика безопасных вложений Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="9287b-303">This example removes the safe attachment policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

<span data-ttu-id="9287b-304">Подробные сведения о синтаксисах и параметрах см. в описании [Remove-SafeAttachmentPolicy.](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentpolicy)</span><span class="sxs-lookup"><span data-stu-id="9287b-304">For detailed syntax and parameter information, see [Remove-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-rules"></a><span data-ttu-id="9287b-305">Удаление правил безопасных вложений с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="9287b-305">Use PowerShell to remove safe attachment rules</span></span>

<span data-ttu-id="9287b-306">При удалении правила безопасных вложений с помощью PowerShell соответствующая политика безопасных вложений не удаляется.</span><span class="sxs-lookup"><span data-stu-id="9287b-306">When you use PowerShell to remove a safe attachment rule, the corresponding safe attachment policy isn't removed.</span></span>

<span data-ttu-id="9287b-307">Чтобы удалить правило безопасного вложения в PowerShell, используйте синтаксис:</span><span class="sxs-lookup"><span data-stu-id="9287b-307">To remove a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

<span data-ttu-id="9287b-308">В этом примере удаляется правило безопасных вложений Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="9287b-308">This example removes the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="9287b-309">Подробные сведения о синтаксисах и параметрах см. в описании [remove-SafeAttachmentRule.](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="9287b-309">For detailed syntax and parameter information, see [Remove-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentrule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="9287b-310">Как проверить, что эти процедуры выполнены?</span><span class="sxs-lookup"><span data-stu-id="9287b-310">How do you know these procedures worked?</span></span>

<span data-ttu-id="9287b-311">Чтобы убедиться, что вы успешно создали, изменили или удалили политики безопасных вложений, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="9287b-311">To verify that you've successfully created, modified, or removed Safe Attachments policies, do any of the following steps:</span></span>

- <span data-ttu-id="9287b-312">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span><span class="sxs-lookup"><span data-stu-id="9287b-312">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span> <span data-ttu-id="9287b-313">Проверьте список политик, их значения **состояния** и их **значения приоритета.**</span><span class="sxs-lookup"><span data-stu-id="9287b-313">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="9287b-314">Чтобы просмотреть дополнительные сведения, выберите политику в списке и просмотреть сведения во внешнем поле.</span><span class="sxs-lookup"><span data-stu-id="9287b-314">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="9287b-315">В Exchange Online PowerShell или Exchange Online Protection PowerShell замените имя политики или правила, запустите следующую команду и проверьте \<Name\> параметры:</span><span class="sxs-lookup"><span data-stu-id="9287b-315">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

<span data-ttu-id="9287b-316">Чтобы убедиться, что безопасные вложения сканирует сообщения, проверьте доступные отчеты Защитника для Office 365.</span><span class="sxs-lookup"><span data-stu-id="9287b-316">To verify that Safe Attachments is scanning messages, check the available Defender for Office 365 reports.</span></span> <span data-ttu-id="9287b-317">Дополнительные сведения см. в отчетах "Просмотр отчетов для [Защитника для Office 365"](view-reports-for-atp.md) и "Использование проводника" в Центре [безопасности & соответствия требованиям.](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="9287b-317">For more information, see [View reports for Defender for Office 365](view-reports-for-atp.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>
