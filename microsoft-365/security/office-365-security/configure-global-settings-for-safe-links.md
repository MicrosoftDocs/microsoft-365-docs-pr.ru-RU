---
title: Настройка глобальных параметров для параметров безопасных ссылок в Защитнике Office 365
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
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Администраторы могут узнать, как просматривать и настраивать глобальные параметры (список "Блокировать следующие URL-адреса" и защиту для приложений Office 365) для безопасных ссылок в Microsoft Defender для Office 365.
ms.openlocfilehash: bc44432d4d9478e4c6a2414a70acc785c5b2c005
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682910"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a><span data-ttu-id="54227-103">Настройка глобальных параметров безопасных ссылок в Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="54227-103">Configure global settings for Safe Links in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="54227-104">Эта статья предназначена для бизнес-клиентов, использующих [Microsoft Defender для Office 365](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="54227-104">This article is intended for business customers who have [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="54227-105">Если вы — домашний пользователь, который ищет сведения о безопасных ссылках в Outlook, см. дополнительные Outlook.com [безопасности.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)</span><span class="sxs-lookup"><span data-stu-id="54227-105">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="54227-106">Функция "Безопасные ссылки" — это функция в Microsoft Defender для [Office 365,](office-365-atp.md) которая обеспечивает сканирование URL-адресов входящие сообщения электронной почты в потоке почты и время проверки URL-адресов и ссылок в сообщениях электронной почты и других расположениях.</span><span class="sxs-lookup"><span data-stu-id="54227-106">Safe Links is a feature in [Microsoft Defender for Office 365](office-365-atp.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="54227-107">Дополнительные сведения см. в [веб-сайте "Безопасные ссылки" в Microsoft Defender для Office 365.](atp-safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="54227-107">For more information, see [Safe Links in Microsoft Defender for Office 365](atp-safe-links.md).</span></span>

<span data-ttu-id="54227-108">Большинство параметров безопасных ссылок настраиваются в политиках безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="54227-108">You configure most Safe Links settings in Safe Links policies.</span></span> <span data-ttu-id="54227-109">Инструкции см. в [настройках политик безопасных ссылок в Microsoft Defender для Office 365.](set-up-atp-safe-links-policies.md)</span><span class="sxs-lookup"><span data-stu-id="54227-109">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-atp-safe-links-policies.md).</span></span>

<span data-ttu-id="54227-110">Однако безопасные ссылки также используют глобальные параметры, которые применяются для всех пользователей, включенных в активные политики безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="54227-110">But, Safe Links also uses global settings that apply to all users who are included in any active Safe Links policies.</span></span> <span data-ttu-id="54227-111">Область глобальных параметров:</span><span class="sxs-lookup"><span data-stu-id="54227-111">These global settings area:</span></span>

