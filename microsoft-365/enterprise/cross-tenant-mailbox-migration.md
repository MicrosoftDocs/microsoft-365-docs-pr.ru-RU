---
title: Миграция почтовых ящиков между клиентами
description: Перемещение почтовых ящиков между клиентами Microsoft 365 или Office 365.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.date: 09/21/2020
ms.reviewer: georgiah
ms.custom:
- it-pro
ms.collection:
- M365-subscription-management
ms.openlocfilehash: 237d47502d28ec43978cef2c16e049ac9e90d7b1
ms.sourcegitcommit: f3059a0065496623e36e5a084cd2291e6b844597
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2021
ms.locfileid: "50040560"
---
# <a name="cross-tenant-mailbox-migration-preview"></a><span data-ttu-id="4dca8-103">Миграция почтовых ящиков между клиентами (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="4dca8-103">Cross-tenant mailbox migration (preview)</span></span>

<span data-ttu-id="4dca8-104">Ранее, когда клиенту Exchange Online требовалось переместить почтовые ящики в другой клиент в той же службе Exchange Online, им придется полностью отключить их в локальной сети, а затем перенести их в новый клиент.</span><span class="sxs-lookup"><span data-stu-id="4dca8-104">Previously, when an Exchange Online tenant needed to move mailboxes to another tenant in the same Exchange Online service, they would have to completely offboard them to on-premises and then onboard them to a new tenant.</span></span> <span data-ttu-id="4dca8-105">С помощью новой функции миграции почтовых ящиков между клиентами администраторы клиентов в исходных и целевых клиентах могут перемещать почтовые ящики между клиентами с минимальными зависимостями инфраструктуры в своих локальной системе.</span><span class="sxs-lookup"><span data-stu-id="4dca8-105">With the new cross-tenant mailbox migration feature, tenant administrators in both source and target tenants can move mailboxes between the tenants with minimal infrastructure dependencies in their on-premises systems.</span></span> <span data-ttu-id="4dca8-106">Это устраняет необходимость в отходящих и входящих почтовых ящиках.</span><span class="sxs-lookup"><span data-stu-id="4dca8-106">This removes the need to off-board and onboard mailboxes.</span></span>

<span data-ttu-id="4dca8-107">Как правило, во время слияния или инклюзности требуется возможность перемещения пользователей и контента в новый клиент.</span><span class="sxs-lookup"><span data-stu-id="4dca8-107">Commonly, during mergers or divestitures, you need the ability to move users and content into a new tenant.</span></span> <span data-ttu-id="4dca8-108">Когда администратор целевого клиента выполняет перемещение, оно называется перемещением pull, аналогично локальной миграции в облачную миграцию.</span><span class="sxs-lookup"><span data-stu-id="4dca8-108">When the target tenant administrator executes the move, it’s called a Pull move, similar to on-premises to cloud onboarding migrations.</span></span>

<span data-ttu-id="4dca8-109">Перемещение почтовых ящиков Exchange между клиентами полностью поддерживается администраторами клиентов с помощью хорошо известных интерфейсов, которые могут быть запрошены в более крупные процессы, необходимые для перехода пользователей в новую организацию.</span><span class="sxs-lookup"><span data-stu-id="4dca8-109">Cross-tenant Exchange mailbox moves are fully self-serviced by tenant administrators, using well known interfaces that can be scripted into the larger workflows needed to transition users to their new organization.</span></span> <span data-ttu-id="4dca8-110">Администраторы могут использовать для выполнения перемещения между клиентами с помощью роли управления "Перемещение почтовых `New-MigrationBatch` ящиков".</span><span class="sxs-lookup"><span data-stu-id="4dca8-110">Administrators can use the `New-MigrationBatch` cmdlet, available through the Move Mailboxes management role, to execute cross-tenant moves.</span></span> <span data-ttu-id="4dca8-111">Процесс перемещения включает проверки авторизации клиента во время синхронизации и проверки почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="4dca8-111">The move process includes tenant authorization checks during mailbox synchronization and finalization.</span></span> 
 
<span data-ttu-id="4dca8-112">Переносимые пользователи должны присутствовать в системе целевого клиента Exchange Online как mailUsers, помеченные определенными атрибутами для обеспечения перемещения между арендаторами.</span><span class="sxs-lookup"><span data-stu-id="4dca8-112">Users migrating must be present in the target tenant Exchange Online system as MailUsers, marked with specific attributes to enable the cross-tenant moves.</span></span> <span data-ttu-id="4dca8-113">Система не сможет двигаться для пользователей, которые неправильно настроены в целевом клиенте.</span><span class="sxs-lookup"><span data-stu-id="4dca8-113">The system will fail moves for users that are not properly set up in the target tenant.</span></span>  

<span data-ttu-id="4dca8-114">После завершения перемещения исходный системный почтовый ящик преобразуется в MailUser, а targetAddress (как ExternalEmailAddress в Exchange) помещен адресом маршрутации в целевой клиент.</span><span class="sxs-lookup"><span data-stu-id="4dca8-114">When the moves are complete, the source system mailbox is converted to MailUser and the targetAddress (shown as ExternalEmailAddress in Exchange) is stamped with the routing address to the destination tenant.</span></span> <span data-ttu-id="4dca8-115">Этот процесс оставляет устаревший mailUser в клиенте-источнике и позволяет в течение определенного периода сосуществования и маршрутизации почты.</span><span class="sxs-lookup"><span data-stu-id="4dca8-115">This process leaves the legacy MailUser in the source tenant, and allows for a period of co-existence and mail routing.</span></span> <span data-ttu-id="4dca8-116">Если бизнес-процессы позволяют, исходный клиент может удалить исходный mailUser или преобразовать его в почтовый контакт.</span><span class="sxs-lookup"><span data-stu-id="4dca8-116">When business processes allow, the source tenant may remove the source MailUser or convert them to a mail contact.</span></span> 

<span data-ttu-id="4dca8-117">Миграция почтовых ящиков Exchange между клиентами поддерживается только для клиентов в гибридной или облачной службе или любой комбинации этих двух вариантов.</span><span class="sxs-lookup"><span data-stu-id="4dca8-117">Cross-tenant Exchange mailbox migrations are supported for tenants in hybrid or cloud only, or any combination of the two.</span></span>

<span data-ttu-id="4dca8-118">В этой статье описывается процесс перемещения почтовых ящиков между клиентами и данная статья содержит инструкции по подготовке исходных и целевых клиентов для перемещения содержимого.</span><span class="sxs-lookup"><span data-stu-id="4dca8-118">This article describes the process for cross-tenant mailbox moves and provides guidance on how to prepare source and target tenants for the content move.</span></span>  

## <a name="preparing-source-and-target-tenants"></a><span data-ttu-id="4dca8-119">Подготовка исходных и целевых клиентов</span><span class="sxs-lookup"><span data-stu-id="4dca8-119">Preparing source and target tenants</span></span>

<span data-ttu-id="4dca8-120">Для миграции почтовых ящиков Exchange между клиентами требуется авторизация и области для миграции между клиентами.</span><span class="sxs-lookup"><span data-stu-id="4dca8-120">The Cross-tenant Exchange mailbox migration feature requires authorization and scoping for cross-tenant migrations.</span></span> <span data-ttu-id="4dca8-121">С помощью приложений Azure Enterprise и решений хранилища Key Vault администраторы клиентов теперь могут управлять как авторизацией, так и разрешением миграции почтовых ящиков Exchange Online из одного клиента в другой.</span><span class="sxs-lookup"><span data-stu-id="4dca8-121">Using the Azure Enterprise application and Key Vault storage solutions, tenant admins are now empowered to manage both authorization and scoping of Exchange Online mailbox migrations from one tenant to another.</span></span> <span data-ttu-id="4dca8-122">Перемещение почтовых ящиков между клиентами поддерживает модель приглашений и согласия на создание приложения Azure Active Directory (Azure AD), используемого для проверки подлинности между парой клиента.</span><span class="sxs-lookup"><span data-stu-id="4dca8-122">Cross-tenant mailbox moves supports an invitation and consent model to establish an Azure Active Directory (Azure AD) application used for authentication between a tenant pair.</span></span> <span data-ttu-id="4dca8-123">Также требуются дополнительные компоненты, такие как связь организации и конечная точка миграции.</span><span class="sxs-lookup"><span data-stu-id="4dca8-123">Additional components such as an organization relationship and a migration endpoint are also required.</span></span>

