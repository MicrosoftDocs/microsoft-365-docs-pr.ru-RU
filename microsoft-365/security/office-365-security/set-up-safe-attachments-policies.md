---
title: Настройка политик Сейф в Microsoft Defender для Office 365
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
description: Узнайте, как определить Сейф вложения для защиты организации от вредоносных файлов в электронной почте.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e516a16ff28c762e154fd908312df65ea48699bc
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108227"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="ca773-103">Настройка политик Сейф в Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="ca773-103">Set up Safe Attachments policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ca773-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="ca773-104">**Applies to**</span></span>
- [<span data-ttu-id="ca773-105">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="ca773-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="ca773-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ca773-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="ca773-107">Эта статья предназначена для бизнес-клиентов, использующих [Microsoft Defender для Office 365](whats-new-in-defender-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="ca773-107">This article is intended for business customers who have [Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md).</span></span> <span data-ttu-id="ca773-108">Если вы домашний пользователь, который ищет сведения о сканировании вложений в Outlook, см. в [Outlook.com.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)</span><span class="sxs-lookup"><span data-stu-id="ca773-108">If you're a home user looking for information about attachment scanning in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="ca773-109">Сейф Вложения — это функция [в Microsoft Defender для Office 365,](whats-new-in-defender-for-office-365.md) которая использует виртуальную среду для проверки вложений в входящие сообщения электронной почты после того, как они были сканированы защитой от вредоносных программ в Exchange Online Protection [(EOP),](anti-malware-protection.md)но перед доставкой получателям.</span><span class="sxs-lookup"><span data-stu-id="ca773-109">Safe Attachments is a feature in [Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md) that uses a virtual environment to check attachments in inbound email messages after they've been scanned by [anti-malware protection in Exchange Online Protection (EOP)](anti-malware-protection.md), but before delivery to recipients.</span></span> <span data-ttu-id="ca773-110">Дополнительные сведения см. [в Сейф Вложения в Microsoft Defender для Office 365.](safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="ca773-110">For more information, see [Safe Attachments in Microsoft Defender for Office 365](safe-attachments.md).</span></span>

<span data-ttu-id="ca773-111">Не существует политики встроенных или Сейф вложений.</span><span class="sxs-lookup"><span data-stu-id="ca773-111">There's no built-in or default Safe Attachments policy.</span></span> <span data-ttu-id="ca773-112">Чтобы Сейф вложения для сканирования вложений сообщений электронной почты, необходимо создать одну или несколько политик Сейф вложений, как описано в этой статье.</span><span class="sxs-lookup"><span data-stu-id="ca773-112">To get Safe Attachments scanning of email message attachments, you need to create one or more Safe Attachments policies as described in this article.</span></span>

<span data-ttu-id="ca773-113">Политики Сейф вложений можно настроить на портале Microsoft 365 Defender или в PowerShell (Exchange Online PowerShell для подходящих Microsoft 365 организаций с почтовыми ящиками в Exchange Online; автономные EOP PowerShell для организаций без Exchange Online почтовых ящиков, но с подписками На надстройки Defender для Office 365).</span><span class="sxs-lookup"><span data-stu-id="ca773-113">You can configure Safe Attachments policies in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="ca773-114">Основные элементы политики Сейф вложения:</span><span class="sxs-lookup"><span data-stu-id="ca773-114">The basic elements of a Safe Attachments policy are:</span></span>

- <span data-ttu-id="ca773-115">**Политика** безопасного вложения: указывает действия для обнаружения неизвестных вредоносных программ, отправку сообщений с вложениями вредоносных программ на указанный адрес электронной почты и отправку сообщений, если Сейф проверку вложений не может завершиться.</span><span class="sxs-lookup"><span data-stu-id="ca773-115">**The safe attachment policy**: Specifies the actions for unknown malware detections, whether to send messages with malware attachments to a specified email address, and whether to deliver messages if Safe Attachments scanning can't complete.</span></span>
- <span data-ttu-id="ca773-116">**Правило безопасного вложения:** указывает фильтры приоритета и получателя (к кому применяется политика).</span><span class="sxs-lookup"><span data-stu-id="ca773-116">**The safe attachment rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="ca773-117">Разница между этими двумя элементами не очевидна при управлении политиками Сейф вложений на Microsoft 365 Defender портале:</span><span class="sxs-lookup"><span data-stu-id="ca773-117">The difference between these two elements isn't obvious when you manage Safe Attachments policies in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="ca773-118">При создании политики Сейф вложений создается правило безопасного вложения и связанная политика безопасного вложения одновременно с тем же именем для обоих.</span><span class="sxs-lookup"><span data-stu-id="ca773-118">When you create a Safe Attachments policy, you're actually creating a safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="ca773-119">При изменении политики Сейф вложений параметры, связанные с именем, приоритетом, включенной или отключенной, а также фильтры получателей изменяют правило безопасного вложения.</span><span class="sxs-lookup"><span data-stu-id="ca773-119">When you modify a Safe Attachments policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe attachment rule.</span></span> <span data-ttu-id="ca773-120">Все остальные параметры изменяют связанную политику безопасного вложения.</span><span class="sxs-lookup"><span data-stu-id="ca773-120">All other settings modify the associated safe attachment policy.</span></span>
- <span data-ttu-id="ca773-121">При удалении политики Сейф вложений правило безопасного вложения и связанная политика безопасного вложения удаляются.</span><span class="sxs-lookup"><span data-stu-id="ca773-121">When you remove a Safe Attachments policy, the safe attachment rule and the associated safe attachment policy are removed.</span></span>

<span data-ttu-id="ca773-122">В Exchange Online PowerShell или автономном EOP PowerShell вы управляете политикой и правилом отдельно.</span><span class="sxs-lookup"><span data-stu-id="ca773-122">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="ca773-123">Дополнительные сведения см. в разделе Использование Exchange Online PowerShell или автономный [EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) для настройки Сейф политик вложений в этой статье.</span><span class="sxs-lookup"><span data-stu-id="ca773-123">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) section later in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="ca773-124">В области глобальных параметров параметров Сейф вложениях настраиваются функции, не зависящие Сейф вложениях.</span><span class="sxs-lookup"><span data-stu-id="ca773-124">In the global settings area of Safe Attachments settings, you configure features that are not dependent on Safe Attachments policies.</span></span> <span data-ttu-id="ca773-125">Инструкции см. в Сейф Вложения для [SharePoint, OneDrive, Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md) и Сейф документов [в Microsoft 365 E5](safe-docs.md).</span><span class="sxs-lookup"><span data-stu-id="ca773-125">For instructions see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md) and [Safe Documents in Microsoft 365 E5](safe-docs.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ca773-126">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="ca773-126">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ca773-127">Чтобы открыть портал Microsoft 365 Defender, перейдите на сайт <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="ca773-127">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="ca773-128">Чтобы перейти непосредственно **на страницу Сейф вложения,** используйте <https://security.microsoft.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="ca773-128">To go directly to the **Safe Attachments** page, use <https://security.microsoft.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="ca773-129">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="ca773-129">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="ca773-130">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="ca773-130">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="ca773-131">Вам необходимы разрешения, прежде чем вы сможете сделать процедуры в этой статье:</span><span class="sxs-lookup"><span data-stu-id="ca773-131">You need permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="ca773-132">Чтобы создать, изменить и удалить Сейф вложения, необходимо быть членом группы  ролей управления организацией или администратором безопасности  на портале  Microsoft 365 Defender и членом группы ролей управления организацией в Exchange Online. </span><span class="sxs-lookup"><span data-stu-id="ca773-132">To create, modify, and delete Safe Attachments policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Microsoft 365 Defender portal **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="ca773-133">Для доступа только для чтения к политикам Сейф вложениям необходимо быть членом групп ролей **Global Reader** или **Security Reader** на Microsoft 365 Defender портале.</span><span class="sxs-lookup"><span data-stu-id="ca773-133">For read-only access to Safe Attachments policies, you need to be a member of the **Global Reader** or **Security Reader** role groups in the Microsoft 365 Defender portal.</span></span>

  <span data-ttu-id="ca773-134">Дополнительные сведения см. [в Microsoft 365 Defender](permissions-microsoft-365-security-center.md) и [разрешениях](/exchange/permissions-exo/permissions-exo)в Exchange Online .</span><span class="sxs-lookup"><span data-stu-id="ca773-134">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="ca773-135">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="ca773-135">**Notes**:</span></span>

  - <span data-ttu-id="ca773-136">Добавление пользователей к соответствующей роли Azure Active Directory в Центр администрирования Microsoft 365 дает пользователям необходимые разрешения на портале  Microsoft 365 Defender и разрешения на другие функции в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ca773-136">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="ca773-137">Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="ca773-137">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="ca773-138">Группа ролей **Управление организацией с правами только на просмотр** в [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) также предоставляет доступ только для чтения к этой функции.</span><span class="sxs-lookup"><span data-stu-id="ca773-138">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="ca773-139">Рекомендуемые параметры для политик Сейф вложений см. в Сейф [вложениях.](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)</span><span class="sxs-lookup"><span data-stu-id="ca773-139">For our recommended settings for Safe Attachments policies, see [Safe Attachments settings](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).</span></span>

- <span data-ttu-id="ca773-140">Разрешить до 30 минут для новой или обновленной политики, которая будет применяться.</span><span class="sxs-lookup"><span data-stu-id="ca773-140">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies"></a><span data-ttu-id="ca773-141">Используйте портал Microsoft 365 Defender для создания Сейф вложений</span><span class="sxs-lookup"><span data-stu-id="ca773-141">Use the Microsoft 365 Defender portal to create Safe Attachments policies</span></span>

<span data-ttu-id="ca773-142">Создание настраиваемой политики Сейф вложений на портале Microsoft 365 Defender создает правило безопасного вложения и связанную политику безопасного вложения одновременно с использованием одного и того же имени для обоих.</span><span class="sxs-lookup"><span data-stu-id="ca773-142">Creating a custom Safe Attachments policy in the Microsoft 365 Defender portal creates the safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="ca773-143">На портале Microsoft 365 Defender перейдите к разделу Политики **совместной** & электронной почты & Политики правил политики угрозы Сейф \>  \>  \>  \> **Вложения .**</span><span class="sxs-lookup"><span data-stu-id="ca773-143">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="ca773-144">На странице **Сейф вложения** нажмите ![ кнопку Создать значок ](../../media/m365-cc-sc-create-icon.png) **Создать**.</span><span class="sxs-lookup"><span data-stu-id="ca773-144">On the **Safe Attachments** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create**.</span></span>

3. <span data-ttu-id="ca773-145">Откроется мастер политик.</span><span class="sxs-lookup"><span data-stu-id="ca773-145">The policy wizard opens.</span></span> <span data-ttu-id="ca773-146">На странице **Имя политики** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="ca773-146">On the **Name your policy** page, configure the following settings:</span></span>
   - <span data-ttu-id="ca773-147">**Имя**. Укажите уникальное, описательное имя политики.</span><span class="sxs-lookup"><span data-stu-id="ca773-147">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="ca773-148">**Описание**. По желанию введите описание политики.</span><span class="sxs-lookup"><span data-stu-id="ca773-148">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="ca773-149">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="ca773-149">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="ca773-150">На странице **Пользователи и домены,** которая отображается, определите внутренних получателей, к которых применяется политика (условия получателей):</span><span class="sxs-lookup"><span data-stu-id="ca773-150">On the **Users and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="ca773-151">**Пользователи**: указывает один или несколько почтовых ящиков, пользователей почты или почтовых контактов в организации.</span><span class="sxs-lookup"><span data-stu-id="ca773-151">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="ca773-152">**Группы**: указывает группы рассылки, группы безопасности с поддержкой почты или группы Microsoft 365 в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="ca773-152">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="ca773-153">**Домены**: все получатели в указанных [обслуживаемых доменах](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="ca773-153">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="ca773-154">Щелкните соответствующее поле, начните вводить значение и выберите нужное значение в результатах.</span><span class="sxs-lookup"><span data-stu-id="ca773-154">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="ca773-155">Повторите эти действия необходимое количество раз.</span><span class="sxs-lookup"><span data-stu-id="ca773-155">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="ca773-156">Чтобы удалить существующее значение, нажмите "Удалить".</span><span class="sxs-lookup"><span data-stu-id="ca773-156">To remove an existing value, click remove</span></span> ![Значок "Удалить"](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="ca773-158">рядом со значением.</span><span class="sxs-lookup"><span data-stu-id="ca773-158">next to the value.</span></span>

   <span data-ttu-id="ca773-159">Для пользователей и групп можно использовать большинство идентификаторов (имя, отображаемое имя, псевдоним, адрес электронной почты, имя учетной записи и т. д.), но в результатах будет выведено отображаемое имя.</span><span class="sxs-lookup"><span data-stu-id="ca773-159">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="ca773-160">Для получения списка всех пользователей введите звездочку (\*) без добавлений, чтобы увидеть все доступные значения.</span><span class="sxs-lookup"><span data-stu-id="ca773-160">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="ca773-161">Указать несколько значений в одном условии можно с помощью оператора OR (например, _\<recipient1\>_ or _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="ca773-161">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="ca773-162">Между разными условиями и исключениями используется оператор AND (например, _\<recipient1\>_ and _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="ca773-162">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="ca773-163">**Исключить этих пользователей, группы и домены**. Чтобы добавить исключения для внутренних получателей, к которым применяется политика (исключение получателей), выберите этот параметр и настройте исключения.</span><span class="sxs-lookup"><span data-stu-id="ca773-163">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="ca773-164">Настройки и поведение такие же, как в разделе условий.</span><span class="sxs-lookup"><span data-stu-id="ca773-164">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="ca773-165">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="ca773-165">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="ca773-166">На странице **Параметры** настройка следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="ca773-166">On the **Settings** page, configure the following settings:</span></span>

   - <span data-ttu-id="ca773-167">**Сейф вложения неизвестного ответа вредоносных** программ: Выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="ca773-167">**Safe Attachments unknown malware response**: Select one of the following values:</span></span>
     - <span data-ttu-id="ca773-168">**Off.** Как правило, мы не рекомендуем это значение.</span><span class="sxs-lookup"><span data-stu-id="ca773-168">**Off**: Typically, we don't recommend this value.</span></span>
     - <span data-ttu-id="ca773-169">**Мониторинг**</span><span class="sxs-lookup"><span data-stu-id="ca773-169">**Monitor**</span></span>
     - <span data-ttu-id="ca773-170">**Блок.** Это значение по умолчанию и рекомендуемое значение в стандартных и строгих [предустановленных политиках безопасности.](preset-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="ca773-170">**Block**: This is the default value, and the recommended value in Standard and Strict [preset security policies](preset-security-policies.md).</span></span>
     - <span data-ttu-id="ca773-171">**Replace**</span><span class="sxs-lookup"><span data-stu-id="ca773-171">**Replace**</span></span>
     - <span data-ttu-id="ca773-172">**Динамическая доставка (функция предварительного просмотра)**</span><span class="sxs-lookup"><span data-stu-id="ca773-172">**Dynamic Delivery (Preview Feature)**</span></span>

     <span data-ttu-id="ca773-173">Эти значения объясняются в [параметрах политики Сейф вложения.](safe-attachments.md#safe-attachments-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="ca773-173">These values are explained in [Safe Attachments policy settings](safe-attachments.md#safe-attachments-policy-settings).</span></span>

   - <span data-ttu-id="ca773-174">Перенаправление сообщений с обнаруженными вложениями. Если вы выберите Включить перенаправление, вы можете указать адрес электронной почты в отправке сообщений, содержащих **заблокированные,** отслеживаемые или замененные вложения в указанный адрес электронной почты для отправки сообщений, содержащих вложения вредоносных программ для анализа и исследования.</span><span class="sxs-lookup"><span data-stu-id="ca773-174">**Redirect messages with detected attachments**: If you select **Enable redirect**, you can specify an email address in the **Send messages that contain blocked, monitored, or replaced attachments to the specified email address** box to send messages that contain malware attachments for analysis and investigation.</span></span>

     <span data-ttu-id="ca773-175">Рекомендация для параметров стандартных и строгих политик — включить перенаправление.</span><span class="sxs-lookup"><span data-stu-id="ca773-175">The recommendation for Standard and Strict policy settings is to enable redirection.</span></span> <span data-ttu-id="ca773-176">Дополнительные сведения см. [в Сейф параметры вложений.](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)</span><span class="sxs-lookup"><span data-stu-id="ca773-176">For more information, see [Safe Attachments settings](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).</span></span>

   - <span data-ttu-id="ca773-177">Применение ответа Сейф вложения, если сканирование не может **завершиться (время** выполнения или ошибки) : действие, указанное Сейф **Вложения** неизвестный ответ вредоносных программ, принимаются в сообщениях, даже если Сейф сканирование вложений не может завершиться.</span><span class="sxs-lookup"><span data-stu-id="ca773-177">**Apply the Safe Attachments detection response if scanning can't complete (timeout or errors)**: The action specified by **Safe Attachments unknown malware response** is taken on messages even when Safe Attachments scanning can't complete.</span></span> <span data-ttu-id="ca773-178">Если выбран этот параметр, всегда выберите **Включить** перенаправление и укажите адрес электронной почты для отправки сообщений, содержащих вложения вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="ca773-178">If you selected this option, always select **Enable redirect** and specify an email address to send messages that contain malware attachments.</span></span> <span data-ttu-id="ca773-179">В противном случае сообщения могут быть потеряны.</span><span class="sxs-lookup"><span data-stu-id="ca773-179">Otherwise, messages might be lost.</span></span>

   <span data-ttu-id="ca773-180">По завершении нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="ca773-180">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="ca773-181">На странице **Просмотр** просмотрите параметры.</span><span class="sxs-lookup"><span data-stu-id="ca773-181">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="ca773-182">Вы можете выбрать **Изменить** в любом разделе, чтобы изменить параметры в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="ca773-182">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="ca773-183">Вы также можете щелкнуть **Назад** или выбрать определенную страницу в мастере.</span><span class="sxs-lookup"><span data-stu-id="ca773-183">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="ca773-184">По завершении нажмите **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="ca773-184">When you're finished, click **Submit**.</span></span>

7. <span data-ttu-id="ca773-185">На странице подтверждения, которая откроется, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="ca773-185">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-safe-attachments-policies"></a><span data-ttu-id="ca773-186">Используйте портал Microsoft 365 Defender для просмотра Сейф вложений</span><span class="sxs-lookup"><span data-stu-id="ca773-186">Use the Microsoft 365 Defender portal to view Safe Attachments policies</span></span>

1. <span data-ttu-id="ca773-187">На портале Microsoft 365 Defender перейдите к разделу Политики **совместной** & электронной почты & Политики правил политики угрозы Сейф \>  \>  \>  \> **Вложения .**</span><span class="sxs-lookup"><span data-stu-id="ca773-187">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="ca773-188">На **странице Сейф вложения** в списке политик отображаются следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="ca773-188">On the **Safe Attachments** page, the following properties are displayed in the list of policies:</span></span>
   - <span data-ttu-id="ca773-189">**Имя**</span><span class="sxs-lookup"><span data-stu-id="ca773-189">**Name**</span></span>
   - <span data-ttu-id="ca773-190">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="ca773-190">**Status**</span></span>
   - <span data-ttu-id="ca773-191">**Приоритет**</span><span class="sxs-lookup"><span data-stu-id="ca773-191">**Priority**</span></span>

3. <span data-ttu-id="ca773-192">При выборе политики, щелкнув имя, параметры политики отображаются в вылете.</span><span class="sxs-lookup"><span data-stu-id="ca773-192">When you select a policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-safe-attachments-policies"></a><span data-ttu-id="ca773-193">Использование портала Microsoft 365 Defender для изменения Сейф вложений</span><span class="sxs-lookup"><span data-stu-id="ca773-193">Use the Microsoft 365 Defender portal to modify Safe Attachments policies</span></span>

1. <span data-ttu-id="ca773-194">На портале Microsoft 365 Defender перейдите к разделу Политики **совместной** & электронной почты & Политики правил политики угрозы Сейф \>  \>  \>  \> **Вложения .**</span><span class="sxs-lookup"><span data-stu-id="ca773-194">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="ca773-195">На странице **Сейф вложения** выберите политику из списка, нажав на имя.</span><span class="sxs-lookup"><span data-stu-id="ca773-195">On the **Safe Attachments** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="ca773-196">Параметры политики будут показаны во всплывающем окне. Вы можете выбрать **Изменить** в любом разделе, чтобы изменить параметры в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="ca773-196">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="ca773-197">Дополнительные сведения о параметрах см. в разделе Использование портала Microsoft 365 Defender для создания [раздела Сейф вложения](#use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies) в этой статье.</span><span class="sxs-lookup"><span data-stu-id="ca773-197">For more information about the settings, see the [Use the Microsoft 365 Defender portal to create Safe Attachments policies](#use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies) section earlier in this article.</span></span>  

<span data-ttu-id="ca773-198">Чтобы включить или отключить политику или установить порядок приоритета политики, см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="ca773-198">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-attachments-policies"></a><span data-ttu-id="ca773-199">Включить или отключить Сейф вложения</span><span class="sxs-lookup"><span data-stu-id="ca773-199">Enable or disable Safe Attachments policies</span></span>

1. <span data-ttu-id="ca773-200">На портале Microsoft 365 Defender перейдите к разделу Политики **совместной** & электронной почты & Политики правил политики угрозы Сейф \>  \>  \>  \> **Вложения .**</span><span class="sxs-lookup"><span data-stu-id="ca773-200">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="ca773-201">На странице **Сейф вложения** выберите политику из списка, нажав на имя.</span><span class="sxs-lookup"><span data-stu-id="ca773-201">On the **Safe Attachments** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="ca773-202">Появится всплывающее окно со сведениями о политике. В верхней его части вы увидите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="ca773-202">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="ca773-203">**Политика отключена**. Чтобы включить политику, щелкните значок !["Включить"](../../media/m365-cc-sc-turn-on-off-icon.png) **Включить** .</span><span class="sxs-lookup"><span data-stu-id="ca773-203">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="ca773-204">**Политика включена**. Чтобы выключить политику, щелкните значок !["Отключить"](../../media/m365-cc-sc-turn-on-off-icon.png) **Отключить**.</span><span class="sxs-lookup"><span data-stu-id="ca773-204">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="ca773-205">В диалоговом окне подтверждения нажмите кнопку **Включить** или **Отключить**.</span><span class="sxs-lookup"><span data-stu-id="ca773-205">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="ca773-206">Во всплывающем окне сведений о политике нажмите **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="ca773-206">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="ca773-207">Когда вы вернетесь на главную страницу политики, значение параметра **Состояние** этой политики будет **Включена** или **Выключена**.</span><span class="sxs-lookup"><span data-stu-id="ca773-207">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-safe-attachments-policies"></a><span data-ttu-id="ca773-208">Установите приоритет политик Сейф вложений</span><span class="sxs-lookup"><span data-stu-id="ca773-208">Set the priority of Safe Attachments policies</span></span>

<span data-ttu-id="ca773-209">По умолчанию Сейф политикам вложений предоставляется приоритет, основанный на порядке, в который они были созданы (более новые политики имеют более низкий приоритет по сравнению с более старыми политиками).</span><span class="sxs-lookup"><span data-stu-id="ca773-209">By default, Safe Attachments policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="ca773-210">Чем ниже значение, тем выше приоритет политики (0 — наивысший приоритет), а порядок обработки политик зависит от их приоритетов (политики с высоким приоритетом обрабатываются раньше, чем политики с низким приоритетом).</span><span class="sxs-lookup"><span data-stu-id="ca773-210">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="ca773-211">Никакие две политики не могут иметь одинаковый приоритет, и обработка политики прекращается после применения первой политики.</span><span class="sxs-lookup"><span data-stu-id="ca773-211">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="ca773-212">Дополнительные сведения о приоритетах, а также оценке и применении нескольких политик см. в статье [Порядок и приоритет защиты электронной почты](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="ca773-212">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="ca773-213">Сейф Политики вложений отображаются в порядке их обработки (первая политика имеет значение **Priority** 0).</span><span class="sxs-lookup"><span data-stu-id="ca773-213">Safe Attachments policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

<span data-ttu-id="ca773-214">**Примечание.** На Microsoft 365 Defender портале можно изменить приоритет политики Сейф вложений после ее создания.</span><span class="sxs-lookup"><span data-stu-id="ca773-214">**Note**: In the Microsoft 365 Defender portal, you can only change the priority of the Safe Attachments policy after you create it.</span></span> <span data-ttu-id="ca773-215">В PowerShell можно переопредить приоритет по умолчанию при создании правила безопасного вложения (которое может повлиять на приоритет существующих правил).</span><span class="sxs-lookup"><span data-stu-id="ca773-215">In PowerShell, you can override the default priority when you create the safe attachment rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="ca773-216">Чтобы изменить приоритет политики, нажмите кнопку **Увеличить приоритет** или **Уменьшить приоритет** в свойствах политики (вы не можете напрямую изменить числовое значение параметра **Приоритет** на портале Microsoft 365 Defender).</span><span class="sxs-lookup"><span data-stu-id="ca773-216">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Microsoft 365 Defender portal).</span></span> <span data-ttu-id="ca773-217">Изменение приоритета политики имеет смысл, только если у вас несколько политик.</span><span class="sxs-lookup"><span data-stu-id="ca773-217">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="ca773-218">На портале Microsoft 365 Defender перейдите к разделу Политики **совместной** & электронной почты & Политики правил политики угрозы Сейф \>  \>  \>  \> **Вложения .**</span><span class="sxs-lookup"><span data-stu-id="ca773-218">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="ca773-219">На странице **Сейф вложения** выберите политику из списка, нажав на имя.</span><span class="sxs-lookup"><span data-stu-id="ca773-219">On the **Safe Attachments** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="ca773-220">В верхней части вылета сведений политики,  которые появляются, вы увидите увеличение приоритета или уменьшение приоритета в зависимости от текущего значения приоритета и количества политик: </span><span class="sxs-lookup"><span data-stu-id="ca773-220">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of policies:</span></span>
   - <span data-ttu-id="ca773-221">Политика со **значением Приоритет** **0** имеет только доступный параметр **Приоритет уменьшения.**</span><span class="sxs-lookup"><span data-stu-id="ca773-221">The policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="ca773-222">Политика с наименьшим **значением** Приоритет (например, **3)** имеет только доступный параметр **Increase priority.**</span><span class="sxs-lookup"><span data-stu-id="ca773-222">The policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="ca773-223">Если у вас есть три или более политик, политики между самыми высокими и самыми низкими значениями приоритетов имеют доступные параметры **приоритета Increase** и **Decrease.**</span><span class="sxs-lookup"><span data-stu-id="ca773-223">If you have three or more policies, the policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="ca773-224">Щелкните ![Значок увеличения приоритета](../../media/m365-cc-sc-increase-icon.png) **Увеличить приоритет** или ![Значок уменьшения приоритета](../../media/m365-cc-sc-decrease-icon.png) **Уменьшить приоритет** чтобы изменить значение параметра **Приоритет**.</span><span class="sxs-lookup"><span data-stu-id="ca773-224">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="ca773-225">Закончив, нажмите **Закрыть** во всплывающем окне сведений о политике.</span><span class="sxs-lookup"><span data-stu-id="ca773-225">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-safe-attachments-policies"></a><span data-ttu-id="ca773-226">Использование портала Microsoft 365 Defender для удаления Сейф вложений</span><span class="sxs-lookup"><span data-stu-id="ca773-226">Use the Microsoft 365 Defender portal to remove Safe Attachments policies</span></span>

1. <span data-ttu-id="ca773-227">На портале Microsoft 365 Defender перейдите к разделу Политики **совместной** & электронной почты & Политики правил политики угрозы Сейф \>  \>  \>  \> **Вложения .**</span><span class="sxs-lookup"><span data-stu-id="ca773-227">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="ca773-228">На странице **Сейф вложения** выберите настраиваемую политику из списка, нажав на имя политики.</span><span class="sxs-lookup"><span data-stu-id="ca773-228">On the **Safe Attachments** page, select a custom policy from the list by clicking on the name of the policy.</span></span>

3. <span data-ttu-id="ca773-229">В открывшемся всплывающем окне сведений о политике щелкните ![значок "Дополнительные действия"](../../media/m365-cc-sc-more-actions-icon.png) **Дополнительные действия** \> ![значок "Удалить политику"](../../media/m365-cc-sc-delete-icon.png) **Удалить политику**.</span><span class="sxs-lookup"><span data-stu-id="ca773-229">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

4. <span data-ttu-id="ca773-230">В диалоговом окне подтверждения нажмите **Да**.</span><span class="sxs-lookup"><span data-stu-id="ca773-230">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a><span data-ttu-id="ca773-231">Используйте Exchange Online PowerShell или автономный EOP PowerShell для настройки Сейф вложений</span><span class="sxs-lookup"><span data-stu-id="ca773-231">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies</span></span>

<span data-ttu-id="ca773-232">Как описано выше, политика Сейф вложений состоит из политики безопасного вложения и правила безопасного вложения.</span><span class="sxs-lookup"><span data-stu-id="ca773-232">As previously described, a Safe Attachments policy consists of a safe attachment policy and a safe attachment rule.</span></span>

<span data-ttu-id="ca773-233">В PowerShell разница между политиками безопасного вложения и правилами безопасного вложения очевидна.</span><span class="sxs-lookup"><span data-stu-id="ca773-233">In PowerShell, the difference between safe attachment policies and safe attachment rules is apparent.</span></span> <span data-ttu-id="ca773-234">Вы управляете политиками безопасного вложения с помощью **\* кодлетов -SafeAttachmentPolicy** и управляете правилами безопасного вложения с помощью cmdlets **\* -SafeAttachmentRule.**</span><span class="sxs-lookup"><span data-stu-id="ca773-234">You manage safe attachment policies by using the **\*-SafeAttachmentPolicy** cmdlets, and you manage safe attachment rules by using the **\*-SafeAttachmentRule** cmdlets.</span></span>

- <span data-ttu-id="ca773-235">В PowerShell сначала создается политика безопасного вложения, а затем создается правило безопасного вложения, которое определяет политику, к которую применяется правило.</span><span class="sxs-lookup"><span data-stu-id="ca773-235">In PowerShell, you create the safe attachment policy first, then you create the safe attachment rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="ca773-236">В PowerShell параметры политики безопасного вложения и правила безопасного вложения изменяются отдельно.</span><span class="sxs-lookup"><span data-stu-id="ca773-236">In PowerShell, you modify the settings in the safe attachment policy and the safe attachment rule separately.</span></span>
- <span data-ttu-id="ca773-237">При удалении политики безопасного вложения из PowerShell соответствующее правило безопасного вложения не удаляется автоматически, и наоборот.</span><span class="sxs-lookup"><span data-stu-id="ca773-237">When you remove a safe attachment policy from PowerShell, the corresponding safe attachment rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-attachments-policies"></a><span data-ttu-id="ca773-238">Использование PowerShell для создания Сейф вложений</span><span class="sxs-lookup"><span data-stu-id="ca773-238">Use PowerShell to create Safe Attachments policies</span></span>

<span data-ttu-id="ca773-239">Создание политики Сейф вложений в PowerShell — это двухшаговая процедура:</span><span class="sxs-lookup"><span data-stu-id="ca773-239">Creating a Safe Attachments policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="ca773-240">Создание политики безопасного вложения.</span><span class="sxs-lookup"><span data-stu-id="ca773-240">Create the safe attachment policy.</span></span>
2. <span data-ttu-id="ca773-241">Создайте правило безопасного вложения, которое указывает политику безопасного вложения, которая применяется к этому правилу.</span><span class="sxs-lookup"><span data-stu-id="ca773-241">Create the safe attachment rule that specifies the safe attachment policy that the rule applies to.</span></span>

 <span data-ttu-id="ca773-242">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="ca773-242">**Notes**:</span></span>

- <span data-ttu-id="ca773-243">Можно создать новое правило безопасного вложения и назначить ему существующую, неассоциированную политику безопасного вложения.</span><span class="sxs-lookup"><span data-stu-id="ca773-243">You can create a new safe attachment rule and assign an existing, unassociated safe attachment policy to it.</span></span> <span data-ttu-id="ca773-244">Правило безопасного вложения не может быть связано с более чем одной политикой безопасного вложения.</span><span class="sxs-lookup"><span data-stu-id="ca773-244">A safe attachment rule can't be associated with more than one safe attachment policy.</span></span>

- <span data-ttu-id="ca773-245">Вы можете настроить следующие параметры для новых политик безопасного вложения в PowerShell, недоступных на портале Microsoft 365 Defender до создания политики:</span><span class="sxs-lookup"><span data-stu-id="ca773-245">You can configure the following settings on new safe attachment policies in PowerShell that aren't available in the Microsoft 365 Defender portal until after you create the policy:</span></span>
  - <span data-ttu-id="ca773-246">Создайте новую политику как отключенную _(включена_ `$false` в **кодлете New-SafeAttachmentRule).**</span><span class="sxs-lookup"><span data-stu-id="ca773-246">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeAttachmentRule** cmdlet).</span></span>
  - <span data-ttu-id="ca773-247">Задай приоритет политики во время создания _(приоритет)_ в _\<Number\>_ **кодлете New-SafeAttachmentRule.**</span><span class="sxs-lookup"><span data-stu-id="ca773-247">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeAttachmentRule** cmdlet).</span></span>

- <span data-ttu-id="ca773-248">Новая политика безопасного вложения, которую вы создаете в PowerShell, не отображается на портале Microsoft 365 Defender, пока не назначите политику правилу безопасного вложения.</span><span class="sxs-lookup"><span data-stu-id="ca773-248">A new safe attachment policy that you create in PowerShell isn't visible in the Microsoft 365 Defender portal until you assign the policy to a safe attachment rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a><span data-ttu-id="ca773-249">Шаг 1. Использование PowerShell для создания политики безопасного вложения</span><span class="sxs-lookup"><span data-stu-id="ca773-249">Step 1: Use PowerShell to create a safe attachment policy</span></span>

<span data-ttu-id="ca773-250">Чтобы создать безопасную политику вложений, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="ca773-250">To create a safe attachment policy, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

<span data-ttu-id="ca773-251">В этом примере создается политика безопасного вложения с именем Contoso All со следующими значениями:</span><span class="sxs-lookup"><span data-stu-id="ca773-251">This example creates a safe attachment policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="ca773-252">Блокируют сообщения, содержащие вредоносные программы Сейф проверки документов (мы не используем параметр _Action,_ а значение по `Block` умолчанию).</span><span class="sxs-lookup"><span data-stu-id="ca773-252">Block messages that are found to contain malware by Safe Documents scanning (we aren't using the _Action_ parameter, and the default value is `Block`).</span></span>
- <span data-ttu-id="ca773-253">Перенаправление включено, и сообщения, содержащие вредоносные программы, отправляются в sec-ops@contoso.com для анализа и исследования.</span><span class="sxs-lookup"><span data-stu-id="ca773-253">Redirection is enabled, and messages that are found to contain malware are sent to sec-ops@contoso.com for analysis and investigation.</span></span>
- <span data-ttu-id="ca773-254">Если Сейф вложения недоступны или встречаются ошибки, не доставляйте сообщение (мы не используем параметр _ActionOnError,_ а значение по `$true` умолчанию).</span><span class="sxs-lookup"><span data-stu-id="ca773-254">If Safe Attachments scanning isn't available or encounters errors, don't deliver the message (we aren't using the _ActionOnError_ parameter, and the default value is `$true`).</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

<span data-ttu-id="ca773-255">Подробные сведения о синтаксисах и параметрах см. в [обзоре New-SafeAttachmentPolicy.](/powershell/module/exchange/new-safeattachmentpolicy)</span><span class="sxs-lookup"><span data-stu-id="ca773-255">For detailed syntax and parameter information, see [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a><span data-ttu-id="ca773-256">Шаг 2. Использование PowerShell для создания правила безопасного вложения</span><span class="sxs-lookup"><span data-stu-id="ca773-256">Step 2: Use PowerShell to create a safe attachment rule</span></span>

<span data-ttu-id="ca773-257">Чтобы создать правило безопасного вложения, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="ca773-257">To create a safe attachment rule, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="ca773-258">В этом примере создается правило безопасного вложения с именем Contoso All со следующими условиями:</span><span class="sxs-lookup"><span data-stu-id="ca773-258">This example creates a safe attachment rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="ca773-259">Это правило связано с политикой безопасного вложения с именем Contoso All.</span><span class="sxs-lookup"><span data-stu-id="ca773-259">The rule is associated with the safe attachment policy named Contoso All.</span></span>
- <span data-ttu-id="ca773-260">Правило применяется ко всем получателям в contoso.com домене.</span><span class="sxs-lookup"><span data-stu-id="ca773-260">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="ca773-261">Так как мы не используем параметр _Priority,_ используется приоритет по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ca773-261">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="ca773-262">Правило включено (мы не используем параметр _Включен,_ а значение по `$true` умолчанию).</span><span class="sxs-lookup"><span data-stu-id="ca773-262">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="ca773-263">Подробные сведения о синтаксисах и параметрах см. [в обзоре New-SafeAttachmentRule.](/powershell/module/exchange/new-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="ca773-263">For detailed syntax and parameter information, see [New-SafeAttachmentRule](/powershell/module/exchange/new-safeattachmentrule).</span></span>

### <a name="use-powershell-to-view-safe-attachment-policies"></a><span data-ttu-id="ca773-264">Использование PowerShell для просмотра политик безопасного вложения</span><span class="sxs-lookup"><span data-stu-id="ca773-264">Use PowerShell to view safe attachment policies</span></span>

<span data-ttu-id="ca773-265">Чтобы просмотреть существующие политики безопасного вложения, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="ca773-265">To view existing safe attachment policies, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="ca773-266">В этом примере возвращается сводный список всех политик безопасного вложения.</span><span class="sxs-lookup"><span data-stu-id="ca773-266">This example returns a summary list of all safe attachment policies.</span></span>

```PowerShell
Get-SafeAttachmentPolicy
```

<span data-ttu-id="ca773-267">В этом примере возвращаются подробные сведения о политике безопасного вложения с именем Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="ca773-267">This example returns detailed information for the safe attachment policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="ca773-268">Подробные сведения о синтаксисах и параметрах см. в [обзоре Get-SafeAttachmentPolicy.](/powershell/module/exchange/get-safeattachmentpolicy)</span><span class="sxs-lookup"><span data-stu-id="ca773-268">For detailed syntax and parameter information, see [Get-SafeAttachmentPolicy](/powershell/module/exchange/get-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-view-safe-attachment-rules"></a><span data-ttu-id="ca773-269">Использование PowerShell для просмотра правил безопасного вложения</span><span class="sxs-lookup"><span data-stu-id="ca773-269">Use PowerShell to view safe attachment rules</span></span>

<span data-ttu-id="ca773-270">Чтобы просмотреть существующие правила безопасного вложения, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="ca773-270">To view existing safe attachment rules, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="ca773-271">В этом примере возвращается сводный список всех правил безопасного вложения.</span><span class="sxs-lookup"><span data-stu-id="ca773-271">This example returns a summary list of all safe attachment rules.</span></span>

```PowerShell
Get-SafeAttachmentRule
```

<span data-ttu-id="ca773-272">Чтобы отфильтровать список по включенным или отключенным правилам, выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="ca773-272">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeAttachmentRule -State Disabled
```

```PowerShell
Get-SafeAttachmentRule -State Enabled
```

<span data-ttu-id="ca773-273">В этом примере возвращается подробная информация для правила безопасного вложения с именем Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="ca773-273">This example returns detailed information for the safe attachment rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="ca773-274">Подробные сведения о синтаксисах и параметрах см. в [ссылке Get-SafeAttachmentRule.](/powershell/module/exchange/get-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="ca773-274">For detailed syntax and parameter information, see [Get-SafeAttachmentRule](/powershell/module/exchange/get-safeattachmentrule).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-policies"></a><span data-ttu-id="ca773-275">Использование PowerShell для изменения политик безопасного вложения</span><span class="sxs-lookup"><span data-stu-id="ca773-275">Use PowerShell to modify safe attachment policies</span></span>

<span data-ttu-id="ca773-276">Нельзя переименовать политику безопасного вложения в PowerShell (в **комлете Set-SafeAttachmentPolicy** нет _параметра Name)._</span><span class="sxs-lookup"><span data-stu-id="ca773-276">You can't rename a safe attachment policy in PowerShell (the **Set-SafeAttachmentPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="ca773-277">При переименовании политики Сейф вложений на портале Microsoft 365 Defender, вы только переименовывать правило безопасного _вложения_.</span><span class="sxs-lookup"><span data-stu-id="ca773-277">When you rename a Safe Attachments policy in the Microsoft 365 Defender portal, you're only renaming the safe attachment _rule_.</span></span>

<span data-ttu-id="ca773-278">В противном случае те же параметры доступны при создании политики безопасного вложения, как описано в шаге [1: Использование PowerShell](#step-1-use-powershell-to-create-a-safe-attachment-policy) для создания безопасного раздела политики вложений в начале этой статьи.</span><span class="sxs-lookup"><span data-stu-id="ca773-278">Otherwise, the same settings are available when you create a safe attachment policy as described in the [Step 1: Use PowerShell to create a safe attachment policy](#step-1-use-powershell-to-create-a-safe-attachment-policy) section earlier in this article.</span></span>

<span data-ttu-id="ca773-279">Чтобы изменить политику безопасного вложения, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="ca773-279">To modify a safe attachment policy, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="ca773-280">Подробные сведения о синтаксисах и параметрах см. в [инструкции Set-SafeAttachmentPolicy.](/powershell/module/exchange/set-safeattachmentpolicy)</span><span class="sxs-lookup"><span data-stu-id="ca773-280">For detailed syntax and parameter information, see [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-rules"></a><span data-ttu-id="ca773-281">Использование PowerShell для изменения правил безопасного вложения</span><span class="sxs-lookup"><span data-stu-id="ca773-281">Use PowerShell to modify safe attachment rules</span></span>

<span data-ttu-id="ca773-282">Единственный параметр, недоступный при изменении правила безопасного вложения  в PowerShell, — это параметр Включен, который позволяет создать правило отключения.</span><span class="sxs-lookup"><span data-stu-id="ca773-282">The only setting that's not available when you modify a safe attachment rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="ca773-283">Чтобы включить или отключить существующие правила безопасного вложения, см. в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="ca773-283">To enable or disable existing safe attachment rules, see the next section.</span></span>

<span data-ttu-id="ca773-284">В противном случае те же параметры доступны при создании правила, описанного в разделе [Шаг 2. Использование PowerShell](#step-2-use-powershell-to-create-a-safe-attachment-rule) для создания раздела правила безопасного вложения в начале этой статьи.</span><span class="sxs-lookup"><span data-stu-id="ca773-284">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe attachment rule](#step-2-use-powershell-to-create-a-safe-attachment-rule) section earlier in this article.</span></span>

<span data-ttu-id="ca773-285">Чтобы изменить правило безопасного вложения, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="ca773-285">To modify a safe attachment rule, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="ca773-286">Подробные сведения о синтаксисах и параметрах см. в [инструкции Set-SafeAttachmentRule.](/powershell/module/exchange/set-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="ca773-286">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a><span data-ttu-id="ca773-287">Использование PowerShell, чтобы включить или отключить правила безопасного вложения</span><span class="sxs-lookup"><span data-stu-id="ca773-287">Use PowerShell to enable or disable safe attachment rules</span></span>

<span data-ttu-id="ca773-288">Включение или отключение правила безопасного вложения в PowerShell включает или отключает всю политику Сейф вложений (правило безопасного вложения и назначенную политику безопасного вложения).</span><span class="sxs-lookup"><span data-stu-id="ca773-288">Enabling or disabling a safe attachment rule in PowerShell enables or disables the whole Safe Attachments policy (the safe attachment rule and the assigned safe attachment policy).</span></span>

<span data-ttu-id="ca773-289">Чтобы включить или отключить правило безопасного вложения в PowerShell, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="ca773-289">To enable or disable a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

<span data-ttu-id="ca773-290">В этом примере отключает правило безопасного вложения с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="ca773-290">This example disables the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="ca773-291">В этом примере включается то же правило.</span><span class="sxs-lookup"><span data-stu-id="ca773-291">This example enables same rule.</span></span>

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="ca773-292">Подробные сведения о синтаксисах и параметрах см. в [инструкции Enable-SafeAttachmentRule](/powershell/module/exchange/enable-safeattachmentrule) и [Disable-SafeAttachmentRule.](/powershell/module/exchange/disable-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="ca773-292">For detailed syntax and parameter information, see [Enable-SafeAttachmentRule](/powershell/module/exchange/enable-safeattachmentrule) and [Disable-SafeAttachmentRule](/powershell/module/exchange/disable-safeattachmentrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a><span data-ttu-id="ca773-293">Использование PowerShell для набора приоритета правил безопасного вложения</span><span class="sxs-lookup"><span data-stu-id="ca773-293">Use PowerShell to set the priority of safe attachment rules</span></span>

<span data-ttu-id="ca773-p126">Максимальный приоритет, который можно задать для правила, — 0. Минимальное значение зависит от количества правил. Например, если у вас есть пять правил, вы можете использовать значения 0-4. Изменение приоритета существующего правила оказывает каскадное влияние на другие правила. Например, если вы измените приоритет правила на 2, когда у вас есть пять настраиваемых правил (с приоритетами от 0 до 4), то для существующего правила с приоритетом 2 будет задан приоритет 3, а для правила с приоритетом 3 будет задан приоритет 4.</span><span class="sxs-lookup"><span data-stu-id="ca773-p126">The highest priority value you can set on a rule is 0. The lowest value you can set depends on the number of rules. For example, if you have five rules, you can use the priority values 0 through 4. Changing the priority of an existing rule can have a cascading effect on other rules. For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="ca773-299">Чтобы установить приоритет правила безопасного вложения в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="ca773-299">To set the priority of a safe attachment rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="ca773-p127">В этом примере для правила Marketing Department задается приоритет 2. Все правила с приоритетом не больше 2 понижаются на один ранг (значения приоритета увеличиваются на 1).</span><span class="sxs-lookup"><span data-stu-id="ca773-p127">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="ca773-302">**Примечание.** Чтобы установить приоритет нового правила при его создании, используйте параметр _Priority_ в **комлете New-SafeAttachmentRule.**</span><span class="sxs-lookup"><span data-stu-id="ca773-302">**Note**: To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeAttachmentRule** cmdlet instead.</span></span>

<span data-ttu-id="ca773-303">Подробные сведения о синтаксисах и параметрах см. в [инструкции Set-SafeAttachmentRule.](/powershell/module/exchange/set-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="ca773-303">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-policies"></a><span data-ttu-id="ca773-304">Использование PowerShell для удаления политик безопасного вложения</span><span class="sxs-lookup"><span data-stu-id="ca773-304">Use PowerShell to remove safe attachment policies</span></span>

<span data-ttu-id="ca773-305">При удалении политики безопасного вложения с помощью PowerShell соответствующее правило безопасного вложения не удаляется.</span><span class="sxs-lookup"><span data-stu-id="ca773-305">When you use PowerShell to remove a safe attachment policy, the corresponding safe attachment rule isn't removed.</span></span>

<span data-ttu-id="ca773-306">Чтобы удалить политику безопасного вложения в PowerShell, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="ca773-306">To remove a safe attachment policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="ca773-307">В этом примере удаляется политика безопасного вложения с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="ca773-307">This example removes the safe attachment policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

<span data-ttu-id="ca773-308">Подробные сведения о синтаксисах и параметрах см. в [обзоре Remove-SafeAttachmentPolicy.](/powershell/module/exchange/remove-safeattachmentpolicy)</span><span class="sxs-lookup"><span data-stu-id="ca773-308">For detailed syntax and parameter information, see [Remove-SafeAttachmentPolicy](/powershell/module/exchange/remove-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-rules"></a><span data-ttu-id="ca773-309">Использование PowerShell для удаления правил безопасного вложения</span><span class="sxs-lookup"><span data-stu-id="ca773-309">Use PowerShell to remove safe attachment rules</span></span>

<span data-ttu-id="ca773-310">При удалении правила безопасного вложения с помощью PowerShell соответствующая политика безопасного вложения не удаляется.</span><span class="sxs-lookup"><span data-stu-id="ca773-310">When you use PowerShell to remove a safe attachment rule, the corresponding safe attachment policy isn't removed.</span></span>

<span data-ttu-id="ca773-311">Чтобы удалить правило безопасного вложения в PowerShell, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="ca773-311">To remove a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

<span data-ttu-id="ca773-312">В этом примере удаляется правило безопасного вложения с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="ca773-312">This example removes the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="ca773-313">Подробные сведения о синтаксисах и параметрах см. в [ссылке Remove-SafeAttachmentRule.](/powershell/module/exchange/remove-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="ca773-313">For detailed syntax and parameter information, see [Remove-SafeAttachmentRule](/powershell/module/exchange/remove-safeattachmentrule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="ca773-314">Как проверить, что эти процедуры выполнены?</span><span class="sxs-lookup"><span data-stu-id="ca773-314">How do you know these procedures worked?</span></span>

<span data-ttu-id="ca773-315">Чтобы убедиться, что вы успешно создали, изменили или Сейф политики вложений, сделайте все следующие действия:</span><span class="sxs-lookup"><span data-stu-id="ca773-315">To verify that you've successfully created, modified, or removed Safe Attachments policies, do any of the following steps:</span></span>

- <span data-ttu-id="ca773-316">На портале Microsoft 365 Defender перейдите к разделу Политики **совместной** & электронной почты & Политики правил политики угрозы Сейф \>  \>  \>  \> **Вложения .**</span><span class="sxs-lookup"><span data-stu-id="ca773-316">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Attachments**.</span></span> <span data-ttu-id="ca773-317">Проверка списка политик, их значений **состояния** и **их значений приоритета.**</span><span class="sxs-lookup"><span data-stu-id="ca773-317">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="ca773-318">Чтобы просмотреть дополнительные сведения, выберите политику из списка, нажав на имя, и просмотреть сведения в поле вылета.</span><span class="sxs-lookup"><span data-stu-id="ca773-318">To view more details, select the policy from the list by clicking on the name, and view the details in the fly out.</span></span>

- <span data-ttu-id="ca773-319">В Exchange Online PowerShell или Exchange Online Protection PowerShell замените имя политики или правила, запустите следующую команду и проверьте \<Name\> параметры:</span><span class="sxs-lookup"><span data-stu-id="ca773-319">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

<span data-ttu-id="ca773-320">Чтобы убедиться, Сейф вложения — это сканирование сообщений, проверьте доступные отчеты Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="ca773-320">To verify that Safe Attachments is scanning messages, check the available Defender for Office 365 reports.</span></span> <span data-ttu-id="ca773-321">Дополнительные сведения см. в обзоре отчетов [для Defender для](view-reports-for-mdo.md) Office 365 и Use Explorer на [портале Microsoft 365 Defender.](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="ca773-321">For more information, see [View reports for Defender for Office 365](view-reports-for-mdo.md) and [Use Explorer in the Microsoft 365 Defender portal](threat-explorer.md).</span></span>
