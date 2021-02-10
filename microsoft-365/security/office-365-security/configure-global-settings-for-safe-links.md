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
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Администраторы могут узнать, как просматривать и настраивать глобальные параметры (список "Блокировать следующие URL-адреса" и защиту приложений Office 365) для безопасных ссылок в Microsoft Defender для Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 885fe6a06cce054bea6d6f20c24c5c1f2a159c07
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165731"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a><span data-ttu-id="b1511-103">Настройка глобальных параметров безопасных ссылок в Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="b1511-103">Configure global settings for Safe Links in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b1511-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="b1511-104">**Applies to**</span></span>
- [<span data-ttu-id="b1511-105">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="b1511-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="b1511-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b1511-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="b1511-107">Эта статья предназначена для бизнес-клиентов, использующих [Microsoft Defender для Office 365](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="b1511-107">This article is intended for business customers who have [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="b1511-108">Если вы — домашний пользователь, который ищет сведения о безопасных ссылках в Outlook, см. дополнительные Outlook.com [безопасности.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)</span><span class="sxs-lookup"><span data-stu-id="b1511-108">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="b1511-109">Функция "Безопасные ссылки" — это функция в Microsoft Defender для [Office 365,](office-365-atp.md) которая обеспечивает сканирование URL-адресов входящие сообщения электронной почты в потоке почты и время проверки URL-адресов и ссылок в сообщениях электронной почты и других расположениях.</span><span class="sxs-lookup"><span data-stu-id="b1511-109">Safe Links is a feature in [Microsoft Defender for Office 365](office-365-atp.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="b1511-110">Дополнительные сведения см. в [веб-сайте "Безопасные ссылки" в Microsoft Defender для Office 365.](atp-safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="b1511-110">For more information, see [Safe Links in Microsoft Defender for Office 365](atp-safe-links.md).</span></span>

<span data-ttu-id="b1511-111">Большинство параметров безопасных ссылок настраиваются в политиках безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="b1511-111">You configure most Safe Links settings in Safe Links policies.</span></span> <span data-ttu-id="b1511-112">Инструкции см. в [настройках политик безопасных ссылок в Microsoft Defender для Office 365.](set-up-atp-safe-links-policies.md)</span><span class="sxs-lookup"><span data-stu-id="b1511-112">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-atp-safe-links-policies.md).</span></span>

<span data-ttu-id="b1511-113">Однако безопасные ссылки также используют глобальные параметры, которые применяются для всех пользователей, включенных в активные политики безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="b1511-113">But, Safe Links also uses global settings that apply to all users who are included in any active Safe Links policies.</span></span> <span data-ttu-id="b1511-114">Область глобальных параметров:</span><span class="sxs-lookup"><span data-stu-id="b1511-114">These global settings area:</span></span>

- <span data-ttu-id="b1511-115">Список **заблокированных URL-адресов.**</span><span class="sxs-lookup"><span data-stu-id="b1511-115">The **Block the following URLs** list.</span></span> <span data-ttu-id="b1511-116">Дополнительные сведения см. в [списке "Блокировка следующих URL-адресов" для безопасных ссылок](atp-safe-links.md#block-the-following-urls-list-for-safe-links)</span><span class="sxs-lookup"><span data-stu-id="b1511-116">For more information, see ["Block the following URLs" list for Safe Links](atp-safe-links.md#block-the-following-urls-list-for-safe-links)</span></span>
- <span data-ttu-id="b1511-117">Защита безопасных ссылок для приложений Office 365.</span><span class="sxs-lookup"><span data-stu-id="b1511-117">Safe Links protection for Office 365 apps.</span></span> <span data-ttu-id="b1511-118">Дополнительные сведения см. в параметрах безопасных [ссылок для приложений Office 365.](atp-safe-links.md#safe-links-settings-for-office-365-apps)</span><span class="sxs-lookup"><span data-stu-id="b1511-118">For more information, see [Safe Links settings for Office 365 apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

<span data-ttu-id="b1511-119">Глобальные параметры безопасных ссылок можно настроить в Центре безопасности и & соответствия требованиям или в PowerShell (Exchange Online PowerShell для соответствующих организаций Microsoft 365 с почтовыми ящиками в Exchange Online; автономный EOP PowerShell для организаций без почтовых ящиков Exchange Online, но с подписками на надстройки Microsoft Defender для Office 365).</span><span class="sxs-lookup"><span data-stu-id="b1511-119">You can configure the global Safe Links settings in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b1511-120">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="b1511-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b1511-121">Функции, предоставляемые глобальными настройками безопасных ссылок, применяются только к пользователям, включенным в активные политики безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="b1511-121">The features provided by global settings for Safe Links are only applied to users who are included in active Safe Links policies.</span></span> <span data-ttu-id="b1511-122">Встроенная или стандартная политика безопасных ссылок не существует, поэтому необходимо создать по крайней мере одну политику безопасных ссылок, чтобы эти глобальные параметры были активными.</span><span class="sxs-lookup"><span data-stu-id="b1511-122">There is no built-in or default Safe Links policy, so you need to create at least one Safe Links policy in order for these global settings to be active.</span></span> <span data-ttu-id="b1511-123">Инструкции см. в [настройках политик безопасных ссылок в Microsoft Defender для Office 365.](set-up-atp-safe-links-policies.md)</span><span class="sxs-lookup"><span data-stu-id="b1511-123">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-atp-safe-links-policies.md).</span></span>

- <span data-ttu-id="b1511-124">Откройте Центр безопасности и соответствия требованиям по ссылке <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="b1511-124">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="b1511-125">Чтобы перейти непосредственно на страницу **"Безопасные ссылки",** используйте <https://protection.office.com/safelinksv2> .</span><span class="sxs-lookup"><span data-stu-id="b1511-125">To go directly to the **Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="b1511-126">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="b1511-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="b1511-127">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="b1511-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="b1511-128">Для выполнения процедур, описанных в этой статье, вам должны быть назначены разрешения в Центре безопасности и соответствия требованиям:</span><span class="sxs-lookup"><span data-stu-id="b1511-128">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="b1511-129">Чтобы настроить глобальные параметры для функции "Безопасные ссылки", необходимо быть членом группы ролей "Управление организацией" или **"Администратор** безопасности". </span><span class="sxs-lookup"><span data-stu-id="b1511-129">To configure the global settings for Safe Links, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="b1511-130">Для доступа только для чтения к глобальным настройкам безопасных ссылок необходимо  быть участником группы ролей **"Глобальное** чтение" или "Читатель безопасности".</span><span class="sxs-lookup"><span data-stu-id="b1511-130">For read-only access to the global settings for Safe Links, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="b1511-131">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="b1511-131">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="b1511-132">**Примечания**.</span><span class="sxs-lookup"><span data-stu-id="b1511-132">**Notes**:</span></span>

  - <span data-ttu-id="b1511-133">Добавление пользователей в соответствующую роль Azure Active Directory в Центре безопасности Microsoft 365 предоставляет пользователям необходимые разрешения в Центре безопасности и соответствия требованиям _и_ разрешения для других функций в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b1511-133">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="b1511-134">Дополнительные сведения см. в статье [О ролях администраторов](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="b1511-134">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="b1511-135">Группа ролей **Управление организацией с правами только на просмотр** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) также предоставляет доступ только для чтения к этой функции.</span><span class="sxs-lookup"><span data-stu-id="b1511-135">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="b1511-136">Рекомендуемые значения глобальных параметров для безопасных ссылок см. в параметрах [безопасных ссылок.](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings)</span><span class="sxs-lookup"><span data-stu-id="b1511-136">For our recommended values for the global settings for Safe Links, see [Safe Links settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings).</span></span>

- <span data-ttu-id="b1511-137">Позволяет применять новую или обновленную политику в течение 30 минут.</span><span class="sxs-lookup"><span data-stu-id="b1511-137">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="b1511-138">[Новые функции постоянно добавляются в Microsoft Defender для Office 365.](office-365-atp.md#new-features-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="b1511-138">[New features are continually being added to Microsoft Defender for Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="b1511-139">При добавлении новых функций может потребоваться внести изменения в существующие политики безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="b1511-139">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a><span data-ttu-id="b1511-140">Настройка списка "Блокировать следующие URL-адреса" в Центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="b1511-140">Configure the "Block the following URLs" list in the Security & Compliance Center</span></span>

<span data-ttu-id="b1511-141">В **списке "Блокировать следующие** URL-адреса" указаны ссылки, которые всегда должны блокироваться при сканировании безопасных ссылок в поддерживаемых приложениях.</span><span class="sxs-lookup"><span data-stu-id="b1511-141">The **Block the following URLs** list identifies the links that should always be blocked by Safe Links scanning in supported apps.</span></span> <span data-ttu-id="b1511-142">Дополнительные сведения см. в [списке "Блокировка следующих URL-адресов" для безопасных ссылок.](atp-safe-links.md#block-the-following-urls-list-for-safe-links)</span><span class="sxs-lookup"><span data-stu-id="b1511-142">For more information, see ["Block the following URLs" list for Safe Links](atp-safe-links.md#block-the-following-urls-list-for-safe-links).</span></span>

1. <span data-ttu-id="b1511-143">В Центре безопасности & соответствия требованиям  перейдите в центр безопасных ссылок ATP политики управления угрозами, а затем щелкните \>  \>  **"Глобальные параметры".**</span><span class="sxs-lookup"><span data-stu-id="b1511-143">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="b1511-144">В **окне "Политика безопасных ссылок"** для организации перейдите к окну **"Блокировать следующие URL-адреса".**</span><span class="sxs-lookup"><span data-stu-id="b1511-144">In the **Safe Links policy for your organization** fly out that appears, go to the **Block the following URLs** box.</span></span>

3. <span data-ttu-id="b1511-145">Настройте одну или несколько записей, как описано в синтаксис записи для [списка "Блокировать следующие URL-адреса".](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="b1511-145">Configure one or more entries as described in [Entry syntax for the "Block the following URLs" list](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

   <span data-ttu-id="b1511-146">По завершении нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b1511-146">When you're finished, click **Save**.</span></span>

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a><span data-ttu-id="b1511-147">Настройка списка "Блокировать следующие URL-адреса" в PowerShell</span><span class="sxs-lookup"><span data-stu-id="b1511-147">Configure the "Block the following URLs" list in PowerShell</span></span>

<span data-ttu-id="b1511-148">Подробные сведения о синтаксисах записей см. в синтаксису записей в списке ["Блокировать следующие URL-адреса".](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="b1511-148">For details about the entry syntax, see [Entry syntax for the "Block the following URLs" list](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

<span data-ttu-id="b1511-149">Для просмотра существующих записей в свойстве _BlockURLs_ можно использовать cmdlet **Get-AtpPolicyForO365.**</span><span class="sxs-lookup"><span data-stu-id="b1511-149">You can use the **Get-AtpPolicyForO365** cmdlet to view existing entries in the _BlockURLs_ property.</span></span>

- <span data-ttu-id="b1511-150">Чтобы добавить значения, которые заменят существующие записи, используйте следующий синтаксис в Exchange Online PowerShell или Exchange Online Protection PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b1511-150">To add values that will replace any existing entries, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  <span data-ttu-id="b1511-151">В этом примере в список добавляются следующие записи:</span><span class="sxs-lookup"><span data-stu-id="b1511-151">This example adds the following entries to the list:</span></span>

  - <span data-ttu-id="b1511-152">Блокировка домена, поддоменов и путей для fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="b1511-152">Block the domain, subdomains, and paths for fabrikam.com.</span></span>
  - <span data-ttu-id="b1511-153">Блокировать исследования поддоменов, но не родительский домен или другие поддомены в tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="b1511-153">Block the subdomain research, but not the parent domain or other subdomains in tailspintoys.com</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- <span data-ttu-id="b1511-154">Чтобы добавить или удалить значения, не затрагивая другие существующие записи, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="b1511-154">To add or remove values without affecting other existing entries, use the following syntax:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  <span data-ttu-id="b1511-155">В этом примере добавляется новая запись для adatum.com и удаляется запись для fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="b1511-155">This example adds a new entry for adatum.com, and removes the entry for fabrikam.com.</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a><span data-ttu-id="b1511-156">Настройка защиты безопасных ссылок для приложений Office 365 в Центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="b1511-156">Configure Safe Links protection for Office 365 apps in the Security & Compliance Center</span></span>

<span data-ttu-id="b1511-157">Защита безопасных ссылок для приложений Office 365 применяется к документам в поддерживаемых классических, мобильных и веб-приложениях Office.</span><span class="sxs-lookup"><span data-stu-id="b1511-157">Safe Links protection for Office 365 apps applies to documents in supported Office desktop, mobile, and web apps.</span></span> <span data-ttu-id="b1511-158">Дополнительные сведения см. в параметрах безопасных [ссылок для приложений Office 365.](atp-safe-links.md#safe-links-settings-for-office-365-apps)</span><span class="sxs-lookup"><span data-stu-id="b1511-158">For more information, see [Safe Links settings for Office 365 apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

1. <span data-ttu-id="b1511-159">В Центре безопасности & соответствия требованиям  перейдите в центр безопасных ссылок ATP политики управления угрозами, а затем щелкните \>  \>  **"Глобальные параметры".**</span><span class="sxs-lookup"><span data-stu-id="b1511-159">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="b1511-160">В политике **безопасных ссылок** для организации настройте следующие параметры в параметрах, которые применяются к контенту, кроме раздела **"Электронная** почта":</span><span class="sxs-lookup"><span data-stu-id="b1511-160">In the **Safe Links policy for your organization** fly out that appears, configure the following settings in the **Settings that apply to content except email** section:</span></span>

   - <span data-ttu-id="b1511-161">**Приложения Office 365:** убедитесь, что этот переладок находится справа, чтобы включить безопасные ссылки для поддерживаемых приложений Office 365: включить. ![ ](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="b1511-161">**Office 365 applications**: Verify the toggle is to the right to enable Safe Links for supported Office 365 apps: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   - <span data-ttu-id="b1511-162">**Не отслеживайте,** когда пользователи нажимают кнопку "Безопасные ссылки": переключение влево для отслеживания переходов пользователей, связанных с заблокированными URL-адресами в поддерживаемых приложениях Office 365: выключение. ![ ](../../media/scc-toggle-off.png)</span><span class="sxs-lookup"><span data-stu-id="b1511-162">**Do not track when users click Safe Links**: Move the toggle to the left to track user clicks related to blocked URLs in supported Office 365 apps: ![Toggle off](../../media/scc-toggle-off.png).</span></span>

   - <span data-ttu-id="b1511-163">Не позволяйте пользователям перейдите по ссылке "Безопасные ссылки" на исходный URL-адрес: убедитесь, что перейдите справа, чтобы запретить пользователям перенажимать исходный заблокированный URL-адрес в поддерживаемых приложениях Office 365: "Нажать кнопку". ![ ](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="b1511-163">**Do not let users click through Safe Links to the original URL**: Verify the toggle is to the right to prevent users from clicking through to the original blocked URL in supported Office 365 apps: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   <span data-ttu-id="b1511-164">По завершении нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b1511-164">When you're finished, click **Save**.</span></span>

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a><span data-ttu-id="b1511-165">Настройка защиты безопасных ссылок для приложений Office 365 в PowerShell</span><span class="sxs-lookup"><span data-stu-id="b1511-165">Configure Safe Links protection for Office 365 apps in PowerShell</span></span>

<span data-ttu-id="b1511-166">Если вы хотите использовать PowerShell для настройки защиты безопасных ссылок для приложений Office 365, используйте следующий синтаксис в Exchange Online PowerShell или Exchange Online Protection PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b1511-166">If you'd rather use PowerShell to configure Safe Links protection for Office 365 apps, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

<span data-ttu-id="b1511-167">В этом примере настраиваются следующие параметры защиты безопасных ссылок в приложениях Office 365:</span><span class="sxs-lookup"><span data-stu-id="b1511-167">This example configures the following settings for Safe Links protection in Office 365 apps:</span></span>

- <span data-ttu-id="b1511-168">Безопасные ссылки для приложений Office 365 включены (мы не используем параметр _EnableSafeLinksForO365Clients,_ а значение по умолчанию — $true).</span><span class="sxs-lookup"><span data-stu-id="b1511-168">Safe Links for Office 365 apps is turned on (we aren't using the _EnableSafeLinksForO365Clients_ parameter, and the default value is $true).</span></span>
- <span data-ttu-id="b1511-169">Щелчки пользователей, связанные с заблокированными URL-адресами в поддерживаемых приложениях Office 365, отслеживаются.</span><span class="sxs-lookup"><span data-stu-id="b1511-169">User clicks related to blocked URLs in supported Office 365 apps are tracked.</span></span>
- <span data-ttu-id="b1511-170">Пользователям не разрешено перебор исходного заблокированного URL-адреса в поддерживаемых приложениях Office 365 (мы не используем параметр _AllowClickThrough,_ а значение по умолчанию — $false).</span><span class="sxs-lookup"><span data-stu-id="b1511-170">Users are not allowed to click through to the original blocked URL in supported Office 365 apps (we aren't using the _AllowClickThrough_ parameter, and the default value is $false).</span></span>

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

<span data-ttu-id="b1511-171">Подробные сведения о синтаксис и параметрах см. в описании [Set-AtpPolicyForO365.](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="b1511-171">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="b1511-172">Как проверить, что эти процедуры выполнены?</span><span class="sxs-lookup"><span data-stu-id="b1511-172">How do you know these procedures worked?</span></span>

<span data-ttu-id="b1511-173">Чтобы убедиться, что вы успешно настроили глобальные  параметры безопасных ссылок (список "Блокировать следующие URL-адреса" и параметры защиты приложений Office 365), сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="b1511-173">To verify that you've successfully configured the global settings for Safe Links (the **Block the following URLs** list and the Office 365 app protection settings), do any of the following steps:</span></span>

- <span data-ttu-id="b1511-174">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links,** click **Global settings**, and verify the settings in the fly out that appears.</span><span class="sxs-lookup"><span data-stu-id="b1511-174">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, click **Global settings**, and verify the settings in the fly out that appears.</span></span>

- <span data-ttu-id="b1511-175">В Exchange Online PowerShell или Exchange Online Protection PowerShell запустите следующую команду и проверьте параметры:</span><span class="sxs-lookup"><span data-stu-id="b1511-175">In Exchange Online PowerShell or Exchange Online Protection PowerShell, run the following command and verify the settings:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  <span data-ttu-id="b1511-176">Подробные сведения о синтаксисах и параметрах см. в описании [get-AtpPolicyForO365.](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="b1511-176">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span></span>
