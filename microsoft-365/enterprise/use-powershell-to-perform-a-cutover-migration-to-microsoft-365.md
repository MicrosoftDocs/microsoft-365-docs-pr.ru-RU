---
title: Прямая миграция в Microsoft 365 с помощью PowerShell
ms.author: sirkkuw
author: sirkkuw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: b468cb4b-a35c-43d3-85bf-65446998af40
description: Узнайте, как использовать PowerShell для перемещения контента из системы электронной почты из источника одновременно, выполняя переход на переход в Microsoft 365.
ms.openlocfilehash: 60bd3cb246e04aba37be06f7a951abbf25708412
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924808"
---
# <a name="use-powershell-to-perform-a-cutover-migration-to-microsoft-365"></a><span data-ttu-id="e3ece-103">Прямая миграция в Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="e3ece-103">Use PowerShell to perform a cutover migration to Microsoft 365</span></span>

<span data-ttu-id="e3ece-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="e3ece-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="e3ece-105">Вы можете перенести содержимое почтовых ящиков пользователей из системы исходных сообщений электронной почты в Microsoft 365 одновременно с помощью переноса нареза.</span><span class="sxs-lookup"><span data-stu-id="e3ece-105">You can migrate the contents of user mailboxes from a source email system to Microsoft 365 all at once by using a cutover migration.</span></span> <span data-ttu-id="e3ece-106">В этой статье описаны задачи, которые выполняются при прямой миграции электронной почты с помощью Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e3ece-106">This article walks you through the tasks for an email cutover migration by using Exchange Online PowerShell.</span></span>

<span data-ttu-id="e3ece-107">Просмотрев тему , Что нужно знать о переносе электронной почты в [Microsoft 365,](/Exchange/mailbox-migration/what-to-know-about-a-cutover-migration)вы можете получить обзор процесса миграции.</span><span class="sxs-lookup"><span data-stu-id="e3ece-107">By reviewing the topic, [What you need to know about a cutover email migration to Microsoft 365](/Exchange/mailbox-migration/what-to-know-about-a-cutover-migration), you can get an overview of the migration process.</span></span> <span data-ttu-id="e3ece-108">Ознакомившись с содержимым этой статьи, начните переносить почтовые ящики из одной почтовой системы в другую, руководствуясь приведенными в этой статье сведениями.</span><span class="sxs-lookup"><span data-stu-id="e3ece-108">When you're comfortable with the contents of that article, use this one to begin migrating mailboxes from one email system to another.</span></span>

> [!NOTE]
> <span data-ttu-id="e3ece-109">Вы также можете использовать центр администрирования Exchange для выполнения переноса перереза.</span><span class="sxs-lookup"><span data-stu-id="e3ece-109">You can also use the Exchange admin center to perform a cutover migration.</span></span> <span data-ttu-id="e3ece-110">См. [врезки переноса электронной почты в Microsoft 365.](/Exchange/mailbox-migration/cutover-migration-to-office-365)</span><span class="sxs-lookup"><span data-stu-id="e3ece-110">See [Perform a cutover migration of email to Microsoft 365](/Exchange/mailbox-migration/cutover-migration-to-office-365).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e3ece-111">Что нужно знать перед началом работы?</span><span class="sxs-lookup"><span data-stu-id="e3ece-111">What do you need to know before you begin?</span></span>

<span data-ttu-id="e3ece-112">Предполагаемое время для выполнения этой задачи: 2-5 минут для создания пакета миграции.</span><span class="sxs-lookup"><span data-stu-id="e3ece-112">Estimated time to complete this task: 2-5 minutes to create a migration batch.</span></span> <span data-ttu-id="e3ece-113">После запуска пакета миграции продолжительность миграции будет зависеть от количества почтовых ящиков в пакете, размера каждого почтового ящика и доступной пропускной способности сети.</span><span class="sxs-lookup"><span data-stu-id="e3ece-113">After the migration batch is started, the duration of the migration will vary based on the number of mailboxes in the batch, the size of each mailbox, and your available network capacity.</span></span> <span data-ttu-id="e3ece-114">Сведения о других факторах, влияющих на время переноса почтовых ящиков в Microsoft 365, см. в см. [в руб.](/Exchange/mailbox-migration/office-365-migration-best-practices)</span><span class="sxs-lookup"><span data-stu-id="e3ece-114">For information about other factors that affect how long it takes to migrate mailboxes to Microsoft 365, see [Migration Performance](/Exchange/mailbox-migration/office-365-migration-best-practices).</span></span>

<span data-ttu-id="e3ece-p105">Для выполнения этой процедуры (процедур) необходимы соответствующие разрешения. Сведения о необходимых разрешениях см. в пункте "Миграция" статьи [Разрешения получателей](/exchange/recipients-permissions-exchange-2013-help) в соответствующей таблице.</span><span class="sxs-lookup"><span data-stu-id="e3ece-p105">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Migration" entry in a table in the [Recipients Permissions](/exchange/recipients-permissions-exchange-2013-help) topic.</span></span>