<span data-ttu-id="4dca8-124">В этом разделе не содержатся конкретные действия, необходимые для подготовки объектов пользователей MailUser в целевом каталоге, а также пример команды для отправки пакета миграции.</span><span class="sxs-lookup"><span data-stu-id="4dca8-124">This section does not include the specific steps required to prepare the MailUser user objects in the target directory, nor does it include the sample command to submit a migration batch.</span></span> <span data-ttu-id="4dca8-125">Эти сведения [см. в подготовьте](#prepare-target-user-objects-for-migration) целевые объекты пользователей к миграции.</span><span class="sxs-lookup"><span data-stu-id="4dca8-125">Please see [Prepare target user objects for migration](#prepare-target-user-objects-for-migration) for this information.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4dca8-126">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="4dca8-126">Prerequisites</span></span>

<span data-ttu-id="4dca8-127">Для перемещения почтовых ящиков между клиентами необходимо, чтобы [azure Key Vault](https://docs.microsoft.com/azure/key-vault/basic-concepts) использовал приложение Azure для безопасного хранения сертификата и секрета, используемого для проверки подлинности и авторизации миграции почтовых ящиков из одного клиента в другой, удаляя все требования к совместному хранимым сертификатам и секретам между клиентами.</span><span class="sxs-lookup"><span data-stu-id="4dca8-127">The cross-tenant mailbox move feature requires [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/basic-concepts) to establish a tenant pair-specific Azure application to securely store and access the certificate/secret used to authenticate and authorize mailbox migration from one tenant to the other, removing any requirements to share certificates/secrets between tenants.</span></span> 

<span data-ttu-id="4dca8-128">Перед началом работы убедитесь, что у вас есть необходимые разрешения для запуска сценариев развертывания для настройки хранилища Azure Key Vault, приложения перемещения почтовых ящиков, конечной точки миграции EXO и связи организации EXO.</span><span class="sxs-lookup"><span data-stu-id="4dca8-128">Before starting, be sure you have the necessary permissions to run the deployment scripts in order to configure Azure Key Vault, Move Mailbox application, EXO Migration Endpoint, and the EXO Organization Relationship.</span></span> <span data-ttu-id="4dca8-129">Как правило, глобальный администратор имеет разрешение на выполнение всех действий по настройке.</span><span class="sxs-lookup"><span data-stu-id="4dca8-129">Typically, Global Admin has permission to perform all configuration steps.</span></span>

<span data-ttu-id="4dca8-130">Кроме того, группы безопасности с включенной поддержкой почты в клиенте-источнике необходимы перед запуском программы установки.</span><span class="sxs-lookup"><span data-stu-id="4dca8-130">Additionally, mail-enabled security groups in the source tenant are required prior to running setup.</span></span> <span data-ttu-id="4dca8-131">Эти группы используются для области списка почтовых ящиков, которые могут перемещаться из клиента источника (или иногда называется ресурсом) в целевой клиент.</span><span class="sxs-lookup"><span data-stu-id="4dca8-131">These groups are used to scope the list of mailboxes that can move from source (or sometimes referred to as resource) tenant to the target tenant.</span></span> <span data-ttu-id="4dca8-132">Это позволяет администратору клиента-источника ограничить или ограничить область действия определенного набора почтовых ящиков, которые необходимо перенести, не позволяя непреднамеренным пользователям перенести их.</span><span class="sxs-lookup"><span data-stu-id="4dca8-132">This allows the source tenant admin to restrict or scope the specific set of mailboxes that need to be moved, preventing unintended users from being migrated.</span></span> <span data-ttu-id="4dca8-133">Вложенные группы не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="4dca8-133">Nested groups are not supported.</span></span>

<span data-ttu-id="4dca8-134">Вам также потребуется связаться с надежной партнерской компанией (с которой будут перемещены почтовые ящики), чтобы получить их ИД клиента Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4dca8-134">You will also need to communicate with your trusted partner company (with whom you will be moving mailboxes) to obtain their Microsoft 365 tenant ID.</span></span> <span data-ttu-id="4dca8-135">Этот ИД клиента используется в поле "Связь `DomainName` организации".</span><span class="sxs-lookup"><span data-stu-id="4dca8-135">This tenant ID is used in the Organization Relationship `DomainName` field.</span></span>

<span data-ttu-id="4dca8-136">Чтобы получить ИД клиента подписки, войдите в Центр администрирования Microsoft 365 и перейдите в [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) .</span><span class="sxs-lookup"><span data-stu-id="4dca8-136">To obtain the tenant ID of a subscription, sign-in to the Microsoft 365 admin center and go to [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> <span data-ttu-id="4dca8-137">Щелкните значок копирования для свойства Tenant ID, чтобы скопировать его в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="4dca8-137">Click the copy icon for the Tenant ID property to copy it to the clipboard.</span></span>

<span data-ttu-id="4dca8-138">Вот как работает этот процесс.</span><span class="sxs-lookup"><span data-stu-id="4dca8-138">Here is how the process works.</span></span>

:::image type="content" source="../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png" alt-text="Подготовка клиента к миграции почтовых ящиков.":::

<span data-ttu-id="4dca8-140">[См. более крупную версию этого изображения.](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)</span><span class="sxs-lookup"><span data-stu-id="4dca8-140">[See a larger version of this image](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png).</span></span>

<!--
[![Tenant preparation for mailbox migration](../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)
--> 

### <a name="prepare-tenants"></a><span data-ttu-id="4dca8-141">Подготовка клиентов</span><span class="sxs-lookup"><span data-stu-id="4dca8-141">Prepare tenants</span></span>

<span data-ttu-id="4dca8-142">На высоком уровне при выполнении сценариев установки выполняются следующие действия по настройке.</span><span class="sxs-lookup"><span data-stu-id="4dca8-142">At a high level, the following configuration actions take place when executing the setup scripts.</span></span>

<span data-ttu-id="4dca8-143">Подготовьте целевой клиент:</span><span class="sxs-lookup"><span data-stu-id="4dca8-143">Prepare the target tenant:</span></span>

1. <span data-ttu-id="4dca8-144">Если существующая группа ресурсов Azure не предоставлена, создается новая группа (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="4dca8-144">If an existing Azure Resource Group is not provided, a new one is created (SCRIPT).</span></span>
2. <span data-ttu-id="4dca8-145">Если существующее хранилище Key Vault не предоставлено, создается новое хранилище (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="4dca8-145">If an existing Key Vault is not provided, a new one is created (SCRIPT).</span></span>
3. <span data-ttu-id="4dca8-146">Для приложения миграции почтовых ящиков Office 365 Exchange Online (SCRIPT) создается новая политика доступа.</span><span class="sxs-lookup"><span data-stu-id="4dca8-146">A new Access Policy is created for the Office 365 Exchange Online Mailbox Migration application (SCRIPT).</span></span>
4. <span data-ttu-id="4dca8-147">Создается новый сертификат (или существующий, если он указан) для снесения секрета в приложение миграции (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="4dca8-147">A new certificate is created (or existing one, if specified) to hold the secret to the Migration application (SCRIPT).</span></span>
5. <span data-ttu-id="4dca8-148">Создается новое приложение Azure AD (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="4dca8-148">A new Azure AD application is created (SCRIPT).</span></span>
6. <span data-ttu-id="4dca8-149">Сертификат/секрет загружается в приложение миграции (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="4dca8-149">The certificate/secret is uploaded to the migration application (SCRIPT).</span></span>
7. <span data-ttu-id="4dca8-150">Приложению (SCRIPT) назначены разрешения на миграцию почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="4dca8-150">Mailbox migration permissions are assigned to the application (SCRIPT).</span></span>
8. <span data-ttu-id="4dca8-151">Сценарий развертывания приостанавливовка до тех пор, пока целевой администратор не согласится на использование собственного приложения (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="4dca8-151">The deployment script pauses until target admin consents to their own application (SCRIPT).</span></span>
9. <span data-ttu-id="4dca8-152">Администратор целевого клиента соглашается на разрешения, которые даются приложению (MANUAL).</span><span class="sxs-lookup"><span data-stu-id="4dca8-152">The target tenant admin consents to the permissions given to the application (MANUAL).</span></span>
10. <span data-ttu-id="4dca8-153">Создается связь организации с целевым клиентом (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="4dca8-153">An organization relationship is created to the target tenant (SCRIPT).</span></span>
11. <span data-ttu-id="4dca8-154">Создается конечная точка миграции, которая извлекает почтовые ящики в целевой клиент (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="4dca8-154">A migration endpoint is created to pull mailboxes to the target tenant (SCRIPT).</span></span>

<span data-ttu-id="4dca8-155">Подготовьте исходный клиент:</span><span class="sxs-lookup"><span data-stu-id="4dca8-155">Prepare the source tenant:</span></span>

1. <span data-ttu-id="4dca8-156">Администратор клиента-источника принимает согласие на приглашение приложения миграции почтовых ящиков из целевого клиента (MANUAL).</span><span class="sxs-lookup"><span data-stu-id="4dca8-156">The source tenant admin accepts consent to Mailbox Migration application invitation from the Target tenant (MANUAL).</span></span>
2. <span data-ttu-id="4dca8-157">Администратор клиента-источника создает в клиенте группу безопасности с включенной поддержкой почты, включаемую в список почтовых ящиков, которые могут быть перемещены приложением миграции (MANUAL).</span><span class="sxs-lookup"><span data-stu-id="4dca8-157">The source tenant admin creates a mail-enabled security group in their tenant to contain the list of mailboxes allowed to be moved by the migration application (MANUAL).</span></span>
3. <span data-ttu-id="4dca8-158">Создается связь организации с целевым клиентом, указывав, что приложение миграции почтовых ящиков должно использоваться для проверки OAuth, чтобы принять запрос на перемещение (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="4dca8-158">An organization relationship is created to the target tenant specifying the mailbox migration application should be used for OAuth verification to accept the move request (SCRIPT).</span></span>

#### <a name="step-by-step-instructions-for-the-target-tenant-admin"></a><span data-ttu-id="4dca8-159">Пошаговая инструкция для администратора целевого клиента</span><span class="sxs-lookup"><span data-stu-id="4dca8-159">Step-by-step instructions for the target tenant admin</span></span>

1. <span data-ttu-id="4dca8-160">Скачайте SetupCrossTenantRelationshipForTargetTenant.ps1 для настройки целевого клиента из [репозитория GitHub.](https://github.com/microsoft/cross-tenant/releases/tag/Preview)</span><span class="sxs-lookup"><span data-stu-id="4dca8-160">Download the SetupCrossTenantRelationshipForTargetTenant.ps1 script for the target tenant setup from the [GitHub repository](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span></span> 
2. <span data-ttu-id="4dca8-161">Сохраните сценарий (SetupCrossTenantRelationshipForTargetTenant.ps1) на компьютере, с которого будет выполняться сценарий.</span><span class="sxs-lookup"><span data-stu-id="4dca8-161">Save the script (SetupCrossTenantRelationshipForTargetTenant.ps1) to the computer from which you will be executing the script.</span></span>
3. <span data-ttu-id="4dca8-162">Создайте удаленное подключение PowerShell к целевому клиенту Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="4dca8-162">Create a Remote PowerShell connection to the Exchange Online target tenant.</span></span> <span data-ttu-id="4dca8-163">Опять же, убедитесь, что у вас есть необходимые разрешения для запуска сценариев развертывания для настройки хранилища и сертификата Azure Key Vault, приложения перемещения почтовых ящиков, конечной точки миграции EXO и связи организации EXO.</span><span class="sxs-lookup"><span data-stu-id="4dca8-163">Again, make sure you have the necessary permissions to run the deployment scripts in order to configure the Azure Key Vault storage and certificate, Move Mailbox application, EXO Migration Endpoint, and the EXO Organization Relationship.</span></span>
4. <span data-ttu-id="4dca8-164">Измените каталог папки файлов на расположение сценария или убедитесь, что сценарий в данный момент сохранен в расположении, в настоящее время в сеансе Удаленной powerShell.</span><span class="sxs-lookup"><span data-stu-id="4dca8-164">Change the file folder directory to the script location or verify the script is currently saved to the location currently in your Remote PowerShell session.</span></span>
5. <span data-ttu-id="4dca8-165">Запустите сценарий со следующими параметрами и значениями.</span><span class="sxs-lookup"><span data-stu-id="4dca8-165">Run the script with the following parameters and values.</span></span>

    | <span data-ttu-id="4dca8-166">Параметр</span><span class="sxs-lookup"><span data-stu-id="4dca8-166">Parameter</span></span> | <span data-ttu-id="4dca8-167">Значение</span><span class="sxs-lookup"><span data-stu-id="4dca8-167">Value</span></span> | <span data-ttu-id="4dca8-168">Обязательный или необязательный</span><span class="sxs-lookup"><span data-stu-id="4dca8-168">Required or Optional</span></span>
    |---------------------------------------------|-----------------|--------------|
    | <span data-ttu-id="4dca8-169">-TargetTenantDomain</span><span class="sxs-lookup"><span data-stu-id="4dca8-169">-TargetTenantDomain</span></span>                         | <span data-ttu-id="4dca8-170">Целевой домен клиента, например contoso \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="4dca8-170">Target tenant domain, such as contoso\.onmicrosoft.com.</span></span> | <span data-ttu-id="4dca8-171">Обязательна</span><span class="sxs-lookup"><span data-stu-id="4dca8-171">Required</span></span> |
    | <span data-ttu-id="4dca8-172">-ResourceTenantDomain</span><span class="sxs-lookup"><span data-stu-id="4dca8-172">-ResourceTenantDomain</span></span>                       | <span data-ttu-id="4dca8-173">Исходный домен клиента, например fabrikam \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="4dca8-173">Source tenant domain, such as fabrikam\.onmicrosoft.com.</span></span> | <span data-ttu-id="4dca8-174">Обязательна</span><span class="sxs-lookup"><span data-stu-id="4dca8-174">Required</span></span> |
    | <span data-ttu-id="4dca8-175">-ResourceTenantAdminEmail</span><span class="sxs-lookup"><span data-stu-id="4dca8-175">-ResourceTenantAdminEmail</span></span>                   | <span data-ttu-id="4dca8-176">Адрес электронной почты администратора клиента источника.</span><span class="sxs-lookup"><span data-stu-id="4dca8-176">Source tenant admin’s email address.</span></span> <span data-ttu-id="4dca8-177">Это исходный администратор клиента, который будет соглашаться на использование приложения миграции почтовых ящиков, отправленного от целевого администратора. Это администратор, который получит приглашение по электронной почте для приложения.</span><span class="sxs-lookup"><span data-stu-id="4dca8-177">This is the source tenant admin who will be consenting to the use of the mailbox migration application sent from the target admin. This is the admin who will receive the email invite for the application.</span></span> | <span data-ttu-id="4dca8-178">Обязательна</span><span class="sxs-lookup"><span data-stu-id="4dca8-178">Required</span></span> |
    | <span data-ttu-id="4dca8-179">-ResourceTenantId</span><span class="sxs-lookup"><span data-stu-id="4dca8-179">-ResourceTenantId</span></span>                           | <span data-ttu-id="4dca8-180">Код организации-источника клиента (GUID).</span><span class="sxs-lookup"><span data-stu-id="4dca8-180">Source tenant organization ID (GUID).</span></span> | <span data-ttu-id="4dca8-181">Обязательна</span><span class="sxs-lookup"><span data-stu-id="4dca8-181">Required</span></span> |
    | <span data-ttu-id="4dca8-182">-SubscriptionId</span><span class="sxs-lookup"><span data-stu-id="4dca8-182">-SubscriptionId</span></span>                             | <span data-ttu-id="4dca8-183">Подписка Azure, используемая для создания ресурсов.</span><span class="sxs-lookup"><span data-stu-id="4dca8-183">The Azure subscription to use for creating resources.</span></span> | <span data-ttu-id="4dca8-184">Обязательна</span><span class="sxs-lookup"><span data-stu-id="4dca8-184">Required</span></span> |
    | <span data-ttu-id="4dca8-185">-ResourceGroup</span><span class="sxs-lookup"><span data-stu-id="4dca8-185">-ResourceGroup</span></span>                              | <span data-ttu-id="4dca8-186">Имя группы ресурсов Azure, которая содержит хранилище Key Vault или будет содержать его.</span><span class="sxs-lookup"><span data-stu-id="4dca8-186">Azure resource group name that contains or will contain the Key Vault.</span></span> | <span data-ttu-id="4dca8-187">Обязательна</span><span class="sxs-lookup"><span data-stu-id="4dca8-187">Required</span></span> |
    | <span data-ttu-id="4dca8-188">-KeyVaultName</span><span class="sxs-lookup"><span data-stu-id="4dca8-188">-KeyVaultName</span></span>                               | <span data-ttu-id="4dca8-189">Экземпляр Azure Key Vault, в который будет храниться сертификат/секрет приложения миграции почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="4dca8-189">Azure Key Vault instance that will store your mailbox migration application certificate/secret.</span></span> | <span data-ttu-id="4dca8-190">Обязательна</span><span class="sxs-lookup"><span data-stu-id="4dca8-190">Required</span></span> |
    | <span data-ttu-id="4dca8-191">-CertificateName</span><span class="sxs-lookup"><span data-stu-id="4dca8-191">-CertificateName</span></span>                            | <span data-ttu-id="4dca8-192">Имя сертификата при создании или поиске сертификата в хранилище ключей.</span><span class="sxs-lookup"><span data-stu-id="4dca8-192">Certificate name when generating or searching for certificate in key vault.</span></span> | <span data-ttu-id="4dca8-193">Обязательна</span><span class="sxs-lookup"><span data-stu-id="4dca8-193">Required</span></span> |
    | <span data-ttu-id="4dca8-194">-CertificateSubject</span><span class="sxs-lookup"><span data-stu-id="4dca8-194">-CertificateSubject</span></span>                         | <span data-ttu-id="4dca8-195">Имя субъекта сертификата Azure Key Vault, например CN=contoso_fabrikam.</span><span class="sxs-lookup"><span data-stu-id="4dca8-195">Azure Key Vault certificate subject name, such as CN=contoso_fabrikam.</span></span> | <span data-ttu-id="4dca8-196">Обязательна</span><span class="sxs-lookup"><span data-stu-id="4dca8-196">Required</span></span> |
    | <span data-ttu-id="4dca8-197">-ExistingApplicationId</span><span class="sxs-lookup"><span data-stu-id="4dca8-197">-ExistingApplicationId</span></span>                      | <span data-ttu-id="4dca8-198">Приложение миграции почты, которое будет использовать, если приложение уже создано.</span><span class="sxs-lookup"><span data-stu-id="4dca8-198">Mail migration application to use if one was already created.</span></span> | <span data-ttu-id="4dca8-199">Необязательна</span><span class="sxs-lookup"><span data-stu-id="4dca8-199">Optional</span></span> |
    | <span data-ttu-id="4dca8-200">-AzureAppPermissions</span><span class="sxs-lookup"><span data-stu-id="4dca8-200">-AzureAppPermissions</span></span>                        | <span data-ttu-id="4dca8-201">Разрешения, необходимые для приложения миграции почтовых ящиков, такие как Exchange или MSGraph (Exchange для перемещения почтовых ящиков, MSGraph для использования этого приложения для отправки приглашения ссылки на согласие в клиент ресурсов).</span><span class="sxs-lookup"><span data-stu-id="4dca8-201">The permissions required to be given to the mailbox migration application, such as Exchange or MSGraph (Exchange for moving mailboxes, MSGraph for using this application to send a consent link invitation to resource tenant).</span></span> | <span data-ttu-id="4dca8-202">Обязательна</span><span class="sxs-lookup"><span data-stu-id="4dca8-202">Required</span></span> |
    | <span data-ttu-id="4dca8-203">-UseAppAndCertGeneratedForSendingInvitation</span><span class="sxs-lookup"><span data-stu-id="4dca8-203">-UseAppAndCertGeneratedForSendingInvitation</span></span> | <span data-ttu-id="4dca8-204">Параметр для использования приложения, созданного для миграции, который будет использоваться для отправки приглашения ссылки на согласие администратору клиента-источника. Если этот запрос не затмеен, в учетных данных целевого администратора будет предложено подключиться к диспетчеру приглашений Azure и отправить приглашение от имени целевого администратора.</span><span class="sxs-lookup"><span data-stu-id="4dca8-204">Parameter for using the application created for migration to be used for sending consent link invitation to source tenant admin. If not present this will prompt for the target admin’s credentials to connect to Azure invitation manager and send the invitation as target admin.</span></span> | <span data-ttu-id="4dca8-205">Необязательна</span><span class="sxs-lookup"><span data-stu-id="4dca8-205">Optional</span></span> |
    | <span data-ttu-id="4dca8-206">-KeyVaultAuditStorageAccountName</span><span class="sxs-lookup"><span data-stu-id="4dca8-206">-KeyVaultAuditStorageAccountName</span></span>            | <span data-ttu-id="4dca8-207">Учетная запись хранения, в которой будут храниться журналы аудита Key Vault.</span><span class="sxs-lookup"><span data-stu-id="4dca8-207">The storage account where Key Vault’s audit logs would be stored.</span></span> | <span data-ttu-id="4dca8-208">Необязательна</span><span class="sxs-lookup"><span data-stu-id="4dca8-208">Optional</span></span> |
    | <span data-ttu-id="4dca8-209">-KeyVaultAuditStorageResourceGroup</span><span class="sxs-lookup"><span data-stu-id="4dca8-209">-KeyVaultAuditStorageResourceGroup</span></span>          | <span data-ttu-id="4dca8-210">Группа ресурсов, которая содержит учетную запись хранения для хранения журналов аудита Key Vault.</span><span class="sxs-lookup"><span data-stu-id="4dca8-210">The resource group that contains the storage account for storing Key Vault audit logs.</span></span> | <span data-ttu-id="4dca8-211">Необязательна</span><span class="sxs-lookup"><span data-stu-id="4dca8-211">Optional</span></span> |
    ||||

    >[!Note]
    > <span data-ttu-id="4dca8-212">Перед запуском сценариев убедитесь, что вы установили модуль Azure AD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4dca8-212">Please ensure you have installed the Azure AD PowerShell module prior to running the scripts.</span></span> <span data-ttu-id="4dca8-213">Действия по установке можно найти ![ ](https://docs.microsoft.com/powershell/azure/install-az-ps?view=azps-5.1.0) здесь</span><span class="sxs-lookup"><span data-stu-id="4dca8-213">Please refer to ![here](https://docs.microsoft.com/powershell/azure/install-az-ps?view=azps-5.1.0) for installation steps</span></span>

6. <span data-ttu-id="4dca8-214">Сценарий приостановит и попросит вас принять или дать согласие приложению для миграции почтовых ящиков Exchange, созданному в ходе этого процесса.</span><span class="sxs-lookup"><span data-stu-id="4dca8-214">The script will pause and ask you to accept or consent to the Exchange mailbox migration application that was created during this process.</span></span> <span data-ttu-id="4dca8-215">Пример:</span><span class="sxs-lookup"><span data-stu-id="4dca8-215">Here is an example.</span></span>

    ```powershell
    PS C:\PowerShell\> .\SetupCrossTenantRelationshipForTargetTenant.ps1 -ResourceTenantDomain contoso.onmicrosoft.com -ResourceTenantAdminEmail admin@contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ResourceTenantId ksagjid39-ede2-4d2c-98ae-874709325b00 -SubscriptionId e4ssd05d-a327-49ss-849a-sd0932439023 -ResourceGroup "Cross-TenantMoves" -KeyVaultName "Cross-TenantMovesVault" -CertificateName "Contoso-Fabrikam-cert" -CertificateSubject "CN=Contoso_Fabrikam" -AzureAppPermissions Exchange, MSGraph -UseAppAndCertGeneratedForSendingInvitation -KeyVaultAuditStorageAccountName "t2tstorageaccount" -KeyVaultAuditStorageResourceGroup "Demo"

    cmdlet Get-Credential at command pipeline position 1
    Supply values for the following parameters:
    Credential
    Setting up key vault in the fabrikam.onmicrosoft.com tenant

    Name                                     Account                                 SubscriptionName                        Environment                             TenantId
        ----                                     -------                                 ----------------                        -----------                             --------
    Pay-As-You-Go (ewe23423-a3327-34232-343... Admin@fabrikam... Pay-As-You-Go                           AzureCloud                              dsad938432-dd8e-s9034-bf9a-83984293n43
    Auditing setup successfully for Cross-TenantMovesVault
    Exchange application given access to KeyVault Cross-TenantMovesVault
    Application fabrikam_Friends_contoso_2520 created successfully in fabrikam.onmicrosoft.com tenant with following permissions. MSGraph - Directory.ReadWrite.All. Exchange - Mailbox.Migration
    Admin consent URI for fabrikam.onmicrosoft.com tenant admin is -
    https://login.microsoftonline.com/fabrikam.onmicrosoft.com/adminconsent?client_id=6fea6ere-0dwe-404d-ad35-c71a15cers5c&redirect_uri=https://office.com
    Admin consent URI for contoso.onmicrosoft.com tenant admin is -
    https://login.microsoftonline.com/contoso.onmicrosoft.com/adminconsent?client_id=6fea6ssd-0753-404d-wer5-c71a154d675c&redirect_uri=https://office.com
    Application details to be registered in organization relationship: ApplicationId: [ 6fes8en4-sjo3-406d-ad35-sldkfjiew993 ]. KeyVault secret Id: [ https://cross-tenantmovesvault.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ksdfj843nt8476h84c288c5a3fb8ec5fdb08 ]. These values are available in variables $AppId and $CertificateId respectively
    Please consent to the application for fabrikam.onmicrosoft.com before sending invitation to admin@contoso.onmicrosoft.com:
    ```  

7. <span data-ttu-id="4dca8-216">URL-адрес будет отображаться в удаленном сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4dca8-216">A URL will be displayed in the Remote PowerShell session.</span></span> <span data-ttu-id="4dca8-217">Скопируйте ссылку, предоставленную для согласия клиента, и вберите ее в веб-браузер.</span><span class="sxs-lookup"><span data-stu-id="4dca8-217">Copy the link provided for your tenant consent and paste it into a Web browser.</span></span>

8. <span data-ttu-id="4dca8-218">Во входе с помощью учетных данных глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="4dca8-218">Sign in with your Global Admin credentials.</span></span> <span data-ttu-id="4dca8-219">При отобраии следующего экрана выберите **"Принять".**</span><span class="sxs-lookup"><span data-stu-id="4dca8-219">When the following screen is presented, select **Accept**.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-dialog.png" alt-text="Диалоговое окно &quot;Принятие разрешений&quot;":::

9. <span data-ttu-id="4dca8-221">Переключиться обратно в удаленный сеанс PowerShell и нажать ввод, чтобы продолжить.</span><span class="sxs-lookup"><span data-stu-id="4dca8-221">Switch back to the Remote PowerShell session and hit Enter to proceed.</span></span>

10. <span data-ttu-id="4dca8-222">Сценарий настроит оставшиеся объекты установки.</span><span class="sxs-lookup"><span data-stu-id="4dca8-222">The script will configure the remaining setup objects.</span></span> <span data-ttu-id="4dca8-223">Пример:</span><span class="sxs-lookup"><span data-stu-id="4dca8-223">Here is an example.</span></span>

    ```powershell
    Successfully sent invitation to admin@contoso.onmicrosoft.com
    Setting up exchange components on target tenant: fabrikam.onmicrosoft.com
    MigrationEndpoint created in fabrikam.onmicrosoft.com for target contoso.onmicrosoft.com
    Exchange setup complete. Migration endpoint details are available in $MigrationEndpoint variable
    ```

<span data-ttu-id="4dca8-224">Настройка целевого администратора завершена!</span><span class="sxs-lookup"><span data-stu-id="4dca8-224">The target admin setup is now complete!</span></span>

#### <a name="step-by-step-instructions-for-the-source-tenant-admin"></a><span data-ttu-id="4dca8-225">Пошаговая инструкция для администратора клиента-источника</span><span class="sxs-lookup"><span data-stu-id="4dca8-225">Step-by-step instructions for the source tenant admin</span></span>

1.  <span data-ttu-id="4dca8-226">Во sign in to your mailbox as the -ResourceTenantAdminEmail specified by the target admin during their setup.</span><span class="sxs-lookup"><span data-stu-id="4dca8-226">Sign in to your mailbox as the -ResourceTenantAdminEmail specified by the target admin during their setup.</span></span> <span data-ttu-id="4dca8-227">Найдите приглашение по электронной почте из целевого клиента и выберите кнопку **"Начало** работы".</span><span class="sxs-lookup"><span data-stu-id="4dca8-227">Find the email invitation from the target tenant, and then select the **Get Started** button.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/invited-by-target-tenant.png" alt-text="Вы были приглашены в диалоговое окно":::

2. <span data-ttu-id="4dca8-229">Выберите **"Принять",** чтобы принять приглашение.</span><span class="sxs-lookup"><span data-stu-id="4dca8-229">Select **Accept** to accept the invitation.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-accept.png" alt-text="Диалоговое окно для принятие разрешений":::

   > [!NOTE]
   > <span data-ttu-id="4dca8-231">Если вы не получили это сообщение электронной почты или не нашли его, администратору целевого клиента был предоставлен прямой URL-адрес, который можно дать вам принять приглашение.</span><span class="sxs-lookup"><span data-stu-id="4dca8-231">If you do not get this email or cannot find it, the target tenant admin was provided a direct URL that can be given to you to accept the invitation.</span></span> <span data-ttu-id="4dca8-232">URL-адрес должен быть указан в записи сеанса удаленной powerShell администратора целевого клиента.</span><span class="sxs-lookup"><span data-stu-id="4dca8-232">The URL should in the in the transcript of the target tenant admin's Remote PowerShell session.</span></span>

3. <span data-ttu-id="4dca8-233">В Центре администрирования Microsoft 365 или удаленном сеансе PowerShell создайте одну или несколько групп безопасности с включенной поддержкой почты, чтобы управлять списком почтовых ящиков, разрешенных целевым клиентом для инициалистики (перемещения) из клиента-источника в целевой.</span><span class="sxs-lookup"><span data-stu-id="4dca8-233">In either the Microsoft 365 admin center or a Remote PowerShell session, create one or more mail-enabled security groups to control the list of mailboxes allowed by the target tenant to pull (move) from the source tenant to the target tenant.</span></span> <span data-ttu-id="4dca8-234">Не нужно заполнять эту группу заранее, но для запуска действий по настройке (сценария) необходимо у вас по крайней мере одна группа.</span><span class="sxs-lookup"><span data-stu-id="4dca8-234">You do not need to populate this group in advance, but at least one group must be provided to run the setup steps (script).</span></span> <span data-ttu-id="4dca8-235">Вложенные группы не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="4dca8-235">Nest groups are not supported.</span></span> 

4. <span data-ttu-id="4dca8-236">Скачайте скрипт SetupCrossTenantRelationshipForResourceTenant.ps1 для настройки клиента источника из репозитория GitHub [https://github.com/microsoft/cross-tenant/releases/tag/Preview](https://github.com/microsoft/cross-tenant/releases/tag/Preview) здесь:</span><span class="sxs-lookup"><span data-stu-id="4dca8-236">Download the SetupCrossTenantRelationshipForResourceTenant.ps1 script for the source tenant setup from the GitHub repository here: [https://github.com/microsoft/cross-tenant/releases/tag/Preview](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span></span> 

5. <span data-ttu-id="4dca8-237">Создайте удаленное подключение PowerShell к клиенту-источнику с разрешениями администратора Exchange.</span><span class="sxs-lookup"><span data-stu-id="4dca8-237">Create a Remote PowerShell connection to the source tenant with your Exchange Administrator permissions.</span></span> <span data-ttu-id="4dca8-238">Разрешения глобального администратора не требуются для настройки клиента-источника, а только целевого клиента из-за процесса создания приложения Azure.</span><span class="sxs-lookup"><span data-stu-id="4dca8-238">Global Admin permissions are not required to configure the source tenant, only the target tenant because of the Azure application creation process.</span></span>

6. <span data-ttu-id="4dca8-239">Измените каталог на расположение сценария или убедитесь, что сценарий в данный момент сохранен в расположении в сеансе Удаленной powerShell.</span><span class="sxs-lookup"><span data-stu-id="4dca8-239">Change directory to the script location or verify that the script is currently saved to the location currently in your Remote PowerShell session.</span></span>

7. <span data-ttu-id="4dca8-240">Запустите сценарий со следующими требуемой параметрами и значениями.</span><span class="sxs-lookup"><span data-stu-id="4dca8-240">Run the script with the following required parameters and values.</span></span>

    | <span data-ttu-id="4dca8-241">Параметр</span><span class="sxs-lookup"><span data-stu-id="4dca8-241">Parameter</span></span> | <span data-ttu-id="4dca8-242">Значение</span><span class="sxs-lookup"><span data-stu-id="4dca8-242">Value</span></span> |
    |-----|------|
    | <span data-ttu-id="4dca8-243">-SourceMailboxMovePublishedScopes</span><span class="sxs-lookup"><span data-stu-id="4dca8-243">-SourceMailboxMovePublishedScopes</span></span> | <span data-ttu-id="4dca8-244">Группа безопасности с включенной поддержкой почты, созданная клиентом-источником для удостоверений и почтовых ящиков, которые находятся в области миграции.</span><span class="sxs-lookup"><span data-stu-id="4dca8-244">Mail-enabled security group created by source tenant for the identities/mailboxes that are in scope for migration.</span></span> |
    | <span data-ttu-id="4dca8-245">-ResourceTenantDomain</span><span class="sxs-lookup"><span data-stu-id="4dca8-245">-ResourceTenantDomain</span></span> | <span data-ttu-id="4dca8-246">Доменное имя клиента-источника, например fabrikam \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="4dca8-246">Source tenant domain name, such as fabrikam\.onmicrosoft.com.</span></span> |
    | <span data-ttu-id="4dca8-247">-ApplicationId</span><span class="sxs-lookup"><span data-stu-id="4dca8-247">-ApplicationId</span></span> | <span data-ttu-id="4dca8-248">GuID приложения Azure, используемого для миграции.</span><span class="sxs-lookup"><span data-stu-id="4dca8-248">Azure application ID (GUID) of the application used for migration.</span></span> <span data-ttu-id="4dca8-249">ИД приложения, доступный на портале Azure (Azure AD, корпоративные приложения, имя приложения, ИД приложения) или включенный в приглашение.</span><span class="sxs-lookup"><span data-stu-id="4dca8-249">Application ID available via your Azure portal (Azure AD, Enterprise Applications, app name, application ID) or included in your invitation email.</span></span>  |
    | <span data-ttu-id="4dca8-250">-TargetTenantDomain</span><span class="sxs-lookup"><span data-stu-id="4dca8-250">-TargetTenantDomain</span></span> | <span data-ttu-id="4dca8-251">Доменное имя целевого клиента, например contoso \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="4dca8-251">Target tenant domain name, such as contoso\.onmicrosoft.com.</span></span> |
    | <span data-ttu-id="4dca8-252">-TargetTenantId</span><span class="sxs-lookup"><span data-stu-id="4dca8-252">-TargetTenantId</span></span> | <span data-ttu-id="4dca8-253">ИД клиента целевого клиента.</span><span class="sxs-lookup"><span data-stu-id="4dca8-253">Tenant ID of the target tenant.</span></span> <span data-ttu-id="4dca8-254">Например, ИД клиента Azure AD клиента contoso \. onmicrosoft.com клиента.</span><span class="sxs-lookup"><span data-stu-id="4dca8-254">For example, the Azure AD tenant ID of contoso\.onmicrosoft.com tenant.</span></span> |
    |||

    <span data-ttu-id="4dca8-255">Пример:</span><span class="sxs-lookup"><span data-stu-id="4dca8-255">Here is an example.</span></span>
    ```powershell
    SetupCrossTenantRelationshipForResourceTenant.ps1 -SourceMailboxMovePublishedScopes "MigScope","MyGroup" -ResourceTenantDomain contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ApplicationId sdf5e87sa-0753-dd88-ad35-c71a15cs8e44c -TargetTenantId 4sdkfo933-3904-sd93-bf9a-sdi39402834
    Exchange setup complete.

    ```

<span data-ttu-id="4dca8-256">Настройка администратора источника завершена!</span><span class="sxs-lookup"><span data-stu-id="4dca8-256">The source admin setup is now complete!</span></span>

### <a name="verify-setup"></a><span data-ttu-id="4dca8-257">Проверка настройки</span><span class="sxs-lookup"><span data-stu-id="4dca8-257">Verify setup</span></span>

<span data-ttu-id="4dca8-258">Убедитесь, что связи организации в исходных и целевых клиентах и конечной точке миграции в целевом объекте созданы успешно.</span><span class="sxs-lookup"><span data-stu-id="4dca8-258">Verify that the organization relationships in both source and target tenants and migration endpoint in the target were created successfully.</span></span>

#### <a name="target-tenant"></a><span data-ttu-id="4dca8-259">Целевой клиент</span><span class="sxs-lookup"><span data-stu-id="4dca8-259">Target tenant</span></span>

<span data-ttu-id="4dca8-260">**Организационная связь**</span><span class="sxs-lookup"><span data-stu-id="4dca8-260">**Organization relationship**</span></span>

<span data-ttu-id="4dca8-261">Убедитесь, что объект связи организации создан и настроен с помощью этой команды.</span><span class="sxs-lookup"><span data-stu-id="4dca8-261">Verify that the organization relationship object was created and configured with this command.</span></span>

```powershell
Get-OrganizationRelationship <source tenant organization name> | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability
```
<span data-ttu-id="4dca8-262">Вот пример:</span><span class="sxs-lookup"><span data-stu-id="4dca8-262">Here is an example:</span></span>

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship fabrikam_contoso_1178 | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability

Name                  : fabrikam_contoso_1123
DomainNames           : {sd0933me9f-9304-s903-s093-s093mfi903m4}
MailboxMoveEnabled    : True
MailboxMoveCapability : Inbound

```

<span data-ttu-id="4dca8-263">**Конечная точка миграции**</span><span class="sxs-lookup"><span data-stu-id="4dca8-263">**Migration endpoint**</span></span>

<span data-ttu-id="4dca8-264">Убедитесь, что объект конечной точки миграции создан и настроен с помощью этой команды.</span><span class="sxs-lookup"><span data-stu-id="4dca8-264">Verify that the migration endpoint object was created and configured with this command.</span></span>

```powershell
Get-MigrationEndpoint "<fabrikam_contoso_1123> | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl
```

<span data-ttu-id="4dca8-265">Пример:</span><span class="sxs-lookup"><span data-stu-id="4dca8-265">Here is an example.</span></span>

```powershell
PS C:\PowerShell\> Get-MigrationEndpoint fabrikam_contoso_1123 | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl


Identity             : fabrikam_contoso_1123
RemoteTenant         : contoso.onmicrosoft.com
ApplicationId        : s93mf93-das9-dq24-dq234-dada9033904m
AppSecretKeyVaultUrl : https://cross-tenantmyvaultformoves.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ae79348mx94384c288c5a3dfsioepw308

```

#### <a name="source-tenant"></a><span data-ttu-id="4dca8-266">Исходный клиент</span><span class="sxs-lookup"><span data-stu-id="4dca8-266">Source tenant</span></span>

<span data-ttu-id="4dca8-267">**Организационная связь**</span><span class="sxs-lookup"><span data-stu-id="4dca8-267">**Organization relationship**</span></span>

<span data-ttu-id="4dca8-268">Убедитесь, что объект связи организации создан и настроен с помощью этой команды.</span><span class="sxs-lookup"><span data-stu-id="4dca8-268">Verify that the organization relationship object was created and configured with this command.</span></span>

```powershell
Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId
```

<span data-ttu-id="4dca8-269">Пример:</span><span class="sxs-lookup"><span data-stu-id="4dca8-269">Here is an example.</span></span>

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId


Name                       : fabrikam_contoso_001
MailboxMoveEnabled         : True
MailboxMoveCapability      : RemoteOutbound
MailboxMovePublishedScopes : {MigScope}
OAuthApplicationId         : sd9890342-3243-3242-fe3w2-fsdade93m0
```

#### <a name="verify-setup-script"></a><span data-ttu-id="4dca8-270">Проверка скрипта установки</span><span class="sxs-lookup"><span data-stu-id="4dca8-270">Verify Setup Script</span></span>

<span data-ttu-id="4dca8-271">Если во время настройки исходных или целевых клиентов будут ошибки, можно запустить скрипт VerifySetup.ps1, расположенный на [GitHub,](https://github.com/microsoft/cross-tenant/releases/tag/Preview) и просмотреть выходные данные.</span><span class="sxs-lookup"><span data-stu-id="4dca8-271">If you receive any errors during the configuration of the source or target tenants, you can run the VerifySetup.ps1 script located [on GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview) and review the output.</span></span>

<span data-ttu-id="4dca8-272">Вот пример запуска VerifySetup.ps1 в целевом клиенте:</span><span class="sxs-lookup"><span data-stu-id="4dca8-272">Here's an example of running VerifySetup.ps1 on the target tenant:</span></span>

```powershell
VerifySetup.ps1 -PartnerTenantId <SourceTenantId> -ApplicationId <AADApplicationId> -ApplicationKeyVaultUrl <appKeyVaultUrl> -PartnerTenantDomain <PartnerTenantDomain> -Verbose
```

<span data-ttu-id="4dca8-273">Вот пример VerifySetup.ps1 в клиенте источника:</span><span class="sxs-lookup"><span data-stu-id="4dca8-273">Here's an example of VerifySetup.ps1 on the source tenant:</span></span>

```powershell
VerifySetup.ps1 -PartnerTenantId <TargetTenantId> -ApplicationId <AADApplicationId>
```

### <a name="move-mailboxes-back-to-the-original-source"></a><span data-ttu-id="4dca8-274">Перемещение почтовых ящиков обратно в исходный источник</span><span class="sxs-lookup"><span data-stu-id="4dca8-274">Move mailboxes back to the original source</span></span>

<span data-ttu-id="4dca8-275">Если требуется переместить почтовый ящик обратно в исходный клиент, необходимо выполнить один и тот же набор действий и сценариев как в новых исходных, так и в новых целевых клиентах.</span><span class="sxs-lookup"><span data-stu-id="4dca8-275">If a mailbox move back to the original source tenant is required, the same set of steps and scripts will need to be run in both new source and new target tenants.</span></span> <span data-ttu-id="4dca8-276">Существующий объект Связи организации будет обновлен или примеен, а не воссоздан.</span><span class="sxs-lookup"><span data-stu-id="4dca8-276">The existing Organization Relationship object will be updated or appended, not recreated.</span></span>

## <a name="prepare-target-user-objects-for-migration"></a><span data-ttu-id="4dca8-277">Подготовка целевых объектов-пользователей к миграции</span><span class="sxs-lookup"><span data-stu-id="4dca8-277">Prepare target user objects for migration</span></span>

<span data-ttu-id="4dca8-278">Миграция пользователей должна присутствовать в целевом клиенте и системе Exchange Online (как MailUsers), помеченной определенными атрибутами, чтобы включить перемещение между клиентами.</span><span class="sxs-lookup"><span data-stu-id="4dca8-278">Users migrating must be present in the target tenant and Exchange Online system (as MailUsers) marked with specific attributes to enable the cross-tenant moves.</span></span> <span data-ttu-id="4dca8-279">Система не сможет двигаться для пользователей, которые неправильно настроены в целевом клиенте.</span><span class="sxs-lookup"><span data-stu-id="4dca8-279">The system will fail moves for users that are not properly set up in the target tenant.</span></span> <span data-ttu-id="4dca8-280">В следующем разделе подробно ются требования к объекту MailUser для целевого клиента.</span><span class="sxs-lookup"><span data-stu-id="4dca8-280">The following section details the MailUser object requirements for the target tenant.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="4dca8-281">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="4dca8-281">Prerequisites</span></span>
  
<span data-ttu-id="4dca8-282">Необходимо убедиться, что в целевой организации установлены следующие объекты и атрибуты.</span><span class="sxs-lookup"><span data-stu-id="4dca8-282">You must ensure the following objects and attributes are set in the target organization.</span></span>  

1. <span data-ttu-id="4dca8-283">Для любого почтового ящика, перемещаемой из организации-источника, необходимо подготовка объекта MailUser в целевой организации:</span><span class="sxs-lookup"><span data-stu-id="4dca8-283">For any mailbox moving from a source organization, you must provision a MailUser object in the Target organization:</span></span> 

   - <span data-ttu-id="4dca8-284">Целевой mailUser должен иметь эти атрибуты из почтового ящика источника или иметь новый объект User:</span><span class="sxs-lookup"><span data-stu-id="4dca8-284">The Target MailUser must have these attributes from the source mailbox or assigned with the new User object:</span></span>
      - <span data-ttu-id="4dca8-285">ExchangeGUID (прямой поток от источника к целевому) — GUID почтового ящика должен совпадать.</span><span class="sxs-lookup"><span data-stu-id="4dca8-285">ExchangeGUID (direct flow from source to target) – The mailbox GUID must match.</span></span> <span data-ttu-id="4dca8-286">Процесс перемещения не будет продолжаться, если он не присутствует в целевом объекте.</span><span class="sxs-lookup"><span data-stu-id="4dca8-286">The move process will not proceed if this is not present on target object.</span></span> 
      - <span data-ttu-id="4dca8-287">ArchiveGUID (прямой поток от источника к целевому) — guID архива должен совпадать.</span><span class="sxs-lookup"><span data-stu-id="4dca8-287">ArchiveGUID (direct flow from source to target) – The archive GUID must match.</span></span> <span data-ttu-id="4dca8-288">Процесс перемещения не будет продолжаться, если он не присутствует в целевом объекте.</span><span class="sxs-lookup"><span data-stu-id="4dca8-288">The move process will not proceed if this is not present on the target object.</span></span> <span data-ttu-id="4dca8-289">(Это необходимо, только если для исходных почтовых ящиков включен архив).</span><span class="sxs-lookup"><span data-stu-id="4dca8-289">(This is only required if the source mailbox is Archive enabled).</span></span> 
      - <span data-ttu-id="4dca8-290">LegacyExchangeDN (поток в качестве proxyAddress, "x500: ") — legacyExchangeDN должен присутствовать в <LegacyExchangeDN> целевом MailUser как x500: proxyAddress.</span><span class="sxs-lookup"><span data-stu-id="4dca8-290">LegacyExchangeDN (flow as proxyAddress, “x500:<LegacyExchangeDN>”) – The LegacyExchangeDN must be present on target MailUser as x500: proxyAddress.</span></span> <span data-ttu-id="4dca8-291">Процессы перемещения не будут продолжаться, если они не присутствуют в целевом объекте.</span><span class="sxs-lookup"><span data-stu-id="4dca8-291">The move processes will not proceed if this is not present on the target object.</span></span> 
      - <span data-ttu-id="4dca8-292">UserPrincipalName — upN будет совпадать с новым удостоверением пользователя или целевой компанией (например, user@northwindtraders.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="4dca8-292">UserPrincipalName – UPN will align to the user’s NEW identity or target company (for example, user@northwindtraders.onmicrosoft.com).</span></span> 
      - <span data-ttu-id="4dca8-293">Primary SMTPAddress — основной SMTP-адрес будет согласован с новой компанией пользователя (например, user@northwind.com).</span><span class="sxs-lookup"><span data-stu-id="4dca8-293">Primary SMTPAddress – Primary SMTP address will align to the user’s NEW company (for example, user@northwind.com).</span></span> 
      - <span data-ttu-id="4dca8-294">TargetAddress/ExternalEmailAddress — MailUser будет ссылаться на текущий почтовый ящик пользователя, который был user@contoso.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="4dca8-294">TargetAddress/ExternalEmailAddress – MailUser will reference the user’s current mailbox hosted in source tenant (for example user@contoso.onmicrosoft.com).</span></span> <span data-ttu-id="4dca8-295">При назначении этого значения убедитесь, что вы также назначаете PrimarySMTPAddress или это значение задает PrimarySMTPAddress, что приведет к сбоям перемещения.</span><span class="sxs-lookup"><span data-stu-id="4dca8-295">When assigning this value, verify that you have/are also assigning PrimarySMTPAddress or this value will set the PrimarySMTPAddress which will cause move failures.</span></span> 
      - <span data-ttu-id="4dca8-296">Вы не можете добавлять устаревшие прокси-адреса smtp из исходных почтовых ящиков в целевой почтовый ящик MailUser.</span><span class="sxs-lookup"><span data-stu-id="4dca8-296">You cannot add legacy smtp proxy addresses from source mailbox to target MailUser.</span></span> <span data-ttu-id="4dca8-297">Например, нельзя поддерживать contoso.com MEU в fabrikam.onmicrosoft.com объектах клиента).</span><span class="sxs-lookup"><span data-stu-id="4dca8-297">For example, you cannot maintain contoso.com on the MEU in fabrikam.onmicrosoft.com tenant objects).</span></span> <span data-ttu-id="4dca8-298">Домены связаны только с одним клиентом Azure AD или Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="4dca8-298">Domains are associated with one Azure AD or Exchange Online tenant only.</span></span>
 
     <span data-ttu-id="4dca8-299">Пример **целевого** объекта MailUser:</span><span class="sxs-lookup"><span data-stu-id="4dca8-299">Example **target** MailUser object:</span></span>
 
     | <span data-ttu-id="4dca8-300">Атрибут</span><span class="sxs-lookup"><span data-stu-id="4dca8-300">Attribute</span></span>             | <span data-ttu-id="4dca8-301">Значение</span><span class="sxs-lookup"><span data-stu-id="4dca8-301">Value</span></span>                                                                                                                    |
     |-----------------------|--------------------------------------------------------------------------------------------------------------------------|
     | <span data-ttu-id="4dca8-302">Alias</span><span class="sxs-lookup"><span data-stu-id="4dca8-302">Alias</span></span>                 | <span data-ttu-id="4dca8-303">Лараан</span><span class="sxs-lookup"><span data-stu-id="4dca8-303">LaraN</span></span>                                                                                                                    |
     | <span data-ttu-id="4dca8-304">RecipientType</span><span class="sxs-lookup"><span data-stu-id="4dca8-304">RecipientType</span></span>         | <span data-ttu-id="4dca8-305">MailUser</span><span class="sxs-lookup"><span data-stu-id="4dca8-305">MailUser</span></span>                                                                                                                 |
     | <span data-ttu-id="4dca8-306">RecipientTypeDetails</span><span class="sxs-lookup"><span data-stu-id="4dca8-306">RecipientTypeDetails</span></span>  | <span data-ttu-id="4dca8-307">MailUser</span><span class="sxs-lookup"><span data-stu-id="4dca8-307">MailUser</span></span>                                                                                                                 |
     | <span data-ttu-id="4dca8-308">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="4dca8-308">UserPrincipalName</span></span>     | <span data-ttu-id="4dca8-309">LaraN@northwintraders.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="4dca8-309">LaraN@northwintraders.onmicrosoft.com</span></span>                                                                                    |
     | <span data-ttu-id="4dca8-310">PrimarySmtpAddress</span><span class="sxs-lookup"><span data-stu-id="4dca8-310">PrimarySmtpAddress</span></span>    | <span data-ttu-id="4dca8-311">Lara.Newton@northwind.com</span><span class="sxs-lookup"><span data-stu-id="4dca8-311">Lara.Newton@northwind.com</span></span>                                                                                                |
     | <span data-ttu-id="4dca8-312">ExternalEmailAddress</span><span class="sxs-lookup"><span data-stu-id="4dca8-312">ExternalEmailAddress</span></span>  | <span data-ttu-id="4dca8-313">SMTP:LaraN@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="4dca8-313">SMTP:LaraN@contoso.onmicrosoft.com</span></span>                                                                                       |
     | <span data-ttu-id="4dca8-314">ExchangeGuid</span><span class="sxs-lookup"><span data-stu-id="4dca8-314">ExchangeGuid</span></span>          | <span data-ttu-id="4dca8-315">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span><span class="sxs-lookup"><span data-stu-id="4dca8-315">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span></span>                                                                                     |
     | <span data-ttu-id="4dca8-316">LegacyExchangeDN</span><span class="sxs-lookup"><span data-stu-id="4dca8-316">LegacyExchangeDN</span></span>      | <span data-ttu-id="4dca8-317">/o=First Organization/ou=Exchange Administrative Group</span><span class="sxs-lookup"><span data-stu-id="4dca8-317">/o=First Organization/ou=Exchange Administrative Group</span></span>                                                                   |
     |                       | <span data-ttu-id="4dca8-318">(FYDIBOHF23SPDLT)/cn=Recipients/cn=74e5385fce4b46d19006876949855035Lara</span><span class="sxs-lookup"><span data-stu-id="4dca8-318">(FYDIBOHF23SPDLT)/cn=Recipients/cn=74e5385fce4b46d19006876949855035Lara</span></span>                                                  |
     | <span data-ttu-id="4dca8-319">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="4dca8-319">EmailAddresses</span></span>        | <span data-ttu-id="4dca8-320">x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c8190</span><span class="sxs-lookup"><span data-stu-id="4dca8-320">x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c8190</span></span>  |
     |                       | <span data-ttu-id="4dca8-321">7273f1f9-Lara</span><span class="sxs-lookup"><span data-stu-id="4dca8-321">7273f1f9-Lara</span></span>                                                                                                            |
     |                       | <span data-ttu-id="4dca8-322">smtp:LaraN@northwindtraders.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="4dca8-322">smtp:LaraN@northwindtraders.onmicrosoft.com</span></span>                                                                              |
     |                       | <span data-ttu-id="4dca8-323">SMTP:Lara.Newton@northwind.com</span><span class="sxs-lookup"><span data-stu-id="4dca8-323">SMTP:Lara.Newton@northwind.com</span></span>                                                                                           |
     |||

     <span data-ttu-id="4dca8-324">Пример **объекта source** Mailbox:</span><span class="sxs-lookup"><span data-stu-id="4dca8-324">Example **source** Mailbox object:</span></span>

     | <span data-ttu-id="4dca8-325">Атрибут</span><span class="sxs-lookup"><span data-stu-id="4dca8-325">Attribute</span></span>             | <span data-ttu-id="4dca8-326">Значение</span><span class="sxs-lookup"><span data-stu-id="4dca8-326">Value</span></span>                                                                    |
     |-----------------------|--------------------------------------------------------------------------|
     | <span data-ttu-id="4dca8-327">Alias</span><span class="sxs-lookup"><span data-stu-id="4dca8-327">Alias</span></span>                 | <span data-ttu-id="4dca8-328">Лараан</span><span class="sxs-lookup"><span data-stu-id="4dca8-328">LaraN</span></span>                                                                    |
     | <span data-ttu-id="4dca8-329">RecipientType</span><span class="sxs-lookup"><span data-stu-id="4dca8-329">RecipientType</span></span>         | <span data-ttu-id="4dca8-330">UserMailbox</span><span class="sxs-lookup"><span data-stu-id="4dca8-330">UserMailbox</span></span>                                                              |
     | <span data-ttu-id="4dca8-331">RecipientTypeDetails</span><span class="sxs-lookup"><span data-stu-id="4dca8-331">RecipientTypeDetails</span></span>  | <span data-ttu-id="4dca8-332">UserMailbox</span><span class="sxs-lookup"><span data-stu-id="4dca8-332">UserMailbox</span></span>                                                              |
     | <span data-ttu-id="4dca8-333">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="4dca8-333">UserPrincipalName</span></span>     | <span data-ttu-id="4dca8-334">LaraN@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="4dca8-334">LaraN@contoso.onmicrosoft.com</span></span>                                            |
     | <span data-ttu-id="4dca8-335">PrimarySmtpAddress</span><span class="sxs-lookup"><span data-stu-id="4dca8-335">PrimarySmtpAddress</span></span>    | <span data-ttu-id="4dca8-336">Lara.Newton@contoso.com</span><span class="sxs-lookup"><span data-stu-id="4dca8-336">Lara.Newton@contoso.com</span></span>                                                  |
     | <span data-ttu-id="4dca8-337">ExchangeGuid</span><span class="sxs-lookup"><span data-stu-id="4dca8-337">ExchangeGuid</span></span>          | <span data-ttu-id="4dca8-338">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span><span class="sxs-lookup"><span data-stu-id="4dca8-338">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span></span>                                     |
     | <span data-ttu-id="4dca8-339">LegacyExchangeDN</span><span class="sxs-lookup"><span data-stu-id="4dca8-339">LegacyExchangeDN</span></span>      | <span data-ttu-id="4dca8-340">/o=First Organization/ou=Exchange Administrative Group</span><span class="sxs-lookup"><span data-stu-id="4dca8-340">/o=First Organization/ou=Exchange Administrative Group</span></span>                   |
     |                       | <span data-ttu-id="4dca8-341">(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara</span><span class="sxs-lookup"><span data-stu-id="4dca8-341">(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara</span></span>  |
     | <span data-ttu-id="4dca8-342">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="4dca8-342">EmailAddresses</span></span>        | <span data-ttu-id="4dca8-343">smtp:LaraN@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="4dca8-343">smtp:LaraN@contoso.onmicrosoft.com</span></span> 
     |                       | <span data-ttu-id="4dca8-344">SMTP:Lara.Newton@contoso.com</span><span class="sxs-lookup"><span data-stu-id="4dca8-344">SMTP:Lara.Newton@contoso.com</span></span>          |
     |||

   - <span data-ttu-id="4dca8-345">Дополнительные атрибуты могут быть уже включены в гибридную функцию записи Exchange.</span><span class="sxs-lookup"><span data-stu-id="4dca8-345">Additional attributes may be included in Exchange hybrid write back already.</span></span> <span data-ttu-id="4dca8-346">Если нет, их следует включить.</span><span class="sxs-lookup"><span data-stu-id="4dca8-346">If not, they should be included.</span></span> 
   - <span data-ttu-id="4dca8-347">msExchBlockedSendersHash — записывает данные надежных и заблокированных отправителей из интернета из клиентов в локальной службе Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4dca8-347">msExchBlockedSendersHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>
   - <span data-ttu-id="4dca8-348">msExchSafeRecipientsHash — записывает данные о надежных и заблокированных отправляях из интернета из клиентов в локальное каталог Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4dca8-348">msExchSafeRecipientsHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>
   - <span data-ttu-id="4dca8-349">msExchSafeSendersHash — записывает данные надежных и заблокированных отправителей из интернета из клиентов в локальной службе Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4dca8-349">msExchSafeSendersHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>

2. <span data-ttu-id="4dca8-350">Если исходный почтовый ящик находится на litigationHold, а размер элементов для восстановления в исходных почтовых ящиках превышает размер базы данных по умолчанию (30 ГБ), перемещение не будет продолжаться, так как целевая квота меньше размера исходных почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="4dca8-350">If the source mailbox is on LitigationHold and the source mailbox Recoverable Items size is greater than our database default (30 GB), moves will not proceed since the target quota is less than the source mailbox size.</span></span> <span data-ttu-id="4dca8-351">Можно обновить целевой объект MailUser, чтобы переместить флаги почтовых ящиков ELC из среды источника в целевую, что активирует целевую систему для расширения квоты MailUser до 100 ГБ, что позволяет перейти к целевому объекту.</span><span class="sxs-lookup"><span data-stu-id="4dca8-351">You can update the target MailUser object to transition the ELC mailbox flags from the source environment to the target, which triggers the target system to expand the quota of the MailUser to 100 GB, thus allowing the move to the target.</span></span> <span data-ttu-id="4dca8-352">Эти инструкции будут работать только для гибридного удостоверения, запускающего Azure AD Connect, так как команды пометки флагов ELC не огосят администраторам клиентов.</span><span class="sxs-lookup"><span data-stu-id="4dca8-352">These instructions will work only for hybrid identity running Azure AD Connect, as the commands to stamp the ELC flags are not exposed to tenant administrators.</span></span>

    >[!Note]
    > <span data-ttu-id="4dca8-353">ПРИМЕР — КАК ЕСТЬ, БЕЗ ГАРАНТИИ</span><span class="sxs-lookup"><span data-stu-id="4dca8-353">SAMPLE – AS IS, NO WARRANTY</span></span><br/><span data-ttu-id="4dca8-354">Этот сценарий предполагает подключение как к исходным почтовым ящикам (для получения исходных значений), так и к целевому локальному каталогу Active Directory (чтобы пометь объект ADUser).</span><span class="sxs-lookup"><span data-stu-id="4dca8-354">This script assumes a connection to both source mailbox (to get source values) and the target on-premises Active Directory (to stamp the ADUser object).</span></span> <span data-ttu-id="4dca8-355">Если в источнике включено восстановление для судебного разбирательства или отдельного элемента, установите его для учетной записи назначения.</span><span class="sxs-lookup"><span data-stu-id="4dca8-355">If source has litigation or single item recovery enabled, set this on the destination account.</span></span>  <span data-ttu-id="4dca8-356">Это увеличит размер контейнера конечной учетной записи до 100 ГБ.</span><span class="sxs-lookup"><span data-stu-id="4dca8-356">This will increase the dumpster size of destination account to 100 GB.</span></span>

    ```powershell
    $ELCValue = 0 
    if ($source.LitigationHoldEnabled) {$ELCValue = $ELCValue + 8} if ($source.SingleItemRecoveryEnabled) {$ELCValue = $ELCValue + 16} if ($ELCValue -gt 0) {Set-ADUser -Server $domainController -Identity $destination.SamAccountName -Replace @{msExchELCMailboxFlags=$ELCValue}} 
    ```

3. <span data-ttu-id="4dca8-357">Негигитовые целевые клиенты могут изменить квоту папки "Элементы с возможностью восстановления" для mailUsers перед миграцией, выдав следующую команду, чтобы включить удержание для судебного разбирательства для объекта MailUser и увеличить квоту до 100 `Set-MailUser -EnableLitigationHoldForMigration $TRUE` ГБ:</span><span class="sxs-lookup"><span data-stu-id="4dca8-357">Non-hybrid target tenants can modify the quota on the Recoverable Items folder for the MailUsers prior to migration by running the following command to enable Litigation Hold on the MailUser object and increasing the quota to 100 GB: `Set-MailUser -EnableLitigationHoldForMigration $TRUE`.</span></span> <span data-ttu-id="4dca8-358">Обратите внимание, что это не будет работать для клиентов в гибридной данной модели.</span><span class="sxs-lookup"><span data-stu-id="4dca8-358">Note this will not work for tenants in hybrid.</span></span>

4. <span data-ttu-id="4dca8-359">Пользователи в целевой организации должны иметь лицензии на соответствующие подписки Exchange Online, применимые к организации.</span><span class="sxs-lookup"><span data-stu-id="4dca8-359">Users in the target organization must be licensed with appropriate Exchange Online subscriptions applicable for the organization.</span></span> <span data-ttu-id="4dca8-360">Вы можете применить лицензию перед перемещением почтового ящика, но только после того, как целевой mailUser правильно настроен с помощью ExchangeGUID и прокси-адресов.</span><span class="sxs-lookup"><span data-stu-id="4dca8-360">You may apply a license in advance of a mailbox move but ONLY once the target MailUser is properly set up with ExchangeGUID and proxy addresses.</span></span> <span data-ttu-id="4dca8-361">Применение лицензии перед применением ExchangeGUID приведет к предоставлению нового почтового ящика в целевой организации.</span><span class="sxs-lookup"><span data-stu-id="4dca8-361">Applying a license before the ExchangeGUID is applied will result in a new mailbox provisioned in target organization.</span></span> 

    > [!Note]
    > <span data-ttu-id="4dca8-362">При применении лицензии к объекту Mailbox или MailUser все адреса proxyAddresses типа SMTP проверяются, чтобы в массив Exchange EmailAddresses включались только проверенные домены.</span><span class="sxs-lookup"><span data-stu-id="4dca8-362">When you apply a license on a Mailbox or MailUser object, all SMTP type proxyAddresses are scrubbed to ensure only verified domains are included in the Exchange EmailAddresses array.</span></span> 

5. <span data-ttu-id="4dca8-363">Необходимо убедиться, что целевой mailUser не имеет предыдущего ExchangeGuid, который не соответствует Source ExchangeGuid.</span><span class="sxs-lookup"><span data-stu-id="4dca8-363">You must ensure that the target MailUser has no previous ExchangeGuid that does not match the Source ExchangeGuid.</span></span> <span data-ttu-id="4dca8-364">Это может произойти, если целевой MEU ранее был лицензирован для Exchange Online и был предусмотрен почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="4dca8-364">This might occur if the target MEU was previously licensed for Exchange Online and provisioned a mailbox.</span></span> <span data-ttu-id="4dca8-365">Если целевой mailUser ранее был лицензирован для ExchangeGuid или имел его, не совпадавший с Исходным кодом ExchangeGuid, необходимо выполнить очистку облачного MEU.</span><span class="sxs-lookup"><span data-stu-id="4dca8-365">If the target MailUser was previously licensed for or had an ExchangeGuid that does not match the Source ExchangeGuid, you need to perform a cleanup of the cloud MEU.</span></span> <span data-ttu-id="4dca8-366">Для этих облачных MEUS можно запустить `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` .</span><span class="sxs-lookup"><span data-stu-id="4dca8-366">For these cloud MEUs, you can run `Set-User <identity> -PermanentlyClearPreviousMailboxInfo`.</span></span>  

    > [!Caution]
    > <span data-ttu-id="4dca8-367">Этот процесс необратим.</span><span class="sxs-lookup"><span data-stu-id="4dca8-367">This process is irreversible.</span></span> <span data-ttu-id="4dca8-368">Если объект имеет почтовый ящик softDeleted, его нельзя восстановить после этой точки.</span><span class="sxs-lookup"><span data-stu-id="4dca8-368">If the object has a softDeleted mailbox, it cannot be restored after this point.</span></span> <span data-ttu-id="4dca8-369">Однако после очистки можно синхронизировать правильный Объект ExchangeGuid с целевым объектом, и служба MRS подключит исходный почтовый ящик к созданному целевому почтовому ящику.</span><span class="sxs-lookup"><span data-stu-id="4dca8-369">Once cleared, however, you can sync the correct ExchangeGuid to the target object and MRS will connect the source mailbox to the newly created target mailbox.</span></span> <span data-ttu-id="4dca8-370">(Ссылаясь на блог EHLO о новом параметре.)</span><span class="sxs-lookup"><span data-stu-id="4dca8-370">(Reference EHLO blog on the new parameter.)</span></span>  

    <span data-ttu-id="4dca8-371">Найдите объекты, которые ранее были почтовыми ящиками, с помощью этой команды.</span><span class="sxs-lookup"><span data-stu-id="4dca8-371">Find objects that were previously mailboxes using this command.</span></span>

    ```powershell
    Get-User <identity> | select Name, *recipient* | ft -AutoSize
    ```

    <span data-ttu-id="4dca8-372">Пример:</span><span class="sxs-lookup"><span data-stu-id="4dca8-372">Here is an example.</span></span> 

    ```powershell
    PS demo> get-user John@northwindtraders.com |select name, *recipient*| ft -AutoSize  

    Name        PreviousRecipientTypeDetails     RecipientType RecipientTypeDetails  
    ----       ---------------------------- ------------- --------------------  
    John       UserMailbox                  MailUser      MailUser  
    ```  

    <span data-ttu-id="4dca8-373">Удаляем почтовый ящик с помощью этой команды.</span><span class="sxs-lookup"><span data-stu-id="4dca8-373">Clear the soft-deleted mailbox using this command.</span></span>

    ```powershell
    Set-User <identity> -PermanentlyClearPreviousMailboxInfo
    ```

    <span data-ttu-id="4dca8-374">Пример:</span><span class="sxs-lookup"><span data-stu-id="4dca8-374">Here is an example.</span></span>

    ```powershell
    PS demo> Set-User John@northwindtraders.com -PermanentlyClearPreviousMailboxInfo Confirm 
    Are you sure you want to perform this action? 
    Delete all existing information about user “John@northwindtraders.com"?. This operation will clear existing values from Previous home MDB and Previous Mailbox GUID of the user. After deletion, reconnecting to the previous mailbox that existed in the cloud will not be possible and any content it had will be unrecoverable PERMANENTLY.  
    Do you want to continue? 
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"): Y  
    ```

## <a name="perform-mailbox-migrations"></a><span data-ttu-id="4dca8-375">Выполнение миграции почтовых ящиков</span><span class="sxs-lookup"><span data-stu-id="4dca8-375">Perform mailbox migrations</span></span>

<span data-ttu-id="4dca8-376">Миграция почтовых ящиков Exchange между клиентами передается в качестве пакетов миграции, инициированных из целевого клиента.</span><span class="sxs-lookup"><span data-stu-id="4dca8-376">Cross-tenant Exchange mailbox migrations are submitted as migration batches initiated from the target tenant.</span></span> <span data-ttu-id="4dca8-377">Это аналогично тому, как работают пакеты миграции при миграции из локальной службы Exchange в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4dca8-377">This is similar to the way that on-boarding migration batches work when migrating from Exchange on-premises to Microsoft 365.</span></span> 

### <a name="create-migration-batches"></a><span data-ttu-id="4dca8-378">Создание пакетов миграции</span><span class="sxs-lookup"><span data-stu-id="4dca8-378">Create Migration batches</span></span>

<span data-ttu-id="4dca8-379">Вот пример пакета миграции для начала перемещения.</span><span class="sxs-lookup"><span data-stu-id="4dca8-379">Here is an example migration batch cmdlet for kicking off moves.</span></span>

```powershell
New-MigrationBatch -Name T2Tbatch-testforignitedemo -SourceEndpoint target_source_7977 -CSVData ([System.IO.File]::ReadAllBytes('users.csv')) -Autostart -TargetDeliveryDomain targetformoves.onmicrosoft.com -AutoComplete

Identity                   Status  Type               TotalCount
--------                   ------  ----               ----------
T2Tbatch-testforignitedemo Syncing ExchangeRemoteMove 1

```

> [!Note]
> <span data-ttu-id="4dca8-380">Адрес электронной почты в CSV-файле должен быть указан в целевом клиенте, а не в клиенте-источнике.</span><span class="sxs-lookup"><span data-stu-id="4dca8-380">The email address in the CSV file must be the one specified in the target tenant, not the source tenant.</span></span>

<span data-ttu-id="4dca8-381">Пакетная отправка миграции также поддерживается из нового Центра администрирования Exchange при выборе меж клиента.</span><span class="sxs-lookup"><span data-stu-id="4dca8-381">Migration batch submission is also supported from the new Exchange Admin Center when selecting the cross-tenant option.</span></span>

#### <a name="update-on-premises-mailusers"></a><span data-ttu-id="4dca8-382">Обновление локального почтового ящика</span><span class="sxs-lookup"><span data-stu-id="4dca8-382">Update on-premises MailUsers</span></span>

<span data-ttu-id="4dca8-383">После перемещения почтового ящика из источника в целевой следует убедиться, что пользователи локальной почты, как исходные, так и целевые, обновлены с помощью нового targetAddress.</span><span class="sxs-lookup"><span data-stu-id="4dca8-383">Once the mailbox moves from source to target, you should ensure that the on-premises mail users, both Source and target, are updated with the new targetAddress.</span></span> <span data-ttu-id="4dca8-384">В примерах targetDeliveryDomain, используемый в движении, contoso.onmicrosoft.com **.**</span><span class="sxs-lookup"><span data-stu-id="4dca8-384">In the examples, the targetDeliveryDomain used in the move is **contoso.onmicrosoft.com**.</span></span> <span data-ttu-id="4dca8-385">Обновим почтовых пользователей с помощью этого targetAddress.</span><span class="sxs-lookup"><span data-stu-id="4dca8-385">Update the mail users with this targetAddress.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="4dca8-386">Часто задаваемые вопросы</span><span class="sxs-lookup"><span data-stu-id="4dca8-386">Frequently asked questions</span></span>

<span data-ttu-id="4dca8-387">**Нужно ли обновлять удаленные почтовые ящики в локальном источнике после перемещения?**</span><span class="sxs-lookup"><span data-stu-id="4dca8-387">**Do we need to update RemoteMailboxes in source on-premises after the move?**</span></span>

<span data-ttu-id="4dca8-388">Да, необходимо обновить targetAddress (RemoteRoutingAddress/ExternalEmailAddress) для исходных пользователей локальной системы, когда исходный почтовый ящик клиента перемещается в целевой клиент.</span><span class="sxs-lookup"><span data-stu-id="4dca8-388">Yes, you should update the targetAddress (RemoteRoutingAddress/ExternalEmailAddress) of the source on-premises users when the source tenant mailbox moves to target tenant.</span></span>  <span data-ttu-id="4dca8-389">Маршруты почты могут следовать рекомендации для нескольких пользователей почты с разными адресами targetAddresses, но запросы о занятости для почтовых пользователей должны быть нацелены на расположение пользователя почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="4dca8-389">While mail routing can follow the referrals across multiple mail users with different targetAddresses, Free/Busy lookups for mail users MUST target the location of the mailbox user.</span></span> <span data-ttu-id="4dca8-390">При подыском о занятости не будет искаться несколько перенаправлений.</span><span class="sxs-lookup"><span data-stu-id="4dca8-390">Free/Busy lookups will not chase multiple redirects.</span></span> 

<span data-ttu-id="4dca8-391">**Переносит ли содержимое папки чата Teams между клиентами?**</span><span class="sxs-lookup"><span data-stu-id="4dca8-391">**Does the Teams chat folder content migrate cross-tenant?**</span></span>  

<span data-ttu-id="4dca8-392">Нет, содержимое папки чата Teams не переносит содержимое между клиентами.</span><span class="sxs-lookup"><span data-stu-id="4dca8-392">No, the Teams chat folder content does not migrate cross-tenant.</span></span>  

<span data-ttu-id="4dca8-393">**Как можно увидеть только перемещения, которые являются перемещениями между арендаторами, а не переходами на несколько клиентов?**</span><span class="sxs-lookup"><span data-stu-id="4dca8-393">**How can I see just moves that are cross-tenant moves, not my onboarding and off-boarding moves?**</span></span>

<span data-ttu-id="4dca8-394">Используйте `-flags` параметр.</span><span class="sxs-lookup"><span data-stu-id="4dca8-394">Use the `-flags` parameter.</span></span> <span data-ttu-id="4dca8-395">Пример:</span><span class="sxs-lookup"><span data-stu-id="4dca8-395">Here is an example.</span></span>

```powershell
Get-MoveRequest -Flags "CrossTenant"  
```

<span data-ttu-id="4dca8-396">**Можно ли предоставить примеры сценариев для копирования атрибутов, используемых при тестировании?**</span><span class="sxs-lookup"><span data-stu-id="4dca8-396">**Can you provide example scripts for copying attributes used in testing?**</span></span>

> [!Note]
> <span data-ttu-id="4dca8-397">ПРИМЕР — КАК ЕСТЬ, БЕЗ ГАРАНТИИ</span><span class="sxs-lookup"><span data-stu-id="4dca8-397">SAMPLE – AS IS, NO WARRANTY</span></span><br/><span data-ttu-id="4dca8-398">Этот сценарий предполагает подключение как к исходным почтовым ящикам (для получения исходных значений), так и к целевым доменным службам Active Directory (чтобы пометь объект ADUser).</span><span class="sxs-lookup"><span data-stu-id="4dca8-398">This script assumes a connection to both source mailbox (to get source values) and the target on-premises Active Directory Domain Services (to stamp the ADUser object).</span></span> <span data-ttu-id="4dca8-399">Если в источнике включено восстановление для судебного разбирательства или отдельного элемента, установите его для учетной записи назначения.</span><span class="sxs-lookup"><span data-stu-id="4dca8-399">If source has litigation or single item recovery enabled, set this on the destination account.</span></span>  <span data-ttu-id="4dca8-400">Это увеличит размер контейнера конечной учетной записи до 100 ГБ.</span><span class="sxs-lookup"><span data-stu-id="4dca8-400">This will increase the dumpster size of destination account to 100 GB.</span></span>

```powershell
#Dumps out the test mailboxes from SourceTenant 
#Note, the filter applied on GetMailbox is for an attribute set on CA1 = “ProjectKermit” 
#These are the ‘target’ users to be moved to the Northwind org tenant #################################################################  
$outFile = "$home\desktop\UserListToImport.csv" 
$outArray = @() 
#output the test objects 
$Mailboxes = get-mailbox -filter "CustomAttribute1 -like ‘ProjectKermit'" -resultsize unlimited  
#created these mailboxes in adv using separate scripts but you get the idea on how to define the user list to move 
Foreach ($i in $Mailboxes)  
{ 
    $user = get-Recipient $i.alias 
    $myobj = New-Object System.Object 
    $myObj | Add-Member -type NoteProperty -name primarysmtpaddress -value $i.PrimarySMTPAddress 
    $myObj | Add-Member -type NoteProperty -name alias -value $i.alias 
    $myObj | Add-Member -type NoteProperty -name FirstName -value $User.FirstName 
    $myObj | Add-Member -type NoteProperty -name LastName -value $User.LastName 
    $myObj | Add-Member -type NoteProperty -name DisplayName -value $User.DisplayName 
    $myObj | Add-Member -type NoteProperty -name Name -value $i.Name 
    $myObj | Add-Member -type NoteProperty -name SamAccountName -value $i.SamAccountName 
    $myObj | Add-Member -type NoteProperty -name legacyExchangeDN -value $i.legacyExchangeDN    $myObj | Add-Member -type NoteProperty -name ExchangeGuid -value $i.ExchangeGuid 
    $outArray += $myObj 
} 
$outArray | Export-CSV $outfile -notypeinformation  
################################################################# 
#Copy the file $outfile to the desktop of the target on-premises 
#then run the below to create MEU in Target 
#################################################################  
$ImportUserList = import-csv "$home\desktop\UserListToImport.csv" 
$pwstr = "Something 98053 Random!!"; 
$pw = new-object "System.Security.SecureString"; 
for ($i=0; $i -lt $pwstr.Length; $i++) {$pw.AppendChar($pwstr[$i])} foreach ($user in $ImportUserList) { 
     $tmpUser = $null 
    $UPNSuffix = "@northwindtraders.com"    $UPN = $user.Alias+$upnsuffix 
    $tmpUser = New-MailUser -organization -UserPrincipalName $upn -ExternalEmailAddress $user.primarysmtpaddress -FirstName $user.FirstName ` 
                 -LastName $user.LastName -SamAccountName $user.SamAccountName -ResetPasswordOnNextLogon $false ` 
                 -Alias $user.alias -PrimarySmtpAddress $UPN -Name $User.Name -DisplayName $user.DisplayName ` 
                 -OrganizationalUnit "OU=ContosoUsers,OU=MLB,DC=ContosoLab,DC=net" -Password $pw       $x500 = "x500:" + $user.legacyExchangeDN 
    $tmpUser | Set-MailUser -ExchangeGuid $user.ExchangeGuid -EmailAddresses @{Add=$x500} -CustomAttribute1 "ProjectKermit" 
}  
################################################################# 
# On AADSync machine, run AADSync 
#################################################################  
Start-ADSyncSyncCycle 
 
#AADSync and FWDSync will create the target MEUs in the Target tenant 
```
<span data-ttu-id="4dca8-401">**Как получить доступ к Outlook в день 1 после того, как почтовый ящик использования будет перемещен?**</span><span class="sxs-lookup"><span data-stu-id="4dca8-401">**How do we access Outlook on Day 1 after the use mailbox is moved?**</span></span>

<span data-ttu-id="4dca8-402">Так как только один клиент может владеть доменом, прежний основной адрес SMTPAddress не будет связан с пользователем в целевом клиенте после завершения перемещения почтового ящика; только те домены, которые связаны с новым клиентом.</span><span class="sxs-lookup"><span data-stu-id="4dca8-402">Since only one tenant can own a domain, the former primary SMTPAddress will not be associated to the user in the target tenant when the mailbox move completes; only those domains associated with the new tenant.</span></span> <span data-ttu-id="4dca8-403">Outlook использует новое upN пользователей для проверки подлинности в службе, а профиль Outlook ожидает найти основной SMTP-адрес, который соответствует почтовому ящику в целевой системе.</span><span class="sxs-lookup"><span data-stu-id="4dca8-403">Outlook uses the users new UPN to authenticate to the service and the Outlook profile expects to find the legacy primary SMTPAddress to match the mailbox in the target system.</span></span> <span data-ttu-id="4dca8-404">Так как устаревший адрес не находится в целевой системе, профиль Outlook не будет подключаться для поиска только что перемещенного почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="4dca8-404">Since the legacy address is not in the target System the outlook profile will not connect to find the newly moved mailbox.</span></span> 

<span data-ttu-id="4dca8-405">Для этого начального развертывания пользователям потребуется перестроить свой профиль с новым и основным SMTP-адресом и повторно синхронизировать содержимое OST.</span><span class="sxs-lookup"><span data-stu-id="4dca8-405">For this initial deployment, users will need to rebuild their profile with their new UPN, primary SMTP address and re-sync OST content.</span></span> 

> [!Note]
> <span data-ttu-id="4dca8-406">Планируйте соответствующим образом по мере того, как вы будете пакетировать пользователей для завершения.</span><span class="sxs-lookup"><span data-stu-id="4dca8-406">Plan accordingly as you batch your users for completion.</span></span> <span data-ttu-id="4dca8-407">При использовании сети и емкости необходимо учитывать при создании профилей клиентов Outlook и загрузке последующих файлов OST и OAB на клиенты.</span><span class="sxs-lookup"><span data-stu-id="4dca8-407">You need to account for network utilization and capacity when Outlook client profiles are created and subsequent OST and OAB files are downloaded to clients.</span></span> 
 
<span data-ttu-id="4dca8-408">**Какие роли Exchange RBAC необходимы для выполнения перекрестного перемещения клиентов?**</span><span class="sxs-lookup"><span data-stu-id="4dca8-408">**What Exchange RBAC roles do I need to be member of to set up or complete a cross-tenant move?**</span></span>
 
<span data-ttu-id="4dca8-409">Существует матрица ролей, основанная на допущении делегирования обязанностей при выполнении перемещения почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="4dca8-409">There a matrix of roles based on assumption of delegated duties when executing a mailbox move.</span></span> <span data-ttu-id="4dca8-410">В настоящее время требуются две роли:</span><span class="sxs-lookup"><span data-stu-id="4dca8-410">Currently, two roles are required:</span></span>  

- <span data-ttu-id="4dca8-411">Первая роль — это одновредная задача установки, которая устанавливает авторизацию перемещения контента в границы клиента или организации или за ее пределы.</span><span class="sxs-lookup"><span data-stu-id="4dca8-411">The first role is for a one-time setup task that establishes the authorization of moving content into or out of your tenant/organizational boundary.</span></span> <span data-ttu-id="4dca8-412">Так как перемещение данных из системы контроля организации является критически важной проблемой для всех компаний, мы выбрали наивысшую назначенную роль администратора организации (OrgAdmin).</span><span class="sxs-lookup"><span data-stu-id="4dca8-412">As moving data out of your organizational control is a critical concern for all companies, we opted with the highest assigned role of Organization Administrator (OrgAdmin).</span></span> <span data-ttu-id="4dca8-413">Эта роль должна изменить или настроить новую организацию OrganizationRelationship, которая определяет -MailboxMoveCapability в удаленной организации.</span><span class="sxs-lookup"><span data-stu-id="4dca8-413">This role must alter or setup a new OrganizationRelationship that defines the -MailboxMoveCapability with the remote organization.</span></span> <span data-ttu-id="4dca8-414">Только OrgAdmin может изменять параметр MailboxMoveCapability, а другими атрибутами в OrganizationRelationhip может управлять администратор федеративного общего доступа.</span><span class="sxs-lookup"><span data-stu-id="4dca8-414">Only the OrgAdmin can alter the MailboxMoveCapability setting, while other attributes on the OrganizationRelationhip can be managed by the Federated Sharing administrator.</span></span> 
 
- <span data-ttu-id="4dca8-415">Роль выполнения фактических команд перемещения можно делегировать функции нижнего уровня.</span><span class="sxs-lookup"><span data-stu-id="4dca8-415">The role of executing the actual move commands can be delegated to a lower-level function.</span></span> <span data-ttu-id="4dca8-416">Роли почтовых ящиков перемещения назначена возможность перемещения почтовых ящиков в организации или из нее с помощью `-RemoteTenant` параметра.</span><span class="sxs-lookup"><span data-stu-id="4dca8-416">The role of Move Mailboxes is assigned the capability of moving mailboxes in or out of the organization by using the `-RemoteTenant` parameter.</span></span>  

<span data-ttu-id="4dca8-417">**Как выбрать адрес SMTP для targetAddress (TargetDeliveryDomain) в преобразованном почтовом ящике (в преобразование MailUser)?**</span><span class="sxs-lookup"><span data-stu-id="4dca8-417">**How do we target which SMTP address is selected for targetAddress (TargetDeliveryDomain) on the converted mailbox (to MailUser conversion)?**</span></span>
 
<span data-ttu-id="4dca8-418">Перемещения почтовых ящиков Exchange с помощью MRS создают targetAddress в исходном исходном почтовом ящике при преобразовании в MailUser путем совпадения адреса электронной почты (proxyAddress) в целевом объекте.</span><span class="sxs-lookup"><span data-stu-id="4dca8-418">Exchange mailbox moves using MRS craft the targetAddress on the original source mailbox when converting to a MailUser by matching an email address (proxyAddress) on the target object.</span></span> <span data-ttu-id="4dca8-419">Процесс принимает значение -TargetDeliveryDomain, переданное в команду перемещения, а затем проверяет наличие совпадающих прокси для этого домена на целевой стороне.</span><span class="sxs-lookup"><span data-stu-id="4dca8-419">The process takes the -TargetDeliveryDomain value passed into the move command, then checks for a matching proxy for that domain on the target side.</span></span> <span data-ttu-id="4dca8-420">При поиске совпадения совпадающий прокси-адрес используется для того, чтобы установить externalEmailAddress (targetAddress) для преобразованного объекта почтового ящика (теперь MailUser).</span><span class="sxs-lookup"><span data-stu-id="4dca8-420">When we find a match, the matching proxyAddress is used to set the ExternalEmailAddress (targetAddress) on the converted mailbox (now MailUser) object.</span></span>
 
<span data-ttu-id="4dca8-421">**Как меняются разрешения для почтового ящика?**</span><span class="sxs-lookup"><span data-stu-id="4dca8-421">**How do mailbox permissions transition?**</span></span>

<span data-ttu-id="4dca8-422">К разрешениям для почтовых ящиков относятся "Отправить от имени" и "Доступ к почтовым ящикам":</span><span class="sxs-lookup"><span data-stu-id="4dca8-422">Mailbox permissions include Send on Behalf of and Mailbox Access:</span></span> 

- <span data-ttu-id="4dca8-423">Send On Behalf of (AD:publicDelegates) хранит DN получателей с доступом к почтовому ящику пользователя в качестве делегата.</span><span class="sxs-lookup"><span data-stu-id="4dca8-423">Send On Behalf Of (AD:publicDelegates) stores the DN of recipients with access to a user’s mailbox as a delegate.</span></span> <span data-ttu-id="4dca8-424">Это значение хранится в Active Directory и в настоящее время не перемещается в рамках перехода почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="4dca8-424">This value is stored in Active Directory and currently does not move as part of the mailbox transition.</span></span> <span data-ttu-id="4dca8-425">Если исходный почтовый ящик имеет открытые объекты PublicDelegates, вам потребуется переустанавлить publicDelegates в целевом почтовом ящике после завершения преобразования MEU в почтовый ящик в целевую среду путем запуска `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` .</span><span class="sxs-lookup"><span data-stu-id="4dca8-425">If the source mailbox has publicDelegates set, you will need to restamp the publicDelegates on the target Mailbox once the MEU to Mailbox conversion completes in the target environment by running `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>`.</span></span> 
 
- <span data-ttu-id="4dca8-426">Разрешения почтового ящика, хранимые в почтовом ящике, перемещаются вместе с почтовым ящиком при перемещении основного и делегата в целевую систему.</span><span class="sxs-lookup"><span data-stu-id="4dca8-426">Mailbox Permissions that are stored in the mailbox will move with the mailbox when both the principal and the delegate are moved to the target system.</span></span> <span data-ttu-id="4dca8-427">Например, пользователю TestUser_7 полный доступ к почтовому ящику TestUser_8 в клиенте SourceCompany.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="4dca8-427">For example, the user TestUser_7 is granted FullAccess to the mailbox TestUser_8 in the tenant SourceCompany.onmicrosoft.com.</span></span> <span data-ttu-id="4dca8-428">После завершения перемещения почтового ящика в TargetCompany.onmicrosoft.com эти же разрешения устанавливаются в целевом каталоге.</span><span class="sxs-lookup"><span data-stu-id="4dca8-428">After the mailbox move completes to TargetCompany.onmicrosoft.com, the same permissions are set up in the target directory.</span></span> <span data-ttu-id="4dca8-429">Примеры использования *Get-MailboxPermission* для TestUser_7 в исходных и целевых клиентах показаны ниже.</span><span class="sxs-lookup"><span data-stu-id="4dca8-429">Examples using *Get-MailboxPermission* for TestUser_7 in both source and target tenants are shown below.</span></span> <span data-ttu-id="4dca8-430">К ним примещается префикс "источник" и "целевой".</span><span class="sxs-lookup"><span data-stu-id="4dca8-430">Exchange cmdlets are prefixed with source and target accordingly.</span></span> 
 
<span data-ttu-id="4dca8-431">Вот пример вывода разрешения почтового ящика перед перемещением.</span><span class="sxs-lookup"><span data-stu-id="4dca8-431">Here's an example of the output of the mailbox permission before a move.</span></span> 

```powershell
PS C:\PowerShell\> Get-SourceMailboxPermission testuser_7 |ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       False
TestUser_8@SourceCompany.onmicrosoft.com         {FullAccess}                                                            False       False....
```
<span data-ttu-id="4dca8-432">Вот пример вывода разрешения почтового ящика после перемещения.</span><span class="sxs-lookup"><span data-stu-id="4dca8-432">Here's an example of the output of the mailbox permission after the move.</span></span> 

```powershell
PS C:\PowerShell\> Get-TargetMailboxPermission testuser_7 | ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       FalseTestUser_8@TargetCompany.onmicrosoft.com         {FullAccess}                                                            False       False
```
 
> [!Note]
> <span data-ttu-id="4dca8-433">Разрешения для почтовых ящиков и календаря между клиентами НЕ поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="4dca8-433">Cross-tenant mailbox and calendar permissions are NOT supported.</span></span> <span data-ttu-id="4dca8-434">Необходимо упорядочить участников и делегатов в консолидированные пакеты перемещения, чтобы эти подключенные почтовые ящики одновременно перемещались из клиента-источника.</span><span class="sxs-lookup"><span data-stu-id="4dca8-434">You must organize principals and delegates into consolidated move batches so that these connected mailboxes are transitioned at the same time from the source tenant.</span></span> 

<span data-ttu-id="4dca8-435">**Какой прокси-сервер X500 следует добавить к целевым прокси-адресам MailUser, чтобы включить миграцию?**</span><span class="sxs-lookup"><span data-stu-id="4dca8-435">**What X500 proxy should be added to the target MailUser proxy addresses to enable migration?**</span></span>  

<span data-ttu-id="4dca8-436">Для миграции почтовых ящиков между клиентами необходимо, чтобы значение LegacyExchangeDN объекта исходных почтовых ящиков было помещено как адрес электронной почты x500 в целевом объекте MailUser.</span><span class="sxs-lookup"><span data-stu-id="4dca8-436">The cross-tenant mailbox migration requires that the LegacyExchangeDN value of the source mailbox object to be stamped as an x500 email address on the target MailUser object.</span></span>  

<span data-ttu-id="4dca8-437">Пример.</span><span class="sxs-lookup"><span data-stu-id="4dca8-437">Example:</span></span>  
```powershell
LegacyExchangeDN value on source mailbox is:  
/o=First Organization/ou=Exchange Administrative Group(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara  

so the x500 email address to be added to target MailUser object would be:  
x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9-Lara  
```

> [!Note]  
> <span data-ttu-id="4dca8-438">Помимо этого прокси-сервера X500 вам потребуется скопировать все прокси-серверы X500 из почтового ящика в источнике в почтовый ящик в целевом.</span><span class="sxs-lookup"><span data-stu-id="4dca8-438">In addition to this X500 proxy, you will need to copy all X500 proxies from the mailbox in the source to the mailbox in the target.</span></span>  

<span data-ttu-id="4dca8-439">**Где начать устранение неполадок, если перемещения не работают?**</span><span class="sxs-lookup"><span data-stu-id="4dca8-439">**Where do I start troubleshooting if moves do not work?**</span></span>  

<span data-ttu-id="4dca8-440">Для начала запустите сценарий VerifySetup.ps1, расположенный на [GitHub,](https://github.com/microsoft/cross-tenant/releases/tag/Preview) и просмотрите выходные данные.</span><span class="sxs-lookup"><span data-stu-id="4dca8-440">Start by running the VerifySetup.ps1 script located [on GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview) and review the output.</span></span>

<span data-ttu-id="4dca8-441">Вот пример запуска VerifySetup.ps1 в целевом клиенте:</span><span class="sxs-lookup"><span data-stu-id="4dca8-441">Here's an example of running VerifySetup.ps1 on the target tenant:</span></span>

```powershell
VerifySetup.ps1 -PartnerTenantId <SourceTenantId> -ApplicationId <AADApplicationId> -ApplicationKeyVaultUrl <appKeyVaultUrl> -PartnerTenantDomain <PartnerTenantDomain> -Verbose
```

<span data-ttu-id="4dca8-442">Вот пример eExample запуска VerifySetup.ps1 в клиенте-источнике:</span><span class="sxs-lookup"><span data-stu-id="4dca8-442">Here's an eExample of running VerifySetup.ps1 on the source tenant:</span></span>

```powershell
VerifySetup.ps1 -PartnerTenantId <TargetTenantId> -ApplicationId <AADApplicationId>
```

<span data-ttu-id="4dca8-443">**Может ли исходный и целевой клиент использовать одно и то же доменное имя?**</span><span class="sxs-lookup"><span data-stu-id="4dca8-443">**Can the source and target tenant utilize the same domain name?**</span></span>  

<span data-ttu-id="4dca8-444">Нет.</span><span class="sxs-lookup"><span data-stu-id="4dca8-444">No.</span></span> <span data-ttu-id="4dca8-445">Имена доменов источника и целевого клиента должны быть уникальными.</span><span class="sxs-lookup"><span data-stu-id="4dca8-445">The source and target tenant domain names must be unique.</span></span> <span data-ttu-id="4dca8-446">Например, исходный домен contoso.com и целевой домен fourthcoffee.com.</span><span class="sxs-lookup"><span data-stu-id="4dca8-446">For example, a source domain of contoso.com and the target domain of fourthcoffee.com.</span></span>

<span data-ttu-id="4dca8-447">**Будут ли общие почтовые ящики перемещаться и по-прежнему работать?**</span><span class="sxs-lookup"><span data-stu-id="4dca8-447">**Will shared mailboxes move and still work?**</span></span>

<span data-ttu-id="4dca8-448">Да, но мы сохраняем только разрешения на хранение, как описано в этих статьях:</span><span class="sxs-lookup"><span data-stu-id="4dca8-448">Yes, however we only keep the store permissions as described in these articles:</span></span>

- [<span data-ttu-id="4dca8-449">Microsoft Docs | Управление разрешениями для получателей в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="4dca8-449">Microsoft Docs | Manage permissions for recipients in Exchange Online</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients)

- [<span data-ttu-id="4dca8-450">Служба поддержки Майкрософт | Предоставление разрешений для почтовых ящиков Exchange и Outlook в Выделенном Office 365</span><span class="sxs-lookup"><span data-stu-id="4dca8-450">Microsoft Support | How to grant Exchange and Outlook mailbox permissions in Office 365 dedicated</span></span>](https://support.microsoft.com/topic/how-to-grant-exchange-and-outlook-mailbox-permissions-in-office-365-dedicated-bac01b2c-08ff-2eac-e1c8-6dd01cf77287)

<span data-ttu-id="4dca8-451">**Требуется ли Azure Key Vault и когда будут выполнены транзакции?**</span><span class="sxs-lookup"><span data-stu-id="4dca8-451">**Is Azure Key Vault required and when are transactions made?**</span></span>  

<span data-ttu-id="4dca8-452">Да, для хранения сертификата для авторизации миграции необходима подписка Azure с использованием Key Vault.</span><span class="sxs-lookup"><span data-stu-id="4dca8-452">Yes, an Azure subscription is required to use Key Vault to store the certificate to authorize migration.</span></span> <span data-ttu-id="4dca8-453">В отличие от миграций с использованием имени пользователя & пароля для проверки подлинности в источнике, при миграции почтовых ящиков между клиентами в качестве секрета и учетных данных используется OAuth и этот сертификат.</span><span class="sxs-lookup"><span data-stu-id="4dca8-453">Unlike onboarding migrations which use username & password to authenticate to the source, cross-tenant mailbox migrations use OAuth and this certificate as the secret/credential.</span></span> <span data-ttu-id="4dca8-454">Доступ к хранилищу Key Vault должен поддерживаться во всех миграциях почтовых ящиков, так как доступ к нему должен быть один раз в начале и после окончания миграции, а также один раз в 24 часа во время добавонной синхронизации.</span><span class="sxs-lookup"><span data-stu-id="4dca8-454">Access to the Key Vault must be maintained throughout all mailbox migrations as it is accessed once at the beginning and once end of migration, as well as once every 24 hours during incremental sync times.</span></span> <span data-ttu-id="4dca8-455">Здесь вы можете просмотреть []( https://azure.microsoft.com/en-us/pricing/details/key-vault/)сведения о стоимости AKV.</span><span class="sxs-lookup"><span data-stu-id="4dca8-455">You can review AKV costing details [here]( https://azure.microsoft.com/en-us/pricing/details/key-vault/).</span></span>  

<span data-ttu-id="4dca8-456">**Есть ли какие-либо рекомендации по пакетам?**</span><span class="sxs-lookup"><span data-stu-id="4dca8-456">**Do you have any recommendations for batches?**</span></span>  

<span data-ttu-id="4dca8-457">Не более 2000 почтовых ящиков на пакет.</span><span class="sxs-lookup"><span data-stu-id="4dca8-457">Do not exceed 2000 mailboxes per batch.</span></span> <span data-ttu-id="4dca8-458">Мы настоятельно рекомендуем отправку пакетов за две недели до даты вырезания, так как они не влияют на конечных пользователей во время синхронизации. Если вам требуется руководство по количеству почтовых ящиков более 50 000, вы можете связаться со списком рассылки отзывов по техническим вопросам по crosstenantmigrationpreview@service.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="4dca8-458">We strongly recommend submitting batches two weeks prior to the cut-over date as there is no impact to the end users during sync. If you need guidance for mailboxes quantities over 50,000 you can reach out to the Engineering Feedback Distribution List at crosstenantmigrationpreview@service.microsoft.com.</span></span>

<span data-ttu-id="4dca8-459">**Что делать, если я использую шифрование службы с ключом клиента?**</span><span class="sxs-lookup"><span data-stu-id="4dca8-459">**What if I use Service encryption with Customer Key?**</span></span>

<span data-ttu-id="4dca8-460">Почтовый ящик будет расшифровываться перед перемещением.</span><span class="sxs-lookup"><span data-stu-id="4dca8-460">The mailbox will be decrypted prior to moving.</span></span> <span data-ttu-id="4dca8-461">Убедитесь, что ключ клиента настроен в целевом клиенте, если он по-прежнему требуется.</span><span class="sxs-lookup"><span data-stu-id="4dca8-461">Ensure Customer Key is configured in the target tenant if it is still required.</span></span> <span data-ttu-id="4dca8-462">Дополнительные [сведения см.](https://docs.microsoft.com/microsoft-365/compliance/customer-key-overview) здесь.</span><span class="sxs-lookup"><span data-stu-id="4dca8-462">See [here](https://docs.microsoft.com/microsoft-365/compliance/customer-key-overview) for more information.</span></span>  

<span data-ttu-id="4dca8-463">**Каково предполагаемое время миграции?**</span><span class="sxs-lookup"><span data-stu-id="4dca8-463">**What is the estimated migration time?**</span></span>

<span data-ttu-id="4dca8-464">Чтобы помочь вам спланировать [](https://docs.microsoft.com/exchange/mailbox-migration/office-365-migration-best-practices#estimated-migration-times) миграцию, в таблице ниже представлены рекомендации по поводу того, когда следует ожидать завершения массовой миграции почтовых ящиков или отдельных миграций.</span><span class="sxs-lookup"><span data-stu-id="4dca8-464">To help you plan your migration, the table present [here](https://docs.microsoft.com/exchange/mailbox-migration/office-365-migration-best-practices#estimated-migration-times) shows the guidelines about when to expect bulk mailbox migrations or individual migrations to complete.</span></span> <span data-ttu-id="4dca8-465">Эти оценки основаны на анализе данных предыдущих миграций клиентов.</span><span class="sxs-lookup"><span data-stu-id="4dca8-465">These estimates are based on a data analysis of previous customer migrations.</span></span> <span data-ttu-id="4dca8-466">Так как каждая среда уникальна, точная скорость миграции может отличаться.</span><span class="sxs-lookup"><span data-stu-id="4dca8-466">Because every environment is unique, your exact migration velocity may vary.</span></span>  

<span data-ttu-id="4dca8-467">Помните, что эта функция в настоящее время находится в предварительной версии, а SLA и применимые уровни обслуживания не применяются к любым вопросам производительности или доступности во время просмотра состояния этой функции.</span><span class="sxs-lookup"><span data-stu-id="4dca8-467">Do remember that this feature is currently in preview and the SLA and any applicable Service Levels do not apply to any performance or availability issues during the preview status of this feature.</span></span>

## <a name="known-issues"></a><span data-ttu-id="4dca8-468">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="4dca8-468">Known issues</span></span>  

-  <span data-ttu-id="4dca8-469">**Проблема: невозможно перенести автоматически расширившие архивы.**</span><span class="sxs-lookup"><span data-stu-id="4dca8-469">**Issue: Auto Expanded archives cannot be migrated.**</span></span> <span data-ttu-id="4dca8-470">Функция миграции между клиентами поддерживает миграцию основного и архивного почтовых ящиков для определенного пользователя.</span><span class="sxs-lookup"><span data-stu-id="4dca8-470">The cross-tenant migration feature support migrations of the primary mailbox and archive mailbox for a specific user.</span></span> <span data-ttu-id="4dca8-471">Если у пользователя в источнике есть автоматически расширенный архив , то есть несколько архивных почтовых ящиков, функция не сможет перенести дополнительные архивы и не сможет ее перенести.</span><span class="sxs-lookup"><span data-stu-id="4dca8-471">If the user in the source however has an auto expanded archive – meaning more than one archive mailbox, the feature is unable to migrate the additional archives and should fail.</span></span>

- <span data-ttu-id="4dca8-472">**Проблема: cloud MailUsers с ненанимателями smtp proxyAddress блок MRS перемещает фон.**</span><span class="sxs-lookup"><span data-stu-id="4dca8-472">**Issue: Cloud MailUsers with non-owned smtp proxyAddress block MRS moves background.**</span></span> <span data-ttu-id="4dca8-473">При создании объектов MailUser целевого клиента необходимо убедиться, что все прокси-адреса SMTP принадлежат целевой организации клиента.</span><span class="sxs-lookup"><span data-stu-id="4dca8-473">When creating target tenant MailUser objects, you must ensure that all SMTP proxy addresses belong to the target tenant organization.</span></span> <span data-ttu-id="4dca8-474">Если прокси-адрес SMTP существует для целевого почтового пользователя, который не принадлежит локальному арендатору, преобразование MailUser в Mailbox будет предотвращено.</span><span class="sxs-lookup"><span data-stu-id="4dca8-474">If an SMTP proxyAddress exists on the target mail user that does not belong to the local tenant, the conversion of the MailUser to Mailbox is prevented.</span></span> <span data-ttu-id="4dca8-475">Это связано с нашей гарантией того, что объекты почтовых ящиков могут отправлять почту только из доменов, для которых клиент является достоверным (домены, заявленные клиентом):</span><span class="sxs-lookup"><span data-stu-id="4dca8-475">This is due to our assurance that mailbox objects can only send mail from domains for which the tenant is authoritative (domains claimed by the tenant):</span></span> 

   - <span data-ttu-id="4dca8-476">При синхронизации пользователей из локальной сети с помощью Azure AD Connect вы подаете локально объекты MailUser с помощью ExternalEmailAddress, указывая на исходный клиент, в котором существует почтовый ящик (laran@contoso.onmicrosoft.com), и помечаете PrimarySMTPAddress как домен, который находится в целевом клиенте (Lara.Newton@northwind.com).</span><span class="sxs-lookup"><span data-stu-id="4dca8-476">When you sync users from on-premises using Azure AD Connect, you provision on-premises MailUser objects with ExternalEmailAddress pointing to the source tenant where the mailbox exists (laran@contoso.onmicrosoft.com) and you stamp the PrimarySMTPAddress as a domain that resides in the target tenant (Lara.Newton@northwind.com).</span></span> <span data-ttu-id="4dca8-477">Эти значения синхронизируются с клиентом, и соответствующий почтовый пользователь готов к миграции.</span><span class="sxs-lookup"><span data-stu-id="4dca8-477">These values sync down to the tenant and an appropriate mail user is provisioned and ready for migration.</span></span> <span data-ttu-id="4dca8-478">Пример объекта показан здесь.</span><span class="sxs-lookup"><span data-stu-id="4dca8-478">An example object is shown here.</span></span>
     ```powershell
     target/AADSynced user] PS C> Get-MailUser laran | select ExternalEmailAddress, EmailAddresses   
     ExternalEmailAddress               EmailAddresses 
     --------------------               -------------- 
     SMTP:laran@contoso.onmicrosoft.com {SMTP:lara.newton@northwind.com} 
     ```

   > [!Note]
   > <span data-ttu-id="4dca8-479">Адрес *contoso.onmicrosoft.com* нет *в* массиве EmailAddresses /proxyAddresses.</span><span class="sxs-lookup"><span data-stu-id="4dca8-479">The *contoso.onmicrosoft.com* address is *not* present in the EmailAddresses / proxyAddresses array.</span></span>

- <span data-ttu-id="4dca8-480">**Проблема: объекты MailUser с "внешними" основными SMTP-адресами изменены или сброшены в "внутренние" домены компании**</span><span class="sxs-lookup"><span data-stu-id="4dca8-480">**Issue: MailUser objects with “external” primary SMTP addresses are modified / reset to “internal” company claimed domains**</span></span>

   <span data-ttu-id="4dca8-481">Объекты MailUser — это указатели на не локальные почтовые ящики.</span><span class="sxs-lookup"><span data-stu-id="4dca8-481">MailUser objects are pointers to non-local mailboxes.</span></span> <span data-ttu-id="4dca8-482">В случае миграции почтовых ящиков между клиентами мы используем объекты MailUser, чтобы представлять исходный почтовый ящик (с точки зрения целевой организации) или целевой почтовый ящик (с точки зрения организации-источника).</span><span class="sxs-lookup"><span data-stu-id="4dca8-482">In the case for cross-tenant mailbox migrations, we use MailUser objects to represent either the source mailbox (from the target organization’s perspective) or target mailbox (from the source organization’s perspective).</span></span> <span data-ttu-id="4dca8-483">У mailUsers будет адрес ExternalEmailAddress (targetAddress), который указывает на smtp-адрес фактического почтового ящика (ProxyTest@fabrikam.onmicrosoft.com) и основной адресSMTP, который представляет smTP-адрес пользователя почтового ящика в каталоге.</span><span class="sxs-lookup"><span data-stu-id="4dca8-483">The MailUsers will have an ExternalEmailAddress (targetAddress) that points to the smtp address of the actual mailbox (ProxyTest@fabrikam.onmicrosoft.com) and primarySMTP address that represents the displayed SMTP address of the mailbox user in the directory.</span></span> <span data-ttu-id="4dca8-484">В некоторых организациях основной SMTP-адрес отображается как внешний SMTP-адрес, а не как адрес, владельцем или проверенным локальным клиентом (например, fabrikam.com, а не как contoso.com).</span><span class="sxs-lookup"><span data-stu-id="4dca8-484">Some organizations choose to display the primary SMTP address as an external SMTP address, not as an address owned/verified by the local tenant (such as fabrikam.com rather than as contoso.com).</span></span>  <span data-ttu-id="4dca8-485">Однако после того как объект плана обслуживания Exchange будет применен к MailUser с помощью операций лицензирования, основной SMTP-адрес будет изменен, чтобы показать его как домен, проверенный локальной организацией (contoso.com).</span><span class="sxs-lookup"><span data-stu-id="4dca8-485">However, once an Exchange service plan object is applied to the MailUser via licensing operations, the primary SMTP address is modified to show as a domain verified by the local organization (contoso.com).</span></span> <span data-ttu-id="4dca8-486">Существует две возможные причины:</span><span class="sxs-lookup"><span data-stu-id="4dca8-486">There are two potential reasons:</span></span>
   
   - <span data-ttu-id="4dca8-487">Когда к MailUser применяется какой-либо план обслуживания Exchange, процесс Azure AD начинает принудительно выполнять очистку прокси-серверов, чтобы убедиться, что локализованная организация не может отправлять почту, подмену или почту из другого клиента.</span><span class="sxs-lookup"><span data-stu-id="4dca8-487">When any Exchange service plan is applied to a MailUser, the Azure AD process starts to enforce proxy scrubbing to ensure that the local organization is not able to send mail out, spoof, or mail from another tenant.</span></span> <span data-ttu-id="4dca8-488">Любой SMTP-адрес объекта получателя с этими планами обслуживания будет удален, если адрес не проверен локальной организацией.</span><span class="sxs-lookup"><span data-stu-id="4dca8-488">Any SMTP address on a recipient object with these service plans will be removed if the address is not verified by the local organization.</span></span> <span data-ttu-id="4dca8-489">Как и в примере, Fabikam.com не проверяется клиентом contoso.onmicrosoft.com, поэтому при очистке этот fabrikam.com домен.</span><span class="sxs-lookup"><span data-stu-id="4dca8-489">As is the case in the example, the Fabikam.com domain is NOT verified by the contoso.onmicrosoft.com tenant, so the scrubbing removes that fabrikam.com domain.</span></span> <span data-ttu-id="4dca8-490">Если вы хотите сохранить эти внешние домены в MailUser до миграции или после миграции, необходимо изменить процессы миграции, чтобы отодвинуть лицензии после завершения перемещения или перед перемещением, чтобы убедиться, что к пользователям применена ожидаемая внешняя фирменая марка.</span><span class="sxs-lookup"><span data-stu-id="4dca8-490">If you wish to persist these external domain on MailUser, either before the migration or after migration, you need to alter your migration processes to strip licenses after the move completes or before the move to ensure that the users have the expected external branding applied.</span></span> <span data-ttu-id="4dca8-491">Необходимо убедиться, что объект почтового ящика имеет правильную лицензию, чтобы не влиять на службу почты.</span><span class="sxs-lookup"><span data-stu-id="4dca8-491">You will need to ensure that the mailbox object is properly licensed to not affect mail service.</span></span><br/><br/><span data-ttu-id="4dca8-492">Ниже показан пример сценария для удаления планов обслуживания для MailUser в Contoso.onmicrosoft.com клиента.</span><span class="sxs-lookup"><span data-stu-id="4dca8-492">An example script to remove the service plans on a MailUser in the Contoso.onmicrosoft.com tenant is shown here.</span></span>

    ```powershell
    $LO = New-MsolLicenseOptions -AccountSkuId "contoso:ENTERPRISEPREMIUM" DisabledPlans 
    "LOCKBOX_ENTERPRISE","EXCHANGE_S_ENTERPRISE","INFORMATION_BARRIERS","MIP_S_CLP2","
    MIP_S_CLP1","MYANALYTICS_P2","EXCHANGE_ANALYTICS","EQUIVIO_ANALYTICS","THREAT_INTE
    LLIGENCE","PAM_ENTERPRISE","PREMIUM_ENCRYPTION" 
    Set-MsolUserLicense -UserPrincipalName proxytest@contoso.com LicenseOptions $lo 
    ```

       <span data-ttu-id="4dca8-493">Здесь показаны результаты в наборе назначенных servicePlans.</span><span class="sxs-lookup"><span data-stu-id="4dca8-493">Results in the set of ServicePlans assigned are shown here.</span></span>

    ```powershell
    (Get-MsolUser -UserPrincipalName proxytest@contoso.com).licenses |select 
    -ExpandProperty servicestatus |sort ProvisioningStatus -Descending   
    ServicePlan           ProvisioningStatus 
    -----------           ------------------ 
    ATP_ENTERPRISE        PendingProvisioning 
    MICROSOFT_SEARCH      PendingProvisioning 
    INTUNE_O365           PendingActivation 
    PAM_ENTERPRISE        Disabled 
    EXCHANGE_ANALYTICS    Disabled 
    EQUIVIO_ANALYTICS     Disabled 
    THREAT_INTELLIGENCE   Disabled 
    LOCKBOX_ENTERPRISE    Disabled 
    PREMIUM_ENCRYPTION    Disabled 
    EXCHANGE_S_ENTERPRISE Disabled 
    INFORMATION_BARRIERS  Disabled 
    MYANALYTICS_P2        Disabled 
    MIP_S_CLP1            Disabled 
    MIP_S_CLP2            Disabled 
    ADALLOM_S_O365        PendingInput 
    RMS_S_ENTERPRISE      Success 
    YAMMER_ENTERPRISE     Success 
    PROJECTWORKMANAGEMENT Success 
    BI_AZURE_P2           Success 
    WHITEBOARD_PLAN3      Success 
    SHAREPOINTENTERPRISE  Success 
    SHAREPOINTWAC         Success 
    KAIZALA_STANDALONE    Success 
    OFFICESUBSCRIPTION    Success 
    MCOSTANDARD           Success 
    Deskless              Success 
    STREAM_O365_E5        Success 
    FLOW_O365_P3          Success 
    POWERAPPS_O365_P3     Success 
    TEAMS1                Success 
    MCOEV                 Success 
    MCOMEETADV            Success 
    BPOS_S_TODO_3         Success 
    FORMS_PLAN_E5         Success 
    SWAY                  Success 

    ```
 
       <span data-ttu-id="4dca8-494">Основное имя пользователя PrimarySMTPAddress больше не будет удалено.</span><span class="sxs-lookup"><span data-stu-id="4dca8-494">The user’s PrimarySMTPAddress is no longer scrubbed.</span></span> <span data-ttu-id="4dca8-495">Домен fabrikam.com не принадлежит contoso.onmicrosoft.com и будет сохраняться в качестве основного SMTP-адреса, показанного в каталоге.</span><span class="sxs-lookup"><span data-stu-id="4dca8-495">The fabrikam.com domain is not owned by the contoso.onmicrosoft.com tenant and will persist as the primary SMTP address shown in the directory.</span></span>

       <span data-ttu-id="4dca8-496">Пример:</span><span class="sxs-lookup"><span data-stu-id="4dca8-496">Here is an example.</span></span>

    ```powershell
    get-recipient proxytest | ft -a userprin*, primary*, external*   
    PrimarySmtpAddress        ExternalDirectoryObjectId               ExternalEmailAddress 
    ------------------        -------------------------               -------------------- 
    proxytest@fabrikam.com    e2513482-1d5b-4066-936a-cbc7f8f6f817    SMTP:proxytest@fabrikam.com 
    ```

   - <span data-ttu-id="4dca8-497">Если для msExchRemoteRecipientType установлено 8 (DeprovisionMailbox) для локальной службы MailUsers, перенесенной в целевой клиент, логика очистки прокси в Azure удалит невторизированные домены и сбросит primarySMTP в собственный домен.</span><span class="sxs-lookup"><span data-stu-id="4dca8-497">When msExchRemoteRecipientType is set to 8 (DeprovisionMailbox), for on-premises MailUsers that are migrated to the target tenant, the proxy scrubbing logic in Azure will remove nonowned domains and reset the primarySMTP to an owned domain.</span></span> <span data-ttu-id="4dca8-498">При очистке msExchRemoteRecipientType в локальном mailUser логика прокси-очистки больше не применяется.</span><span class="sxs-lookup"><span data-stu-id="4dca8-498">By clearing msExchRemoteRecipientType in the on-premises MailUser, the proxy scrub logic no longer applies.</span></span> <br/><br><span data-ttu-id="4dca8-499">Ниже приведен полный набор возможных планов обслуживания, включая Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="4dca8-499">Below is the full set of possible Service Plans that include Exchange Online.</span></span>

   | <span data-ttu-id="4dca8-500">Имя</span><span class="sxs-lookup"><span data-stu-id="4dca8-500">Name</span></span>                                              |
   |---------------------------------------------------|
   | <span data-ttu-id="4dca8-501">Advanced eDiscovery Storage (500 ГБ)</span><span class="sxs-lookup"><span data-stu-id="4dca8-501">Advanced eDiscovery Storage (500GB)</span></span>               |
   | <span data-ttu-id="4dca8-502">Защищенное хранилище</span><span class="sxs-lookup"><span data-stu-id="4dca8-502">Customer Lockbox</span></span>                                  |
   | <span data-ttu-id="4dca8-503">Защита от потери данных</span><span class="sxs-lookup"><span data-stu-id="4dca8-503">Data Loss Prevention</span></span>                              |
   | <span data-ttu-id="4dca8-504">Exchange Enterprise CAL Services (EOP, DLP)</span><span class="sxs-lookup"><span data-stu-id="4dca8-504">Exchange Enterprise CAL Services (EOP, DLP)</span></span>       |
   | <span data-ttu-id="4dca8-505">Exchange Essentials</span><span class="sxs-lookup"><span data-stu-id="4dca8-505">Exchange Essentials</span></span>                               |
   | <span data-ttu-id="4dca8-506">Exchange Foundation</span><span class="sxs-lookup"><span data-stu-id="4dca8-506">Exchange Foundation</span></span>                               |
   | <span data-ttu-id="4dca8-507">Exchange Online (P1)</span><span class="sxs-lookup"><span data-stu-id="4dca8-507">Exchange Online (P1)</span></span>                              |
   | <span data-ttu-id="4dca8-508">Exchange Online (план 1)</span><span class="sxs-lookup"><span data-stu-id="4dca8-508">Exchange Online (Plan 1)</span></span>                          |
   | <span data-ttu-id="4dca8-509">Exchange Online (план 2)</span><span class="sxs-lookup"><span data-stu-id="4dca8-509">Exchange Online (Plan 2)</span></span>                          |
   | <span data-ttu-id="4dca8-510">Архивация на базе Exchange Online для Exchange Online</span><span class="sxs-lookup"><span data-stu-id="4dca8-510">Exchange Online Archiving for Exchange Online</span></span>     |
   | <span data-ttu-id="4dca8-511">Архивация на базе Exchange Online для Exchange Server</span><span class="sxs-lookup"><span data-stu-id="4dca8-511">Exchange Online Archiving for Exchange Server</span></span>     |
   | <span data-ttu-id="4dca8-512">Надстройка неактивного пользователя Exchange Online</span><span class="sxs-lookup"><span data-stu-id="4dca8-512">Exchange Online Inactive User Add-on</span></span>              |
   | <span data-ttu-id="4dca8-513">Базовая подписка на Exchange Online</span><span class="sxs-lookup"><span data-stu-id="4dca8-513">Exchange Online Kiosk</span></span>                             |
   | <span data-ttu-id="4dca8-514">Exchange Online с поддержкой нескольких регионов</span><span class="sxs-lookup"><span data-stu-id="4dca8-514">Exchange Online Multi-Geo</span></span>                         |
   | <span data-ttu-id="4dca8-515">Exchange Online (план 1)</span><span class="sxs-lookup"><span data-stu-id="4dca8-515">Exchange Online Plan 1</span></span>                            |
   | <span data-ttu-id="4dca8-516">Exchange Online POP</span><span class="sxs-lookup"><span data-stu-id="4dca8-516">Exchange Online POP</span></span>                               |
   | <span data-ttu-id="4dca8-517">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="4dca8-517">Exchange Online Protection</span></span>                        |
   | <span data-ttu-id="4dca8-518">Информационные барьеры</span><span class="sxs-lookup"><span data-stu-id="4dca8-518">Information Barriers</span></span>                              |
   | <span data-ttu-id="4dca8-519">Защита данных для Office 365 — Premium</span><span class="sxs-lookup"><span data-stu-id="4dca8-519">Information Protection for Office 365 - Premium</span></span>   |
   | <span data-ttu-id="4dca8-520">Защита данных для Office 365 — Standard</span><span class="sxs-lookup"><span data-stu-id="4dca8-520">Information Protection for Office 365 - Standard</span></span>  |
   | <span data-ttu-id="4dca8-521">Аналитика myAnalytics</span><span class="sxs-lookup"><span data-stu-id="4dca8-521">Insights by MyAnalytics</span></span>                           |
   | <span data-ttu-id="4dca8-522">Расширенный аудит Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4dca8-522">Microsoft 365 Advanced Auditing</span></span>                   |
   | <span data-ttu-id="4dca8-523">Microsoft Bookings</span><span class="sxs-lookup"><span data-stu-id="4dca8-523">Microsoft Bookings</span></span>                                |
   | <span data-ttu-id="4dca8-524">Microsoft Business Center</span><span class="sxs-lookup"><span data-stu-id="4dca8-524">Microsoft Business Center</span></span>                         |
   | <span data-ttu-id="4dca8-525">Microsoft MyAnalytics (полнофункциональная версия)</span><span class="sxs-lookup"><span data-stu-id="4dca8-525">Microsoft MyAnalytics (Full)</span></span>                      |
   | <span data-ttu-id="4dca8-526">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="4dca8-526">Office 365 Advanced eDiscovery</span></span>                    |
   | <span data-ttu-id="4dca8-527">Microsoft Defender для Office 365 (план 1)</span><span class="sxs-lookup"><span data-stu-id="4dca8-527">Microsoft Defender for Office 365 (Plan 1)</span></span>    |
   | <span data-ttu-id="4dca8-528">Microsoft Defender для Office 365 (план 2)</span><span class="sxs-lookup"><span data-stu-id="4dca8-528">Microsoft Defender for Office 365 (Plan 2)</span></span>    |
   | <span data-ttu-id="4dca8-529">Office 365 Privileged Access Management</span><span class="sxs-lookup"><span data-stu-id="4dca8-529">Office 365 Privileged Access Management</span></span>           |
   | <span data-ttu-id="4dca8-530">Шифрование premium в Office 365</span><span class="sxs-lookup"><span data-stu-id="4dca8-530">Premium Encryption in Office 365</span></span>                  |
    
