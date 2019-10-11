---
title: Управление почтовыми пользователями в EOP
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: "Определение почтовых пользователей \x97 важный этап управления службой Exchange Online Protection (EOP)."
ms.openlocfilehash: 85a2c3ee278af36b9743fd9ff70ea9ab21437de8
ms.sourcegitcommit: cbf117a4cd92a907115c9f10752f3c557361e586
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/10/2019
ms.locfileid: "37441246"
---
# <a name="manage-mail-users-in-eop"></a><span data-ttu-id="0c4cf-103">Управление почтовыми пользователями в EOP</span><span class="sxs-lookup"><span data-stu-id="0c4cf-103">Manage mail users in EOP</span></span>

<span data-ttu-id="0c4cf-p101">Определение почтовых пользователей  важный этап управления службой Exchange Online Protection (EOP). Существует несколько способов управления получателями в EOP.</span><span class="sxs-lookup"><span data-stu-id="0c4cf-p101">Defining mail users is an important part of managing the Exchange Online Protection (EOP) service. There are several ways that you can manage users in EOP:</span></span>

- <span data-ttu-id="0c4cf-p102">**Управление почтовыми пользователями с помощью синхронизации службы каталогов**: если в вашей компании существуют учетные записи пользователей в локальной среде Active Directory, их можно синхронизировать с Azure Active Directory (AD), чтобы сохранить их копии в облаке. При синхронизации существующих учетных записей с Azure Active Directory соответствующих пользователей можно просматривать в области **Получатели** в Центре администрирования Exchange. Рекомендуется использовать синхронизацию службы каталогов.</span><span class="sxs-lookup"><span data-stu-id="0c4cf-p102">**Use directory synchronization to manage mail users**: If your company has existing user accounts in an on-premises Active Directory environment, you can synchronize those accounts to Azure Active Directory (AD), where a copy of the accounts is stored in the cloud. When you synchronize your existing user accounts to Azure Active Directory, you can view those users in the **Recipients** pane of the Exchange admin center (EAC). Using directory synchronization is recommended.</span></span>

- <span data-ttu-id="0c4cf-p103">**Управление почтовыми пользователями с помощью Центра администрирования Exchange**: добавление почтовых пользователей и управление ими непосредственно в Центре администрирования Exchange. Это самый простой и удобный способ добавить почтовых пользователей по одному.</span><span class="sxs-lookup"><span data-stu-id="0c4cf-p103">**Use the EAC to manage mail users**: Add and manage mail users directly in the EAC. This is the easiest way to add mail users and is useful for adding one user at a time.</span></span>

- <span data-ttu-id="0c4cf-111">**Использование PowerShell для управления почтовыми пользователями**: Добавление почтовых пользователей и управление ими с помощью Exchange Online Protection PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0c4cf-111">**Use PowerShell to manage mail users**: Add and manage mail users by in Exchange Online Protection PowerShell.</span></span> <span data-ttu-id="0c4cf-112">Этот способ удобен для добавления нескольких записей и создания сценариев.</span><span class="sxs-lookup"><span data-stu-id="0c4cf-112">This method is useful for adding multiple records and creating scripts.</span></span>

> [!NOTE]
> <span data-ttu-id="0c4cf-113">Вы можете добавлять пользователей в центре администрирования Microsoft 365, но эти пользователи не могут использоваться в качестве получателей почты.</span><span class="sxs-lookup"><span data-stu-id="0c4cf-113">You can add users in the Microsoft 365 admin center, however these users can't be used as mail recipients.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="0c4cf-114">Подготовка к работе</span><span class="sxs-lookup"><span data-stu-id="0c4cf-114">Before you begin</span></span>