- <span data-ttu-id="54227-112">Список **заблокированных URL-адресов.**</span><span class="sxs-lookup"><span data-stu-id="54227-112">The **Block the following URLs** list.</span></span> <span data-ttu-id="54227-113">Дополнительные сведения см. в [списке "Блокировка следующих URL-адресов" для безопасных ссылок](atp-safe-links.md#block-the-following-urls-list-for-safe-links)</span><span class="sxs-lookup"><span data-stu-id="54227-113">For more information, see ["Block the following URLs" list for Safe Links](atp-safe-links.md#block-the-following-urls-list-for-safe-links)</span></span>
- <span data-ttu-id="54227-114">Защита безопасных ссылок для приложений Office 365.</span><span class="sxs-lookup"><span data-stu-id="54227-114">Safe Links protection for Office 365 apps.</span></span> <span data-ttu-id="54227-115">Дополнительные сведения см. в параметрах безопасных [ссылок для приложений Office 365.](atp-safe-links.md#safe-links-settings-for-office-365-apps)</span><span class="sxs-lookup"><span data-stu-id="54227-115">For more information, see [Safe Links settings for Office 365 apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

<span data-ttu-id="54227-116">Глобальные параметры безопасных ссылок можно настроить в Центре безопасности и & соответствия требованиям или в PowerShell (Exchange Online PowerShell для соответствующих организаций Microsoft 365 с почтовыми ящиками в Exchange Online; автономный EOP PowerShell для организаций без почтовых ящиков Exchange Online, но с подписками на надстройки Microsoft Defender для Office 365).</span><span class="sxs-lookup"><span data-stu-id="54227-116">You can configure the global Safe Links settings in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="54227-117">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="54227-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="54227-118">Функции, предоставляемые глобальными настройками безопасных ссылок, применяются только к пользователям, включенным в активные политики безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="54227-118">The features provided by global settings for Safe Links are only applied to users who are included in active Safe Links policies.</span></span> <span data-ttu-id="54227-119">Встроенная или стандартная политика безопасных ссылок не существует, поэтому необходимо создать по крайней мере одну политику безопасных ссылок, чтобы эти глобальные параметры были активными.</span><span class="sxs-lookup"><span data-stu-id="54227-119">There is no built-in or default Safe Links policy, so you need to create at least one Safe Links policy in order for these global settings to be active.</span></span> <span data-ttu-id="54227-120">Инструкции см. в [настройках политик безопасных ссылок в Microsoft Defender для Office 365.](set-up-atp-safe-links-policies.md)</span><span class="sxs-lookup"><span data-stu-id="54227-120">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-atp-safe-links-policies.md).</span></span>

- <span data-ttu-id="54227-121">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="54227-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="54227-122">Чтобы перейти непосредственно на страницу **"Безопасные ссылки",** используйте <https://protection.office.com/safelinksv2> .</span><span class="sxs-lookup"><span data-stu-id="54227-122">To go directly to the **Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="54227-123">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="54227-123">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="54227-124">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="54227-124">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="54227-125">Для выполнения процедур, описанных в этой статье, вам должны быть назначены разрешения в Центре безопасности и соответствия требованиям:</span><span class="sxs-lookup"><span data-stu-id="54227-125">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="54227-126">Чтобы настроить глобальные параметры для функции "Безопасные ссылки", необходимо быть членом группы ролей "Управление организацией" или **"Администратор** безопасности". </span><span class="sxs-lookup"><span data-stu-id="54227-126">To configure the global settings for Safe Links, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="54227-127">Для доступа только для чтения к глобальным настройкам безопасных ссылок необходимо  быть членом группы ролей **"Глобальное** чтение" или "Читатель безопасности".</span><span class="sxs-lookup"><span data-stu-id="54227-127">For read-only access to the global settings for Safe Links, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="54227-128">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="54227-128">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="54227-129">**Примечания**.</span><span class="sxs-lookup"><span data-stu-id="54227-129">**Notes**:</span></span>

  - <span data-ttu-id="54227-130">Добавление пользователей в соответствующую роль Azure Active Directory в Центре безопасности Microsoft 365 предоставляет пользователям необходимые разрешения в Центре безопасности и соответствия требованиям _и_ разрешения для других функций в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="54227-130">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="54227-131">Дополнительные сведения см. в статье [О ролях администраторов](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="54227-131">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="54227-132">Группа ролей **Управление организацией с правами только на просмотр** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) также предоставляет доступ только для чтения к этой функции.</span><span class="sxs-lookup"><span data-stu-id="54227-132">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="54227-133">Рекомендуемые значения глобальных параметров для безопасных ссылок см. в параметрах [безопасных ссылок.](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings)</span><span class="sxs-lookup"><span data-stu-id="54227-133">For our recommended values for the global settings for Safe Links, see [Safe Links settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings).</span></span>

- <span data-ttu-id="54227-134">Позволяет применять новую или обновленную политику в течение 30 минут.</span><span class="sxs-lookup"><span data-stu-id="54227-134">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="54227-135">[Новые функции постоянно добавляются в Microsoft Defender для Office 365.](office-365-atp.md#new-features-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="54227-135">[New features are continually being added to Microsoft Defender for Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="54227-136">При добавлении новых функций может потребоваться внести изменения в существующие политики безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="54227-136">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a><span data-ttu-id="54227-137">Настройка списка "Блокировать следующие URL-адреса" в Центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="54227-137">Configure the "Block the following URLs" list in the Security & Compliance Center</span></span>

<span data-ttu-id="54227-138">В **списке "Блокировать следующие** URL-адреса" указаны ссылки, которые всегда должны блокироваться при сканировании безопасных ссылок в поддерживаемых приложениях.</span><span class="sxs-lookup"><span data-stu-id="54227-138">The **Block the following URLs** list identifies the links that should always be blocked by Safe Links scanning in supported apps.</span></span> <span data-ttu-id="54227-139">Дополнительные сведения см. в [списке "Блокировка следующих URL-адресов" для безопасных ссылок.](atp-safe-links.md#block-the-following-urls-list-for-safe-links)</span><span class="sxs-lookup"><span data-stu-id="54227-139">For more information, see ["Block the following URLs" list for Safe Links](atp-safe-links.md#block-the-following-urls-list-for-safe-links).</span></span>

1. <span data-ttu-id="54227-140">В Центре безопасности & соответствия требованиям  перейдите в центр безопасных ссылок ATP политики управления угрозами, а затем щелкните \>  \>  **"Глобальные параметры".**</span><span class="sxs-lookup"><span data-stu-id="54227-140">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="54227-141">В **окне "Политика безопасных ссылок"** для организации перейдите к окну **"Блокировать следующие URL-адреса".**</span><span class="sxs-lookup"><span data-stu-id="54227-141">In the **Safe Links policy for your organization** fly out that appears, go to the **Block the following URLs** box.</span></span>

3. <span data-ttu-id="54227-142">Настройте одну или несколько записей, как описано в синтаксис записи для [списка "Блокировать следующие URL-адреса".](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="54227-142">Configure one or more entries as described in [Entry syntax for the "Block the following URLs" list](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

   <span data-ttu-id="54227-143">По завершении нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="54227-143">When you're finished, click **Save**.</span></span>

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a><span data-ttu-id="54227-144">Настройка списка "Блокировать следующие URL-адреса" в PowerShell</span><span class="sxs-lookup"><span data-stu-id="54227-144">Configure the "Block the following URLs" list in PowerShell</span></span>

<span data-ttu-id="54227-145">Подробные сведения о синтаксис записи см. в синтаксис записи для [списка "Блокировать следующие URL-адреса".](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="54227-145">For details about the entry syntax, see [Entry syntax for the "Block the following URLs" list](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

<span data-ttu-id="54227-146">Для просмотра существующих записей в свойстве _BlockURLs_ можно использовать cmdlet **Get-AtpPolicyForO365.**</span><span class="sxs-lookup"><span data-stu-id="54227-146">You can use the **Get-AtpPolicyForO365** cmdlet to view existing entries in the _BlockURLs_ property.</span></span>

- <span data-ttu-id="54227-147">Чтобы добавить значения, которые заменят существующие записи, используйте следующий синтаксис в Exchange Online PowerShell или Exchange Online Protection PowerShell:</span><span class="sxs-lookup"><span data-stu-id="54227-147">To add values that will replace any existing entries, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  <span data-ttu-id="54227-148">В этом примере в список добавляются следующие записи:</span><span class="sxs-lookup"><span data-stu-id="54227-148">This example adds the following entries to the list:</span></span>

  - <span data-ttu-id="54227-149">Блокировка домена, поддоменов и путей для fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="54227-149">Block the domain, subdomains, and paths for fabrikam.com.</span></span>
  - <span data-ttu-id="54227-150">Блокировать исследования поддоменов, но не родительский домен или другие поддомены в tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="54227-150">Block the subdomain research, but not the parent domain or other subdomains in tailspintoys.com</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- <span data-ttu-id="54227-151">Чтобы добавить или удалить значения, не затрагивая другие существующие записи, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="54227-151">To add or remove values without affecting other existing entries, use the following syntax:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  <span data-ttu-id="54227-152">В этом примере добавляется новая запись для adatum.com и удаляется запись для fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="54227-152">This example adds a new entry for adatum.com, and removes the entry for fabrikam.com.</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a><span data-ttu-id="54227-153">Настройка защиты безопасных ссылок для приложений Office 365 в Центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="54227-153">Configure Safe Links protection for Office 365 apps in the Security & Compliance Center</span></span>

<span data-ttu-id="54227-154">Защита безопасных ссылок для приложений Office 365 применяется к документам в поддерживаемых классических, мобильных и веб-приложениях Office.</span><span class="sxs-lookup"><span data-stu-id="54227-154">Safe Links protection for Office 365 apps applies to documents in supported Office desktop, mobile, and web apps.</span></span> <span data-ttu-id="54227-155">Дополнительные сведения см. в параметрах безопасных [ссылок для приложений Office 365.](atp-safe-links.md#safe-links-settings-for-office-365-apps)</span><span class="sxs-lookup"><span data-stu-id="54227-155">For more information, see [Safe Links settings for Office 365 apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

1. <span data-ttu-id="54227-156">В Центре безопасности & соответствия требованиям  перейдите в центр безопасных ссылок ATP политики управления угрозами, а затем щелкните \>  \>  **"Глобальные параметры".**</span><span class="sxs-lookup"><span data-stu-id="54227-156">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="54227-157">В политике **безопасных ссылок** для организации настройте следующие параметры в параметрах, которые применяются к содержимому, кроме раздела **"Электронная** почта":</span><span class="sxs-lookup"><span data-stu-id="54227-157">In the **Safe Links policy for your organization** fly out that appears, configure the following settings in the **Settings that apply to content except email** section:</span></span>

   - <span data-ttu-id="54227-158">**Приложения Office 365:** убедитесь, что этот переладок находится справа, чтобы включить безопасные ссылки для поддерживаемых приложений Office 365: включить. ![ ](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="54227-158">**Office 365 applications**: Verify the toggle is to the right to enable Safe Links for supported Office 365 apps: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   - <span data-ttu-id="54227-159">**Не отслеживайте,** когда пользователи нажимают кнопку "Безопасные ссылки": переключение влево для отслеживания щелчков, связанных с заблокированными URL-адресами, в поддерживаемых приложениях Office 365: выключение. ![ ](../../media/scc-toggle-off.png)</span><span class="sxs-lookup"><span data-stu-id="54227-159">**Do not track when users click Safe Links**: Move the toggle to the left to track user clicks related to blocked URLs in supported Office 365 apps: ![Toggle off](../../media/scc-toggle-off.png).</span></span>

   - <span data-ttu-id="54227-160">Не позволяйте пользователям перейдите по ссылке "Безопасные ссылки" на исходный URL-адрес: убедитесь, что перейдите справа, чтобы запретить пользователям перенажимать исходный заблокированный URL-адрес в поддерживаемых приложениях Office 365: "Нажать кнопку". ![ ](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="54227-160">**Do not let users click through Safe Links to the original URL**: Verify the toggle is to the right to prevent users from clicking through to the original blocked URL in supported Office 365 apps: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   <span data-ttu-id="54227-161">По завершении нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="54227-161">When you're finished, click **Save**.</span></span>

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a><span data-ttu-id="54227-162">Настройка защиты безопасных ссылок для приложений Office 365 в PowerShell</span><span class="sxs-lookup"><span data-stu-id="54227-162">Configure Safe Links protection for Office 365 apps in PowerShell</span></span>

<span data-ttu-id="54227-163">Если вы хотите использовать PowerShell для настройки защиты безопасных ссылок для приложений Office 365, используйте следующий синтаксис в Exchange Online PowerShell или Exchange Online Protection PowerShell:</span><span class="sxs-lookup"><span data-stu-id="54227-163">If you'd rather use PowerShell to configure Safe Links protection for Office 365 apps, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

<span data-ttu-id="54227-164">В этом примере настраиваются следующие параметры защиты безопасных ссылок в приложениях Office 365:</span><span class="sxs-lookup"><span data-stu-id="54227-164">This example configures the following settings for Safe Links protection in Office 365 apps:</span></span>

- <span data-ttu-id="54227-165">Безопасные ссылки для приложений Office 365 включены (мы не используем параметр _EnableSafeLinksForO365Clients,_ а значение по умолчанию — $true).</span><span class="sxs-lookup"><span data-stu-id="54227-165">Safe Links for Office 365 apps is turned on (we aren't using the _EnableSafeLinksForO365Clients_ parameter, and the default value is $true).</span></span>
- <span data-ttu-id="54227-166">Щелчки пользователей, связанные с заблокированными URL-адресами в поддерживаемых приложениях Office 365, отслеживаются.</span><span class="sxs-lookup"><span data-stu-id="54227-166">User clicks related to blocked URLs in supported Office 365 apps are tracked.</span></span>
- <span data-ttu-id="54227-167">Пользователям не разрешено перебор исходного заблокированного URL-адреса в поддерживаемых приложениях Office 365 (мы не используем параметр _AllowClickThrough,_ а значение по умолчанию — $false).</span><span class="sxs-lookup"><span data-stu-id="54227-167">Users are not allowed to click through to the original blocked URL in supported Office 365 apps (we aren't using the _AllowClickThrough_ parameter, and the default value is $false).</span></span>

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

<span data-ttu-id="54227-168">Подробные сведения о синтаксис и параметрах см. в описании [Set-AtpPolicyForO365.](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="54227-168">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="54227-169">Как проверить, что эти процедуры выполнены?</span><span class="sxs-lookup"><span data-stu-id="54227-169">How do you know these procedures worked?</span></span>

<span data-ttu-id="54227-170">Чтобы убедиться, что вы успешно настроили глобальные  параметры безопасных ссылок (список "Блокировать следующие URL-адреса" и параметры защиты приложений Office 365), сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="54227-170">To verify that you've successfully configured the global settings for Safe Links (the **Block the following URLs** list and the Office 365 app protection settings), do any of the following steps:</span></span>

- <span data-ttu-id="54227-171">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links,** click **Global settings**, and verify the settings in the fly out that appears.</span><span class="sxs-lookup"><span data-stu-id="54227-171">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, click **Global settings**, and verify the settings in the fly out that appears.</span></span>

- <span data-ttu-id="54227-172">В Exchange Online PowerShell или Exchange Online Protection PowerShell запустите следующую команду и проверьте параметры:</span><span class="sxs-lookup"><span data-stu-id="54227-172">In Exchange Online PowerShell or Exchange Online Protection PowerShell, run the following command and verify the settings:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  <span data-ttu-id="54227-173">Подробные сведения о синтаксисах и параметрах см. в описании [get-AtpPolicyForO365.](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="54227-173">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span></span>
