---
title: Настройка политик безопасных ссылок в Microsoft Defender для Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: Администраторы могут узнать, как просматривать, создавать, изменять и удалять политики безопасных ссылок и глобальные параметры безопасных ссылок в Microsoft Defender для Office 365.
ms.openlocfilehash: 7a00b73855302f5046afa0605fd7188007394ed7
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683167"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="557af-103">Настройка политик безопасных ссылок в Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="557af-103">Set up Safe Links policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="557af-104">Эта статья предназначена для бизнес-клиентов, использующих [Microsoft Defender для Office 365](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="557af-104">This article is intended for business customers who have [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="557af-105">Если вы — домашний пользователь, который ищет сведения о безопасных ссылках в Outlook, см. дополнительные Outlook.com [безопасности.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)</span><span class="sxs-lookup"><span data-stu-id="557af-105">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="557af-106">Функция "Безопасные ссылки" — это функция в Microsoft Defender для [Office 365,](office-365-atp.md) которая обеспечивает сканирование URL-адресов входящие сообщения электронной почты в потоке почты и время проверки URL-адресов и ссылок в сообщениях электронной почты и других расположениях.</span><span class="sxs-lookup"><span data-stu-id="557af-106">Safe Links is a feature in [Microsoft Defender for Office 365](office-365-atp.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="557af-107">Дополнительные сведения см. в [веб-сайте "Безопасные ссылки" в Microsoft Defender для Office 365.](atp-safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="557af-107">For more information, see [Safe Links in Microsoft Defender for Office 365](atp-safe-links.md).</span></span>

<span data-ttu-id="557af-108">Встроенная или стандартная политика безопасных ссылок не существует.</span><span class="sxs-lookup"><span data-stu-id="557af-108">There's no built-in or default Safe Links policy.</span></span> <span data-ttu-id="557af-109">Чтобы получить возможность сканирования URL-адресов с проверкой безопасных ссылок, необходимо создать одну или несколько политик безопасных ссылок, как описано в этой статье.</span><span class="sxs-lookup"><span data-stu-id="557af-109">To get Safe Links scanning of URLs, you need to create one or more Safe Links policies as described in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="557af-110">Глобальные параметры защиты безопасных ссылок настраиваются за **пределами** политик безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="557af-110">You configure the global settings for Safe Links protection **outside** of Safe Links policies.</span></span> <span data-ttu-id="557af-111">Инструкции см. в подстройке "Настройка глобальных параметров безопасных [ссылок" в Microsoft Defender для Office 365.](configure-global-settings-for-safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="557af-111">For instructions, see [Configure global settings for Safe Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span></span>

<span data-ttu-id="557af-112">Политики безопасных ссылок можно настроить в Центре безопасности & и соответствия требованиям или в PowerShell (Exchange Online PowerShell для соответствующих организаций Microsoft 365 с почтовыми ящиками в Exchange Online; автономный EOP PowerShell для организаций без почтовых ящиков Exchange Online, но с подписками на надстройки Microsoft Defender для Office 365).</span><span class="sxs-lookup"><span data-stu-id="557af-112">You can configure Safe Links policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="557af-113">Основные элементы политики безопасных ссылок:</span><span class="sxs-lookup"><span data-stu-id="557af-113">The basic elements of a Safe Links policy are:</span></span>

- <span data-ttu-id="557af-114">Политика безопасных ссылок: включить защиту безопасных ссылок, включить сканирование URL-адресов в режиме реального времени, указать, следует ли дождаться завершения сканирования в режиме реального времени перед доставкой сообщения, включить проверку внутренних сообщений, указать, следует ли отслеживать щелчки URL-адресов пользователями, а также разрешить ли пользователям нажимать ссылку на исходный URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="557af-114">**The safe links policy**: Turn on Safe Links protection, turn on real-time URL scanning, specify whether to wait for real-time scanning to complete before delivering the message, turn on scanning for internal messages, specify whether to track user clicks on URLs, and specify whether to allow users to click trough to the original URL.</span></span>
- <span data-ttu-id="557af-115">**Правило безопасных ссылок:** определяет приоритет и фильтры получателей (к кому применяется политика).</span><span class="sxs-lookup"><span data-stu-id="557af-115">**The safe links rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="557af-116">Разница между этими двумя элементами не очевидна при управлении политиками безопасных ссылок в Центре безопасности & соответствия требованиям:</span><span class="sxs-lookup"><span data-stu-id="557af-116">The difference between these two elements isn't obvious when you manage Safe Links polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="557af-117">При создании политики безопасных ссылок фактически создается правило безопасных ссылок и связанная с ней политика безопасных ссылок одновременно с использованием одного и того же имени для обоих.</span><span class="sxs-lookup"><span data-stu-id="557af-117">When you create a Safe Links policy, you're actually creating a safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="557af-118">При изменении политики безопасных ссылок параметры, связанные с именем, приоритетом, включенным или отключенным фильтрами получателей, изменяют правило безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="557af-118">When you modify a Safe Links policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe links rule.</span></span> <span data-ttu-id="557af-119">Все остальные параметры изменяют связанную политику безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="557af-119">All other settings modify the associated safe links policy.</span></span>
- <span data-ttu-id="557af-120">При удалении политики безопасных ссылок удаляется правило безопасных ссылок и связанная с ней политика безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="557af-120">When you remove a Safe Links policy, the safe links rule and the associated safe links policy are removed.</span></span>

<span data-ttu-id="557af-121">В Exchange Online PowerShell или автономном EOP PowerShell вы управляете политикой и правилом отдельно.</span><span class="sxs-lookup"><span data-stu-id="557af-121">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="557af-122">Дополнительные сведения см. в разделе "Использование Exchange Online PowerShell или автономный [EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) для настройки политик безопасных ссылок" далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="557af-122">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) section later in this article.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="557af-123">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="557af-123">What do you need to know before you begin?</span></span>