- <span data-ttu-id="0c4cf-115">Чтобы открыть центр администрирования Exchange, ознакомьтесь со статьей [центр администрирования Exchange в Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="0c4cf-115">To open the Exchange admin center, see [Exchange admin center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="0c4cf-p105">Для выполнения этих процедур необходимы соответствующие разрешения. Сведения о необходимых разрешениях см. в статье Запись "Пользователи, контакты и группы ролей" в разделе [Разрешения на функции в службе EOP](feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="0c4cf-p105">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Users, Contacts, and Role Groups" entry in [Feature permissions in EOP](feature-permissions-in-eop.md).</span></span>

- <span data-ttu-id="0c4cf-118">Имейте в виду, что при создании почтовых пользователей с помощью командлетов PowerShell для Exchange Online Protection вы можете столкнуться с регулированием.</span><span class="sxs-lookup"><span data-stu-id="0c4cf-118">Be aware that when creating mail users by using Exchange Online Protection PowerShell cmdlets, you may encounter throttling.</span></span>

- <span data-ttu-id="0c4cf-119">Команды PowerShell, приведенные в этом разделе, используют метод пакетной обработки, который приводит к задержке распространения в течение нескольких минут до того, как результаты команд будут видны.</span><span class="sxs-lookup"><span data-stu-id="0c4cf-119">The PowerShell commands in this topic use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="0c4cf-120">Чтобы узнать, как использовать Windows PowerShell для подключения к Exchange Online Protection, ознакомьтесь [со статьей подключение к PowerShell для Exchange Online Protection](http://technet.microsoft.com/library/054e0fd7-d465-4572-93f8-a00a9136e4d1.aspx).</span><span class="sxs-lookup"><span data-stu-id="0c4cf-120">To learn how to use Windows PowerShell to connect to Exchange Online Protection, see [Connect to Exchange Online Protection PowerShell](http://technet.microsoft.com/library/054e0fd7-d465-4572-93f8-a00a9136e4d1.aspx).</span></span>

- <span data-ttu-id="0c4cf-121">Дополнительные сведения о сочетаниях клавиш, которые могут применяться к процедурам, описанным в этой статье, приведены в статье [сочетания клавиш для центра администрирования Exchange в Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="0c4cf-121">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="0c4cf-122">Возникли проблемы?</span><span class="sxs-lookup"><span data-stu-id="0c4cf-122">Having problems?</span></span> <span data-ttu-id="0c4cf-123">Обратитесь за помощью к форуму [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .</span><span class="sxs-lookup"><span data-stu-id="0c4cf-123">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-directory-synchronization-to-manage-mail-users"></a><span data-ttu-id="0c4cf-124">Управление почтовыми пользователями с помощью синхронизации службы каталогов</span><span class="sxs-lookup"><span data-stu-id="0c4cf-124">Use directory synchronization to manage mail users</span></span>

<span data-ttu-id="0c4cf-125">В этом разделе представлены сведения об управлении пользователями электронной почты с помощью синхронизации службы каталогов.</span><span class="sxs-lookup"><span data-stu-id="0c4cf-125">This section provides information about managing email users by using directory synchronization.</span></span>

<span data-ttu-id="0c4cf-126">**Примечания.**</span><span class="sxs-lookup"><span data-stu-id="0c4cf-126">**Notes**:</span></span>

- <span data-ttu-id="0c4cf-127">Если вы используете синхронизацию службы каталогов для управления получателями, вы по-прежнему можете добавлять пользователей в центр администрирования Microsoft 365 и управлять ими, но они не будут синхронизированы с локальной службой Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0c4cf-127">If you use directory synchronization to manage your recipients, you can still add and manage users in the Microsoft 365 admin center, but they will not be synchronized with your on-premises Active Directory.</span></span> <span data-ttu-id="0c4cf-128">Это связано с тем, что синхронизация службы каталогов синхронизирует только получателей **из** локальной службы Active Directory **с** облаком.</span><span class="sxs-lookup"><span data-stu-id="0c4cf-128">This is because directory synchronization only syncs recipients **from** your on-premises Active Directory **to** the cloud.</span></span>

- <span data-ttu-id="0c4cf-129">Синхронизация службы каталогов рекомендуется для использования со следующими функциями:</span><span class="sxs-lookup"><span data-stu-id="0c4cf-129">Directory synchronization is recommended for use with the following features:</span></span>

  - <span data-ttu-id="0c4cf-130">**Списки надежных отправителей и заблокированных отправителей Outlook**: при синхронизации со службой эти списки занимают более высокий приоритет, чем фильтрация нежелательной почты в службе.</span><span class="sxs-lookup"><span data-stu-id="0c4cf-130">**Outlook safe sender and blocked sender lists**: When synchronized to the service, these lists will take precedence over spam filtering in the service.</span></span> <span data-ttu-id="0c4cf-131">Это позволяет пользователям управлять собственными списками безопасных и заблокированных отправителей индивидуально для каждого пользователя или для каждого домена.</span><span class="sxs-lookup"><span data-stu-id="0c4cf-131">This lets users manage their own safe sender and blocked sender lists on a per-user or per-domain basis.</span></span>

  - <span data-ttu-id="0c4cf-132">**Пограничная блокировка на основе каталогов (DBEB)**: Дополнительные сведения о DBEB см. [в статье Использование пограничной блокировки на основе каталогов для отклонения сообщений, отправляемых недопустимым получателям](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx).</span><span class="sxs-lookup"><span data-stu-id="0c4cf-132">**Directory Based Edge Blocking (DBEB)**: For more information about DBEB, see [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx).</span></span>

  - <span data-ttu-id="0c4cf-133">**Карантин нежелательной почты конечного пользователя**: чтобы получить доступ к карантину нежелательной почты конечного пользователя, конечные пользователи должны иметь действительный идентификатор пользователя и пароль Office 365.</span><span class="sxs-lookup"><span data-stu-id="0c4cf-133">**End user spam quarantine**: In order to access the end user spam quarantine, end users must have a valid Office 365 user ID and password.</span></span> <span data-ttu-id="0c4cf-134">EOP клиенты, защищающие локальные почтовые ящики, должны быть действительными пользователями электронной почты.</span><span class="sxs-lookup"><span data-stu-id="0c4cf-134">EOP customers protecting on-premises mailboxes must be valid email users.</span></span>
 
  - <span data-ttu-id="0c4cf-135">**Правила**для рабочего процесса: при использовании синхронизации службы каталогов существующие пользователи и группы Active Directory автоматически отправляются в облако, и вы можете создавать правила для поток обработки почты (также называемые правилами транспорта), предназначенные для определенных пользователей и/или группы без необходимости вручную добавлять их через центр администрирования Exchange или Exchange Online Protection PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0c4cf-135">**Mail flow rules**: When you use directory synchronization, your existing Active Directory users and groups are automatically uploaded to the cloud, and you can then create mail flow rules (also known as transport rules) that target specific users and/or groups without having to manually add them via the the EAC or Exchange Online Protection PowerShell.</span></span> <span data-ttu-id="0c4cf-136">Обратите внимание на то, что [динамические группы рассылки](https://go.microsoft.com/fwlink/?LinkId=507569) невозможно синхронизировать через синхронизацию службы каталогов.</span><span class="sxs-lookup"><span data-stu-id="0c4cf-136">Note that [dynamic distribution groups](https://go.microsoft.com/fwlink/?LinkId=507569) can't be synchronized via directory synchronization.</span></span>

<span data-ttu-id="0c4cf-137">Получите необходимые разрешения и подготовьтесь к синхронизации службы каталогов, как описано в статье [Подготовка к синхронизации службы каталогов](https://go.microsoft.com/fwlink/p/?LinkId=308908).</span><span class="sxs-lookup"><span data-stu-id="0c4cf-137">Get the necessary permissions and prepare for directory synchronization, as described in [Prepare for directory synchronization](https://go.microsoft.com/fwlink/p/?LinkId=308908).</span></span>

### <a name="to-synchronize-user-directories-with-azure-active-directory-connect-aad-connect"></a><span data-ttu-id="0c4cf-138">Синхронизация каталогов пользователей с помощью Azure Active Directory Connect (AAD Connect)</span><span class="sxs-lookup"><span data-stu-id="0c4cf-138">To synchronize user directories with Azure Active Directory Connect (AAD Connect)</span></span>

<span data-ttu-id="0c4cf-139">Чтобы синхронизировать пользователей с Azure Active Directory (AAD), необходимо сначала **активировать синхронизацию службы каталогов**, как описано в разделе [Активация синхронизации службы каталогов](https://go.microsoft.com/fwlink/p/?LinkId=308909).</span><span class="sxs-lookup"><span data-stu-id="0c4cf-139">To synchronize users to Azure Active Directory (AAD) you first have to **activate directory synchronization**, as described in [Activate directory synchronization](https://go.microsoft.com/fwlink/p/?LinkId=308909).</span></span>

<span data-ttu-id="0c4cf-140">Далее это установка и настройка локального компьютера для запуска AAD Connect (если у вас еще нет еще одной проверки времени).</span><span class="sxs-lookup"><span data-stu-id="0c4cf-140">Next is the installation and configuration of an on-premises computer to run AAD Connect (if you don't already have one -- something worth checking ahead of time).</span></span> <span data-ttu-id="0c4cf-141">При [настройке AAD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express) вы узнаете о том, как настроить и синхронизировать учетные записи из локальной среды в Azure AD с помощью AAD Connect.</span><span class="sxs-lookup"><span data-stu-id="0c4cf-141">The [Setting up AAD Connect, the express way](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express) topic tells you how to setup and synchronize your accounts from on-premises to Azure AD with AAD Connect.</span></span>

<span data-ttu-id="0c4cf-142">Прежде чем выполнять эту работу, убедитесь, [что вы отвечаете за необходимые условия](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites), и [выберите тип установки](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation).</span><span class="sxs-lookup"><span data-stu-id="0c4cf-142">But before you do that work, make certain [you meet prerequisites](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites), and [choose your installation type](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation).</span></span> <span data-ttu-id="0c4cf-143">Предыдущая статья содержит краткую статью об экспресс-установках.</span><span class="sxs-lookup"><span data-stu-id="0c4cf-143">The earlier link is to a short article for express installs.</span></span> <span data-ttu-id="0c4cf-144">Кроме того, при необходимости можно найти статьи по [настраиваемым установкам](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)или [пройти проверку подлинности](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start) .</span><span class="sxs-lookup"><span data-stu-id="0c4cf-144">You can also find articles on [custom installations](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom), or [pass-through authentication](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start) if they're needed.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0c4cf-p113">Когда Мастер настройки средства синхронизации Azure Active Directory завершит работу, учетная запись **MSOL_AD_SYNC** будет создана в вашем лесу Active Directory. Она используется для чтения и синхронизации локальных данных Active Directory. Чтобы каталоги синхронизировались правильно, убедитесь, что порт TCP 443 на локальном сервере синхронизации службы каталогов открыт.</span><span class="sxs-lookup"><span data-stu-id="0c4cf-p113">When you finish the Azure Active Directory Sync Tool Configuration Wizard, the **MSOL_AD_SYNC** account is created in your Active Directory forest. This account is used to read and synchronize your on-premises Active Directory information. In order for directory synchronization to work correctly, make sure that TCP 443 on your local directory synchronization server is open.</span></span>

<span data-ttu-id="0c4cf-148">После настройки синхронизации обязательно убедитесь, что EOP правильно синхронизируется.</span><span class="sxs-lookup"><span data-stu-id="0c4cf-148">After configuring your sync, be sure to verify that EOP is synchronizing correctly.</span></span> <span data-ttu-id="0c4cf-149">В Центре администрирования Exchange перейдите в раздел **Получатели** \> **Контакты** и убедитесь, что список пользователей с локальной среды должным образом синхронизирован.</span><span class="sxs-lookup"><span data-stu-id="0c4cf-149">In the EAC, go to **Recipients** \> **Contacts** and view that the list of users was correctly synchronized from your on-premises environment.</span></span>

## <a name="use-the-eac-to-manage-mail-users"></a><span data-ttu-id="0c4cf-150">Управление почтовыми пользователями с помощью Центра администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="0c4cf-150">Use the EAC to manage mail users</span></span>

<span data-ttu-id="0c4cf-151">В этом разделе предоставлены сведения о добавлении пользователей электронной почты непосредственно в Центр администрирования Exchange и управлении ими.</span><span class="sxs-lookup"><span data-stu-id="0c4cf-151">This section provides information about adding and managing email users directly in the EAC.</span></span>

### <a name="use-the-eac-to-add-a-mail-user"></a><span data-ttu-id="0c4cf-152">Добавление почтового пользователя с помощью центра администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="0c4cf-152">Use the EAC to add a mail user</span></span>

1. <span data-ttu-id="0c4cf-153">Создайте пользователя электронной почты. Для этого перейдите в раздел **Получатели** \> **Контакты** в Центре администрирования Exchange, а затем нажмите кнопку **Создать +**.</span><span class="sxs-lookup"><span data-stu-id="0c4cf-153">Create an email user by going to go to **Recipients** \> **Contacts** in the EAC, and then clicking **New +**.</span></span>

2. <span data-ttu-id="0c4cf-154">На странице **Создание почтового пользователя** введите сведения о пользователе, в том числе приведенные ниже.</span><span class="sxs-lookup"><span data-stu-id="0c4cf-154">On the **New mail user** page, enter the user's information, including the following:</span></span>

   ****

   |<span data-ttu-id="0c4cf-155">**Свойство почтового пользователя**</span><span class="sxs-lookup"><span data-stu-id="0c4cf-155">**Mail user property**</span></span>|<span data-ttu-id="0c4cf-156">**Описание**</span><span class="sxs-lookup"><span data-stu-id="0c4cf-156">**Description**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="0c4cf-157">**Имя**, **Отчество** и **Фамилия**</span><span class="sxs-lookup"><span data-stu-id="0c4cf-157">**First name**, **Initials**, and **Last name**</span></span>|<span data-ttu-id="0c4cf-158">Введите полное имя пользователя в соответствующие поля.</span><span class="sxs-lookup"><span data-stu-id="0c4cf-158">Type the user's full name in the appropriate boxes.</span></span>|
   |<span data-ttu-id="0c4cf-159">**Отображаемое имя**</span><span class="sxs-lookup"><span data-stu-id="0c4cf-159">**Display name**</span></span>|<span data-ttu-id="0c4cf-p115">Введите имя до 64 символов в длину. По умолчанию в этом поле отображаются имена, введенные в поля **Имя**, **Инициалы** и **Фамилия** (при наличии). Отображаемое имя является обязательным параметром.  </span><span class="sxs-lookup"><span data-stu-id="0c4cf-p115">Type a name, using up to 64 characters. By default, this box shows the names in the **First name**, **Initials**, and **Last name** boxes if any. The display name is required.</span></span>|
   |<span data-ttu-id="0c4cf-163">**Псевдоним**</span><span class="sxs-lookup"><span data-stu-id="0c4cf-163">**Alias**</span></span>|<span data-ttu-id="0c4cf-p116">Введите уникальный псевдоним пользователя, содержащий до 64 символов. Псевдоним является обязательным параметром.</span><span class="sxs-lookup"><span data-stu-id="0c4cf-p116">Type a unique alias, using up to 64 characters, for the user. The alias is required.</span></span>|
   |<span data-ttu-id="0c4cf-166">**Внешний адрес электронной почты**</span><span class="sxs-lookup"><span data-stu-id="0c4cf-166">**External email address**</span></span>|<span data-ttu-id="0c4cf-167">Введите внешний адрес электронной почты пользователя.</span><span class="sxs-lookup"><span data-stu-id="0c4cf-167">Type the external email address of the user.</span></span>|
   |<span data-ttu-id="0c4cf-168">**Идентификатор пользователя**</span><span class="sxs-lookup"><span data-stu-id="0c4cf-168">**User id**</span></span>|<span data-ttu-id="0c4cf-p117">Введите имя, с помощью которого почтовый пользователь будет входить в службу. Учетное имя пользователя состоит из имени пользователя, который находится слева от символа @, и суффикса справа от этого символа. Обычно в качестве суффикса выступает имя домена, в котором размещается учетная запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="0c4cf-p117">Type the name that the mail user will use to sign in to the service. The user sign-in name consists of a user name on the left side of the at (@) symbol and a suffix on the right side. Typically, the suffix is the domain name in which the user account resides.</span></span>|
   |<span data-ttu-id="0c4cf-172">**Новый пароль**</span><span class="sxs-lookup"><span data-stu-id="0c4cf-172">**New password**</span></span>|<span data-ttu-id="0c4cf-p118">Введите пароль, с помощью которого почтовый пользователь будет входить в службу. Убедитесь, что введенный пароль соответствует требованиям к длине, сложности и истории паролей, предъявляемым для домена, в котором создается учетная запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="0c4cf-p118">Type the password that the mail user will use to sign in to the service. Make sure that the password you supply complies with the password length, complexity, and history requirements of the domain in which you're creating the user account.</span></span>|
   |<span data-ttu-id="0c4cf-175">**Подтверждение пароля**</span><span class="sxs-lookup"><span data-stu-id="0c4cf-175">**Confirm password**</span></span>|<span data-ttu-id="0c4cf-176">Повторно введите пароль, чтобы подтвердить его.</span><span class="sxs-lookup"><span data-stu-id="0c4cf-176">Retype the password to confirm it.</span></span>|

3. <span data-ttu-id="0c4cf-p119">Нажмите кнопку **Сохранить**, чтобы создать нового пользователя электронной почты. Новый пользователь должен отобразиться в списке пользователей.</span><span class="sxs-lookup"><span data-stu-id="0c4cf-p119">Click **Save** to create the new email user. The new user should appear in the list of users.</span></span>

### <a name="use-the-eac-to-edit-or-remove-a-mail-user"></a><span data-ttu-id="0c4cf-179">Использование центра администрирования Exchange для изменения или удаления почтового пользователя</span><span class="sxs-lookup"><span data-stu-id="0c4cf-179">Use the EAC to edit or remove a mail user</span></span>

- <span data-ttu-id="0c4cf-180">В Центре администрирования Exchange перейдите в раздел **Получатели** \> **Контакты**.</span><span class="sxs-lookup"><span data-stu-id="0c4cf-180">In the EAC, go to **Recipients** \> **Contacts**.</span></span> <span data-ttu-id="0c4cf-181">В списке пользователей выберите пользователя, которого нужно просмотреть или изменить, а затем нажмите кнопку **изменить** ![значок](../media/ITPro-EAC-EditIcon.gif) редактирования, чтобы обновить параметры пользователя по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="0c4cf-181">In the list of users, click the user that you want to view or change, and then select **Edit** ![Edit icon](../media/ITPro-EAC-EditIcon.gif) to update the user settings as needed.</span></span> <span data-ttu-id="0c4cf-182">Вы можете изменить имя, псевдоним или контактные данные пользователя, а также записать подробные сведения о его роли в организации.</span><span class="sxs-lookup"><span data-stu-id="0c4cf-182">You can change the user's name, alias, or contact information, and you can record detailed information about the user's role in the organization.</span></span> <span data-ttu-id="0c4cf-183">Вы также можете выбрать пользователя и нажать кнопку **Удалить** ![значок](../media/ITPro-EAC-RemoveIcon.gif) удалить, чтобы удалить его.</span><span class="sxs-lookup"><span data-stu-id="0c4cf-183">You can also select a user and then choose **Remove** ![Remove icon](../media/ITPro-EAC-RemoveIcon.gif) to delete it.</span></span>

## <a name="use-exchange-online-protection-powershell-to-manage-mail-users"></a><span data-ttu-id="0c4cf-184">Управление почтовыми пользователями с помощью PowerShell Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="0c4cf-184">Use Exchange Online Protection PowerShell to manage mail users</span></span>

<span data-ttu-id="0c4cf-185">В этом разделе приведены сведения о добавлении почтовых пользователей и управлении ими с помощью удаленной консоли Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0c4cf-185">This section provides information about adding and managing mail users by using remote Windows PowerShell.</span></span>

### <a name="use-eop-powershell-to-add-a-mail-user"></a><span data-ttu-id="0c4cf-186">Добавление почтового пользователя с помощью EOP PowerShell</span><span class="sxs-lookup"><span data-stu-id="0c4cf-186">Use EOP PowerShell to add a mail user</span></span>

<span data-ttu-id="0c4cf-187">В этом примере с помощью командлета [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-eopmailuser) создается учетная запись пользователя с включенной поддержкой почты в EOP для Григория Иванова с такими сведениями:</span><span class="sxs-lookup"><span data-stu-id="0c4cf-187">This example uses the [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-eopmailuser) cmdlet to create a mail-enabled user account for Jeffrey Zeng in EOP with the following details:</span></span>

- <span data-ttu-id="0c4cf-188">Имя  Григорий, фамилия  Иванов.</span><span class="sxs-lookup"><span data-stu-id="0c4cf-188">The first name is Jeffrey and the last name is Zeng.</span></span>

- <span data-ttu-id="0c4cf-189">Имя  Григорий, отображаемое имя  Григорий Иванов.</span><span class="sxs-lookup"><span data-stu-id="0c4cf-189">The name is Jeffrey and the display name is Jeffrey Zeng.</span></span>

- <span data-ttu-id="0c4cf-190">Псевдоним  gregoryiv.</span><span class="sxs-lookup"><span data-stu-id="0c4cf-190">The alias is jeffreyz.</span></span>

- <span data-ttu-id="0c4cf-191">Внешний адрес электронной почты  givanov@tailspintoys.com.</span><span class="sxs-lookup"><span data-stu-id="0c4cf-191">The external email address is jzeng@tailspintoys.com.</span></span>

- <span data-ttu-id="0c4cf-192">Имя входа в Office 365  gregoryiv@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="0c4cf-192">The Office 365 sign in name is jeffreyz@contoso.onmicrosoft.com.</span></span>

- <span data-ttu-id="0c4cf-193">Пароль  Pa$$word1.</span><span class="sxs-lookup"><span data-stu-id="0c4cf-193">The password is Pa$$word1.</span></span>

```PowerShell
New-EOPMailUser -LastName Zeng -FirstName Jeffrey -DisplayName "Jeffrey Zeng" -Name Jeffrey -Alias jeffreyz -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -ExternalEmailAddress jeffreyz@tailspintoys.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force)
```

<span data-ttu-id="0c4cf-194">Чтобы убедиться, что это сработало, выполните следующую команду, чтобы отобразить сведения о новом почтовом пользователе Джеффри Иванова:</span><span class="sxs-lookup"><span data-stu-id="0c4cf-194">To verify that this worked, run the following command to display information about new mail user Jeffrey Zeng:</span></span>

```PowerShell
Get-User -Identity "Jeffrey Zeng"
```

<span data-ttu-id="0c4cf-195">Подробные сведения о синтаксисе и параметрах можно найти в статье [Get – User](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-user).</span><span class="sxs-lookup"><span data-stu-id="0c4cf-195">For detailed syntax and parameter information, see [Get-User](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-user).</span></span>

### <a name="use-eop-powershell-to-edit-the-properties-of-a-mail-user"></a><span data-ttu-id="0c4cf-196">Изменение свойств почтового пользователя с помощью EOP PowerShell</span><span class="sxs-lookup"><span data-stu-id="0c4cf-196">Use EOP PowerShell to edit the properties of a mail user</span></span>

<span data-ttu-id="0c4cf-197">Просматривайте и изменяйте свойства почтовых пользователей с помощью командлетов [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) и [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopmailuser).</span><span class="sxs-lookup"><span data-stu-id="0c4cf-197">Use the [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) and [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopmailuser) cmdlets to view or change properties for mail users.</span></span>

<span data-ttu-id="0c4cf-198">В этом примере настраивается внешний адрес электронной почты для пользователя Марты Артемьевой.</span><span class="sxs-lookup"><span data-stu-id="0c4cf-198">This example sets the external email address for Pilar Pinilla.</span></span>

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

<span data-ttu-id="0c4cf-199">В этом примере значение "Компания" задано как Contoso для всех почтовых пользователей.</span><span class="sxs-lookup"><span data-stu-id="0c4cf-199">This example sets the Company property for all mail users to Contoso.</span></span>

```PowerShell
$Recip = Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')}
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

<span data-ttu-id="0c4cf-200">Чтобы проверить, что это сработало, используйте командлет [Get – Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) для проверки изменений.</span><span class="sxs-lookup"><span data-stu-id="0c4cf-200">To verify that this worked, use the [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) cmdlet to verify the changes.</span></span> <span data-ttu-id="0c4cf-201">(Обратите внимание, что вы можете просматривать несколько свойств для нескольких почтовых контактов.)</span><span class="sxs-lookup"><span data-stu-id="0c4cf-201">(Note that you can view multiple properties for multiple mail contacts.)</span></span>

```PowerShell
Get-Recipient -Identity "Pilar Pinilla" | Format-List
```

<span data-ttu-id="0c4cf-202">Проверьте изменения из предыдущего примера, в котором для свойства "Компания" было задано значение Contoso для всех пользователей почты. Для этого выполните такую команду:</span><span class="sxs-lookup"><span data-stu-id="0c4cf-202">In the previous example where the Company property was set to Contoso for all mail users, run the following command to verify the changes:</span></span>

```PowerShell
Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')} | Format-List Name,Company
```

> [!IMPORTANT]
> <span data-ttu-id="0c4cf-203">Этот командлет использует метод пакетной обработки, из-за чего результаты его выполнения становятся видны через несколько минут.</span><span class="sxs-lookup"><span data-stu-id="0c4cf-203">This cmdlet uses a batch processing method that results in a propagation delay of a few minutes before the results of the cmdlet are visible.</span></span>

### <a name="use-eop-powershell-to-remove-a-mail-user"></a><span data-ttu-id="0c4cf-204">Удаление почтового пользователя с помощью EOP PowerShell</span><span class="sxs-lookup"><span data-stu-id="0c4cf-204">Use EOP PowerShell to remove a mail user</span></span>

<span data-ttu-id="0c4cf-205">В этом примере командлет [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient/remove-eopmailuser) используется для удаления пользователя Григория Иванова:</span><span class="sxs-lookup"><span data-stu-id="0c4cf-205">This example uses the [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient/remove-eopmailuser) cmdlet to delete user Jeffrey Zeng:</span></span>

```PowerShell
Remove-EOPMailUser -Identity Jeffrey
```
<span data-ttu-id="0c4cf-206">Чтобы убедиться, что это сработало, выполните командлет [Get – Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) , чтобы убедиться, что пользователь почты больше не существует.</span><span class="sxs-lookup"><span data-stu-id="0c4cf-206">To verify that this worked, run the [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) cmdlet to verify that the mail user no longer exists.</span></span>

```PowerShell
Get-Recipient Jeffrey | Format-List
```
