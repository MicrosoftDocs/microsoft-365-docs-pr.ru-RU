---
title: Настройка политик Сейф ссылок в Microsoft Defender для Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: Администраторы могут научиться просматривать, создавать, изменять и удалять Сейф ссылки и глобальные Сейф ссылки в Microsoft Defender для Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b4254d62cfa5844756392c00686e7b93c466d160
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2021
ms.locfileid: "53082760"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="e6939-103">Настройка политик Сейф ссылок в Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="e6939-103">Set up Safe Links policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e6939-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="e6939-104">**Applies to**</span></span>
- [<span data-ttu-id="e6939-105">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="e6939-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="e6939-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e6939-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="e6939-107">Эта статья предназначена для бизнес-клиентов, использующих [Microsoft Defender для Office 365](defender-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="e6939-107">This article is intended for business customers who have [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="e6939-108">Если вы домашний пользователь, который ищет сведения о Safelinks в Outlook, см. в [Outlook.com.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)</span><span class="sxs-lookup"><span data-stu-id="e6939-108">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="e6939-109">Сейф Ссылки в Microsoft Defender для Office 365 для сканирования [URL-адресов входящие](defender-for-office-365.md) сообщения электронной почты в потоке почты, а также время проверки URL-адресов и ссылок в сообщениях электронной почты и в других местах.</span><span class="sxs-lookup"><span data-stu-id="e6939-109">Safe Links in [Microsoft Defender for Office 365](defender-for-office-365.md) provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="e6939-110">Дополнительные сведения см. [в Сейф Ссылки в Microsoft Defender для Office 365.](safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="e6939-110">For more information, see [Safe Links in Microsoft Defender for Office 365](safe-links.md).</span></span>

<span data-ttu-id="e6939-111">Не существует политики встроенных или Сейф ссылок.</span><span class="sxs-lookup"><span data-stu-id="e6939-111">There's no built-in or default Safe Links policy.</span></span> <span data-ttu-id="e6939-112">Чтобы получить Сейф ссылки для сканирования URL-адресов, необходимо создать одну или несколько Сейф ссылок, как описано в этой статье.</span><span class="sxs-lookup"><span data-stu-id="e6939-112">To get Safe Links scanning of URLs, you need to create one or more Safe Links policies as described in this article.</span></span>

> [!NOTE]
>
> <span data-ttu-id="e6939-113">Вы настраивает глобальные параметры защиты Сейф **ссылок** за пределами политик Сейф ссылки.</span><span class="sxs-lookup"><span data-stu-id="e6939-113">You configure the global settings for Safe Links protection **outside** of Safe Links policies.</span></span> <span data-ttu-id="e6939-114">Инструкции см. в перенастройке глобальных [параметров для Сейф ссылок в Microsoft Defender для Office 365.](configure-global-settings-for-safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="e6939-114">For instructions, see [Configure global settings for Safe Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span></span>
>
> <span data-ttu-id="e6939-115">Администраторы должны учитывать различные параметры конфигурации для Сейф ссылки.</span><span class="sxs-lookup"><span data-stu-id="e6939-115">Admins should consider the different configuration settings for Safe Links.</span></span> <span data-ttu-id="e6939-116">Один из доступных вариантов — включить идентифицируемую пользователем информацию в Сейф Ссылки.</span><span class="sxs-lookup"><span data-stu-id="e6939-116">One of the available options is to include user identifiable information in Safe Links.</span></span> <span data-ttu-id="e6939-117">Эта функция позволяет *командам security Ops* исследовать потенциальный пользовательский компромисс, принимать меры по исправлению и ограничивать дорогостоящие нарушения.</span><span class="sxs-lookup"><span data-stu-id="e6939-117">This feature enables *Security Ops teams* to investigate potential user compromise, take corrective action, and limit costly breaches.</span></span>

<span data-ttu-id="e6939-118">Вы можете настроить политики Сейф Ссылки на портале Microsoft 365 Defender или в PowerShell (Exchange Online PowerShell для подходящих Microsoft 365 организаций с почтовыми ящиками в Exchange Online; автономные EOP PowerShell для организаций без Exchange Online почтовых ящиков, но с Microsoft Defender для Office 365 надстройки подписки).</span><span class="sxs-lookup"><span data-stu-id="e6939-118">You can configure Safe Links policies in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="e6939-119">Основные элементы политики Сейф ссылки:</span><span class="sxs-lookup"><span data-stu-id="e6939-119">The basic elements of a Safe Links policy are:</span></span>

- <span data-ttu-id="e6939-120">Политика безопасных ссылок: включайте защиту Сейф ссылок, включайте сканирование URL-адресов в режиме реального времени, укажите, следует ли ждать завершения сканирования в режиме реального времени перед доставкой сообщения, включить сканирование внутренних сообщений, указать, следует ли отслеживать клики пользователя по URL-адресам, а также указать, следует ли разрешить пользователям щелкнуть корыто на исходный URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="e6939-120">**The safe links policy**: Turn on Safe Links protection, turn on real-time URL scanning, specify whether to wait for real-time scanning to complete before delivering the message, turn on scanning for internal messages, specify whether to track user clicks on URLs, and specify whether to allow users to click trough to the original URL.</span></span>
- <span data-ttu-id="e6939-121">**Правило безопасных ссылок:** указывает фильтры приоритета и получателя (к кому применяется политика).</span><span class="sxs-lookup"><span data-stu-id="e6939-121">**The safe links rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="e6939-122">Разница между этими двумя элементами не очевидна при управлении Сейф ссылками на Microsoft 365 Defender портале:</span><span class="sxs-lookup"><span data-stu-id="e6939-122">The difference between these two elements isn't obvious when you manage Safe Links polices in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="e6939-123">При создании политики Сейф ссылки создается правило безопасных ссылок и связанная политика безопасных ссылок одновременно с использованием одного и того же имени для обоих.</span><span class="sxs-lookup"><span data-stu-id="e6939-123">When you create a Safe Links policy, you're actually creating a safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="e6939-124">При изменении политики Сейф ссылки параметры, связанные с именем, приоритетом, включенной или отключенной, а также фильтры получателей изменяют правило безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="e6939-124">When you modify a Safe Links policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe links rule.</span></span> <span data-ttu-id="e6939-125">Все остальные параметры изменяют связанную политику безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="e6939-125">All other settings modify the associated safe links policy.</span></span>
- <span data-ttu-id="e6939-126">При удалении политики Сейф ссылки правило безопасных ссылок и связанная политика безопасных ссылок удаляются.</span><span class="sxs-lookup"><span data-stu-id="e6939-126">When you remove a Safe Links policy, the safe links rule and the associated safe links policy are removed.</span></span>

<span data-ttu-id="e6939-127">В Exchange Online PowerShell или автономном EOP PowerShell вы управляете политикой и правилом отдельно.</span><span class="sxs-lookup"><span data-stu-id="e6939-127">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="e6939-128">Дополнительные сведения см. в разделе Использование Exchange Online PowerShell или автономный [EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) для настройки Сейф ссылок далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="e6939-128">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) section later in this article.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e6939-129">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="e6939-129">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e6939-130">Чтобы открыть портал Microsoft 365 Defender, перейдите на сайт <https://security.microsoft.com/>.</span><span class="sxs-lookup"><span data-stu-id="e6939-130">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="e6939-131">Чтобы перейти непосредственно **на страницу Сейф ссылки,** используйте <https://security.microsoft.com/safelinksv2> .</span><span class="sxs-lookup"><span data-stu-id="e6939-131">To go directly to the **Safe Links** page, use <https://security.microsoft.com/safelinksv2>.</span></span>

- <span data-ttu-id="e6939-132">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="e6939-132">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="e6939-133">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="e6939-133">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="e6939-134">Прежде чем делать процедуры в этой статье, необходимо получить соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="e6939-134">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="e6939-135">Чтобы создать, изменить и удалить политики Сейф ссылки, необходимо быть  членом групп  ролей управления организацией или администратором безопасности на  портале Microsoft 365 Defender и членом группы ролей управления организацией в Exchange Online. </span><span class="sxs-lookup"><span data-stu-id="e6939-135">To create, modify, and delete Safe Links policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Microsoft 365 Defender portal **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="e6939-136">Для доступа только для чтения к политикам Сейф ссылки необходимо быть членом групп ролей **Global Reader** или **Security Reader.**</span><span class="sxs-lookup"><span data-stu-id="e6939-136">For read-only access to Safe Links policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="e6939-137">Дополнительные сведения см. [в Microsoft 365 Defender](permissions-microsoft-365-security-center.md) и [разрешениях](/exchange/permissions-exo/permissions-exo)в Exchange Online .</span><span class="sxs-lookup"><span data-stu-id="e6939-137">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="e6939-138">Добавление пользователей к соответствующей роли Azure Active Directory в Центр администрирования Microsoft 365 дает пользователям необходимые разрешения на портале  Microsoft 365 Defender и разрешения на другие функции в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e6939-138">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="e6939-139">Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="e6939-139">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  <span data-ttu-id="e6939-140">.</span><span class="sxs-lookup"><span data-stu-id="e6939-140">.</span></span> <span data-ttu-id="e6939-141">— Группа **ролей для** управления только для просмотра организации в [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) также предоставляет доступ только для чтения к этой функции.</span><span class="sxs-lookup"><span data-stu-id="e6939-141">- The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="e6939-142">Рекомендуемые параметры для политик Сейф ссылки см. в Сейф [параметров политики ссылок.](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="e6939-142">For our recommended settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="e6939-143">Разрешить до 30 минут для новой или обновленной политики, которая будет применяться.</span><span class="sxs-lookup"><span data-stu-id="e6939-143">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="e6939-144">[Новые функции постоянно добавляются в Microsoft Defender для](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365)Office 365 .</span><span class="sxs-lookup"><span data-stu-id="e6939-144">[New features are continually being added to Microsoft Defender for Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="e6939-145">При добавлении новых функций может потребоваться внести изменения в существующие политики Сейф ссылки.</span><span class="sxs-lookup"><span data-stu-id="e6939-145">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-safe-links-policies"></a><span data-ttu-id="e6939-146">Используйте портал Microsoft 365 Defender для создания Сейф ссылок</span><span class="sxs-lookup"><span data-stu-id="e6939-146">Use the Microsoft 365 Defender portal to create Safe Links policies</span></span>

<span data-ttu-id="e6939-147">Создание настраиваемой политики Сейф ссылок на портале Microsoft 365 Defender создает правило безопасных ссылок и связанную политику безопасных ссылок одновременно с использованием одного и того же имени для обоих.</span><span class="sxs-lookup"><span data-stu-id="e6939-147">Creating a custom Safe Links policy in the Microsoft 365 Defender portal creates the safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="e6939-148">На портале Microsoft 365 Defender перейдите в раздел **Политики & правила** политики угрозы Сейф \>  \>  \> **ссылки**.</span><span class="sxs-lookup"><span data-stu-id="e6939-148">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="e6939-149">На странице **Сейф ссылки** нажмите ![ кнопку Создать значок ](../../media/m365-cc-sc-create-icon.png) **Создать**.</span><span class="sxs-lookup"><span data-stu-id="e6939-149">On the **Safe Links** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create**.</span></span>

3. <span data-ttu-id="e6939-150">Откроется **мастер политики Сейф** ссылки.</span><span class="sxs-lookup"><span data-stu-id="e6939-150">The **New Safe Links policy** wizard opens.</span></span> <span data-ttu-id="e6939-151">На странице **Имя политики** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="e6939-151">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="e6939-152">**Имя**. Укажите уникальное, описательное имя политики.</span><span class="sxs-lookup"><span data-stu-id="e6939-152">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="e6939-153">**Описание**. По желанию введите описание политики.</span><span class="sxs-lookup"><span data-stu-id="e6939-153">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="e6939-154">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e6939-154">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="e6939-155">На странице **Пользователи и домены,** которая отображается, определите внутренних получателей, к которых применяется политика (условия получателей):</span><span class="sxs-lookup"><span data-stu-id="e6939-155">On the **Users and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="e6939-156">**Пользователи**: указывает один или несколько почтовых ящиков, пользователей почты или почтовых контактов в организации.</span><span class="sxs-lookup"><span data-stu-id="e6939-156">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="e6939-157">**Группы**: указывает группы рассылки, группы безопасности с поддержкой почты или группы Microsoft 365 в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="e6939-157">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="e6939-158">**Домены**: все получатели в указанных [обслуживаемых доменах](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="e6939-158">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="e6939-159">Щелкните соответствующее поле, начните вводить значение и выберите нужное значение в результатах.</span><span class="sxs-lookup"><span data-stu-id="e6939-159">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="e6939-160">Повторите эти действия необходимое количество раз.</span><span class="sxs-lookup"><span data-stu-id="e6939-160">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="e6939-161">Чтобы удалить существующее значение, нажмите "Удалить".</span><span class="sxs-lookup"><span data-stu-id="e6939-161">To remove an existing value, click remove</span></span> ![Значок "Удалить"](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="e6939-163">рядом со значением.</span><span class="sxs-lookup"><span data-stu-id="e6939-163">next to the value.</span></span>

   <span data-ttu-id="e6939-164">Для пользователей и групп можно использовать большинство идентификаторов (имя, отображаемое имя, псевдоним, адрес электронной почты, имя учетной записи и т. д.), но в результатах будет выведено отображаемое имя.</span><span class="sxs-lookup"><span data-stu-id="e6939-164">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="e6939-165">Для получения списка всех пользователей введите звездочку (\*) без добавлений, чтобы увидеть все доступные значения.</span><span class="sxs-lookup"><span data-stu-id="e6939-165">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="e6939-166">Указать несколько значений в одном условии можно с помощью оператора OR (например, _\<recipient1\>_ or _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="e6939-166">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="e6939-167">Между разными условиями и исключениями используется оператор AND (например, _\<recipient1\>_ and _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="e6939-167">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="e6939-168">**Исключить этих пользователей, группы и домены**. Чтобы добавить исключения для внутренних получателей, к которым применяется политика (исключение получателей), выберите этот параметр и настройте исключения.</span><span class="sxs-lookup"><span data-stu-id="e6939-168">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="e6939-169">Настройки и поведение такие же, как в разделе условий.</span><span class="sxs-lookup"><span data-stu-id="e6939-169">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="e6939-170">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e6939-170">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="e6939-171">На странице **Параметры защиты,** которая появится, настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="e6939-171">On the **Protection settings** page that appears, configure the following settings:</span></span>
   - <span data-ttu-id="e6939-172">**Выберите действие для неизвестных** потенциально вредоносных URL-адресов в сообщениях: Выберите On, чтобы включить защиту Сейф ссылок для ссылок в сообщениях электронной почты. </span><span class="sxs-lookup"><span data-stu-id="e6939-172">**Select the action for unknown potentially malicious URLs in messages**: Select **On** to enable Safe Links protection for links in email messages.</span></span> <span data-ttu-id="e6939-173">Если включить этот параметр, доступны следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="e6939-173">If you turn this setting on, the following settings are available:</span></span>
     - <span data-ttu-id="e6939-174">**Применение сканирования URL-адресов** в режиме реального времени для подозрительных ссылок и ссылок, которые указывают на файлы: Выберите этот параметр, чтобы включить сканирование ссылок в электронной почте в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="e6939-174">**Apply real-time URL scanning for suspicious links and links that point to files**: Select this option to enable real-time scanning of links in email messages.</span></span> <span data-ttu-id="e6939-175">Если включить этот параметр в следующем параметре, можно:</span><span class="sxs-lookup"><span data-stu-id="e6939-175">If you turn this setting on the following setting is available:</span></span>
       - <span data-ttu-id="e6939-176">**Дождись завершения** сканирования URL-адресов перед доставкой сообщения. Выберите этот параметр, чтобы дождаться завершения сканирования URL-адресов в режиме реального времени перед доставкой сообщения.</span><span class="sxs-lookup"><span data-stu-id="e6939-176">**Wait for URL scanning to complete before delivering the message**: Select this option to wait for real-time URL scanning to complete before delivering the message.</span></span>
     - <span data-ttu-id="e6939-177">**Применение Сейф** ссылки на сообщения электронной почты, отправленные в организации: Выберите этот параметр, чтобы применить политику Сейф ссылок к сообщениям между внутренними отправителями и внутренними получателями.</span><span class="sxs-lookup"><span data-stu-id="e6939-177">**Apply Safe Links to email messages sent within the organization**: Select this option to apply the Safe Links policy to messages between internal senders and internal recipients.</span></span>
   - <span data-ttu-id="e6939-178">**Выберите действие для** неизвестных или потенциально вредоносных URL-адресов в Microsoft Teams : **Выберите** on, чтобы включить защиту Сейф ссылок для ссылок в Teams.</span><span class="sxs-lookup"><span data-stu-id="e6939-178">**Select the action for unknown or potentially malicious URLs within Microsoft Teams**: Select **On** to enable Safe Links protection for links in Teams.</span></span>
   - <span data-ttu-id="e6939-179">**Не отслеживайте щелчки** пользователя: оставьте этот параметр незасеченным, чтобы включить щелчки пользователя отслеживания url-адресов в сообщениях электронной почты.</span><span class="sxs-lookup"><span data-stu-id="e6939-179">**Do not track user clicks**: Leave this setting unselected to enable the tracking user clicks on URLs in email messages.</span></span>
   - <span data-ttu-id="e6939-180">**Не позволяйте пользователям** щелкнуть исходный URL-адрес: Выберите этот параметр, чтобы заблокировать доступ пользователей к исходному URL-адресу на страницах [с предупреждением.](safe-links.md#warning-pages-from-safe-links)</span><span class="sxs-lookup"><span data-stu-id="e6939-180">**Do not allow users to click through to original URL**: Select this option to block users from clicking through to the original URL in [warning pages](safe-links.md#warning-pages-from-safe-links).</span></span>
   - <span data-ttu-id="e6939-181">**Не переписать** следующие URL-адреса: разрешить доступ к указанным URL-адресам, которые в противном случае будут заблокированы Сейф ссылками.</span><span class="sxs-lookup"><span data-stu-id="e6939-181">**Do not rewrite the following URLs**: Allows access the specified URLs that would otherwise be blocked by Safe Links.</span></span>

     <span data-ttu-id="e6939-182">В поле введите URL-адрес или значение, которое необходимо, а затем нажмите **кнопку Добавить**.</span><span class="sxs-lookup"><span data-stu-id="e6939-182">In the box, type the URL or value that you want, and then click **Add**.</span></span> <span data-ttu-id="e6939-183">Повторите этот шаг нужное количество раз.</span><span class="sxs-lookup"><span data-stu-id="e6939-183">Repeat this step as many times as necessary.</span></span>

     <span data-ttu-id="e6939-184">Чтобы удалить существующую запись, нажмите кнопку</span><span class="sxs-lookup"><span data-stu-id="e6939-184">To remove an existing entry, click</span></span> ![Значок "Удалить"](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="e6939-186">рядом с записью.</span><span class="sxs-lookup"><span data-stu-id="e6939-186">next to the entry.</span></span>

     <span data-ttu-id="e6939-187">Синтаксис записи см. в синтаксис Записи в списке "Не переписать следующие [URL-адреса".](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="e6939-187">For entry syntax, see [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

   <span data-ttu-id="e6939-188">Подробные сведения об этих параметрах см. в [Сейф ссылки](safe-links.md#safe-links-settings-for-email-messages) на сообщения электронной почты и [Сейф ссылки для Microsoft Teams.](safe-links.md#safe-links-settings-for-microsoft-teams)</span><span class="sxs-lookup"><span data-stu-id="e6939-188">For detailed information about these settings, see [Safe Links settings for email messages](safe-links.md#safe-links-settings-for-email-messages) and [Safe Links settings for Microsoft Teams](safe-links.md#safe-links-settings-for-microsoft-teams).</span></span>

   <span data-ttu-id="e6939-189">Дополнительные рекомендуемые значения для параметров стандартной и строгой политики см. в [Сейф параметров политики ссылок.](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="e6939-189">For more the recommended values for Standard and Strict policy settings, see [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span></span>

   <span data-ttu-id="e6939-190">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e6939-190">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="e6939-191">На странице **Уведомление** выберите одно из следующих значений для **уведомления пользователей?**:</span><span class="sxs-lookup"><span data-stu-id="e6939-191">On the **Notification** page that appears, select one of the following values for **How would you like to notify your users?**:</span></span>
   - <span data-ttu-id="e6939-192">**Использование текста уведомления по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="e6939-192">**Use the default notification text**</span></span>
   - <span data-ttu-id="e6939-193">**Используйте настраиваемый текст уведомления.** Если выбрать это значение, появятся следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="e6939-193">**Use custom notification text**: If you select this value, the following settings appear:</span></span>
     - <span data-ttu-id="e6939-194">**Использование Переводчик Майкрософт для автоматической локализации**</span><span class="sxs-lookup"><span data-stu-id="e6939-194">**Use Microsoft Translator for automatic localization**</span></span>
     - <span data-ttu-id="e6939-195">**Пользовательский текст уведомления.** Введите пользовательский текст уведомления в этом поле.</span><span class="sxs-lookup"><span data-stu-id="e6939-195">**Custom notification text**: Enter the custom notification text in this box.</span></span>

   <span data-ttu-id="e6939-196">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e6939-196">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="e6939-197">На странице **Просмотр** просмотрите параметры.</span><span class="sxs-lookup"><span data-stu-id="e6939-197">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="e6939-198">Вы можете выбрать **Изменить** в любом разделе, чтобы изменить параметры в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="e6939-198">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="e6939-199">Вы также можете щелкнуть **Назад** или выбрать определенную страницу в мастере.</span><span class="sxs-lookup"><span data-stu-id="e6939-199">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="e6939-200">По завершению нажмите кнопку **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="e6939-200">When you're finished, click **Submit**.</span></span>

8. <span data-ttu-id="e6939-201">На странице подтверждения, которая откроется, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="e6939-201">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-safe-links-policies"></a><span data-ttu-id="e6939-202">Используйте портал Microsoft 365 Defender для просмотра Сейф ссылок</span><span class="sxs-lookup"><span data-stu-id="e6939-202">Use the Microsoft 365 Defender portal to view Safe Links policies</span></span>

1. <span data-ttu-id="e6939-203">На портале Microsoft 365 Defender перейдите в раздел **Политики & правила** политики угрозы Сейф \>  \>  \> **ссылки**.</span><span class="sxs-lookup"><span data-stu-id="e6939-203">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="e6939-204">На **странице Сейф ссылки** в списке политик Сейф ссылки отображаются следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="e6939-204">On the **Safe Links** page, the following properties are displayed in the list of Safe Links policies:</span></span>
   - <span data-ttu-id="e6939-205">**Имя**</span><span class="sxs-lookup"><span data-stu-id="e6939-205">**Name**</span></span>
   - <span data-ttu-id="e6939-206">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="e6939-206">**Status**</span></span>
   - <span data-ttu-id="e6939-207">**Приоритет**</span><span class="sxs-lookup"><span data-stu-id="e6939-207">**Priority**</span></span>

3. <span data-ttu-id="e6939-208">При выборе политики, щелкнув имя, параметры политики отображаются в вылете.</span><span class="sxs-lookup"><span data-stu-id="e6939-208">When you select a policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-safe-links-policies"></a><span data-ttu-id="e6939-209">Используйте портал Microsoft 365 Defender для изменения Сейф ссылок</span><span class="sxs-lookup"><span data-stu-id="e6939-209">Use the Microsoft 365 Defender portal to modify Safe Links policies</span></span>

1. <span data-ttu-id="e6939-210">На портале Microsoft 365 Defender перейдите в раздел **Политики & правила** политики угрозы Сейф \>  \>  \> **ссылки**.</span><span class="sxs-lookup"><span data-stu-id="e6939-210">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="e6939-211">На странице **Сейф ссылки** выберите политику из списка, нажав на имя.</span><span class="sxs-lookup"><span data-stu-id="e6939-211">On the **Safe Links** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="e6939-212">Параметры политики будут показаны во всплывающем окне. Вы можете выбрать **Изменить** в любом разделе, чтобы изменить параметры в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="e6939-212">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="e6939-213">Дополнительные сведения о параметрах см. в предыдущем разделе Использование портала Microsoft 365 Defender для создания [Сейф](#use-the-microsoft-365-defender-portal-to-create-safe-links-policies) ссылок в этой статье.</span><span class="sxs-lookup"><span data-stu-id="e6939-213">For more information about the settings, see the previous [Use the Microsoft 365 Defender portal to create Safe Links policies](#use-the-microsoft-365-defender-portal-to-create-safe-links-policies) section in this article.</span></span>  

<span data-ttu-id="e6939-214">Чтобы включить или отключить политику или установить порядок приоритета политики, см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="e6939-214">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-links-policies"></a><span data-ttu-id="e6939-215">Включить или отключить Сейф ссылки</span><span class="sxs-lookup"><span data-stu-id="e6939-215">Enable or disable Safe Links policies</span></span>

1. <span data-ttu-id="e6939-216">На портале Microsoft 365 Defender перейдите в раздел Политики **совместной** & электронной почты & политики угрозы Сейф \>  \>  \>  \> **ссылки**.</span><span class="sxs-lookup"><span data-stu-id="e6939-216">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="e6939-217">На странице **Сейф ссылки** выберите политику из списка, нажав на имя.</span><span class="sxs-lookup"><span data-stu-id="e6939-217">On the **Safe Links** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="e6939-218">Появится всплывающее окно со сведениями о политике. В верхней его части вы увидите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="e6939-218">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="e6939-219">**Политика отключена**. Чтобы включить политику, щелкните значок !["Включить"](../../media/m365-cc-sc-turn-on-off-icon.png) **Включить** .</span><span class="sxs-lookup"><span data-stu-id="e6939-219">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="e6939-220">**Политика включена**. Чтобы выключить политику, щелкните значок !["Отключить"](../../media/m365-cc-sc-turn-on-off-icon.png) **Отключить**.</span><span class="sxs-lookup"><span data-stu-id="e6939-220">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="e6939-221">В диалоговом окне подтверждения нажмите кнопку **Включить** или **Отключить**.</span><span class="sxs-lookup"><span data-stu-id="e6939-221">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="e6939-222">Во всплывающем окне сведений о политике нажмите **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="e6939-222">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="e6939-223">Когда вы вернетесь на главную страницу политики, значение параметра **Состояние** этой политики будет **Включена** или **Выключена**.</span><span class="sxs-lookup"><span data-stu-id="e6939-223">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-safe-links-policies"></a><span data-ttu-id="e6939-224">Установите приоритет политик Сейф ссылки</span><span class="sxs-lookup"><span data-stu-id="e6939-224">Set the priority of Safe Links policies</span></span>

<span data-ttu-id="e6939-225">По умолчанию Сейф ссылки имеют приоритет, основанный на порядке, в который они были созданы (более новые политики имеют более низкий приоритет по сравнению с более старыми политиками).</span><span class="sxs-lookup"><span data-stu-id="e6939-225">By default, Safe Links are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="e6939-226">Чем ниже значение, тем выше приоритет политики (0 — наивысший приоритет), а порядок обработки политик зависит от их приоритетов (политики с высоким приоритетом обрабатываются раньше, чем политики с низким приоритетом).</span><span class="sxs-lookup"><span data-stu-id="e6939-226">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="e6939-227">Никакие две политики не могут иметь одинаковый приоритет, и обработка политики прекращается после применения первой политики.</span><span class="sxs-lookup"><span data-stu-id="e6939-227">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="e6939-228">Чтобы изменить приоритет политики, нажмите кнопку **Увеличить приоритет** или **Уменьшить приоритет** в свойствах политики (вы не можете напрямую изменить числовое значение параметра **Приоритет** на портале Microsoft 365 Defender).</span><span class="sxs-lookup"><span data-stu-id="e6939-228">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Microsoft 365 Defender portal).</span></span> <span data-ttu-id="e6939-229">Изменение приоритета политики имеет смысл, только если у вас несколько политик.</span><span class="sxs-lookup"><span data-stu-id="e6939-229">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

<span data-ttu-id="e6939-230">**Примечание.**</span><span class="sxs-lookup"><span data-stu-id="e6939-230">**Note**:</span></span>

- <span data-ttu-id="e6939-231">На портале Microsoft 365 Defender можно изменить приоритет политики Сейф ссылок после ее создания.</span><span class="sxs-lookup"><span data-stu-id="e6939-231">In the Microsoft 365 Defender portal, you can only change the priority of the Safe Links policy after you create it.</span></span> <span data-ttu-id="e6939-232">В PowerShell можно переопредить приоритет по умолчанию при создании правила безопасных ссылок (которое может повлиять на приоритет существующих правил).</span><span class="sxs-lookup"><span data-stu-id="e6939-232">In PowerShell, you can override the default priority when you create the safe links rule (which can affect the priority of existing rules).</span></span>
- <span data-ttu-id="e6939-233">Сейф Политики ссылок обрабатываются в порядке отображения (первая политика имеет значение **Priority** 0).</span><span class="sxs-lookup"><span data-stu-id="e6939-233">Safe Links policies are processed in the order that they're displayed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="e6939-234">Дополнительные сведения о приоритетах, а также оценке и применении нескольких политик см. в статье [Порядок и приоритет защиты электронной почты](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="e6939-234">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

1. <span data-ttu-id="e6939-235">На портале Microsoft 365 Defender перейдите в раздел Политики **совместной** & электронной почты & политики угрозы Сейф \>  \>  \>  \> **ссылки**.</span><span class="sxs-lookup"><span data-stu-id="e6939-235">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="e6939-236">На странице **Сейф ссылки** выберите политику из списка, нажав на имя.</span><span class="sxs-lookup"><span data-stu-id="e6939-236">On the **Safe Links** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="e6939-237">Появится всплывающее окно со сведениями о политике. В верхней его части вы увидите одно из следующих значений: **Увеличить приоритет** или **Уменьшить приоритет** в зависимости от текущего значения приоритета и количества настраиваемых политик:</span><span class="sxs-lookup"><span data-stu-id="e6939-237">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of custom policies:</span></span>
   - <span data-ttu-id="e6939-238">Политика со **значением Приоритет** **0** имеет только доступный параметр **Приоритет уменьшения.**</span><span class="sxs-lookup"><span data-stu-id="e6939-238">The policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="e6939-239">Политика с наименьшим **значением** Приоритет (например, **3)** имеет только доступный параметр **Increase priority.**</span><span class="sxs-lookup"><span data-stu-id="e6939-239">The policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="e6939-240">Если у вас есть три или более политик, политики между самыми высокими и самыми низкими значениями приоритетов имеют доступные параметры **приоритета Increase** и **Decrease.**</span><span class="sxs-lookup"><span data-stu-id="e6939-240">If you have three or more policies, the policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="e6939-241">Щелкните ![Значок увеличения приоритета](../../media/m365-cc-sc-increase-icon.png) **Увеличить приоритет** или ![Значок уменьшения приоритета](../../media/m365-cc-sc-decrease-icon.png) **Уменьшить приоритет** чтобы изменить значение параметра **Приоритет**.</span><span class="sxs-lookup"><span data-stu-id="e6939-241">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="e6939-242">Закончив, нажмите **Закрыть** во всплывающем окне сведений о политике.</span><span class="sxs-lookup"><span data-stu-id="e6939-242">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-safe-links-policies"></a><span data-ttu-id="e6939-243">Использование портала Microsoft 365 Defender для удаления Сейф ссылок</span><span class="sxs-lookup"><span data-stu-id="e6939-243">Use the Microsoft 365 Defender portal to remove Safe Links policies</span></span>

1. <span data-ttu-id="e6939-244">На портале Microsoft 365 Defender перейдите в раздел Политики **совместной** & электронной почты & политики угрозы Сейф \>  \>  \>  \> **ссылки**.</span><span class="sxs-lookup"><span data-stu-id="e6939-244">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="e6939-245">На странице **Сейф ссылки** выберите политику из списка, нажав на имя.</span><span class="sxs-lookup"><span data-stu-id="e6939-245">On the **Safe Links** page, select a policy from the list by clicking on the name.</span></span> <span data-ttu-id="e6939-246">В открывшемся всплывающем окне сведений о политике щелкните ![значок "Дополнительные действия"](../../media/m365-cc-sc-more-actions-icon.png) **Дополнительные действия** \> ![значок "Удалить политику"](../../media/m365-cc-sc-delete-icon.png) **Удалить политику**.</span><span class="sxs-lookup"><span data-stu-id="e6939-246">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

3. <span data-ttu-id="e6939-247">В диалоговом окне подтверждения нажмите **Да**.</span><span class="sxs-lookup"><span data-stu-id="e6939-247">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a><span data-ttu-id="e6939-248">Для настройки Сейф ссылок используйте Exchange Online PowerShell или автономный EOP PowerShell</span><span class="sxs-lookup"><span data-stu-id="e6939-248">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies</span></span>

<span data-ttu-id="e6939-249">Как описано выше, политика Сейф ссылок состоит из политики безопасных ссылок и правила безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="e6939-249">As previously described, a Safe Links policy consists of a safe links policy and a safe links rule.</span></span>

<span data-ttu-id="e6939-250">В PowerShell очевидна разница между политиками безопасных ссылок и правилами безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="e6939-250">In PowerShell, the difference between safe links policies and safe links rules is apparent.</span></span> <span data-ttu-id="e6939-251">Вы управляете политиками безопасных ссылок с помощью **\* кодлетов -SafeLinksPolicy** и управляете правилами безопасных ссылок с помощью **\* cmdlets-SafeLinksRule.**</span><span class="sxs-lookup"><span data-stu-id="e6939-251">You manage safe links policies by using the **\*-SafeLinksPolicy** cmdlets, and you manage safe links rules by using the **\*-SafeLinksRule** cmdlets.</span></span>

- <span data-ttu-id="e6939-252">В PowerShell сначала создается политика безопасных ссылок, а затем создается правило безопасных ссылок, которое определяет политику, к которую применяется правило.</span><span class="sxs-lookup"><span data-stu-id="e6939-252">In PowerShell, you create the safe links policy first, then you create the safe links rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="e6939-253">В PowerShell параметры политики безопасных ссылок и правила безопасных ссылок изменяются отдельно.</span><span class="sxs-lookup"><span data-stu-id="e6939-253">In PowerShell, you modify the settings in the safe links policy and the safe links rule separately.</span></span>
- <span data-ttu-id="e6939-254">При удалении политики безопасных ссылок из PowerShell соответствующее правило безопасных ссылок не удаляется автоматически, и наоборот.</span><span class="sxs-lookup"><span data-stu-id="e6939-254">When you remove a safe links policy from PowerShell, the corresponding safe links rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-links-policies"></a><span data-ttu-id="e6939-255">Использование PowerShell для создания Сейф ссылок</span><span class="sxs-lookup"><span data-stu-id="e6939-255">Use PowerShell to create Safe Links policies</span></span>

<span data-ttu-id="e6939-256">Создание политики Сейф ссылок в PowerShell — это двухшаговая процедура:</span><span class="sxs-lookup"><span data-stu-id="e6939-256">Creating a Safe Links policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="e6939-257">Создание политики безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="e6939-257">Create the safe links policy.</span></span>
2. <span data-ttu-id="e6939-258">Создайте правило безопасных ссылок, которое указывает политику безопасных ссылок, к которую применяется правило.</span><span class="sxs-lookup"><span data-stu-id="e6939-258">Create the safe links rule that specifies the safe links policy that the rule applies to.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="e6939-259">Можно создать новое правило безопасных ссылок и назначить к ней существующую политику безопасных ссылок без связи.</span><span class="sxs-lookup"><span data-stu-id="e6939-259">You can create a new safe links rule and assign an existing, unassociated safe links policy to it.</span></span> <span data-ttu-id="e6939-260">Правило безопасных ссылок не может быть связано с более чем одной политикой безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="e6939-260">A safe links rule can't be associated with more than one safe links policy.</span></span>
>
> - <span data-ttu-id="e6939-261">Вы можете настроить следующие параметры для новых политик безопасных ссылок в PowerShell, недоступных на портале Microsoft 365 Defender до создания политики:</span><span class="sxs-lookup"><span data-stu-id="e6939-261">You can configure the following settings on new safe links policies in PowerShell that aren't available in the Microsoft 365 Defender portal until after you create the policy:</span></span>
>   - <span data-ttu-id="e6939-262">Создайте новую политику как отключенную _(включена_ `$false` в **комлете New-SafeLinksRule).**</span><span class="sxs-lookup"><span data-stu-id="e6939-262">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeLinksRule** cmdlet).</span></span>
>   - <span data-ttu-id="e6939-263">Задай приоритет политики во время создания _(priority)_ в _\<Number\>_ **комлете New-SafeLinksRule.**</span><span class="sxs-lookup"><span data-stu-id="e6939-263">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeLinksRule** cmdlet).</span></span>
>
> - <span data-ttu-id="e6939-264">Новая политика безопасных ссылок, которую вы создаете в PowerShell, не отображается на портале Microsoft 365 Defender, пока не назначите политику правилу безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="e6939-264">A new safe links policy that you create in PowerShell isn't visible in the Microsoft 365 Defender portal until you assign the policy to a safe links rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a><span data-ttu-id="e6939-265">Шаг 1. Использование PowerShell для создания политики безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="e6939-265">Step 1: Use PowerShell to create a safe links policy</span></span>

<span data-ttu-id="e6939-266">Чтобы создать политику безопасных ссылок, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="e6939-266">To create a safe links policy, use this syntax:</span></span>

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

> [!NOTE]
>
> - <span data-ttu-id="e6939-267">Подробные сведения о синтаксисе записи, используемом для параметра _DoNotRewriteUrls,_ см. в материале Запись синтаксиса для списка "Не переписывай следующие [URL-адреса".](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="e6939-267">For details about the entry syntax to use for the _DoNotRewriteUrls_ parameter, see [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>
>
> - <span data-ttu-id="e6939-268">Дополнительный синтаксис, который можно использовать для параметра _DoNotRewriteUrls_ при изменении существующих политик безопасных ссылок с помощью комлета **Set-SafeLinksPolicy,** см. в разделе [Использование PowerShell](#use-powershell-to-modify-safe-links-policies) для изменения политик безопасных ссылок в этой статье.</span><span class="sxs-lookup"><span data-stu-id="e6939-268">For additional syntax that you can use for the _DoNotRewriteUrls_ parameter when you modify existing safe links policies by using the **Set-SafeLinksPolicy** cmdlet, see the [Use PowerShell to modify safe links policies](#use-powershell-to-modify-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="e6939-269">В этом примере создается политика безопасных ссылок с именем Contoso All со следующими значениями:</span><span class="sxs-lookup"><span data-stu-id="e6939-269">This example creates a safe links policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="e6939-270">Включайте сканирование URL-адресов и переписывание в сообщениях электронной почты.</span><span class="sxs-lookup"><span data-stu-id="e6939-270">Turn on URL scanning and rewriting in email messages.</span></span>
- <span data-ttu-id="e6939-271">Включив сканирование URL Teams в режиме Teams (только для предварительного просмотра TAP).</span><span class="sxs-lookup"><span data-stu-id="e6939-271">Turn on URL scanning in Teams (TAP Preview only).</span></span>
- <span data-ttu-id="e6939-272">Включайте сканирование url-адресов в режиме реального времени, в том числе щелкнув ссылки, которые указывают на файлы.</span><span class="sxs-lookup"><span data-stu-id="e6939-272">Turn on real-time scanning of clicked URLs, including clicked links that point to files.</span></span>
- <span data-ttu-id="e6939-273">Дождись завершения сканирования URL-адресов перед доставкой сообщения.</span><span class="sxs-lookup"><span data-stu-id="e6939-273">Wait for URL scanning to complete before delivering the message.</span></span>
- <span data-ttu-id="e6939-274">Включи сканирование URL-адресов и переописывание внутренних сообщений.</span><span class="sxs-lookup"><span data-stu-id="e6939-274">Turn on URL scanning and rewriting for internal messages.</span></span>
- <span data-ttu-id="e6939-275">Отслеживайте щелчки пользователей, связанные с защитой Сейф ссылок (мы не используем параметр _DoNotTrackUserClicks,_ а значение по умолчанию $false, что означает отслеживание кликов пользователей).</span><span class="sxs-lookup"><span data-stu-id="e6939-275">Track user clicks related to Safe Links protection (we aren't using the _DoNotTrackUserClicks_ parameter, and the default value is $false, which means user clicks are tracked).</span></span>
- <span data-ttu-id="e6939-276">Не позволяйте пользователям щелкнуть исходный URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="e6939-276">Do not allow users to click through to the original URL.</span></span>

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

<span data-ttu-id="e6939-277">Подробные сведения о синтаксисах и параметрах см. [в обзоре New-SafeLinksPolicy.](/powershell/module/exchange/new-safelinkspolicy)</span><span class="sxs-lookup"><span data-stu-id="e6939-277">For detailed syntax and parameter information, see [New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a><span data-ttu-id="e6939-278">Шаг 2. Использование PowerShell для создания правила безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="e6939-278">Step 2: Use PowerShell to create a safe links rule</span></span>

<span data-ttu-id="e6939-279">Чтобы создать правило безопасных ссылок, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="e6939-279">To create a safe links rule, use this syntax:</span></span>

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="e6939-280">В этом примере создается правило безопасных ссылок с именем Contoso All со следующими условиями:</span><span class="sxs-lookup"><span data-stu-id="e6939-280">This example creates a safe links rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="e6939-281">Правило связано с политикой безопасных ссылок с именем Contoso All.</span><span class="sxs-lookup"><span data-stu-id="e6939-281">The rule is associated with the safe links policy named Contoso All.</span></span>
- <span data-ttu-id="e6939-282">Правило применяется ко всем получателям в contoso.com домене.</span><span class="sxs-lookup"><span data-stu-id="e6939-282">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="e6939-283">Так как мы не используем параметр _Priority,_ используется приоритет по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e6939-283">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="e6939-284">Правило включено (мы не используем параметр _Включен,_ а значение по `$true` умолчанию).</span><span class="sxs-lookup"><span data-stu-id="e6939-284">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="e6939-285">Подробные сведения о синтаксисах и параметрах см. [в обзоре New-SafeLinksRule.](/powershell/module/exchange/new-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="e6939-285">For detailed syntax and parameter information, see [New-SafeLinksRule](/powershell/module/exchange/new-safelinksrule).</span></span>

### <a name="use-powershell-to-view-safe-links-policies"></a><span data-ttu-id="e6939-286">Использование PowerShell для просмотра политик безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="e6939-286">Use PowerShell to view safe links policies</span></span>

<span data-ttu-id="e6939-287">Чтобы просмотреть существующие политики безопасных ссылок, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="e6939-287">To view existing safe links policies, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="e6939-288">В этом примере возвращается сводный список всех политик безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="e6939-288">This example returns a summary list of all safe links policies.</span></span>

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

<span data-ttu-id="e6939-289">В этом примере возвращаются подробные сведения о политике безопасных ссылок с именем Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="e6939-289">This example returns detailed information for the safe links policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

<span data-ttu-id="e6939-290">Подробные сведения о синтаксисах и параметрах см. в [обзоре Get-SafeLinksPolicy.](/powershell/module/exchange/get-safelinkspolicy)</span><span class="sxs-lookup"><span data-stu-id="e6939-290">For detailed syntax and parameter information, see [Get-SafeLinksPolicy](/powershell/module/exchange/get-safelinkspolicy).</span></span>

### <a name="use-powershell-to-view-safe-links-rules"></a><span data-ttu-id="e6939-291">Использование PowerShell для просмотра правил безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="e6939-291">Use PowerShell to view safe links rules</span></span>

<span data-ttu-id="e6939-292">Чтобы просмотреть существующие правила безопасных ссылок, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="e6939-292">To view existing safe links rules, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="e6939-293">В этом примере возвращается сводный список всех правил безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="e6939-293">This example returns a summary list of all safe links rules.</span></span>

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

<span data-ttu-id="e6939-294">Чтобы отфильтровать список по включенным или отключенным правилам, выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="e6939-294">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

<span data-ttu-id="e6939-295">В этом примере возвращается подробная информация для правила безопасных ссылок с именем Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="e6939-295">This example returns detailed information for the safe links rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

<span data-ttu-id="e6939-296">Подробные сведения о синтаксисах и параметрах см. в [обзоре Get-SafeLinksRule.](/powershell/module/exchange/get-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="e6939-296">For detailed syntax and parameter information, see [Get-SafeLinksRule](/powershell/module/exchange/get-safelinksrule).</span></span>

### <a name="use-powershell-to-modify-safe-links-policies"></a><span data-ttu-id="e6939-297">Использование PowerShell для изменения политик безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="e6939-297">Use PowerShell to modify safe links policies</span></span>

<span data-ttu-id="e6939-298">В PowerShell нельзя переименовать политику безопасных ссылок (в **комлете Set-SafeLinksPolicy** нет _параметра Name)._</span><span class="sxs-lookup"><span data-stu-id="e6939-298">You can't rename a safe links policy in PowerShell (the **Set-SafeLinksPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="e6939-299">При переименовании политики Сейф ссылок на портале Microsoft 365 Defender вы только переименовывать правило безопасных _ссылок._</span><span class="sxs-lookup"><span data-stu-id="e6939-299">When you rename a Safe Links policy in the Microsoft 365 Defender portal, you're only renaming the safe links _rule_.</span></span>

<span data-ttu-id="e6939-300">Единственным дополнительным фактором для изменения политик безопасных ссылок в PowerShell является доступный синтаксис для параметра _DoNotRewriteUrls_ (список "Не переписать следующие [URL-адреса"):](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)</span><span class="sxs-lookup"><span data-stu-id="e6939-300">The only additional consideration for modifying safe links policies in PowerShell is the available syntax for the _DoNotRewriteUrls_ parameter (the ["Do not rewrite the following URLs" list](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span></span>

- <span data-ttu-id="e6939-301">Чтобы добавить значения, которые заменят существующие записи, используйте следующий синтаксис: `"Entry1","Entry2,..."EntryN"` .</span><span class="sxs-lookup"><span data-stu-id="e6939-301">To add values that will replace any existing entries, use the following syntax: `"Entry1","Entry2,..."EntryN"`.</span></span>
- <span data-ttu-id="e6939-302">Чтобы добавить или удалить значения, не затрагивая другие существующие записи, используйте следующий синтаксис: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span><span class="sxs-lookup"><span data-stu-id="e6939-302">To add or remove values without affecting other existing entries, use the following syntax: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span></span>

<span data-ttu-id="e6939-303">В противном случае те же параметры доступны при создании политики безопасных ссылок, как описано в шаге [1: Использование PowerShell](#step-1-use-powershell-to-create-a-safe-links-policy) для создания раздела политики безопасных ссылок ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="e6939-303">Otherwise, the same settings are available when you create a safe links policy as described in the [Step 1: Use PowerShell to create a safe links policy](#step-1-use-powershell-to-create-a-safe-links-policy) section earlier in this article.</span></span>

<span data-ttu-id="e6939-304">Чтобы изменить политику безопасных ссылок, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="e6939-304">To modify a safe links policy, use this syntax:</span></span>

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="e6939-305">Подробные сведения о синтаксисах и параметрах см. в [инструкции Set-SafeLinksPolicy.](/powershell/module/exchange/set-safelinkspolicy)</span><span class="sxs-lookup"><span data-stu-id="e6939-305">For detailed syntax and parameter information, see [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy).</span></span>

### <a name="use-powershell-to-modify-safe-links-rules"></a><span data-ttu-id="e6939-306">Использование PowerShell для изменения правил безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="e6939-306">Use PowerShell to modify safe links rules</span></span>

<span data-ttu-id="e6939-307">Единственным параметром, недоступным при изменении правила безопасных ссылок  в PowerShell, является параметр Включен, который позволяет создать правило отключения.</span><span class="sxs-lookup"><span data-stu-id="e6939-307">The only setting that's not available when you modify a safe links rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="e6939-308">Чтобы включить или отключить существующие правила безопасных ссылок, см. в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="e6939-308">To enable or disable existing safe links rules, see the next section.</span></span>

<span data-ttu-id="e6939-309">В противном случае те же параметры доступны при создании правила, описанного в шаге [2: Использование PowerShell](#step-2-use-powershell-to-create-a-safe-links-rule) для создания раздела правила безопасных ссылок в начале этой статьи.</span><span class="sxs-lookup"><span data-stu-id="e6939-309">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe links rule](#step-2-use-powershell-to-create-a-safe-links-rule) section earlier in this article.</span></span>

<span data-ttu-id="e6939-310">Чтобы изменить правило безопасных ссылок, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="e6939-310">To modify a safe links rule, use this syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="e6939-311">Подробные сведения о синтаксисах и параметрах см. в [инструкции Set-SafeLinksRule.](/powershell/module/exchange/set-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="e6939-311">For detailed syntax and parameter information, see [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a><span data-ttu-id="e6939-312">Использование PowerShell для включения или отключения правил безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="e6939-312">Use PowerShell to enable or disable safe links rules</span></span>

<span data-ttu-id="e6939-313">Включение или отключение правила безопасных ссылок в PowerShell включает или отключает всю политику Сейф ссылок (правило безопасных ссылок и назначенную политику безопасных ссылок).</span><span class="sxs-lookup"><span data-stu-id="e6939-313">Enabling or disabling a safe links rule in PowerShell enables or disables the whole Safe Links policy (the safe links rule and the assigned safe links policy).</span></span>

<span data-ttu-id="e6939-314">Чтобы включить или отключить правило безопасных ссылок в PowerShell, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="e6939-314">To enable or disable a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

<span data-ttu-id="e6939-315">В этом примере отключает правило безопасных ссылок с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="e6939-315">This example disables the safe links rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="e6939-316">В этом примере включается то же правило.</span><span class="sxs-lookup"><span data-stu-id="e6939-316">This example enables same rule.</span></span>

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="e6939-317">Подробные сведения о синтаксисах и параметрах см. в [рублях Enable-SafeLinksRule](/powershell/module/exchange/enable-safelinksrule) и [Disable-SafeLinksRule.](/powershell/module/exchange/disable-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="e6939-317">For detailed syntax and parameter information, see [Enable-SafeLinksRule](/powershell/module/exchange/enable-safelinksrule) and [Disable-SafeLinksRule](/powershell/module/exchange/disable-safelinksrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a><span data-ttu-id="e6939-318">Используйте PowerShell, чтобы установить приоритет правил безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="e6939-318">Use PowerShell to set the priority of safe links rules</span></span>

<span data-ttu-id="e6939-p131">Максимальный приоритет, который можно задать для правила, — 0. Минимальное значение зависит от количества правил. Например, если у вас есть пять правил, вы можете использовать значения 0-4. Изменение приоритета существующего правила оказывает каскадное влияние на другие правила. Например, если вы измените приоритет правила на 2, когда у вас есть пять настраиваемых правил (с приоритетами от 0 до 4), то для существующего правила с приоритетом 2 будет задан приоритет 3, а для правила с приоритетом 3 будет задан приоритет 4.</span><span class="sxs-lookup"><span data-stu-id="e6939-p131">The highest priority value you can set on a rule is 0. The lowest value you can set depends on the number of rules. For example, if you have five rules, you can use the priority values 0 through 4. Changing the priority of an existing rule can have a cascading effect on other rules. For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="e6939-324">Чтобы установить приоритет правила безопасных ссылок в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="e6939-324">To set the priority of a safe links rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="e6939-p132">В этом примере для правила Marketing Department задается приоритет 2. Все правила с приоритетом не больше 2 понижаются на один ранг (значения приоритета увеличиваются на 1).</span><span class="sxs-lookup"><span data-stu-id="e6939-p132">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
> <span data-ttu-id="e6939-327">Чтобы установить приоритет нового правила при его создании, используйте параметр _Priority_ в **комлете New-SafeLinksRule.**</span><span class="sxs-lookup"><span data-stu-id="e6939-327">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeLinksRule** cmdlet instead.</span></span>

<span data-ttu-id="e6939-328">Подробные сведения о синтаксисах и параметрах см. в [инструкции Set-SafeLinksRule.](/powershell/module/exchange/set-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="e6939-328">For detailed syntax and parameter information, see [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-remove-safe-links-policies"></a><span data-ttu-id="e6939-329">Использование PowerShell для удаления политик безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="e6939-329">Use PowerShell to remove safe links policies</span></span>

<span data-ttu-id="e6939-330">При удалении политики безопасных ссылок с помощью PowerShell соответствующее правило безопасных ссылок не удаляется.</span><span class="sxs-lookup"><span data-stu-id="e6939-330">When you use PowerShell to remove a safe links policy, the corresponding safe links rule isn't removed.</span></span>

<span data-ttu-id="e6939-331">Чтобы удалить политику безопасных ссылок в PowerShell, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="e6939-331">To remove a safe links policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="e6939-332">В этом примере удаляется политика безопасных ссылок с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="e6939-332">This example removes the safe links policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

<span data-ttu-id="e6939-333">Подробные сведения о синтаксисах и параметрах см. в этой ссылке [Remove-SafeLinksPolicy.](/powershell/module/exchange/remove-safelinkspolicy)</span><span class="sxs-lookup"><span data-stu-id="e6939-333">For detailed syntax and parameter information, see [Remove-SafeLinksPolicy](/powershell/module/exchange/remove-safelinkspolicy).</span></span>

### <a name="use-powershell-to-remove-safe-links-rules"></a><span data-ttu-id="e6939-334">Использование PowerShell для удаления правил безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="e6939-334">Use PowerShell to remove safe links rules</span></span>

<span data-ttu-id="e6939-335">При удалении правила безопасных ссылок с помощью PowerShell соответствующая политика безопасных ссылок не удаляется.</span><span class="sxs-lookup"><span data-stu-id="e6939-335">When you use PowerShell to remove a safe links rule, the corresponding safe links policy isn't removed.</span></span>

<span data-ttu-id="e6939-336">Чтобы удалить правило безопасных ссылок в PowerShell, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="e6939-336">To remove a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

<span data-ttu-id="e6939-337">В этом примере удаляется правило безопасных ссылок с именем Отдел маркетинга.</span><span class="sxs-lookup"><span data-stu-id="e6939-337">This example removes the safe links rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="e6939-338">Подробные сведения о синтаксисах и параметрах см. в [ссылке Remove-SafeLinksRule.](/powershell/module/exchange/remove-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="e6939-338">For detailed syntax and parameter information, see [Remove-SafeLinksRule](/powershell/module/exchange/remove-safelinksrule).</span></span>

<span data-ttu-id="e6939-339">Чтобы убедиться, Сейф ссылки — это сканирование сообщений, проверьте доступные microsoft Defender для Office 365 отчетов.</span><span class="sxs-lookup"><span data-stu-id="e6939-339">To verify that Safe Links is scanning messages, check the available Microsoft Defender for Office 365 reports.</span></span> <span data-ttu-id="e6939-340">Дополнительные сведения см. в обзоре отчетов [для Defender для](view-reports-for-mdo.md) Office 365 и Use Explorer на [портале Microsoft 365 Defender.](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="e6939-340">For more information, see [View reports for Defender for Office 365](view-reports-for-mdo.md) and [Use Explorer in the Microsoft 365 Defender portal](threat-explorer.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="e6939-341">Как проверить, что эти процедуры выполнены?</span><span class="sxs-lookup"><span data-stu-id="e6939-341">How do you know these procedures worked?</span></span>

<span data-ttu-id="e6939-342">Чтобы убедиться, что вы успешно создали, изменили или удалили Сейф ссылки, сделайте все следующие действия:</span><span class="sxs-lookup"><span data-stu-id="e6939-342">To verify that you've successfully created, modified, or removed Safe Links policies, do any of the following steps:</span></span>

- <span data-ttu-id="e6939-343">На портале Microsoft 365 Defender перейдите к **политикам & правил** политики \>  \> **угрозы Сейф ссылки**.</span><span class="sxs-lookup"><span data-stu-id="e6939-343">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat policies** \> **Safe Links**.</span></span> <span data-ttu-id="e6939-344">Проверка списка политик, их значений **состояния** и **их значений приоритета.**</span><span class="sxs-lookup"><span data-stu-id="e6939-344">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="e6939-345">Чтобы просмотреть дополнительные сведения, выберите политику из списка и просмотреть сведения в поле вылета.</span><span class="sxs-lookup"><span data-stu-id="e6939-345">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="e6939-346">В Exchange Online PowerShell или Exchange Online Protection PowerShell замените имя политики или правила, запустите следующую команду и проверьте \<Name\> параметры:</span><span class="sxs-lookup"><span data-stu-id="e6939-346">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