<span data-ttu-id="e3ece-p106">Чтобы использовать командлеты Exchange Online PowerShell, вам необходимо войти в систему и импортировать командлеты в локальный сеанс Windows PowerShell. Инструкции см в статье [Подключение к Exchange Online с помощью удаленной оболочки PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="e3ece-p106">To use the Exchange Online PowerShell cmdlets, you need to sign in and import the cmdlets into your local Windows PowerShell session. See [Connect to Exchange Online using remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) for instructions.</span></span>

<span data-ttu-id="e3ece-119">Полный список команд миграции см. в статье [Командлеты перемещения и миграции](/powershell/exchange/).</span><span class="sxs-lookup"><span data-stu-id="e3ece-119">For a full list of migration commands, see [Move and migration cmdlets](/powershell/exchange/).</span></span>

## <a name="migration-steps"></a><span data-ttu-id="e3ece-120">Шаги миграции</span><span class="sxs-lookup"><span data-stu-id="e3ece-120">Migration steps</span></span>

### <a name="step-1-prepare-for-a-cutover-migration"></a><span data-ttu-id="e3ece-121">Шаг 1. Подготовка к прямой миграции</span><span class="sxs-lookup"><span data-stu-id="e3ece-121">Step 1: Prepare for a cutover migration</span></span>
<span data-ttu-id="e3ece-122"><a name="BK_Step1"> </a></span><span class="sxs-lookup"><span data-stu-id="e3ece-122"><a name="BK_Step1"> </a></span></span>

- <span data-ttu-id="e3ece-123">**Добавление локальной организации Exchange в качестве принятого домена организации Microsoft 365.**</span><span class="sxs-lookup"><span data-stu-id="e3ece-123">**Add your on-premises Exchange organization as an accepted domain of your Microsoft 365 organization.**</span></span> <span data-ttu-id="e3ece-124">Служба миграции использует SMTP-адрес локального почтового ящика для создания Microsoft Online Services и адреса электронной почты для новых почтовых ящиков Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e3ece-124">The migration service uses the SMTP address of your on-premises mailboxes to create the Microsoft Online Services user ID and email address for the new Microsoft 365 mailboxes.</span></span> <span data-ttu-id="e3ece-125">Миграция не удалась, если ваш домен Exchange не является принятым доменом или основным доменом организации Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e3ece-125">Migration will fail if your Exchange domain isn't an accepted domain or the primary domain of your Microsoft 365 organization.</span></span> <span data-ttu-id="e3ece-126">Дополнительные сведения см. в [дополнительных сведениях: Проверка домена.](../admin/setup/add-domain.md)</span><span class="sxs-lookup"><span data-stu-id="e3ece-126">For more information, see [Verify your domain](../admin/setup/add-domain.md).</span></span>

- <span data-ttu-id="e3ece-p108">**Настройте мобильный Outlook на локальном сервере Exchange.** Служба миграции электронной почты использует протокол RPC через HTTP, также называемый мобильный Outlook, для подключения к локальному серверу Exchange Server. Дополнительные сведения о настройке службы мобильный Outlook для Exchange 2010, Exchange 2007 и Exchange 2003 см. в следующих статьях.</span><span class="sxs-lookup"><span data-stu-id="e3ece-p108">**Configure Outlook Anywhere on your on-premises Exchange server.** The email migration service uses RPC over HTTP, or Outlook Anywhere, to connect to your on-premises Exchange server. For information about how to set up Outlook Anywhere for Exchange 2010, Exchange 2007, and Exchange 2003, see the following:</span></span>

  - <span data-ttu-id="e3ece-130">[Exchange 2010. Включение мобильного Outlook](/previous-versions/office/exchange-server-2010/bb123542(v=exchg.141))</span><span class="sxs-lookup"><span data-stu-id="e3ece-130">[Exchange 2010: Enable Outlook Anywhere](/previous-versions/office/exchange-server-2010/bb123542(v=exchg.141))</span></span>

  - <span data-ttu-id="e3ece-131">[Exchange 2007. Инструкции по включению мобильного Outlook](/previous-versions/office/exchange-server-2007/bb123889(v=exchg.80))</span><span class="sxs-lookup"><span data-stu-id="e3ece-131">[Exchange 2007: How to Enable Outlook Anywhere](/previous-versions/office/exchange-server-2007/bb123889(v=exchg.80))</span></span>

  - <span data-ttu-id="e3ece-132">[Exchange 2003. Сценарии развертывания для RPC через HTTP](/previous-versions/tn-archive/bb124876(v=exchg.65))</span><span class="sxs-lookup"><span data-stu-id="e3ece-132">[Exchange 2003: Deployment Scenarios for RPC over HTTP](/previous-versions/tn-archive/bb124876(v=exchg.65))</span></span>

  - <span data-ttu-id="e3ece-133">[Настройка мобильного Outlook в Exchange 2003](/previous-versions/office/exchange-server-2007/aa996922(v=exchg.80))</span><span class="sxs-lookup"><span data-stu-id="e3ece-133">[How to Configure Outlook Anywhere with Exchange 2003](/previous-versions/office/exchange-server-2007/aa996922(v=exchg.80))</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="e3ece-p109">Конфигурацию мобильного Outlook необходимо настроить с использованием сертификата, выпущенного доверенным центром сертификации (ЦС). Настройка с использованием самозаверяющего сертификата невозможна. Дополнительные сведения см. в статье [Инструкции по настройке протокола SSL для мобильного Outlook](/previous-versions/office/exchange-server-2007/aa995982(v=exchg.80)).</span><span class="sxs-lookup"><span data-stu-id="e3ece-p109">Your Outlook Anywhere configuration must be configured with a certificate issued by a trusted certification authority (CA). It can't be configured with a self-signed certificate. For more information, see [How to Configure SSL for Outlook Anywhere](/previous-versions/office/exchange-server-2007/aa995982(v=exchg.80)).</span></span>

- <span data-ttu-id="e3ece-p110">**Проверьте возможность подключения к организации Exchange с помощью мобильного Outlook.** Проверьте настройки подключения с использованием следующих способов.</span><span class="sxs-lookup"><span data-stu-id="e3ece-p110">**Verify that you can connect to your Exchange organization using Outlook Anywhere.** Try one of these methods to test your connection settings:</span></span>

  - <span data-ttu-id="e3ece-139">Подключитесь к локальному почтовому ящику Exchange с помощью Microsoft Outlook из-за пределов корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="e3ece-139">Use Microsoft Outlook from outside your corporate network to connect to your on-premises Exchange mailbox.</span></span>

  - <span data-ttu-id="e3ece-p111">Проверьте настройки подключения с помощью [анализатора удаленного подключения Exchange](https://www.testexchangeconnectivity.com/) корпорации Майкрософт. Используйте средства мобильного Outlook (RPC через HTTP) или проверки автообнаружения Outlook.</span><span class="sxs-lookup"><span data-stu-id="e3ece-p111">Use the Microsoft [Exchange Remote Connectivity Analyzer](https://www.testexchangeconnectivity.com/) to test your connection settings. Use the Outlook Anywhere (RPC over HTTP) or Outlook Autodiscover tests.</span></span>

  - <span data-ttu-id="e3ece-142">В Exchange Online PowerShell выполните следующие команды.</span><span class="sxs-lookup"><span data-stu-id="e3ece-142">Run the following commands in Exchange Online PowerShell.</span></span>

  ```powershell
  $Credentials = Get-Credential
  ```

  ```powershell
  Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress <email address for on-premises administrator> -Credentials $credentials
  ```

- <span data-ttu-id="e3ece-143">**Назначьте для локальной учетной записи необходимые разрешения на доступ к почтовым ящикам в организации Exchange.**</span><span class="sxs-lookup"><span data-stu-id="e3ece-143">**Assign an on-premises user account the necessary permissions to access mailboxes in your Exchange organization.**</span></span> <span data-ttu-id="e3ece-144">Учетная запись локального пользователя, используемая для подключения к локальной организации Exchange (также называемая администратором миграции), должна иметь необходимые разрешения для доступа к локальному почтовому ящику, который необходимо перенести в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e3ece-144">The on-premises user account that you use to connect to your on-premises Exchange organization (also called the migration administrator) must have the necessary permissions to access the on-premises mailboxes that you want to migrate to Microsoft 365.</span></span> <span data-ttu-id="e3ece-145">Эта учетная запись пользователя необходима для создания конечной точки миграции в вашей локальной организации.</span><span class="sxs-lookup"><span data-stu-id="e3ece-145">This user account is used to create a migration endpoint to your on-premises organization.</span></span>

    <span data-ttu-id="e3ece-p113">В следующем списке перечислены права администратора, необходимые для переноса почтовых ящиков с помощью прямой миграции. У вас есть три варианта.</span><span class="sxs-lookup"><span data-stu-id="e3ece-p113">The following list shows the administrative privileges required to migrate mailboxes using a cutover migration. There are three possible options.</span></span>

  - <span data-ttu-id="e3ece-148">Администратор миграции должен быть членом группы **Администраторы домена** в службе каталогов Active Directory локальной организации.</span><span class="sxs-lookup"><span data-stu-id="e3ece-148">The migration administrator must be a member of the **Domain Admins** group in Active Directory in the on-premises organization.</span></span>

    <span data-ttu-id="e3ece-149">Или</span><span class="sxs-lookup"><span data-stu-id="e3ece-149">Or</span></span>

  - <span data-ttu-id="e3ece-150">Администратор миграции должен иметь разрешение **FullAccess** для всех локальных почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="e3ece-150">The migration administrator must be assigned the **FullAccess** permission for each on-premises mailbox.</span></span>

    <span data-ttu-id="e3ece-151">Или</span><span class="sxs-lookup"><span data-stu-id="e3ece-151">Or</span></span>

  - <span data-ttu-id="e3ece-152">Администратор миграции должен иметь разрешение **Получить как** в локальной базе данных, где хранятся почтовые ящики пользователей.</span><span class="sxs-lookup"><span data-stu-id="e3ece-152">The migration administrator must be assigned the **Receive As** permission on the on-premises mailbox database that stores the user mailboxes.</span></span>

- <span data-ttu-id="e3ece-p114">**Отключите единую систему обмена сообщениями.** Если для локальных почтовых ящиков включена поддержка единой системы обмена сообщениями, ее необходимо отключить, прежде чем переносить почтовые ящики. После завершения миграции поддержку единой системы обмена сообщениями для этих ящиков можно снова включить.</span><span class="sxs-lookup"><span data-stu-id="e3ece-p114">**Disable Unified Messaging.** If the on-premises mailboxes you're migrating are enabled for Unified Messaging (UM), you have to disable UM on the mailboxes before you migrate them. You can then enable UM on the mailboxes after the migration is complete.</span></span>

- <span data-ttu-id="e3ece-156">**Группы безопасности и делегаты** Служба миграции электронной почты не может определить, являются ли локально группы Active Directory группами безопасности или нет, поэтому она не может представить какие-либо перенесенные группы в качестве групп безопасности в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e3ece-156">**Security Groups and Delegates** The email migration service cannot detect whether on-premises Active Directory groups are security groups or not, so it cannot provision any migrated groups as security groups in Microsoft 365.</span></span> <span data-ttu-id="e3ece-157">Если вы хотите иметь группы безопасности в клиенте Microsoft 365, перед началом миграции отсечь необходимо сначала у вас в клиенте Microsoft 365 пустую группу безопасности с включенной почтой.</span><span class="sxs-lookup"><span data-stu-id="e3ece-157">If you want to have security groups in your Microsoft 365 tenant, you must first provision an empty mail-enabled security group in your Microsoft 365 tenant before starting the cutover migration.</span></span> <span data-ttu-id="e3ece-158">Кроме того, при этом способе перемещаются только почтовые ящики, почтовые пользователи, контакты и группы с поддержкой электронной почты.</span><span class="sxs-lookup"><span data-stu-id="e3ece-158">Additionally, this migration method only moves mailboxes, mail users, mail contacts, and mail-enabled groups.</span></span> <span data-ttu-id="e3ece-159">Если любой другой объект Active Directory, например пользователь, не перенесенный в Microsoft 365, назначен в качестве диспетчера или делегирования переносимого объекта, его необходимо удалить из объекта перед миграцией.</span><span class="sxs-lookup"><span data-stu-id="e3ece-159">If any other Active Directory object, such as user that is not migrated to Microsoft 365, is assigned as a manager or delegate to an object being migrated, they must be removed from the object before you migrate.</span></span>

### <a name="step-2-create-a-migration-endpoint"></a><span data-ttu-id="e3ece-160">Шаг 2. Создание конечной точки миграции</span><span class="sxs-lookup"><span data-stu-id="e3ece-160">Step 2: Create a migration endpoint</span></span>
<span data-ttu-id="e3ece-161"><a name="BK_Step2"> </a></span><span class="sxs-lookup"><span data-stu-id="e3ece-161"><a name="BK_Step2"> </a></span></span>

<span data-ttu-id="e3ece-162">Чтобы успешно перенести электронную почту, Microsoft 365 необходимо подключиться и связаться с системой электронной почты источника.</span><span class="sxs-lookup"><span data-stu-id="e3ece-162">To migrate email successfully, Microsoft 365 needs to connect and communicate with the source email system.</span></span> <span data-ttu-id="e3ece-163">Для этого в Microsoft 365 используется конечная точка миграции.</span><span class="sxs-lookup"><span data-stu-id="e3ece-163">To do this, Microsoft 365 uses a migration endpoint.</span></span> <span data-ttu-id="e3ece-164">Чтобы создать конечную точку миграции мобильного Outlook для прямой миграции, сначала [подключитесь к Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="e3ece-164">To create an Outlook Anywhere migration endpoint for cutover migration, first [connect to Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="e3ece-165">Полный список команд миграции см. в статье [Командлеты перемещения и миграции](/powershell/exchange/).</span><span class="sxs-lookup"><span data-stu-id="e3ece-165">For a full list of migration commands, see [Move and migration cmdlets](/powershell/exchange/).</span></span>

<span data-ttu-id="e3ece-166">В Exchange Online PowerShell выполните следующие команды.</span><span class="sxs-lookup"><span data-stu-id="e3ece-166">Run the following commands in Exchange Online PowerShell:</span></span>

```powershell
$Credentials = Get-Credential
```

<span data-ttu-id="e3ece-167">В примере используется командлет [Test-MigrationServerAvailability](/powershell/module/exchange/test-migrationserveravailability), который получает и проверяет параметры подключения к локальному серверу Exchange, а затем использует эти параметры для создания конечной точки миграции CutoverEndpoint.</span><span class="sxs-lookup"><span data-stu-id="e3ece-167">The example uses the [Test-MigrationServerAvailability](/powershell/module/exchange/test-migrationserveravailability) cmdlet to obtain and test the connection settings to the on-premises Exchange server, and then uses those connection settings to create the migration endpoint called "CutoverEndpoint".</span></span>

```powershell
$TSMA = Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress administrator@contoso.com -Credentials $credentials
```

```powershell
New-MigrationEndpoint -ExchangeOutlookAnywhere -Name CutoverEndpoint -ConnectionSettings $TSMA.ConnectionSettings
```

> [!NOTE]
> <span data-ttu-id="e3ece-p117">С помощью командлета **New-MigrationEndpoint** и параметра **-TargetDatabase** можно указать базу данных, которая будет использоваться службой. В противном случае база данных назначается случайным образом на сайте Службы федерации Active Directory (AD FS) 2.0, на котором расположен почтовый ящик управления.</span><span class="sxs-lookup"><span data-stu-id="e3ece-p117">The **New-MigrationEndpoint** cmdlet can be used to specify a database for the service to use by using the **-TargetDatabase** option. Otherwise a database is randomly assigned from the Active Directory Federation Services (AD FS) 2.0 site where the management mailbox is located.</span></span>

#### <a name="verify-it-worked"></a><span data-ttu-id="e3ece-170">Проверка работы</span><span class="sxs-lookup"><span data-stu-id="e3ece-170">Verify it worked</span></span>

<span data-ttu-id="e3ece-171">В Exchange Online PowerShell выполните следующую команду, чтобы отобразить сведения о конечной точке миграции CutoverEndpoint.</span><span class="sxs-lookup"><span data-stu-id="e3ece-171">In Exchange Online PowerShell, run the following command to display information about the "CutoverEndpoint" migration endpoint:</span></span>

```powershell
Get-MigrationEndpoint CutoverEndpoint | Format-List EndpointType,ExchangeServer,UseAutoDiscover,Max*

```

### <a name="step-3-create-the-cutover-migration-batch"></a><span data-ttu-id="e3ece-172">Шаг 3. Создание пакета прямой миграции</span><span class="sxs-lookup"><span data-stu-id="e3ece-172">Step 3: Create the cutover migration batch</span></span>
<span data-ttu-id="e3ece-173"><a name="BK_Step3"> </a></span><span class="sxs-lookup"><span data-stu-id="e3ece-173"><a name="BK_Step3"> </a></span></span>

<span data-ttu-id="e3ece-p118">Чтобы создать пакет для прямой миграции, выполните командлет **New-MigrationBatch** в Exchange Online PowerShell. Можно создать пакет миграции и запустить его обработку автоматически, включив параметр _AutoStart_. Кроме того, вы можете создать пакет миграции, а затем вручную запустить его с помощью командлета **Start-MigrationBatch**. В этом примере создается пакет миграции CutoverBatch и используется конечная точка миграции, созданная на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="e3ece-p118">You can use the **New-MigrationBatch** cmdlet in Exchange Online PowerShell to create a migration batch for a cutover migration. You can create a migration batch and start it automatically by including the _AutoStart_ parameter. Alternatively, you can create the migration batch and then manually start it afterwards by using the **Start-MigrationBatch** cmdlet. This example creates a migration batch called "CutoverBatch" and uses the migration endpoint that was created in the previous step.</span></span>

```powershell
New-MigrationBatch -Name CutoverBatch -SourceEndpoint CutoverEndpoint -AutoStart
```

<span data-ttu-id="e3ece-p119">В этом примере также создается пакет миграции CutoverBatch и используется конечная точка миграции, созданная на предыдущем шаге. Так как параметр  _AutoStart_ не включен, пакет миграции необходимо запустить вручную на панели мониторинга миграции или с помощью командлета **Start-MigrationBatch**. Как было сказано выше, в одно и то же время может существовать только один пакет прямой миграции.</span><span class="sxs-lookup"><span data-stu-id="e3ece-p119">This example also creates a migration batch called "CutoverBatch" and uses the migration endpoint that was created in the previous step. Because the  _AutoStart_ parameter isn't included, the migration batch has to be manually started on the migration dashboard or by using **Start-MigrationBatch** cmdlet. As previously stated, only one cutover migration batch can exist at a time.</span></span>

```powershell
New-MigrationBatch -Name CutoverBatch -SourceEndpoint CutoverEndpoint
```

#### <a name="verify-it-worked"></a><span data-ttu-id="e3ece-181">Проверка работы</span><span class="sxs-lookup"><span data-stu-id="e3ece-181">Verify it worked</span></span>

<span data-ttu-id="e3ece-182">Чтобы убедиться, что вы успешно создали пакет прямой миграции, выполните следующую команду в Exchange Online PowerShell для отображения сведений о новом пакете миграции.</span><span class="sxs-lookup"><span data-stu-id="e3ece-182">To verify that you've successfully created a migration batch for a cutover migration, run the following command in Exchange Online PowerShell to display information about the new migration batch:</span></span>

```powershell
Get-MigrationBatch | Format-List
```

### <a name="step-4-start-the-cutover-migration-batch"></a><span data-ttu-id="e3ece-183">Шаг 4. Запуск пакета прямой миграции</span><span class="sxs-lookup"><span data-stu-id="e3ece-183">Step 4: Start the cutover migration batch</span></span>
<span data-ttu-id="e3ece-184"><a name="BK_Step4"> </a></span><span class="sxs-lookup"><span data-stu-id="e3ece-184"><a name="BK_Step4"> </a></span></span>

<span data-ttu-id="e3ece-p120">Чтобы запустить пакет миграции в Exchange Online PowerShell, выполните следующую команду. Будет создан пакет миграции CutoverBatch.</span><span class="sxs-lookup"><span data-stu-id="e3ece-p120">To start the migration batch in Exchange Online PowerShell, run the following command. This will create a migration batch called "CutoverBatch".</span></span>

```powershell
Start-MigrationBatch -Identity CutoverBatch
```

#### <a name="verify-it-worked"></a><span data-ttu-id="e3ece-187">Проверка работы</span><span class="sxs-lookup"><span data-stu-id="e3ece-187">Verify it worked</span></span>

<span data-ttu-id="e3ece-p121">Если пакет миграции успешно запущен, состояние пакета на панели мониторинга миграции изменится на "Синхронизация". Чтобы убедиться, вы успешно запустили пакет миграции с помощью Exchange Online PowerShell, выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="e3ece-p121">If a migration batch is successfully started, its status on the migration dashboard is specified as Syncing. To verify that you've successfully started a migration batch using Exchange Online PowerShell, run the following command:</span></span>

```powershell
Get-MigrationBatch -Identity CutoverBatch |  Format-List Status
```

### <a name="step-5-route-your-email-to-microsoft-365"></a><span data-ttu-id="e3ece-190">Шаг 5. Маршрут электронной почты в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e3ece-190">Step 5: Route your email to Microsoft 365</span></span>
<span data-ttu-id="e3ece-191"><a name="BK_Step5"> </a></span><span class="sxs-lookup"><span data-stu-id="e3ece-191"><a name="BK_Step5"> </a></span></span>

<span data-ttu-id="e3ece-192">Почтовые системы используют запись DNS, которая называется записью MX, чтобы определять, куда нужно доставить электронную почту.</span><span class="sxs-lookup"><span data-stu-id="e3ece-192">Email systems use a DNS record called an MX record to figure out where to deliver emails.</span></span> <span data-ttu-id="e3ece-193">В процессе миграции электронной почты запись MX указывала на вашу исходную систему электронной почты.</span><span class="sxs-lookup"><span data-stu-id="e3ece-193">During the email migration process, your MX record was pointing to your source email system.</span></span> <span data-ttu-id="e3ece-194">Теперь, когда миграция электронной почты в Microsoft 365 завершена, пришло время указать запись MX в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e3ece-194">Now that the email migration to Microsoft 365 is complete, it's time to point your MX record at Microsoft 365.</span></span> <span data-ttu-id="e3ece-195">Это помогает убедиться, что электронная почта доставляется в почтовые ящики Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e3ece-195">This helps make sure that email is delivered to your Microsoft 365 mailboxes.</span></span> <span data-ttu-id="e3ece-196">Перемещая запись MX, вы также сможете отключить старую систему электронной почты, когда будете готовы сделать это.</span><span class="sxs-lookup"><span data-stu-id="e3ece-196">By moving the MX record, you can also you turn off your old email system when you're ready.</span></span>

<span data-ttu-id="e3ece-197">Для многих поставщиков DNS предоставляются отдельные инструкции по изменению записей MX.</span><span class="sxs-lookup"><span data-stu-id="e3ece-197">For many DNS providers, there are specific instructions to change your MX record.</span></span> <span data-ttu-id="e3ece-198">Если вашего поставщика DNS нет в списке или вы хотите в целом понять, как выполнять этот процесс, также существуют [общие инструкции по настройке записей MX](https://support.office.microsoft.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166#bkmk_add_mx).</span><span class="sxs-lookup"><span data-stu-id="e3ece-198">If your DNS provider isn't included, or if you want to get a sense of the general directions, [general MX record instructions](https://support.office.microsoft.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166#bkmk_add_mx) are provided as well.</span></span>

<span data-ttu-id="e3ece-p124">Системам электронной почты клиентов и партнеров может потребоваться до 72 часов, чтобы распознать измененную запись MX. Подождите по крайней мере 72 часа, прежде чем перейти к следующей задаче: [Шаг 6. Удаление пакета прямой миграции](use-powershell-to-perform-a-cutover-migration-to-microsoft-365.md#Bk_step6).</span><span class="sxs-lookup"><span data-stu-id="e3ece-p124">It can take up to 72 hours for the email systems of your customers and partners to recognize the changed MX record. Wait at least 72 hours before you proceed to the next task: [Step 6: Delete the cutover migration batch](use-powershell-to-perform-a-cutover-migration-to-microsoft-365.md#Bk_step6).</span></span>

### <a name="step-6-delete-the-cutover-migration-batch"></a><span data-ttu-id="e3ece-201">Шаг 6. Удаление пакета прямой миграции</span><span class="sxs-lookup"><span data-stu-id="e3ece-201">Step 6: Delete the cutover migration batch</span></span>
<span data-ttu-id="e3ece-202"><a name="Bk_step6"> </a></span><span class="sxs-lookup"><span data-stu-id="e3ece-202"><a name="Bk_step6"> </a></span></span>

<span data-ttu-id="e3ece-203">После изменения записи MX и проверки того, что вся электронная почта передается в почтовые ящики Microsoft 365, уведомите пользователей о том, что их почта будет отправлена в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e3ece-203">After you change the MX record and verify that all email is being routed to Microsoft 365 mailboxes, notify the users that their mail is going to Microsoft 365.</span></span> <span data-ttu-id="e3ece-204">Затем можно удалить пакет прямой миграции.</span><span class="sxs-lookup"><span data-stu-id="e3ece-204">After this, you can delete the cutover migration batch.</span></span> <span data-ttu-id="e3ece-205">Убедитесь в следующем, прежде чем удалить пакет миграции.</span><span class="sxs-lookup"><span data-stu-id="e3ece-205">Verify the following before you delete the migration batch.</span></span>

- <span data-ttu-id="e3ece-206">Все пользователи используют почтовые ящики Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e3ece-206">All users are using Microsoft 365 mailboxes.</span></span> <span data-ttu-id="e3ece-207">После удаления пакета почта, отправленная в почтовые ящики в локальном Exchange Server не копируется в соответствующие почтовые ящики Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e3ece-207">After the batch is deleted, mail sent to mailboxes on the on-premises Exchange Server isn't copied to the corresponding Microsoft 365 mailboxes.</span></span>

- <span data-ttu-id="e3ece-208">Почтовые ящики Microsoft 365 были синхронизированы по крайней мере один раз после начала непосредственной рассылки почты.</span><span class="sxs-lookup"><span data-stu-id="e3ece-208">Microsoft 365 mailboxes were synchronized at least once after mail began being sent directly to them.</span></span> <span data-ttu-id="e3ece-209">Чтобы сделать это, убедитесь, что значение в поле Последнее синхронизированное время для пакета миграции является более последним, чем когда почта начала маршрутизироваться непосредственно в почтовые ящики Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e3ece-209">To do this, make sure that the value in the Last Synced Time box for the migration batch is more recent than when mail started being routed directly to Microsoft 365 mailboxes.</span></span>

<span data-ttu-id="e3ece-210">Чтобы удалить пакет миграции CutoverBatch в Exchange Online PowerShell, выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="e3ece-210">To delete the "CutoverBatch" migration batch in Exchange Online PowerShell, run the following command:</span></span>

```powershell
Remove-MigrationBatch -Identity CutoverBatch
```

### <a name="section-7-assign-user-licenses"></a><span data-ttu-id="e3ece-211">Шаг 7. Назначение пользователям лицензий</span><span class="sxs-lookup"><span data-stu-id="e3ece-211">Section 7: Assign user licenses</span></span>
<span data-ttu-id="e3ece-212"><a name="BK_Step7"> </a></span><span class="sxs-lookup"><span data-stu-id="e3ece-212"><a name="BK_Step7"> </a></span></span>

 <span data-ttu-id="e3ece-213">**Активируйте учетные записи пользователей Microsoft 365 для перенесенных учетных записей, назначив лицензии.**</span><span class="sxs-lookup"><span data-stu-id="e3ece-213">**Activate Microsoft 365 user accounts for the migrated accounts by assigning licenses.**</span></span> <span data-ttu-id="e3ece-214">Если не назначить лицензию, почтовый ящик отключается после окончания льготного периода (30 дней).</span><span class="sxs-lookup"><span data-stu-id="e3ece-214">If you don't assign a license, the mailbox is disabled when the grace period ends (30 days).</span></span> <span data-ttu-id="e3ece-215">Чтобы назначить лицензию в центре администрирования Microsoft 365, см. в руб. Назначение или [неназначимые лицензии.](../admin/manage/assign-licenses-to-users.md)</span><span class="sxs-lookup"><span data-stu-id="e3ece-215">To assign a license in the Microsoft 365 admin center, see [Assign or unassign licenses](../admin/manage/assign-licenses-to-users.md).</span></span>

### <a name="step-8-complete-post-migration-tasks"></a><span data-ttu-id="e3ece-216">Шаг 8. Необходимые действия после миграции</span><span class="sxs-lookup"><span data-stu-id="e3ece-216">Step 8: Complete post-migration tasks</span></span>
<span data-ttu-id="e3ece-217"><a name="BK_Step8"> </a></span><span class="sxs-lookup"><span data-stu-id="e3ece-217"><a name="BK_Step8"> </a></span></span>

- <span data-ttu-id="e3ece-218">**Создайте DNS-запись автообнаружения, чтобы пользователи смогли с легкостью получить доступ к своим почтовым ящикам.**</span><span class="sxs-lookup"><span data-stu-id="e3ece-218">**Create an Autodiscover DNS record so users can easily get to their mailboxes.**</span></span> <span data-ttu-id="e3ece-219">После переноса всех почтовых ящиков в Microsoft 365 можно настроить запись DNS автообнаружаемых данных для организации Microsoft 365, чтобы пользователи могли легко подключаться к новым почтовым ящикам Microsoft 365 с помощью Outlook и мобильных клиентов.</span><span class="sxs-lookup"><span data-stu-id="e3ece-219">After all on-premises mailboxes are migrated to Microsoft 365, you can configure an Autodiscover DNS record for your Microsoft 365 organization to enable users to easily connect to their new Microsoft 365 mailboxes with Outlook and mobile clients.</span></span> <span data-ttu-id="e3ece-220">Эта новая запись DNS с автоматическим открытием должна использовать то же пространство имен, что и для организации Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e3ece-220">This new Autodiscover DNS record has to use the same namespace that you're using for your Microsoft 365 organization.</span></span> <span data-ttu-id="e3ece-221">Например, если пространство имен облачной службы имеет значение cloud.contoso.com, необходимо создать запись DNS автообнаружения autodiscover.cloud.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="e3ece-221">For example, if your cloud-based namespace is cloud.contoso.com, the Autodiscover DNS record you need to create is autodiscover.cloud.contoso.com.</span></span>

    <span data-ttu-id="e3ece-222">Если вы Exchange Server, необходимо также убедиться, что запись CNAME для автоматического разобновки DNS должна указать на Microsoft 365 как во внутренней, так и во внешней DNS после миграции, чтобы клиент Outlook подключил к правильному почтовому ящику.</span><span class="sxs-lookup"><span data-stu-id="e3ece-222">If you keep your Exchange Server, you should also make sure that Autodiscover DNS CNAME record has to point to Microsoft 365 in both internal and external DNS after the migration so that the Outlook client will to connect to the correct mailbox.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="e3ece-223">В Exchange 2007, Exchange 2010 и Exchange 2013 для параметра  `Set-ClientAccessServer AutodiscoverInternalConnectionURI` необходимо задать значение `Null`.</span><span class="sxs-lookup"><span data-stu-id="e3ece-223">In Exchange 2007, Exchange 2010, and Exchange 2013 you should also set `Set-ClientAccessServer AutodiscoverInternalConnectionURI` to `Null`.</span></span>

    <span data-ttu-id="e3ece-224">Microsoft 365 использует запись CNAME для реализации службы автонаружия для Outlook и мобильных клиентов.</span><span class="sxs-lookup"><span data-stu-id="e3ece-224">Microsoft 365 uses a CNAME record to implement the Autodiscover service for Outlook and mobile clients.</span></span> <span data-ttu-id="e3ece-225">Запись CNAME автообнаружения должна содержать следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="e3ece-225">The Autodiscover CNAME record must contain the following information:</span></span>

  - <span data-ttu-id="e3ece-226">**Псевдоним:** autodiscover</span><span class="sxs-lookup"><span data-stu-id="e3ece-226">**Alias:** autodiscover</span></span>

  - <span data-ttu-id="e3ece-227">**Целевой объект:** autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="e3ece-227">**Target:** autodiscover.outlook.com</span></span>

    <span data-ttu-id="e3ece-228">Дополнительные сведения см. в [добавлении записей DNS для подключения домена.](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span><span class="sxs-lookup"><span data-stu-id="e3ece-228">For more information, see [Add DNS records to connect your domain](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

- <span data-ttu-id="e3ece-229">**Спишите локальные сервера Exchange.**</span><span class="sxs-lookup"><span data-stu-id="e3ece-229">**Decommission on-premises Exchange servers.**</span></span> <span data-ttu-id="e3ece-230">После проверки того, что вся электронная почта передается непосредственно в почтовые ящики Microsoft 365, и вам больше не нужно поддерживать локальное почтовое сообщение или не планировать реализацию решения единого входного (SSO) решения, вы можете удалить Exchange с серверов и удалить локальное решение Exchange.</span><span class="sxs-lookup"><span data-stu-id="e3ece-230">After you've verified that all email is being routed directly to the Microsoft 365 mailboxes, and you no longer need to maintain your on-premises email organization or don't plan on implementing a single sign-on (SSO) solution, you can uninstall Exchange from your servers and remove your on-premises Exchange organization.</span></span>

    <span data-ttu-id="e3ece-231">Дополнительные сведения см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="e3ece-231">For more information, see the following:</span></span>

  - <span data-ttu-id="e3ece-232">[Изменение или удаление Exchange 2010](/previous-versions/office/exchange-server-2010/ee332361(v=exchg.141))</span><span class="sxs-lookup"><span data-stu-id="e3ece-232">[Modify or Remove Exchange 2010](/previous-versions/office/exchange-server-2010/ee332361(v=exchg.141))</span></span>

  - <span data-ttu-id="e3ece-233">[Удаление организации Exchange 2007](/previous-versions/office/exchange-server-2007/aa998313(v=exchg.80))</span><span class="sxs-lookup"><span data-stu-id="e3ece-233">[How to Remove an Exchange 2007 Organization](/previous-versions/office/exchange-server-2007/aa998313(v=exchg.80))</span></span>

  - <span data-ttu-id="e3ece-234">[Удаление сервера Exchange Server 2003](/previous-versions/tn-archive/bb125110(v=exchg.65))</span><span class="sxs-lookup"><span data-stu-id="e3ece-234">[How to Uninstall Exchange Server 2003](/previous-versions/tn-archive/bb125110(v=exchg.65))</span></span>