- <span data-ttu-id="557af-124">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="557af-124">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="557af-125">Чтобы перейти непосредственно на страницу **"Безопасные ссылки",** используйте <https://protection.office.com/safelinksv2> .</span><span class="sxs-lookup"><span data-stu-id="557af-125">To go directly to the **Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="557af-126">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="557af-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="557af-127">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="557af-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="557af-128">Для выполнения процедур, описанных в этой статье, вам должны быть назначены разрешения в Центре безопасности и соответствия требованиям:</span><span class="sxs-lookup"><span data-stu-id="557af-128">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="557af-129">Для создания, изменения и удаления политик безопасных ссылок необходимо  быть членом группы ролей "Управление организацией" или "Администратор **безопасности".**</span><span class="sxs-lookup"><span data-stu-id="557af-129">To create, modify, and delete Safe Links policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="557af-130">Для доступа только для чтения к политикам безопасных ссылок необходимо  быть членом группы ролей **"Глобальный** читатель" или "Читатель безопасности".</span><span class="sxs-lookup"><span data-stu-id="557af-130">For read-only access to Safe Links policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="557af-131">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="557af-131">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="557af-132">**Примечания**.</span><span class="sxs-lookup"><span data-stu-id="557af-132">**Notes**:</span></span>

  - <span data-ttu-id="557af-133">Добавление пользователей в соответствующую роль Azure Active Directory в Центре безопасности Microsoft 365 предоставляет пользователям необходимые разрешения в Центре безопасности и соответствия требованиям _и_ разрешения для других функций в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="557af-133">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="557af-134">Дополнительные сведения см. в статье [О ролях администраторов](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="557af-134">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="557af-135">Группа ролей **Управление организацией с правами только на просмотр** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) также предоставляет доступ только для чтения к этой функции.</span><span class="sxs-lookup"><span data-stu-id="557af-135">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="557af-136">Рекомендуемые параметры политик безопасных ссылок см. в параметрах [политики безопасных ссылок.](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="557af-136">For our recommended settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="557af-137">Позволяет применять новую или обновленную политику в течение 30 минут.</span><span class="sxs-lookup"><span data-stu-id="557af-137">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="557af-138">[Новые функции постоянно добавляются в Microsoft Defender для Office 365.](office-365-atp.md#new-features-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="557af-138">[New features are continually being added to Microsoft Defender for Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="557af-139">При добавлении новых функций может потребоваться внести изменения в существующие политики безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="557af-139">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-links-policies"></a><span data-ttu-id="557af-140">Использование Центра безопасности & соответствия требованиям для создания политик безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="557af-140">Use the Security & Compliance Center to create Safe Links policies</span></span>

<span data-ttu-id="557af-141">При создании настраиваемой политики безопасных ссылок в Центре безопасности & соответствия требованиям одновременно создаются правило безопасных ссылок и связанная политика безопасных ссылок с одинаковым именем для обоих этих ссылок.</span><span class="sxs-lookup"><span data-stu-id="557af-141">Creating a custom Safe Links policy in the Security & Compliance Center creates the safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="557af-142">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span><span class="sxs-lookup"><span data-stu-id="557af-142">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="557af-143">На странице **"Безопасные ссылки"** нажмите кнопку **"Создать".**</span><span class="sxs-lookup"><span data-stu-id="557af-143">On the **Safe Links** page, click **Create**.</span></span>

3. <span data-ttu-id="557af-144">Откроется **мастер новой политики безопасных** ссылок.</span><span class="sxs-lookup"><span data-stu-id="557af-144">The **New Safe Links policy** wizard opens.</span></span> <span data-ttu-id="557af-145">На странице **"Имя политики"** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="557af-145">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="557af-146">**Имя**. Укажите уникальное, понятное имя политики.</span><span class="sxs-lookup"><span data-stu-id="557af-146">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="557af-147">**Описание**. Укажите необязательное описание политики.</span><span class="sxs-lookup"><span data-stu-id="557af-147">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="557af-148">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="557af-148">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="557af-149">На странице **"Параметры"** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="557af-149">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="557af-150">**Выберите действие для неизвестных потенциально вредоносных** URL-адресов в сообщениях: выберите "Включить", чтобы включить защиту безопасных ссылок для ссылок в сообщениях электронной почты. </span><span class="sxs-lookup"><span data-stu-id="557af-150">**Select the action for unknown potentially malicious URLs in messages**: Select **On** to enable Safe Links protection for links in email messages.</span></span>

   - <span data-ttu-id="557af-151">**Выберите действие для неизвестных или потенциально вредоносных**  URL-адресов в Microsoft Teams: выберите "Включить", чтобы включить защиту безопасных ссылок для ссылок в Teams.</span><span class="sxs-lookup"><span data-stu-id="557af-151">**Select the action for unknown or potentially malicious URLs within Microsoft Teams**: Select **On** to enable Safe Links protection for links in Teams.</span></span>

   - <span data-ttu-id="557af-152">**Применяет сканирование URL-адресов в** режиме реального времени для подозрительных ссылок и ссылок, которые указывают на файлы: выберите этот параметр, чтобы включить сканирование ссылок в сообщениях электронной почты в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="557af-152">**Apply real-time URL scanning for suspicious links and links that point to files**: Select this setting to enable real-time scanning of links in email messages.</span></span>

   - <span data-ttu-id="557af-153">**Дождись завершения проверки** URL-адресов перед доставкой сообщения: выберите этот параметр, чтобы дождаться завершения сканирования URL-адресов в режиме реального времени перед доставкой сообщения.</span><span class="sxs-lookup"><span data-stu-id="557af-153">**Wait for URL scanning to complete before delivering the message**: Select this setting to wait for real-time URL scanning to complete before delivering the message.</span></span>

   - <span data-ttu-id="557af-154">**Применение безопасных ссылок** к электронным письмам, отправленным в организации: выберите этот параметр, чтобы применить политику безопасных ссылок к сообщениям между внутренними и внутренними получателями.</span><span class="sxs-lookup"><span data-stu-id="557af-154">**Apply Safe Links to email messages sent within the organization**: Select this setting to apply the Safe Links policy to messages between internal senders and internal recipients.</span></span>

   - <span data-ttu-id="557af-155">**Не отслеживайте щелчки пользователей:** оставьте этот параметр невыбранным, чтобы пользователь отслеживания щелкнул URL-адреса в сообщениях электронной почты.</span><span class="sxs-lookup"><span data-stu-id="557af-155">**Do not track user clicks**: Leave this setting unselected to enable the tracking user clicks on URLs in email messages.</span></span>

   - <span data-ttu-id="557af-156">**Не разрешайте пользователям перебирать** исходный URL-адрес: выберите этот параметр, чтобы пользователи не перебирали исходный URL-адрес на страницах [предупреждений.](atp-safe-links.md#warning-pages-from-safe-links)</span><span class="sxs-lookup"><span data-stu-id="557af-156">**Do not allow users to click through to original URL**: Select this setting to block users from clicking through to the original URL in [warning pages](atp-safe-links.md#warning-pages-from-safe-links).</span></span>

   - <span data-ttu-id="557af-157">**Не переописывание следующих** URL-адресов: разрешает доступ к указанным URL-адресам, которые в противном случае были бы заблокированы с помощью безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="557af-157">**Do not rewrite the following URLs**: Allows access the specified URLs that would otherwise be blocked by Safe Links.</span></span>

     <span data-ttu-id="557af-158">В поле введите нужный URL-адрес или значение, а затем нажмите кнопку</span><span class="sxs-lookup"><span data-stu-id="557af-158">In the box, type the URL or value that you want, and then click</span></span> ![Значок "Добавить кнопку"](../../media/ITPro-EAC-AddIcon.png)<span data-ttu-id="557af-160">.</span><span class="sxs-lookup"><span data-stu-id="557af-160">.</span></span>

     <span data-ttu-id="557af-161">Чтобы удалить существующую запись, выберите ее и нажмите кнопку</span><span class="sxs-lookup"><span data-stu-id="557af-161">To remove an existing entry, select it and then click</span></span> ![Значок кнопки "Удалить"](../../media/ITPro-EAC-DeleteIcon.png)<span data-ttu-id="557af-163">.</span><span class="sxs-lookup"><span data-stu-id="557af-163">.</span></span>

     <span data-ttu-id="557af-164">Синтаксис записей см. в синтаксис записи в списке ["Не переописывать следующие URL-адреса".](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="557af-164">For entry syntax, see [Entry syntax for the "Do not rewrite the following URLs" list](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

   <span data-ttu-id="557af-165">Подробные сведения об этих [](atp-safe-links.md#safe-links-settings-for-email-messages) параметрах см. в параметрах безопасных ссылок для сообщений электронной почты и параметрах безопасных ссылок [для Microsoft Teams.](atp-safe-links.md#safe-links-settings-for-microsoft-teams)</span><span class="sxs-lookup"><span data-stu-id="557af-165">For detailed information about these settings, see [Safe Links settings for email messages](atp-safe-links.md#safe-links-settings-for-email-messages) and [Safe Links settings for Microsoft Teams](atp-safe-links.md#safe-links-settings-for-microsoft-teams).</span></span>

   <span data-ttu-id="557af-166">Дополнительные рекомендуемые значения для параметров политики Standard и Strict см. в параметрах [политики безопасных ссылок.](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="557af-166">For more the recommended values for Standard and Strict policy settings, see [Safe Links policy settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span></span>

   <span data-ttu-id="557af-167">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="557af-167">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="557af-168">На странице **"Применено к"** определите внутренних получателей, к которые применяется политика.</span><span class="sxs-lookup"><span data-stu-id="557af-168">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="557af-169">Условие или исключение можно использовать только один раз, но можно указать для них несколько значений.</span><span class="sxs-lookup"><span data-stu-id="557af-169">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="557af-170">Указать несколько значений в одном условии или исключении можно с помощью оператора OR (например, _\<recipient1\>_ or _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="557af-170">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="557af-171">Между разными условиями и исключениями используется оператор AND (например, _\<recipient1\>_ and _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="557af-171">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="557af-172">Нажмите **кнопку "Добавить условие".**</span><span class="sxs-lookup"><span data-stu-id="557af-172">Click **Add a condition**.</span></span> <span data-ttu-id="557af-173">В отобраложенном выпадаемом окном выберите условие в области **"Применено", если:**</span><span class="sxs-lookup"><span data-stu-id="557af-173">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="557af-174">**Получатель:** указывает один или несколько почтовых ящиков, почтовых пользователей или почтовых контактов в организации.</span><span class="sxs-lookup"><span data-stu-id="557af-174">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="557af-175">**Получатель является членом**: указывает одну или несколько групп в организации.</span><span class="sxs-lookup"><span data-stu-id="557af-175">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="557af-176">**Домен получателя**: Указывает получателей в одном или нескольких настроенных принятых доменов в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="557af-176">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="557af-177">После выбора условия появится соответствующее dropdown с любым **из этих полей.**</span><span class="sxs-lookup"><span data-stu-id="557af-177">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="557af-178">Щелкните поле и прокрутите список выбранных значений.</span><span class="sxs-lookup"><span data-stu-id="557af-178">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="557af-179">Щелкните поле и начните вводить текст, чтобы отфильтровать список и выбрать значение.</span><span class="sxs-lookup"><span data-stu-id="557af-179">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="557af-180">Чтобы добавить дополнительные значения, щелкните пустую область в поле.</span><span class="sxs-lookup"><span data-stu-id="557af-180">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="557af-181">Чтобы удалить отдельные записи, **щелкните значок "Удалить** ![ удалить" ](../../media/scc-remove-icon.png) в значении.</span><span class="sxs-lookup"><span data-stu-id="557af-181">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="557af-182">Чтобы удалить все условие, щелкните **значок "Удалить** ![ удалить" ](../../media/scc-remove-icon.png) в этом условии.</span><span class="sxs-lookup"><span data-stu-id="557af-182">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="557af-183">Чтобы добавить дополнительное условие, нажмите кнопку **"Добавить условие"** и выберите оставшееся значение **в области "Применено", если**.</span><span class="sxs-lookup"><span data-stu-id="557af-183">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="557af-184">Чтобы добавить исключения, нажмите **кнопку "Добавить условие"** и выберите исключение в области **"Кроме случаев, когда"**.</span><span class="sxs-lookup"><span data-stu-id="557af-184">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="557af-185">Параметры и поведение полностью идентичны условиям.</span><span class="sxs-lookup"><span data-stu-id="557af-185">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="557af-186">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="557af-186">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="557af-187">На странице **"Просмотр параметров"** просмотрите параметры.</span><span class="sxs-lookup"><span data-stu-id="557af-187">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="557af-188">Вы можете нажать **кнопку "Изменить"** для каждого параметра, чтобы изменить его.</span><span class="sxs-lookup"><span data-stu-id="557af-188">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="557af-189">Закончив, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="557af-189">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-links-policies"></a><span data-ttu-id="557af-190">Использование Центра безопасности & соответствия требованиям для просмотра политик безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="557af-190">Use the Security & Compliance Center to view Safe Links policies</span></span>

1. <span data-ttu-id="557af-191">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span><span class="sxs-lookup"><span data-stu-id="557af-191">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="557af-192">На странице **"Безопасные ссылки"** выберите политику в списке и щелкните ее (не выбирайте этот контроль).</span><span class="sxs-lookup"><span data-stu-id="557af-192">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="557af-193">Сведения о политике отображаются во внешнем поле</span><span class="sxs-lookup"><span data-stu-id="557af-193">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-links-policies"></a><span data-ttu-id="557af-194">Использование Центра безопасности & соответствия требованиям для изменения политик безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="557af-194">Use the Security & Compliance Center to modify Safe Links policies</span></span>

1. <span data-ttu-id="557af-195">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span><span class="sxs-lookup"><span data-stu-id="557af-195">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="557af-196">На странице **"Безопасные ссылки"** выберите политику в списке и щелкните ее (не выбирайте этот контроль).</span><span class="sxs-lookup"><span data-stu-id="557af-196">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="557af-197">В появились сведения о политике, нажмите кнопку **"Изменить политику".**</span><span class="sxs-lookup"><span data-stu-id="557af-197">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="557af-198">Доступные параметры во время выполнения идентичны тем, которые описаны в разделе "Использование центра безопасности [&](#use-the-security--compliance-center-to-create-safe-links-policies) соответствия требованиям для создания политик безопасных ссылок".</span><span class="sxs-lookup"><span data-stu-id="557af-198">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Links policies](#use-the-security--compliance-center-to-create-safe-links-policies) section.</span></span>

<span data-ttu-id="557af-199">Чтобы включить или отключить политику или установить порядок приоритетов политики, см. следующие разделы.</span><span class="sxs-lookup"><span data-stu-id="557af-199">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-links-policies"></a><span data-ttu-id="557af-200">Включить или отключить политики безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="557af-200">Enable or disable Safe Links policies</span></span>

1. <span data-ttu-id="557af-201">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span><span class="sxs-lookup"><span data-stu-id="557af-201">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="557af-202">Обратите внимание на значение в **столбце "Состояние":**</span><span class="sxs-lookup"><span data-stu-id="557af-202">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="557af-203">Чтобы отключить политику, переместите переключатель влево:</span><span class="sxs-lookup"><span data-stu-id="557af-203">Move the toggle to the left to disable the policy:</span></span> ![Отключение политики](../../media/scc-toggle-off.png)<span data-ttu-id="557af-205">.</span><span class="sxs-lookup"><span data-stu-id="557af-205">.</span></span>

   - <span data-ttu-id="557af-206">Чтобы включить политику, переместите переключатель вправо:</span><span class="sxs-lookup"><span data-stu-id="557af-206">Move the toggle to the right to enable the policy:</span></span> ![Включить политику](../../media/scc-toggle-on.png)<span data-ttu-id="557af-208">.</span><span class="sxs-lookup"><span data-stu-id="557af-208">.</span></span>

### <a name="set-the-priority-of-safe-links-policies"></a><span data-ttu-id="557af-209">Настройка приоритета политик безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="557af-209">Set the priority of Safe Links policies</span></span>

<span data-ttu-id="557af-210">По умолчанию политикам безопасных ссылок предоставляется приоритет, основанный на порядке их создания (приоритет новых политик ниже, чем у старых).</span><span class="sxs-lookup"><span data-stu-id="557af-210">By default, Safe Links policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="557af-211">Чем ниже значение, тем выше приоритет политики (0 — наивысший приоритет), а порядок обработки политик зависит от их приоритетов (политики с высоким приоритетом обрабатываются раньше, чем политики с низким приоритетом).</span><span class="sxs-lookup"><span data-stu-id="557af-211">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="557af-212">Никакие две политики не могут иметь одинаковый приоритет, и обработка политики прекращается после применения первой политики.</span><span class="sxs-lookup"><span data-stu-id="557af-212">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="557af-213">Дополнительные сведения о приоритетах, а также оценке и применении нескольких политик см. в статье [Порядок и приоритет защиты электронной почты](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="557af-213">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="557af-214">Политики безопасных ссылок отображаются в порядке их обработки (первая политика имеет значение **приоритета** 0).</span><span class="sxs-lookup"><span data-stu-id="557af-214">Safe Links policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

<span data-ttu-id="557af-215">**Примечание.** В Центре & соответствия требованиям приоритет политики безопасных ссылок можно изменить только после ее создания.</span><span class="sxs-lookup"><span data-stu-id="557af-215">**Note**: In the Security & Compliance Center, you can only change the priority of the Safe Links policy after you create it.</span></span> <span data-ttu-id="557af-216">В PowerShell можно переопредить приоритет по умолчанию при создании правила безопасных ссылок (которое может повлиять на приоритет существующих правил).</span><span class="sxs-lookup"><span data-stu-id="557af-216">In PowerShell, you can override the default priority when you create the safe links rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="557af-217">Чтобы изменить приоритет политики, переместите ее вверх или вниз в списке (в Центре безопасности и соответствия требованиям невозможно напрямую изменить значение свойства **Приоритет**).</span><span class="sxs-lookup"><span data-stu-id="557af-217">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="557af-218">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span><span class="sxs-lookup"><span data-stu-id="557af-218">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="557af-219">На странице **"Безопасные ссылки"** выберите политику в списке и щелкните ее (не выбирайте этот контроль).</span><span class="sxs-lookup"><span data-stu-id="557af-219">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="557af-220">В появились сведения о политике, нажмите доступную кнопку приоритета:</span><span class="sxs-lookup"><span data-stu-id="557af-220">In the policy details fly out that appears, click the available priority button:</span></span>

   - <span data-ttu-id="557af-221">В политике безопасных ссылок со **значением** приоритета **0** доступна только кнопка **"Уменьшить приоритет".**</span><span class="sxs-lookup"><span data-stu-id="557af-221">The Safe Links policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="557af-222">В политике безопасных ссылок с наименьшим **значением** приоритета (например, **3)** доступна только кнопка "Увеличить **приоритет".**</span><span class="sxs-lookup"><span data-stu-id="557af-222">The Safe Links policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="557af-223">Если у вас есть три или более политик безопасных ссылок, политики между  значениями  с самым высоким и низким приоритетом имеют доступные кнопки "Увеличить приоритет" и "Уменьшить приоритет".</span><span class="sxs-lookup"><span data-stu-id="557af-223">If you have three or more Safe Links policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="557af-224">Нажмите **кнопку "Увеличить приоритет"** или **"Уменьшить приоритет",** чтобы изменить **значение приоритета.**</span><span class="sxs-lookup"><span data-stu-id="557af-224">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="557af-225">Когда закончите, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="557af-225">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-links-policies"></a><span data-ttu-id="557af-226">Удаление политик безопасных & с помощью Центра безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="557af-226">Use the Security & Compliance Center to remove Safe Links policies</span></span>

1. <span data-ttu-id="557af-227">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span><span class="sxs-lookup"><span data-stu-id="557af-227">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="557af-228">На странице **"Безопасные ссылки"** выберите политику в списке и щелкните ее (не выбирайте этот контроль).</span><span class="sxs-lookup"><span data-stu-id="557af-228">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="557af-229">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span><span class="sxs-lookup"><span data-stu-id="557af-229">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a><span data-ttu-id="557af-230">Настройка политик безопасных ссылок с помощью Exchange Online PowerShell или автономных EOP PowerShell</span><span class="sxs-lookup"><span data-stu-id="557af-230">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies</span></span>

<span data-ttu-id="557af-231">Как было описано выше, политика безопасных ссылок состоит из политики безопасных ссылок и правила безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="557af-231">As previously described, a Safe Links policy consists of a safe links policy and a safe links rule.</span></span>

<span data-ttu-id="557af-232">В PowerShell разница между политиками безопасных ссылок и правилами безопасных ссылок очевидна.</span><span class="sxs-lookup"><span data-stu-id="557af-232">In PowerShell, the difference between safe links policies and safe links rules is apparent.</span></span> <span data-ttu-id="557af-233">Вы управляете политиками безопасных ссылок с помощью cmdlets **\* -SafeLinksPolicy,** а правила безопасных ссылок — с помощью **\* -SafeLinksRule.**</span><span class="sxs-lookup"><span data-stu-id="557af-233">You manage safe links policies by using the **\*-SafeLinksPolicy** cmdlets, and you manage safe links rules by using the **\*-SafeLinksRule** cmdlets.</span></span>

- <span data-ttu-id="557af-234">В PowerShell сначала создается политика безопасных ссылок, а затем правило безопасных ссылок, определяя политику, к которую применяется правило.</span><span class="sxs-lookup"><span data-stu-id="557af-234">In PowerShell, you create the safe links policy first, then you create the safe links rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="557af-235">В PowerShell параметры политики безопасных ссылок и правила безопасных ссылок изменяются отдельно.</span><span class="sxs-lookup"><span data-stu-id="557af-235">In PowerShell, you modify the settings in the safe links policy and the safe links rule separately.</span></span>
- <span data-ttu-id="557af-236">При удалении политики безопасных ссылок из PowerShell соответствующее правило безопасных ссылок не удаляется автоматически и наоборот.</span><span class="sxs-lookup"><span data-stu-id="557af-236">When you remove a safe links policy from PowerShell, the corresponding safe links rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-links-policies"></a><span data-ttu-id="557af-237">Создание политик безопасных ссылок с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="557af-237">Use PowerShell to create Safe Links policies</span></span>

<span data-ttu-id="557af-238">Создание политики безопасных ссылок в PowerShell — это двухшаговая процедура:</span><span class="sxs-lookup"><span data-stu-id="557af-238">Creating a Safe Links policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="557af-239">Создайте политику безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="557af-239">Create the safe links policy.</span></span>
2. <span data-ttu-id="557af-240">Создайте правило безопасных ссылок, которое определяет политику безопасных ссылок, к которую применяется правило.</span><span class="sxs-lookup"><span data-stu-id="557af-240">Create the safe links rule that specifies the safe links policy that the rule applies to.</span></span>

 <span data-ttu-id="557af-241">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="557af-241">**Notes**:</span></span>

- <span data-ttu-id="557af-242">Можно создать новое правило безопасных ссылок и назначить ему существующую несвязаную политику безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="557af-242">You can create a new safe links rule and assign an existing, unassociated safe links policy to it.</span></span> <span data-ttu-id="557af-243">Правило безопасных ссылок не может быть связано с более чем одной политикой безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="557af-243">A safe links rule can't be associated with more than one safe links policy.</span></span>

- <span data-ttu-id="557af-244">Вы можете настроить следующие параметры для новых политик безопасных ссылок в PowerShell, которые недоступны в Центре безопасности & соответствия требованиям, пока не создайте политику:</span><span class="sxs-lookup"><span data-stu-id="557af-244">You can configure the following settings on new safe links policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="557af-245">Создайте новую политику как отключенную _(включена_ `$false` в **cmdlet New-SafeLinksRule).**</span><span class="sxs-lookup"><span data-stu-id="557af-245">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeLinksRule** cmdlet).</span></span>
  - <span data-ttu-id="557af-246">Установите приоритет политики во время создания _(Priority)_ в _\<Number\>_ **cmdlet New-SafeLinksRule).**</span><span class="sxs-lookup"><span data-stu-id="557af-246">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeLinksRule** cmdlet).</span></span>

- <span data-ttu-id="557af-247">Новая политика безопасных ссылок, которую вы создаете в PowerShell, не отображается в Центре безопасности & соответствия требованиям, пока вы не назначите политику правилу безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="557af-247">A new safe links policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe links rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a><span data-ttu-id="557af-248">Шаг 1. Создание политики безопасных ссылок с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="557af-248">Step 1: Use PowerShell to create a safe links policy</span></span>

<span data-ttu-id="557af-249">Чтобы создать политику безопасных ссылок, используйте синтаксис:</span><span class="sxs-lookup"><span data-stu-id="557af-249">To create a safe links policy, use this syntax:</span></span>

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

<span data-ttu-id="557af-250">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="557af-250">**Notes**:</span></span>

- <span data-ttu-id="557af-251">Подробные сведения о синтаксисе записи, используемом для параметра _DoNotRewriteUrls,_ см. в синтаксис записи для списка "Не переописывать следующие [URL-адреса".](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="557af-251">For details about the entry syntax to use for the _DoNotRewriteUrls_ parameter, see [Entry syntax for the "Do not rewrite the following URLs" list](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

- <span data-ttu-id="557af-252">Дополнительный синтаксис, который можно использовать для параметра _DoNotRewriteUrls_ при изменении существующих политик безопасных ссылок с помощью cmdlet **Set-SafeLinksPolicy,** см. в разделе "Использование [PowerShell](#use-powershell-to-modify-safe-links-policies) для изменения политик безопасных ссылок" далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="557af-252">For additional syntax that you can use for the _DoNotRewriteUrls_ parameter when you modify existing safe links policies by using the **Set-SafeLinksPolicy** cmdlet, see the [Use PowerShell to modify safe links policies](#use-powershell-to-modify-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="557af-253">В этом примере создается политика безопасных ссылок с именем Contoso All со следующими значениями:</span><span class="sxs-lookup"><span data-stu-id="557af-253">This example creates a safe links policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="557af-254">Включайте сканирование и переописывание URL-адресов в сообщениях электронной почты.</span><span class="sxs-lookup"><span data-stu-id="557af-254">Turn on URL scanning and rewriting in email messages.</span></span>
- <span data-ttu-id="557af-255">Включите сканирование URL-адресов в Teams (только для предварительного просмотра TAP).</span><span class="sxs-lookup"><span data-stu-id="557af-255">Turn on URL scanning in Teams (TAP Preview only).</span></span>
- <span data-ttu-id="557af-256">Включайте проверку url-адресов в режиме реального времени, включая ссылки, которые указывают на файлы.</span><span class="sxs-lookup"><span data-stu-id="557af-256">Turn on real-time scanning of clicked URLs, including clicked links that point to files.</span></span>
- <span data-ttu-id="557af-257">Дождись завершения проверки URL-адресов перед доставкой сообщения.</span><span class="sxs-lookup"><span data-stu-id="557af-257">Wait for URL scanning to complete before delivering the message.</span></span>
- <span data-ttu-id="557af-258">Включит сканирование URL-адресов и переописывание внутренних сообщений.</span><span class="sxs-lookup"><span data-stu-id="557af-258">Turn on URL scanning and rewriting for internal messages.</span></span>
- <span data-ttu-id="557af-259">Отслеживайте щелчки пользователей, связанные с защитой безопасных ссылок (мы не используем параметр _DoNotTrackUserClicks,_ а значение по умолчанию — $false, что означает, что щелчки пользователей отслеживаются).</span><span class="sxs-lookup"><span data-stu-id="557af-259">Track user clicks related to Safe Links protection (we aren't using the _DoNotTrackUserClicks_ parameter, and the default value is $false, which means user clicks are tracked).</span></span>
- <span data-ttu-id="557af-260">Не разрешайте пользователям перенажимать исходный URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="557af-260">Do not allow users to click through to the original URL.</span></span>

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

<span data-ttu-id="557af-261">Подробные сведения о синтаксисах и параметрах см. в описании [New-SafeLinksPolicy.](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy)</span><span class="sxs-lookup"><span data-stu-id="557af-261">For detailed syntax and parameter information, see [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a><span data-ttu-id="557af-262">Шаг 2. Создание правила безопасных ссылок с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="557af-262">Step 2: Use PowerShell to create a safe links rule</span></span>

<span data-ttu-id="557af-263">Чтобы создать правило безопасных ссылок, используйте синтаксис:</span><span class="sxs-lookup"><span data-stu-id="557af-263">To create a safe links rule, use this syntax:</span></span>

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="557af-264">В этом примере создается правило безопасных ссылок с именем Contoso All со следующими условиями:</span><span class="sxs-lookup"><span data-stu-id="557af-264">This example creates a safe links rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="557af-265">Правило связано с политикой безопасных ссылок с именем Contoso All.</span><span class="sxs-lookup"><span data-stu-id="557af-265">The rule is associated with the safe links policy named Contoso All.</span></span>
- <span data-ttu-id="557af-266">Правило применяется ко всем получателям в contoso.com домене.</span><span class="sxs-lookup"><span data-stu-id="557af-266">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="557af-267">Так как мы не используем параметр _Priority,_ используется приоритет по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="557af-267">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="557af-268">Правило включено (мы не используем параметр _Enabled,_ а по умолчанию используется `$true` значение).</span><span class="sxs-lookup"><span data-stu-id="557af-268">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="557af-269">Подробные сведения о синтаксисах и параметрах см. в описании [New-SafeLinksRule.](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="557af-269">For detailed syntax and parameter information, see [New-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule).</span></span>

### <a name="use-powershell-to-view-safe-links-policies"></a><span data-ttu-id="557af-270">Просмотр политик безопасных ссылок с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="557af-270">Use PowerShell to view safe links policies</span></span>

<span data-ttu-id="557af-271">Чтобы просмотреть существующие политики безопасных ссылок, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="557af-271">To view existing safe links policies, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="557af-272">В этом примере возвращается сводный список всех политик безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="557af-272">This example returns a summary list of all safe links policies.</span></span>

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

<span data-ttu-id="557af-273">В этом примере возвращаются подробные сведения о политике безопасных ссылок с именем Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="557af-273">This example returns detailed information for the safe links policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

<span data-ttu-id="557af-274">Подробные сведения о синтаксисах и параметрах см. в описании [Get-SafeLinksPolicy.](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy)</span><span class="sxs-lookup"><span data-stu-id="557af-274">For detailed syntax and parameter information, see [Get-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy).</span></span>

### <a name="use-powershell-to-view-safe-links-rules"></a><span data-ttu-id="557af-275">Просмотр правил безопасных ссылок с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="557af-275">Use PowerShell to view safe links rules</span></span>

<span data-ttu-id="557af-276">Чтобы просмотреть существующие правила безопасных ссылок, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="557af-276">To view existing safe links rules, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="557af-277">В этом примере возвращается сводный список всех правил безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="557af-277">This example returns a summary list of all safe links rules.</span></span>

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

<span data-ttu-id="557af-278">Чтобы отфильтровать список по включенным или отключенным правилам, выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="557af-278">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

<span data-ttu-id="557af-279">В этом примере возвращаются подробные сведения о правиле безопасных ссылок с именем Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="557af-279">This example returns detailed information for the safe links rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

<span data-ttu-id="557af-280">Подробные сведения о синтаксисах и параметрах см. в описании [get-SafeLinksRule.](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="557af-280">For detailed syntax and parameter information, see [Get-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule).</span></span>

### <a name="use-powershell-to-modify-safe-links-policies"></a><span data-ttu-id="557af-281">Изменение политик безопасных ссылок с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="557af-281">Use PowerShell to modify safe links policies</span></span>

<span data-ttu-id="557af-282">Политику безопасных ссылок нельзя переименовать в PowerShell (у cmdlet **Set-SafeLinksPolicy** нет _параметра Name)._</span><span class="sxs-lookup"><span data-stu-id="557af-282">You can't rename a safe links policy in PowerShell (the **Set-SafeLinksPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="557af-283">При переименовании политики безопасных ссылок в Центре безопасности & соответствия требованиям переименовывать нужно только правило безопасных _ссылок._</span><span class="sxs-lookup"><span data-stu-id="557af-283">When you rename a Safe Links policy in the Security & Compliance Center, you're only renaming the safe links _rule_.</span></span>

<span data-ttu-id="557af-284">Единственным дополнительным фактором при изменении политик безопасных ссылок в PowerShell является доступный синтаксис для параметра _DoNotRewriteUrls_ (список "Не переописывать следующие [URL-адреса"](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span><span class="sxs-lookup"><span data-stu-id="557af-284">The only additional consideration for modifying safe links policies in PowerShell is the available syntax for the _DoNotRewriteUrls_ parameter (the ["Do not rewrite the following URLs" list](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span></span>

- <span data-ttu-id="557af-285">Чтобы добавить значения, которые заменят существующие записи, используйте следующий синтаксис: `"Entry1","Entry2,..."EntryN"`</span><span class="sxs-lookup"><span data-stu-id="557af-285">To add values that will replace any existing entries, use the following syntax: `"Entry1","Entry2,..."EntryN"`.</span></span>
- <span data-ttu-id="557af-286">Чтобы добавить или удалить значения, не затрагивая другие существующие записи, используйте следующий синтаксис: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span><span class="sxs-lookup"><span data-stu-id="557af-286">To add or remove values without affecting other existing entries, use the following syntax: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span></span>

<span data-ttu-id="557af-287">В противном случае при создании политики безопасных ссылок будут доступны те же параметры, что и в разделе "Политика безопасных ссылок", описанном в разделе "Шаг 1. Создание политики безопасных ссылок с помощью [PowerShell"](#step-1-use-powershell-to-create-a-safe-links-policy) выше в этой статье.</span><span class="sxs-lookup"><span data-stu-id="557af-287">Otherwise, the same settings are available when you create a safe links policy as described in the [Step 1: Use PowerShell to create a safe links policy](#step-1-use-powershell-to-create-a-safe-links-policy) section earlier in this article.</span></span>

<span data-ttu-id="557af-288">Чтобы изменить политику безопасных ссылок, используйте синтаксис:</span><span class="sxs-lookup"><span data-stu-id="557af-288">To modify a safe links policy, use this syntax:</span></span>

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="557af-289">Подробные сведения о синтаксисах и параметрах см. в описании [Set-SafeLinksPolicy.](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy)</span><span class="sxs-lookup"><span data-stu-id="557af-289">For detailed syntax and parameter information, see [Set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy).</span></span>

### <a name="use-powershell-to-modify-safe-links-rules"></a><span data-ttu-id="557af-290">Изменение правил безопасных ссылок с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="557af-290">Use PowerShell to modify safe links rules</span></span>

<span data-ttu-id="557af-291">Единственным параметром, недоступным при изменении правила безопасных ссылок в PowerShell, является параметр _Enabled,_ позволяющий создать отключенное правило.</span><span class="sxs-lookup"><span data-stu-id="557af-291">The only setting that's not available when you modify a safe links rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="557af-292">Чтобы включить или отключить существующие правила безопасных ссылок, см. следующий раздел.</span><span class="sxs-lookup"><span data-stu-id="557af-292">To enable or disable existing safe links rules, see the next section.</span></span>

<span data-ttu-id="557af-293">В противном случае те же параметры доступны при создании правила, как описано в разделе "Шаг 2. Создание правила безопасных ссылок с помощью [PowerShell"](#step-2-use-powershell-to-create-a-safe-links-rule) ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="557af-293">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe links rule](#step-2-use-powershell-to-create-a-safe-links-rule) section earlier in this article.</span></span>

<span data-ttu-id="557af-294">Чтобы изменить правило безопасных ссылок, используйте синтаксис:</span><span class="sxs-lookup"><span data-stu-id="557af-294">To modify a safe links rule, use this syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="557af-295">Подробные сведения о синтаксисах и параметрах см. в описании [Set-SafeLinksRule.](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="557af-295">For detailed syntax and parameter information, see [Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a><span data-ttu-id="557af-296">Использование PowerShell для включения или отключения правил безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="557af-296">Use PowerShell to enable or disable safe links rules</span></span>

<span data-ttu-id="557af-297">Включение или отключение правила безопасных ссылок в PowerShell включает или отключает всю политику безопасных ссылок (правило безопасных ссылок и назначенную политику безопасных ссылок).</span><span class="sxs-lookup"><span data-stu-id="557af-297">Enabling or disabling a safe links rule in PowerShell enables or disables the whole Safe Links policy (the safe links rule and the assigned safe links policy).</span></span>

<span data-ttu-id="557af-298">Чтобы включить или отключить правило безопасных ссылок в PowerShell, используйте синтаксис:</span><span class="sxs-lookup"><span data-stu-id="557af-298">To enable or disable a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

<span data-ttu-id="557af-299">В этом примере отключается правило безопасных ссылок Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="557af-299">This example disables the safe links rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="557af-300">В этом примере включается то же правило.</span><span class="sxs-lookup"><span data-stu-id="557af-300">This example enables same rule.</span></span>

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="557af-301">Подробные сведения о синтаксисах и параметрах см. в описании [Enable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) и [Disable-SafeLinksRule.](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="557af-301">For detailed syntax and parameter information, see [Enable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) and [Disable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a><span data-ttu-id="557af-302">Настройка приоритета правил безопасных ссылок с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="557af-302">Use PowerShell to set the priority of safe links rules</span></span>

<span data-ttu-id="557af-303">Максимальный приоритет, который можно задать для правила, — 0.</span><span class="sxs-lookup"><span data-stu-id="557af-303">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="557af-304">Минимальное значение зависит от количества правил.</span><span class="sxs-lookup"><span data-stu-id="557af-304">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="557af-305">Например, если у вас есть пять правил, вы можете использовать значения 0–4.</span><span class="sxs-lookup"><span data-stu-id="557af-305">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="557af-306">Изменение приоритета существующего правила оказывает каскадное влияние на другие правила.</span><span class="sxs-lookup"><span data-stu-id="557af-306">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="557af-307">Например, если вы измените приоритет правила на 2, когда у вас есть пять настраиваемых правил (с приоритетами от 0 до 4), то для существующего правила с приоритетом 2 будет задан приоритет 3, а для правила с приоритетом 3 будет задан приоритет 4.</span><span class="sxs-lookup"><span data-stu-id="557af-307">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="557af-308">Чтобы установить приоритет правила безопасных ссылок в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="557af-308">To set the priority of a safe links rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="557af-p123">В этом примере для правила Marketing Department задается приоритет 2. Все правила с приоритетом не больше 2 понижаются на один ранг (значения приоритета увеличиваются на 1).</span><span class="sxs-lookup"><span data-stu-id="557af-p123">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="557af-311">**Примечание.** Чтобы установить приоритет нового правила при его создании, используйте параметр _Priority_ в параметре **New-SafeLinksRule.**</span><span class="sxs-lookup"><span data-stu-id="557af-311">**Note**: To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeLinksRule** cmdlet instead.</span></span>

<span data-ttu-id="557af-312">Подробные сведения о синтаксисах и параметрах см. в описании [Set-SafeLinksRule.](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="557af-312">For detailed syntax and parameter information, see [Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-remove-safe-links-policies"></a><span data-ttu-id="557af-313">Удаление политик безопасных ссылок с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="557af-313">Use PowerShell to remove safe links policies</span></span>

<span data-ttu-id="557af-314">При удалении политики безопасных ссылок с помощью PowerShell соответствующее правило безопасных ссылок не удаляется.</span><span class="sxs-lookup"><span data-stu-id="557af-314">When you use PowerShell to remove a safe links policy, the corresponding safe links rule isn't removed.</span></span>

<span data-ttu-id="557af-315">Чтобы удалить политику безопасных ссылок в PowerShell, используйте синтаксис:</span><span class="sxs-lookup"><span data-stu-id="557af-315">To remove a safe links policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="557af-316">В этом примере удаляется политика безопасных ссылок Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="557af-316">This example removes the safe links policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

<span data-ttu-id="557af-317">Подробные сведения о синтаксисах и параметрах см. в описании [Remove-SafeLinksPolicy.](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy)</span><span class="sxs-lookup"><span data-stu-id="557af-317">For detailed syntax and parameter information, see [Remove-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy).</span></span>

### <a name="use-powershell-to-remove-safe-links-rules"></a><span data-ttu-id="557af-318">Удаление правил безопасных ссылок с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="557af-318">Use PowerShell to remove safe links rules</span></span>

<span data-ttu-id="557af-319">При удалении правила безопасных ссылок с помощью PowerShell соответствующая политика безопасных ссылок не удаляется.</span><span class="sxs-lookup"><span data-stu-id="557af-319">When you use PowerShell to remove a safe links rule, the corresponding safe links policy isn't removed.</span></span>

<span data-ttu-id="557af-320">Чтобы удалить правило безопасных ссылок в PowerShell, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="557af-320">To remove a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

<span data-ttu-id="557af-321">В этом примере удаляется правило безопасных ссылок Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="557af-321">This example removes the safe links rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="557af-322">Подробные сведения о синтаксисах и параметрах см. в описании [remove-SafeLinksRule.](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="557af-322">For detailed syntax and parameter information, see [Remove-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule).</span></span>

<span data-ttu-id="557af-323">Чтобы убедиться, что безопасные ссылки сканирует сообщения, проверьте доступные отчеты Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="557af-323">To verify that Safe Links is scanning messages, check the available Microsoft Defender for Office 365 reports.</span></span> <span data-ttu-id="557af-324">Дополнительные сведения см. в отчетах "Просмотр отчетов для [Защитника для Office 365"](view-reports-for-atp.md) и "Использование проводника" в Центре [безопасности & соответствия требованиям.](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="557af-324">For more information, see [View reports for Defender for Office 365](view-reports-for-atp.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="557af-325">Как проверить, что эти процедуры выполнены?</span><span class="sxs-lookup"><span data-stu-id="557af-325">How do you know these procedures worked?</span></span>

<span data-ttu-id="557af-326">Чтобы убедиться, что вы успешно создали, изменили или удалили политики безопасных ссылок, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="557af-326">To verify that you've successfully created, modified, or removed Safe Links policies, do any of the following steps:</span></span>

- <span data-ttu-id="557af-327">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span><span class="sxs-lookup"><span data-stu-id="557af-327">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span> <span data-ttu-id="557af-328">Проверьте список политик, их значения **состояния** и их **значения приоритета.**</span><span class="sxs-lookup"><span data-stu-id="557af-328">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="557af-329">Чтобы просмотреть дополнительные сведения, выберите политику в списке и просмотреть сведения во внешнем поле.</span><span class="sxs-lookup"><span data-stu-id="557af-329">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="557af-330">В Exchange Online PowerShell или Exchange Online Protection PowerShell замените имя политики или правила, запустите следующую команду и проверьте \<Name\> параметры:</span><span class="sxs-lookup"><span data-stu-id="557af-330">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
