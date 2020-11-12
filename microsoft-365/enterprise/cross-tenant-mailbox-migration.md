---
title: Миграция почтовых ящиков между клиентами
description: Сведения о том, как перемещать почтовые ящики между клиентами Microsoft 365 или Office 365.
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
ms.openlocfilehash: a2065ac324acd0a4d5980bceb97f9f6b8ad73058
ms.sourcegitcommit: f07442d077eb4357fa5d99d051b035705eb30efa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2020
ms.locfileid: "49002249"
---
# <a name="cross-tenant-mailbox-migration-preview"></a><span data-ttu-id="27eb3-103">Миграция почтовых ящиков между клиентами (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="27eb3-103">Cross-tenant mailbox migration (preview)</span></span>

<span data-ttu-id="27eb3-104">Ранее, когда клиенту Exchange Online требовалось переместить почтовые ящики на другой клиент в той же службе Exchange Online, им придется полностью переносе их в локальную систему, а затем подключить их к новому клиенту.</span><span class="sxs-lookup"><span data-stu-id="27eb3-104">Previously, when an Exchange Online tenant needed to move mailboxes to another tenant in the same Exchange Online service, they would have to completely offboard them to on-premises and then onboard them to a new tenant.</span></span> <span data-ttu-id="27eb3-105">С помощью новой функции переноса почтовых ящиков между клиентами Администраторы клиентов в исходном и целевом клиентах могут перемещать почтовые ящики между клиентами с минимальной зависимостью от инфраструктуры в локальных системах.</span><span class="sxs-lookup"><span data-stu-id="27eb3-105">With the new cross-tenant mailbox migration feature, tenant administrators in both source and target tenants can move mailboxes between the tenants with minimal infrastructure dependencies in their on-premises systems.</span></span> <span data-ttu-id="27eb3-106">Это избавляет от необходимости переносе и встроенные почтовые ящики.</span><span class="sxs-lookup"><span data-stu-id="27eb3-106">This removes the need to offboard and onboard mailboxes.</span></span>

<span data-ttu-id="27eb3-107">Как правило, при слиянии или дивеститурес необходимо иметь возможность перемещать пользователей и содержимое в новый клиент.</span><span class="sxs-lookup"><span data-stu-id="27eb3-107">Commonly, during mergers or divestitures, you need the ability to move users and content into a new tenant.</span></span> <span data-ttu-id="27eb3-108">Когда администратор целевого клиента выполняет перемещение, он называется перемещением по запросу, как в локальной среде для миграции в облако.</span><span class="sxs-lookup"><span data-stu-id="27eb3-108">When the target tenant administrator executes the move, it’s called a Pull move, similar to on-premises to cloud onboarding migrations.</span></span>

<span data-ttu-id="27eb3-109">Передвижения почтовых ящиков Exchange с перекрестными клиентами полностью обслуживаются администраторами клиентов, используя общедоступные интерфейсы, которые могут быть написаны в сценариях с большим количеством рабочих процессов, необходимых для переноса пользователей в новую организацию.</span><span class="sxs-lookup"><span data-stu-id="27eb3-109">Cross-tenant Exchange mailbox moves are fully self-serviced by tenant administrators, using well known interfaces that can be scripted into the larger workflows needed to transition users to their new organization.</span></span> <span data-ttu-id="27eb3-110">Администраторы могут использовать `New-MigrationBatch` командлеты, доступные через роль управления перемещением почтовых ящиков, для выполнения перемещения между клиентами.</span><span class="sxs-lookup"><span data-stu-id="27eb3-110">Administrators can use the `New-MigrationBatch` cmdlet, available through the Move Mailboxes management role, to execute cross-tenant moves.</span></span> <span data-ttu-id="27eb3-111">Процесс перемещения включает проверки авторизации клиента во время синхронизации и завершения работы почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="27eb3-111">The move process includes tenant authorization checks during mailbox synchronization and finalization.</span></span> 
 
<span data-ttu-id="27eb3-112">Миграция пользователей должна присутствовать в целевой системе Exchange Online Server в виде Маилусерс, помеченной с определенными атрибутами, чтобы включить перемещение между клиентами.</span><span class="sxs-lookup"><span data-stu-id="27eb3-112">Users migrating must be present in the target tenant Exchange Online system as MailUsers, marked with specific attributes to enable the cross-tenant moves.</span></span> <span data-ttu-id="27eb3-113">Система не будет перемещаться для пользователей, которые не были настроены должным образом в целевом клиенте.</span><span class="sxs-lookup"><span data-stu-id="27eb3-113">The system will fail moves for users that are not properly set up in the target tenant.</span></span> 

<span data-ttu-id="27eb3-114">По завершении перемещений почтовый ящик исходной системы преобразуется в MailUser, а объект targetAddress (показанный как ExternalEmailAddress в Exchange) помечаются адресом маршрутизации в целевом клиенте.</span><span class="sxs-lookup"><span data-stu-id="27eb3-114">When the moves are complete, the source system mailbox is converted to MailUser and the targetAddress (shown as ExternalEmailAddress in Exchange) is stamped with the routing address to the destination tenant.</span></span> <span data-ttu-id="27eb3-115">Этот процесс оставляет устаревший MailUser в исходном клиенте и разрешает период совместной работы и маршрутизации почты.</span><span class="sxs-lookup"><span data-stu-id="27eb3-115">This process leaves the legacy MailUser in the source tenant, and allows for a period of co-existence and mail routing.</span></span> <span data-ttu-id="27eb3-116">Когда бизнес-процессы разрешаются, клиент источника может удалить исходный MailUser или преобразовать их в почтовый контакт.</span><span class="sxs-lookup"><span data-stu-id="27eb3-116">When business processes allow, the source tenant may remove the source MailUser or convert them to a mail contact.</span></span> 

<span data-ttu-id="27eb3-117">Миграция почтовых ящиков Exchange между клиентами поддерживается только для клиентов в гибридной среде или в облаке, а также в любом сочетании этих двух способов.</span><span class="sxs-lookup"><span data-stu-id="27eb3-117">Cross-tenant Exchange mailbox migrations are supported for tenants in hybrid or cloud only, or any combination of the two.</span></span>

<span data-ttu-id="27eb3-118">В этой статье описывается процесс перемещения почтовых ящиков между клиентами и приводятся инструкции по подготовке исходных и целевых клиентов к перемещению контента.</span><span class="sxs-lookup"><span data-stu-id="27eb3-118">This article describes the process for cross-tenant mailbox moves and provides guidance on how to prepare source and target tenants for the content move.</span></span> 

## <a name="preparing-source-and-target-tenants"></a><span data-ttu-id="27eb3-119">Подготовка исходных и целевых клиентов</span><span class="sxs-lookup"><span data-stu-id="27eb3-119">Preparing source and target tenants</span></span>

<span data-ttu-id="27eb3-120">Для функции переноса почтовых ящиков Exchange между клиентами требуется авторизация и область видимости для межклиентской миграции.</span><span class="sxs-lookup"><span data-stu-id="27eb3-120">The Cross-tenant Exchange mailbox migration feature requires authorization and scoping for cross-tenant migrations.</span></span> <span data-ttu-id="27eb3-121">С помощью решений Azure Enterprise и хранилища ключей Администраторы клиентов теперь могут управлять отправкой и областью миграции почтовых ящиков Exchange Online от одного клиента к другому.</span><span class="sxs-lookup"><span data-stu-id="27eb3-121">Using the Azure Enterprise application and Key Vault storage solutions, tenant admins are now empowered to manage both authorization and scoping of Exchange Online mailbox migrations from one tenant to another.</span></span> <span data-ttu-id="27eb3-122">При перемещении почтовых ящиков между клиентами поддерживается модель приглашения и согласия, чтобы создать приложение Azure Active Directory (Azure AD), используемое для проверки подлинности между клиентом.</span><span class="sxs-lookup"><span data-stu-id="27eb3-122">Cross-tenant mailbox moves supports an invitation and consent model to establish an Azure Active Directory (Azure AD) application used for authentication between a tenant pair.</span></span> <span data-ttu-id="27eb3-123">Также требуются дополнительные компоненты, такие как связь организации и конечная точка миграции.</span><span class="sxs-lookup"><span data-stu-id="27eb3-123">Additional components such as an organization relationship and a migration endpoint are also required.</span></span>

<span data-ttu-id="27eb3-124">В этом разделе не приведены действия, необходимые для подготовки объектов пользователя MailUser в целевом каталоге, а также пример команды для подтверждения пакета миграции.</span><span class="sxs-lookup"><span data-stu-id="27eb3-124">This section does not include the specific steps required to prepare the MailUser user objects in the target directory, nor does it include the sample command to submit a migration batch.</span></span> <span data-ttu-id="27eb3-125">Сведения о том, как [подготовить объекты конечного пользователя к миграции](#prepare-target-user-objects-for-migration) , можно найти в этой статье.</span><span class="sxs-lookup"><span data-stu-id="27eb3-125">Please see [Prepare target user objects for migration](#prepare-target-user-objects-for-migration) for this information.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="27eb3-126">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="27eb3-126">Prerequisites</span></span>

<span data-ttu-id="27eb3-127">Для функции перемещения почтовых ящиков с несколькими клиентами требуется [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/basic-concepts) для создания приложения Azure с особым набором клиентов для безопасного хранения и доступа к сертификату или секрету, используемому для проверки подлинности и авторизации миграции почтовых ящиков от одного клиента к другому, удаляя любые требования для совместного использования сертификатов и секретов между клиентами.</span><span class="sxs-lookup"><span data-stu-id="27eb3-127">The cross-tenant mailbox move feature requires [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/basic-concepts) to establish a tenant pair-specific Azure application to securely store and access the certificate/secret used to authenticate and authorize mailbox migration from one tenant to the other, removing any requirements to share certificates/secrets between tenants.</span></span> 

<span data-ttu-id="27eb3-128">Прежде чем начать, убедитесь, что у вас есть необходимые разрешения для запуска скриптов развертывания, чтобы настроить Azure Key Vault, переместить приложение почтового ящика, конечную точку миграции EXO и связь организации EXO.</span><span class="sxs-lookup"><span data-stu-id="27eb3-128">Before starting, be sure you have the necessary permissions to run the deployment scripts in order to configure Azure Key Vault, Move Mailbox application, EXO Migration Endpoint, and the EXO Organization Relationship.</span></span> <span data-ttu-id="27eb3-129">Как правило, глобальный администратор имеет разрешение на выполнение всех действий по настройке.</span><span class="sxs-lookup"><span data-stu-id="27eb3-129">Typically, Global Admin has permission to perform all configuration steps.</span></span>

<span data-ttu-id="27eb3-130">Кроме того, перед запуском программы установки необходимы группы безопасности с включенной поддержкой почты в исходном клиенте.</span><span class="sxs-lookup"><span data-stu-id="27eb3-130">Additionally, mail-enabled security groups in the source tenant are required prior to running setup.</span></span> <span data-ttu-id="27eb3-131">Эти группы используются для определения списка почтовых ящиков, которые могут перемещаться от источника к конечному клиенту (или иногда называются в качестве ресурса).</span><span class="sxs-lookup"><span data-stu-id="27eb3-131">These groups are used to scope the list of mailboxes that can move from source (or sometimes referred to as resource) tenant to the target tenant.</span></span> <span data-ttu-id="27eb3-132">Это позволяет администратору клиента системы ограничить или ограничить область применения определенного набора почтовых ящиков, которые необходимо переместить, предотвращая миграцию нежелательных пользователей.</span><span class="sxs-lookup"><span data-stu-id="27eb3-132">This allows the source tenant admin to restrict or scope the specific set of mailboxes that need to be moved, preventing unintended users from being migrated.</span></span> <span data-ttu-id="27eb3-133">Вложенные группы не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="27eb3-133">Nested groups are not supported.</span></span>

<span data-ttu-id="27eb3-134">Кроме того, вам потребуется общаться с доверенной компанией-партнером (с помощью которой будут перемещаться почтовые ящики), чтобы получить идентификатор клиента Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="27eb3-134">You will also need to communicate with your trusted partner company (with whom you will be moving mailboxes) to obtain their Microsoft 365 tenant ID.</span></span> <span data-ttu-id="27eb3-135">Этот идентификатор клиента используется в поле "связь организации" `DomainName` .</span><span class="sxs-lookup"><span data-stu-id="27eb3-135">This tenant ID is used in the Organization Relationship `DomainName` field.</span></span>

<span data-ttu-id="27eb3-136">Чтобы получить идентификатор клиента для подписки, войдите в центр администрирования Microsoft 365 и перейдите по адресу [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) .</span><span class="sxs-lookup"><span data-stu-id="27eb3-136">To obtain the tenant ID of a subscription, sign-in to the Microsoft 365 admin center and go to [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> <span data-ttu-id="27eb3-137">Щелкните значок "Копировать" для свойства "идентификатор клиента", чтобы скопировать его в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="27eb3-137">Click the copy icon for the Tenant ID property to copy it to the clipboard.</span></span>

<span data-ttu-id="27eb3-138">Ниже показано, как работает процесс.</span><span class="sxs-lookup"><span data-stu-id="27eb3-138">Here is how the process works.</span></span>

:::image type="content" source="../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png" alt-text="Подготовка клиента к миграции почтовых ящиков.":::

<!--
[![Tenant preparation for mailbox migration](../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)

[See a larger version of this image](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png).
--> 

### <a name="prepare-tenants"></a><span data-ttu-id="27eb3-140">Подготовка клиентов</span><span class="sxs-lookup"><span data-stu-id="27eb3-140">Prepare tenants</span></span>

<span data-ttu-id="27eb3-141">На высоком уровне при выполнении сценариев установки выполняются следующие действия по настройке.</span><span class="sxs-lookup"><span data-stu-id="27eb3-141">At a high level, the following configuration actions take place when executing the setup scripts.</span></span>

<span data-ttu-id="27eb3-142">Подготовка целевого клиента:</span><span class="sxs-lookup"><span data-stu-id="27eb3-142">Prepare the target tenant:</span></span>

1. <span data-ttu-id="27eb3-143">Если не указана существующая группа ресурсов Azure, создается новая (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="27eb3-143">If an existing Azure Resource Group is not provided, a new one is created (SCRIPT).</span></span>
2. <span data-ttu-id="27eb3-144">Если существующее ключевое хранилище не предоставлено, создается новый объект (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="27eb3-144">If an existing Key Vault is not provided, a new one is created (SCRIPT).</span></span>
3. <span data-ttu-id="27eb3-145">Для приложения переноса почтовых ящиков Office 365 Exchange Online создается новая политика доступа (сценарий).</span><span class="sxs-lookup"><span data-stu-id="27eb3-145">A new Access Policy is created for the Office 365 Exchange Online Mailbox Migration application (SCRIPT).</span></span>
4. <span data-ttu-id="27eb3-146">Создается новый сертификат (или, если он указан) для хранения секрета для приложения переноса (сценария).</span><span class="sxs-lookup"><span data-stu-id="27eb3-146">A new certificate is created (or existing one, if specified) to hold the secret to the Migration application (SCRIPT).</span></span>
5. <span data-ttu-id="27eb3-147">Создается новое приложение Azure AD (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="27eb3-147">A new Azure AD application is created (SCRIPT).</span></span>
6. <span data-ttu-id="27eb3-148">Сертификат/секрет отправляется в приложение миграции (скрипт).</span><span class="sxs-lookup"><span data-stu-id="27eb3-148">The certificate/secret is uploaded to the migration application (SCRIPT).</span></span>
7. <span data-ttu-id="27eb3-149">Разрешения на миграцию почтовых ящиков назначаются приложению (СЦЕНАРию).</span><span class="sxs-lookup"><span data-stu-id="27eb3-149">Mailbox migration permissions are assigned to the application (SCRIPT).</span></span>
8. <span data-ttu-id="27eb3-150">Скрипт развертывания приостанавливается до тех пор, пока целевой администратор не отправил в собственное приложение (сценарий).</span><span class="sxs-lookup"><span data-stu-id="27eb3-150">The deployment script pauses until target admin consents to their own application (SCRIPT).</span></span>
9. <span data-ttu-id="27eb3-151">Целевой администратор клиента отправляется на разрешения, предоставленные приложению (вручную).</span><span class="sxs-lookup"><span data-stu-id="27eb3-151">The target tenant admin consents to the permissions given to the application (MANUAL).</span></span>
10. <span data-ttu-id="27eb3-152">Связь организации создается для целевого клиента (сценария).</span><span class="sxs-lookup"><span data-stu-id="27eb3-152">An organization relationship is created to the target tenant (SCRIPT).</span></span>
11. <span data-ttu-id="27eb3-153">Создается конечная точка миграции для извлечения почтовых ящиков на целевой клиент (сценарий).</span><span class="sxs-lookup"><span data-stu-id="27eb3-153">A migration endpoint is created to pull mailboxes to the target tenant (SCRIPT).</span></span>

<span data-ttu-id="27eb3-154">Подготовка исходного клиента:</span><span class="sxs-lookup"><span data-stu-id="27eb3-154">Prepare the source tenant:</span></span>

1. <span data-ttu-id="27eb3-155">Администратор исходного клиента принимает согласие на приглашение приложения переноса почтовых ящиков от целевого клиента (вручную).</span><span class="sxs-lookup"><span data-stu-id="27eb3-155">The source tenant admin accepts consent to Mailbox Migration application invitation from the Target tenant (MANUAL).</span></span>
2. <span data-ttu-id="27eb3-156">Администратор исходного клиента создает группу безопасности с включенной поддержкой почты в своем клиенте, чтобы включить список почтовых ящиков, разрешенных для перемещения приложением миграции (вручную).</span><span class="sxs-lookup"><span data-stu-id="27eb3-156">The source tenant admin creates a mail-enabled security group in their tenant to contain the list of mailboxes allowed to be moved by the migration application (MANUAL).</span></span>
3. <span data-ttu-id="27eb3-157">В целевом клиенте создается связь организации, указывающая на необходимость использования приложения переноса почтовых ящиков для проверки OAuth, чтобы принять запрос на перемещение (сценарий).</span><span class="sxs-lookup"><span data-stu-id="27eb3-157">An organization relationship is created to the target tenant specifying the mailbox migration application should be used for OAuth verification to accept the move request (SCRIPT).</span></span>

#### <a name="step-by-step-instructions-for-the-target-tenant-admin"></a><span data-ttu-id="27eb3-158">Пошаговые инструкции для администратора целевого клиента</span><span class="sxs-lookup"><span data-stu-id="27eb3-158">Step-by-step instructions for the target tenant admin</span></span>

1. <span data-ttu-id="27eb3-159">Скачайте скрипт SetupCrossTenantRelationshipForTargetTenant.ps1 для установки целевого клиента из [репозитория GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span><span class="sxs-lookup"><span data-stu-id="27eb3-159">Download the SetupCrossTenantRelationshipForTargetTenant.ps1 script for the target tenant setup from the [GitHub repository](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span></span> 
2. <span data-ttu-id="27eb3-160">Сохраните сценарий (SetupCrossTenantRelationshipForTargetTenant.ps1) на компьютере, с которого будет выполняться сценарий.</span><span class="sxs-lookup"><span data-stu-id="27eb3-160">Save the script (SetupCrossTenantRelationshipForTargetTenant.ps1) to the computer from which you will be executing the script.</span></span>
3. <span data-ttu-id="27eb3-161">Создайте удаленное подключение PowerShell к конечному клиенту Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="27eb3-161">Create a Remote PowerShell connection to the Exchange Online target tenant.</span></span> <span data-ttu-id="27eb3-162">Опять же, убедитесь, что у вас есть необходимые разрешения для запуска скриптов развертывания, чтобы настроить хранилище и сертификат Azure Key Vault, переместить приложение почтового ящика, конечную точку миграции EXO и связь организации EXO.</span><span class="sxs-lookup"><span data-stu-id="27eb3-162">Again, make sure you have the necessary permissions to run the deployment scripts in order to configure the Azure Key Vault storage and certificate, Move Mailbox application, EXO Migration Endpoint, and the EXO Organization Relationship.</span></span>
4. <span data-ttu-id="27eb3-163">Измените каталог папки файлов на расположение скрипта или убедитесь, что сценарий в текущий момент сохранен в удаленном сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="27eb3-163">Change the file folder directory to the script location or verify the script is currently saved to the location currently in your Remote PowerShell session.</span></span>
5. <span data-ttu-id="27eb3-164">Выполните скрипт со следующими параметрами и значениями.</span><span class="sxs-lookup"><span data-stu-id="27eb3-164">Run the script with the following parameters and values.</span></span>

    | <span data-ttu-id="27eb3-165">Параметр</span><span class="sxs-lookup"><span data-stu-id="27eb3-165">Parameter</span></span> | <span data-ttu-id="27eb3-166">Значение</span><span class="sxs-lookup"><span data-stu-id="27eb3-166">Value</span></span> | <span data-ttu-id="27eb3-167">Обязательный или необязательный</span><span class="sxs-lookup"><span data-stu-id="27eb3-167">Required or Optional</span></span>
    |---------------------------------------------|-----------------|--------------|
    | <span data-ttu-id="27eb3-168">— Ресаурцетенантдомаин</span><span class="sxs-lookup"><span data-stu-id="27eb3-168">-ResourceTenantDomain</span></span>                       | <span data-ttu-id="27eb3-169">Исходный домен клиента, например fabrikam \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="27eb3-169">Source tenant domain, such as fabrikam\.onmicrosoft.com.</span></span> | <span data-ttu-id="27eb3-170">Обязательный</span><span class="sxs-lookup"><span data-stu-id="27eb3-170">Required</span></span> |
    | <span data-ttu-id="27eb3-171">— Ресаурцетенантадминемаил</span><span class="sxs-lookup"><span data-stu-id="27eb3-171">-ResourceTenantAdminEmail</span></span>                   | <span data-ttu-id="27eb3-172">Адрес электронной почты администратора исходного клиента.</span><span class="sxs-lookup"><span data-stu-id="27eb3-172">Source tenant admin’s email address.</span></span> <span data-ttu-id="27eb3-173">Это исходный администратор клиента, который будет отослано использовать приложение переноса почтовых ящиков, отправленное от целевого администратора. Это администратор, который будет получать приглашение на получение электронной почты для приложения.</span><span class="sxs-lookup"><span data-stu-id="27eb3-173">This is the source tenant admin who will be consenting to the use of the mailbox migration application sent from the target admin. This is the admin who will receive the email invite for the application.</span></span> | <span data-ttu-id="27eb3-174">Обязательный</span><span class="sxs-lookup"><span data-stu-id="27eb3-174">Required</span></span> |
    | <span data-ttu-id="27eb3-175">— Таржеттенантдомаин</span><span class="sxs-lookup"><span data-stu-id="27eb3-175">-TargetTenantDomain</span></span>                         | <span data-ttu-id="27eb3-176">Целевой домен клиента, например contoso \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="27eb3-176">Target tenant domain, such as contoso\.onmicrosoft.com.</span></span> | <span data-ttu-id="27eb3-177">Обязательный</span><span class="sxs-lookup"><span data-stu-id="27eb3-177">Required</span></span> |
    | <span data-ttu-id="27eb3-178">— Ресаурцетенантид</span><span class="sxs-lookup"><span data-stu-id="27eb3-178">-ResourceTenantId</span></span>                           | <span data-ttu-id="27eb3-179">Идентификатор исходной организации клиента (GUID).</span><span class="sxs-lookup"><span data-stu-id="27eb3-179">Source tenant organization ID (GUID).</span></span> | <span data-ttu-id="27eb3-180">Обязательный</span><span class="sxs-lookup"><span data-stu-id="27eb3-180">Required</span></span> |
    | <span data-ttu-id="27eb3-181">— SubscriptionId</span><span class="sxs-lookup"><span data-stu-id="27eb3-181">-SubscriptionId</span></span>                             | <span data-ttu-id="27eb3-182">Подписка на Azure, используемая для создания ресурсов.</span><span class="sxs-lookup"><span data-stu-id="27eb3-182">The Azure subscription to use for creating resources.</span></span> | <span data-ttu-id="27eb3-183">Обязательный</span><span class="sxs-lookup"><span data-stu-id="27eb3-183">Required</span></span> |
    | <span data-ttu-id="27eb3-184">— ResourceGroup</span><span class="sxs-lookup"><span data-stu-id="27eb3-184">-ResourceGroup</span></span>                              | <span data-ttu-id="27eb3-185">Имя группы ресурсов Azure, которое содержит или будет содержать Key Vault.</span><span class="sxs-lookup"><span data-stu-id="27eb3-185">Azure resource group name that contains or will contain the Key Vault.</span></span> | <span data-ttu-id="27eb3-186">Обязательный</span><span class="sxs-lookup"><span data-stu-id="27eb3-186">Required</span></span> |
    | <span data-ttu-id="27eb3-187">— Кэйваултнаме</span><span class="sxs-lookup"><span data-stu-id="27eb3-187">-KeyVaultName</span></span>                               | <span data-ttu-id="27eb3-188">Экземпляр Azure Key Vault, который будет хранить сертификат и секрет приложения переноса почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="27eb3-188">Azure Key Vault instance that will store your mailbox migration application certificate/secret.</span></span> | <span data-ttu-id="27eb3-189">Обязательный</span><span class="sxs-lookup"><span data-stu-id="27eb3-189">Required</span></span> |
    | <span data-ttu-id="27eb3-190">— CertificateName</span><span class="sxs-lookup"><span data-stu-id="27eb3-190">-CertificateName</span></span>                            | <span data-ttu-id="27eb3-191">Имя сертификата при создании или поиске сертификата в ключе Vault.</span><span class="sxs-lookup"><span data-stu-id="27eb3-191">Certificate name when generating or searching for certificate in key vault.</span></span> | <span data-ttu-id="27eb3-192">Обязательный</span><span class="sxs-lookup"><span data-stu-id="27eb3-192">Required</span></span> |
    | <span data-ttu-id="27eb3-193">— CertificateSubject</span><span class="sxs-lookup"><span data-stu-id="27eb3-193">-CertificateSubject</span></span>                         | <span data-ttu-id="27eb3-194">Имя субъекта сертификата Azure Key Vault, например CN = contoso_fabrikam.</span><span class="sxs-lookup"><span data-stu-id="27eb3-194">Azure Key Vault certificate subject name, such as CN=contoso_fabrikam.</span></span> | <span data-ttu-id="27eb3-195">Обязательный</span><span class="sxs-lookup"><span data-stu-id="27eb3-195">Required</span></span> |
    | <span data-ttu-id="27eb3-196">— Ексистингаппликатионид</span><span class="sxs-lookup"><span data-stu-id="27eb3-196">-ExistingApplicationId</span></span>                      | <span data-ttu-id="27eb3-197">Приложение переноса почты, которое будет использоваться, если оно уже было создано.</span><span class="sxs-lookup"><span data-stu-id="27eb3-197">Mail migration application to use if one was already created.</span></span> | <span data-ttu-id="27eb3-198">Необязательный</span><span class="sxs-lookup"><span data-stu-id="27eb3-198">Optional</span></span> |
    | <span data-ttu-id="27eb3-199">— Азуреапппермиссионс</span><span class="sxs-lookup"><span data-stu-id="27eb3-199">-AzureAppPermissions</span></span>                        | <span data-ttu-id="27eb3-200">Разрешения, которые необходимо предоставить для приложения переноса почтовых ящиков, например Exchange или MSGraph (Exchange для перемещения почтовых ящиков, MSGraph, чтобы использовать это приложение для отправки приглашения на согласие для клиента ресурсов).</span><span class="sxs-lookup"><span data-stu-id="27eb3-200">The permissions required to be given to the mailbox migration application, such as Exchange or MSGraph (Exchange for moving mailboxes, MSGraph for using this application to send a consent link invitation to resource tenant).</span></span> | <span data-ttu-id="27eb3-201">Обязательный</span><span class="sxs-lookup"><span data-stu-id="27eb3-201">Required</span></span> |
    | <span data-ttu-id="27eb3-202">— Усеаппандцертженератедфорсендингинвитатион</span><span class="sxs-lookup"><span data-stu-id="27eb3-202">-UseAppAndCertGeneratedForSendingInvitation</span></span> | <span data-ttu-id="27eb3-203">Параметр для использования приложения, созданного для миграции, для отправки приглашения на предоставление разрешения на отправку приглашения для ссылки на администратора исходного клиента. Если этот параметр отсутствует, будет предложено ввести учетные данные конечного администратора для подключения к диспетчеру приглашений Azure и отправить приглашение в качестве целевого администратора.</span><span class="sxs-lookup"><span data-stu-id="27eb3-203">Parameter for using the application created for migration to be used for sending consent link invitation to source tenant admin. If not present this will prompt for the target admin’s credentials to connect to Azure invitation manager and send the invitation as target admin.</span></span> | <span data-ttu-id="27eb3-204">Необязательный</span><span class="sxs-lookup"><span data-stu-id="27eb3-204">Optional</span></span> |
    | <span data-ttu-id="27eb3-205">— Кэйваултаудитсторажеаккаунтнаме</span><span class="sxs-lookup"><span data-stu-id="27eb3-205">-KeyVaultAuditStorageAccountName</span></span>            | <span data-ttu-id="27eb3-206">Учетная запись хранения, в которой будут храниться журналы аудита для основного хранилища.</span><span class="sxs-lookup"><span data-stu-id="27eb3-206">The storage account where Key Vault’s audit logs would be stored.</span></span> | <span data-ttu-id="27eb3-207">Необязательный</span><span class="sxs-lookup"><span data-stu-id="27eb3-207">Optional</span></span> |
    | <span data-ttu-id="27eb3-208">— Кэйваултаудитсторажересаурцеграуп</span><span class="sxs-lookup"><span data-stu-id="27eb3-208">-KeyVaultAuditStorageResourceGroup</span></span>          | <span data-ttu-id="27eb3-209">Группа ресурсов, содержащая учетную запись хранения для хранения журналов аудита ключевых хранилищ.</span><span class="sxs-lookup"><span data-stu-id="27eb3-209">The resource group that contains the storage account for storing Key Vault audit logs.</span></span> | <span data-ttu-id="27eb3-210">Необязательный</span><span class="sxs-lookup"><span data-stu-id="27eb3-210">Optional</span></span> |
    ||||

6. <span data-ttu-id="27eb3-211">Сценарий приостанавливает или предложит принять или подтвердить согласие на приложение миграции почтовых ящиков Exchange, созданное в ходе этого процесса.</span><span class="sxs-lookup"><span data-stu-id="27eb3-211">The script will pause and ask you to accept or consent to the Exchange mailbox migration application that was created during this process.</span></span> <span data-ttu-id="27eb3-212">Пример:</span><span class="sxs-lookup"><span data-stu-id="27eb3-212">Here is an example.</span></span>

    ```powershell
    PS C:\Users\Admin\scripts\T2TMovesV2> .\SetupCrossTenantRelationshipForTargetTenant.ps1 -ResourceTenantDomain contoso.onmicrosoft.com -ResourceTenantAdminEmail admin@contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ResourceTenantId ksagjid39-ede2-4d2c-98ae-874709325b00 -SubscriptionId e4ssd05d-a327-49ss-849a-sd0932439023 -ResourceGroup "Cross-TenantMoves" -KeyVaultName "Cross-TenantMovesVault" -CertificateName "Contoso-Fabrikam-cert" -CertificateSubject "CN=Contoso_Fabrikam" -AzureAppPermissions Exchange, MSGraph -UseAppAndCertGeneratedForSendingInvitation -KeyVaultAuditStorageAccountName "t2tstorageaccount" -KeyVaultAuditStorageResourceGroup "Demo"

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

7. <span data-ttu-id="27eb3-213">URL-адрес будет отображаться в удаленном сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="27eb3-213">A URL will be displayed in the Remote PowerShell session.</span></span> <span data-ttu-id="27eb3-214">Скопируйте ссылку, предоставленную для вашего согласия клиента, и вставьте ее в веб-браузер.</span><span class="sxs-lookup"><span data-stu-id="27eb3-214">Copy the link provided for your tenant consent and paste it into a Web browser.</span></span>

8. <span data-ttu-id="27eb3-215">Войдите с помощью учетных данных глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="27eb3-215">Sign in with your Global Admin credentials.</span></span> <span data-ttu-id="27eb3-216">Когда появится следующий экран, нажмите кнопку **принять**.</span><span class="sxs-lookup"><span data-stu-id="27eb3-216">When the following screen is presented, select **Accept**.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-dialog.png" alt-text="Диалоговое окно _OL_QUOTE_PLACEHOLDER_принятие разрешений_OL_QUOTE_PLACEHOLDER_":::
    
9. <span data-ttu-id="27eb3-218">Вернитесь к удаленному сеансу PowerShell и нажмите клавишу ВВОД, чтобы продолжить.</span><span class="sxs-lookup"><span data-stu-id="27eb3-218">Switch back to the Remote PowerShell session and hit Enter to proceed.</span></span>

10. <span data-ttu-id="27eb3-219">В сценарии будут настроены оставшиеся объекты программы установки.</span><span class="sxs-lookup"><span data-stu-id="27eb3-219">The script will configure the remaining setup objects.</span></span> <span data-ttu-id="27eb3-220">Пример:</span><span class="sxs-lookup"><span data-stu-id="27eb3-220">Here is an example.</span></span>

    ```powershell
    Successfully sent invitation to admin@contoso.onmicrosoft.com
    Setting up exchange components on target tenant: fabrikam.onmicrosoft.com
    MigrationEndpoint created in fabrikam.onmicrosoft.com for target contoso.onmicrosoft.com
    Exchange setup complete. Migration endpoint details are available in $MigrationEndpoint variable
    ```

<span data-ttu-id="27eb3-221">Настройка целевого администратора теперь завершена.</span><span class="sxs-lookup"><span data-stu-id="27eb3-221">The target admin setup is now complete!</span></span>

#### <a name="step-by-step-instructions-for-the-source-tenant-admin"></a><span data-ttu-id="27eb3-222">Пошаговые инструкции для администратора исходного клиента</span><span class="sxs-lookup"><span data-stu-id="27eb3-222">Step-by-step instructions for the source tenant admin</span></span>

1.  <span data-ttu-id="27eb3-223">Войдите в свой почтовый ящик как параметр – Ресаурцетенантадминемаил, заданный целевым администратором во время установки.</span><span class="sxs-lookup"><span data-stu-id="27eb3-223">Sign in to your mailbox as the -ResourceTenantAdminEmail specified by the target admin during their setup.</span></span> <span data-ttu-id="27eb3-224">Найдите приглашение от целевого клиента и нажмите кнопку **Get Start** (начало работы).</span><span class="sxs-lookup"><span data-stu-id="27eb3-224">Find the email invitation from the target tenant, and then select the **Get Started** button.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/invited-by-target-tenant.png" alt-text="Диалоговое окно с приглашением":::

2. <span data-ttu-id="27eb3-226">Нажмите кнопку **принять** , чтобы принять приглашение.</span><span class="sxs-lookup"><span data-stu-id="27eb3-226">Select **Accept** to accept the invitation.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-accept.png" alt-text="Диалоговое окно для принятия разрешений":::

   > [!NOTE]
   > <span data-ttu-id="27eb3-228">Если вы не получаете это сообщение электронной почты или не можете найти его, администратору целевого клиента предоставляется прямой URL-адрес, который можно предоставить для принятия приглашения.</span><span class="sxs-lookup"><span data-stu-id="27eb3-228">If you do not get this email or cannot find it, the target tenant admin was provided a direct URL that can be given to you to accept the invitation.</span></span> <span data-ttu-id="27eb3-229">URL-адрес должен находиться в разделе в записи удаленного сеанса PowerShell администратора целевого клиента.</span><span class="sxs-lookup"><span data-stu-id="27eb3-229">The URL should in the in the transcript of the target tenant admin's Remote PowerShell session.</span></span>

3. <span data-ttu-id="27eb3-230">В центре администрирования Microsoft 365 или удаленном сеансе PowerShell создайте одну или несколько групп безопасности с включенной поддержкой почты, чтобы управлять списком почтовых ящиков, разрешенных целевым клиентом для получения (перемещения) из исходного клиента в Целевой клиент.</span><span class="sxs-lookup"><span data-stu-id="27eb3-230">In either the Microsoft 365 admin center or a Remote PowerShell session, create one or more mail-enabled security groups to control the list of mailboxes allowed by the target tenant to pull (move) from the source tenant to the target tenant.</span></span> <span data-ttu-id="27eb3-231">Вам не нужно заполнять эту группу заранее, но для запуска процедуры установки (скрипт) необходимо предоставить хотя бы одну группу.</span><span class="sxs-lookup"><span data-stu-id="27eb3-231">You do not need to populate this group in advance, but at least one group must be provided to run the setup steps (script).</span></span> <span data-ttu-id="27eb3-232">Группы вложений не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="27eb3-232">Nest groups are not supported.</span></span> 

4. <span data-ttu-id="27eb3-233">Скачайте скрипт SetupCrossTenantRelationshipForTargetResource.ps1 для установки исходного клиента из репозитория GitHub [здесь](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span><span class="sxs-lookup"><span data-stu-id="27eb3-233">Download the SetupCrossTenantRelationshipForTargetResource.ps1 script for the source tenant setup from the GitHub repository [here](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span></span> 

5. <span data-ttu-id="27eb3-234">Создайте удаленное подключение PowerShell к исходному клиенту с разрешениями администратора Exchange.</span><span class="sxs-lookup"><span data-stu-id="27eb3-234">Create a Remote PowerShell connection to the source tenant with your Exchange Administrator permissions.</span></span> <span data-ttu-id="27eb3-235">Разрешения глобального администратора не являются обязательными для настройки исходного клиента, только целевой клиент из-за процесса создания приложения Azure.</span><span class="sxs-lookup"><span data-stu-id="27eb3-235">Global Admin permissions are not required to configure the source tenant, only the target tenant because of the Azure application creation process.</span></span>

6. <span data-ttu-id="27eb3-236">Измените каталог на расположение скрипта или убедитесь, что сценарий в текущий момент сохранен в удаленном сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="27eb3-236">Change directory to the script location or verify that the script is currently saved to the location currently in your Remote PowerShell session.</span></span>

7. <span data-ttu-id="27eb3-237">Выполните скрипт со следующими обязательными параметрами и значениями.</span><span class="sxs-lookup"><span data-stu-id="27eb3-237">Run the script with the following required parameters and values.</span></span>

    | <span data-ttu-id="27eb3-238">Параметр</span><span class="sxs-lookup"><span data-stu-id="27eb3-238">Parameter</span></span> | <span data-ttu-id="27eb3-239">Значение</span><span class="sxs-lookup"><span data-stu-id="27eb3-239">Value</span></span> |
    |-----|------|
    | <span data-ttu-id="27eb3-240">— Саурцемаилбоксмовепублишедскопес</span><span class="sxs-lookup"><span data-stu-id="27eb3-240">-SourceMailboxMovePublishedScopes</span></span> | <span data-ttu-id="27eb3-241">Группа безопасности с включенной поддержкой почты, созданная исходным клиентом для удостоверений и почтовых ящиков, которые находятся в области для миграции.</span><span class="sxs-lookup"><span data-stu-id="27eb3-241">Mail-enabled security group created by source tenant for the identities/mailboxes that are in scope for migration.</span></span> |
    | <span data-ttu-id="27eb3-242">— Ресаурцетенантдомаин</span><span class="sxs-lookup"><span data-stu-id="27eb3-242">-ResourceTenantDomain</span></span> | <span data-ttu-id="27eb3-243">Имя домена исходного клиента, например fabrikam \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="27eb3-243">Source tenant domain name, such as fabrikam\.onmicrosoft.com.</span></span> |
    | <span data-ttu-id="27eb3-244">— Таржеттенантдомаин</span><span class="sxs-lookup"><span data-stu-id="27eb3-244">-TargetTenantDomain</span></span> | <span data-ttu-id="27eb3-245">Имя конечного домена клиента, например contoso \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="27eb3-245">Target tenant domain name, such as contoso\.onmicrosoft.com.</span></span> |
    | <span data-ttu-id="27eb3-246">— ApplicationId</span><span class="sxs-lookup"><span data-stu-id="27eb3-246">-ApplicationId</span></span> | <span data-ttu-id="27eb3-247">Идентификатор приложения Azure (GUID) приложения, используемого для миграции.</span><span class="sxs-lookup"><span data-stu-id="27eb3-247">Azure application ID (GUID) of the application used for migration.</span></span> <span data-ttu-id="27eb3-248">Идентификатор приложения доступен на портале Azure (Azure AD, корпоративные приложения, имя приложения, идентификатор приложения) или включено в приглашение.</span><span class="sxs-lookup"><span data-stu-id="27eb3-248">Application ID available via your Azure portal (Azure AD, Enterprise Applications, app name, application ID) or included in your invitation email.</span></span>  |
    | <span data-ttu-id="27eb3-249">— Таржеттенантид</span><span class="sxs-lookup"><span data-stu-id="27eb3-249">-TargetTenantId</span></span> | <span data-ttu-id="27eb3-250">Идентификатор клиента целевого клиента.</span><span class="sxs-lookup"><span data-stu-id="27eb3-250">Tenant ID of the target tenant.</span></span> <span data-ttu-id="27eb3-251">Например, идентификатор клиента Azure AD для \. клиента contoso onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="27eb3-251">For example, the Azure AD tenant ID of contoso\.onmicrosoft.com tenant.</span></span> |
    |||
    
    <span data-ttu-id="27eb3-252">Пример:</span><span class="sxs-lookup"><span data-stu-id="27eb3-252">Here is an example.</span></span>
    ```powershell
    SetupCrossTenantRelationshipForResourceTenant.ps1 -SourceMailboxMovePublishedScopes "MigScope","MyGroup" -ResourceTenantDomain contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ApplicationId sdf5e87sa-0753-dd88-ad35-c71a15cs8e44c -TargetTenantId 4sdkfo933-3904-sd93-bf9a-sdi39402834
    Exchange setup complete.

    ```

<span data-ttu-id="27eb3-253">Настройка администратора источника теперь завершена.</span><span class="sxs-lookup"><span data-stu-id="27eb3-253">The source admin setup is now complete!</span></span>

### <a name="verify-setup"></a><span data-ttu-id="27eb3-254">Проверка программы установки</span><span class="sxs-lookup"><span data-stu-id="27eb3-254">Verify setup</span></span>

<span data-ttu-id="27eb3-255">Убедитесь, что связи Организации в исходном и целевом клиентах и конечных точках миграции в целевом объекте успешно созданы.</span><span class="sxs-lookup"><span data-stu-id="27eb3-255">Verify that the organization relationships in both source and target tenants and migration endpoint in the target were created successfully.</span></span>

#### <a name="target-tenant"></a><span data-ttu-id="27eb3-256">Целевой клиент</span><span class="sxs-lookup"><span data-stu-id="27eb3-256">Target tenant</span></span>

<span data-ttu-id="27eb3-257">**Организационная связь**</span><span class="sxs-lookup"><span data-stu-id="27eb3-257">**Organization relationship**</span></span>

<span data-ttu-id="27eb3-258">Убедитесь, что объект связи Организации был создан и настроен с помощью этой команды.</span><span class="sxs-lookup"><span data-stu-id="27eb3-258">Verify that the organization relationship object was created and configured with this command.</span></span>

```powershell
Get-OrganizationRelationship <source tenant organization name> | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability
```
<span data-ttu-id="27eb3-259">Вот пример:</span><span class="sxs-lookup"><span data-stu-id="27eb3-259">Here is an example:</span></span>

```powershell
PS C:\Users\Admin\scripts\T2TMovesV2> Get-OrganizationRelationship fabrikam_contoso_1178 | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability

Name                  : fabrikam_contoso_1123
DomainNames           : {sd0933me9f-9304-s903-s093-s093mfi903m4}
MailboxMoveEnabled    : True
MailboxMoveCapability : Inbound

```

<span data-ttu-id="27eb3-260">**Конечная точка миграции**</span><span class="sxs-lookup"><span data-stu-id="27eb3-260">**Migration endpoint**</span></span>

<span data-ttu-id="27eb3-261">Убедитесь, что объект конечной точки миграции был создан и настроен с помощью этой команды.</span><span class="sxs-lookup"><span data-stu-id="27eb3-261">Verify that the migration endpoint object was created and configured with this command.</span></span>

```powershell
Get-MigrationEndpoint "<fabrikam_contoso_1123> | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl
```

<span data-ttu-id="27eb3-262">Пример:</span><span class="sxs-lookup"><span data-stu-id="27eb3-262">Here is an example.</span></span>

```powershell
PS C:\Users\Admin\scripts\T2TMovesV2> Get-MigrationEndpoint fabrikam_contoso_1123 | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl


Identity             : fabrikam_contoso_1123
RemoteTenant         : contoso.onmicrosoft.com
ApplicationId        : s93mf93-das9-dq24-dq234-dada9033904m
AppSecretKeyVaultUrl : https://cross-tenantmyvaultformoves.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ae79348mx94384c288c5a3dfsioepw308

```

#### <a name="source-tenant"></a><span data-ttu-id="27eb3-263">Клиент источника</span><span class="sxs-lookup"><span data-stu-id="27eb3-263">Source tenant</span></span>

<span data-ttu-id="27eb3-264">**Организационная связь**</span><span class="sxs-lookup"><span data-stu-id="27eb3-264">**Organization relationship**</span></span>

<span data-ttu-id="27eb3-265">Убедитесь, что объект связи Организации был создан и настроен с помощью этой команды.</span><span class="sxs-lookup"><span data-stu-id="27eb3-265">Verify that the organization relationship object was created and configured with this command.</span></span>

```powershell
Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId
```
<span data-ttu-id="27eb3-266">Пример:</span><span class="sxs-lookup"><span data-stu-id="27eb3-266">Here is an example.</span></span>

```powershell
PS C:\Users\Admin\scripts\T2TMovesV2> Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId


Name                       : fabrikam_contoso_001
MailboxMoveEnabled         : True
MailboxMoveCapability      : RemoteOutbound
MailboxMovePublishedScopes : {MigScope}
OAuthApplicationId         : sd9890342-3243-3242-fe3w2-fsdade93m0
```

### <a name="move-mailboxes-back-to-the-original-source"></a><span data-ttu-id="27eb3-267">Перемещение почтовых ящиков обратно в исходный источник</span><span class="sxs-lookup"><span data-stu-id="27eb3-267">Move mailboxes back to the original source</span></span>

<span data-ttu-id="27eb3-268">Если почтовые ящики перемещаются обратно в исходный клиент, необходимо выполнить один и тот же набор действий и сценариев в новом исходном и новом целевом клиенте.</span><span class="sxs-lookup"><span data-stu-id="27eb3-268">If a mailbox move back to the original source tenant is required, the same set of steps and scripts will need to be run in both new source and new target tenants.</span></span> <span data-ttu-id="27eb3-269">Существующий объект связи Организации будет обновлен или добавлен, а не создан повторно.</span><span class="sxs-lookup"><span data-stu-id="27eb3-269">The existing Organization Relationship object will be updated or appended, not recreated.</span></span>

## <a name="prepare-target-user-objects-for-migration"></a><span data-ttu-id="27eb3-270">Подготовка объектов целевого пользователя к миграции</span><span class="sxs-lookup"><span data-stu-id="27eb3-270">Prepare target user objects for migration</span></span>

<span data-ttu-id="27eb3-271">Миграция пользователей должна присутствовать в целевом клиенте и в системе Exchange Online (как Маилусерс), помеченные определенными атрибутами, чтобы включить перемещение между клиентами.</span><span class="sxs-lookup"><span data-stu-id="27eb3-271">Users migrating must be present in the target tenant and Exchange Online system (as MailUsers) marked with specific attributes to enable the cross-tenant moves.</span></span> <span data-ttu-id="27eb3-272">Система не будет перемещаться для пользователей, которые не были настроены должным образом в целевом клиенте.</span><span class="sxs-lookup"><span data-stu-id="27eb3-272">The system will fail moves for users that are not properly set up in the target tenant.</span></span> <span data-ttu-id="27eb3-273">В следующем разделе описываются требования к объекту MailUser для целевого клиента.</span><span class="sxs-lookup"><span data-stu-id="27eb3-273">The following section details the MailUser object requirements for the target tenant.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="27eb3-274">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="27eb3-274">Prerequisites</span></span>
  
<span data-ttu-id="27eb3-275">В целевой организации необходимо убедиться в том, что в целевой организации установлены следующие объекты и атрибуты.</span><span class="sxs-lookup"><span data-stu-id="27eb3-275">You must ensure the following objects and attributes are set in the target organization.</span></span>  

1. <span data-ttu-id="27eb3-276">Для всех почтовых ящиков, перемещаемых из исходной организации, необходимо подготовить объект MailUser в целевой организации:</span><span class="sxs-lookup"><span data-stu-id="27eb3-276">For any mailbox moving from a source organization, you must provision a MailUser object in the Target organization:</span></span> 
   - <span data-ttu-id="27eb3-277">Целевой MailUser должен иметь эти атрибуты из исходного почтового ящика или назначаться новому объекту User:</span><span class="sxs-lookup"><span data-stu-id="27eb3-277">The Target MailUser must have these attributes from the source mailbox or assigned with the new User object:</span></span>
      - <span data-ttu-id="27eb3-278">ExchangeGUID (прямой Flow от источника к целевому) — GUID почтового ящика должен быть соответствующим.</span><span class="sxs-lookup"><span data-stu-id="27eb3-278">ExchangeGUID (direct flow from source to target) – The mailbox GUID must match.</span></span> <span data-ttu-id="27eb3-279">Процесс перемещения не будет продолжаться, если он отсутствует в целевом объекте.</span><span class="sxs-lookup"><span data-stu-id="27eb3-279">The move process will not proceed if this is not present on target object.</span></span> 
      - <span data-ttu-id="27eb3-280">Свойств archiveguid (прямой Flow от источника к целевому) — GUID архива должен быть соответствующим.</span><span class="sxs-lookup"><span data-stu-id="27eb3-280">ArchiveGUID (direct flow from source to target) – The archive GUID must match.</span></span> <span data-ttu-id="27eb3-281">Процесс перемещения не будет продолжаться, если он отсутствует в целевом объекте.</span><span class="sxs-lookup"><span data-stu-id="27eb3-281">The move process will not proceed if this is not present on the target object.</span></span> <span data-ttu-id="27eb3-282">(Это необходимо только в том случае, если для исходного почтового ящика включена архивация).</span><span class="sxs-lookup"><span data-stu-id="27eb3-282">(This is only required if the source mailbox is Archive enabled).</span></span> 
      - <span data-ttu-id="27eb3-283">LegacyExchangeDN (Flow AS proxyAddress, "x500: <LegacyExchangeDN> ") — legacyExchangeDN должен присутствовать в целевом MailUser как x500: ProxyAddress.</span><span class="sxs-lookup"><span data-stu-id="27eb3-283">LegacyExchangeDN (flow as proxyAddress, “x500:<LegacyExchangeDN>”) – The LegacyExchangeDN must be present on target MailUser as x500: proxyAddress.</span></span> <span data-ttu-id="27eb3-284">Процессы перемещения не будут продолжаться, если они отсутствуют в целевом объекте.</span><span class="sxs-lookup"><span data-stu-id="27eb3-284">The move processes will not proceed if this is not present on the target object.</span></span> 
      - <span data-ttu-id="27eb3-285">UserPrincipalName — имя участника-пользователя будет выровнено с новым удостоверением или целевой компанией пользователя (например, user@northwindtraders.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="27eb3-285">UserPrincipalName – UPN will align to the user’s NEW identity or target company (for example, user@northwindtraders.onmicrosoft.com).</span></span> 
      - <span data-ttu-id="27eb3-286">Основной SMTP-адрес SMTPAddress — основной SMTP-адрес, который будет выровнен по новой компании пользователя (например, user@northwind.com).</span><span class="sxs-lookup"><span data-stu-id="27eb3-286">Primary SMTPAddress – Primary SMTP address will align to the user’s NEW company (for example, user@northwind.com).</span></span> 
      - <span data-ttu-id="27eb3-287">TargetAddress/ExternalEmailAddress – MailUser будет ссылаться на текущий почтовый ящик пользователя, размещенный в исходном клиенте (например, user@contoso.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="27eb3-287">TargetAddress/ExternalEmailAddress – MailUser will reference the user’s current mailbox hosted in source tenant (for example user@contoso.onmicrosoft.com).</span></span> <span data-ttu-id="27eb3-288">При назначении этого значения убедитесь, что вы также назначаете PrimarySMTPAddress или это значение задает PrimarySMTPAddress, что приведет к сбоям перемещения.</span><span class="sxs-lookup"><span data-stu-id="27eb3-288">When assigning this value, verify that you have/are also assigning PrimarySMTPAddress or this value will set the PrimarySMTPAddress which will cause move failures.</span></span> 
      - <span data-ttu-id="27eb3-289">Невозможно добавить устаревшие SMTP-адреса прокси-сервера из исходного почтового ящика в целевой MailUser.</span><span class="sxs-lookup"><span data-stu-id="27eb3-289">You cannot add legacy smtp proxy addresses from source mailbox to target MailUser.</span></span> <span data-ttu-id="27eb3-290">Например, нельзя поддерживать contoso.com в MEU в объектах клиента fabrikam.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="27eb3-290">For example, you cannot maintain contoso.com on the MEU in fabrikam.onmicrosoft.com tenant objects).</span></span> <span data-ttu-id="27eb3-291">Домены связаны только с одним клиентом Azure AD или Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="27eb3-291">Domains are associated with one Azure AD or Exchange Online tenant only.</span></span>
 
    <span data-ttu-id="27eb3-292">Пример **целевого** объекта MailUser:</span><span class="sxs-lookup"><span data-stu-id="27eb3-292">Example **target** MailUser object:</span></span>
 
    | <span data-ttu-id="27eb3-293">Атрибут</span><span class="sxs-lookup"><span data-stu-id="27eb3-293">Attribute</span></span>             | <span data-ttu-id="27eb3-294">Значение</span><span class="sxs-lookup"><span data-stu-id="27eb3-294">Value</span></span>                                                                                                                    |
    |-----------------------|--------------------------------------------------------------------------------------------------------------------------|
    | <span data-ttu-id="27eb3-295">Alias</span><span class="sxs-lookup"><span data-stu-id="27eb3-295">Alias</span></span>                 | <span data-ttu-id="27eb3-296">ларан</span><span class="sxs-lookup"><span data-stu-id="27eb3-296">LaraN</span></span>                                                                                                                    |
    | <span data-ttu-id="27eb3-297">RecipientType</span><span class="sxs-lookup"><span data-stu-id="27eb3-297">RecipientType</span></span>         | <span data-ttu-id="27eb3-298">MailUser</span><span class="sxs-lookup"><span data-stu-id="27eb3-298">MailUser</span></span>                                                                                                                 |
    | <span data-ttu-id="27eb3-299">RecipientTypeDetails</span><span class="sxs-lookup"><span data-stu-id="27eb3-299">RecipientTypeDetails</span></span>  | <span data-ttu-id="27eb3-300">MailUser</span><span class="sxs-lookup"><span data-stu-id="27eb3-300">MailUser</span></span>                                                                                                                 |
    | <span data-ttu-id="27eb3-301">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="27eb3-301">UserPrincipalName</span></span>     | <span data-ttu-id="27eb3-302">LaraN@northwintraders \. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="27eb3-302">LaraN@northwintraders\.onmicrosoft.com</span></span>                                                                                    |
    | <span data-ttu-id="27eb3-303">PrimarySmtpAddress</span><span class="sxs-lookup"><span data-stu-id="27eb3-303">PrimarySmtpAddress</span></span>    | <span data-ttu-id="27eb3-304">Лара \. Newton@northwind.com</span><span class="sxs-lookup"><span data-stu-id="27eb3-304">Lara\.Newton@northwind.com</span></span>                                                                                                |
    | <span data-ttu-id="27eb3-305">ExternalEmailAddress</span><span class="sxs-lookup"><span data-stu-id="27eb3-305">ExternalEmailAddress</span></span>  | <span data-ttu-id="27eb3-306">SMTP: LaraN@contoso \. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="27eb3-306">SMTP:LaraN@contoso\.onmicrosoft.com</span></span>                                                                                       |
    | <span data-ttu-id="27eb3-307">ExchangeGuid</span><span class="sxs-lookup"><span data-stu-id="27eb3-307">ExchangeGuid</span></span>          | <span data-ttu-id="27eb3-308">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span><span class="sxs-lookup"><span data-stu-id="27eb3-308">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span></span>                                                                                     |
    | <span data-ttu-id="27eb3-309">LegacyExchangeDN</span><span class="sxs-lookup"><span data-stu-id="27eb3-309">LegacyExchangeDN</span></span>      | <span data-ttu-id="27eb3-310">/o = First Organization/ou = административная группа Exchange</span><span class="sxs-lookup"><span data-stu-id="27eb3-310">/o=First Organization/ou=Exchange Administrative Group</span></span>                                                                   |
    |                       | <span data-ttu-id="27eb3-311">(FYDIBOHF23SPDLT)/CN = Recipients/CN = 74e5385fce4b46d19006876949855035Lara</span><span class="sxs-lookup"><span data-stu-id="27eb3-311">(FYDIBOHF23SPDLT)/cn=Recipients/cn=74e5385fce4b46d19006876949855035Lara</span></span>                                                  |
    | <span data-ttu-id="27eb3-312">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="27eb3-312">EmailAddresses</span></span>        | <span data-ttu-id="27eb3-313">x500:/o = First Organization/OU = Exchange Administrative Group (FYDIBOHF23SPDLT)/CN = Recipients/CN = d11ec1a2cacd4f81858c8190</span><span class="sxs-lookup"><span data-stu-id="27eb3-313">x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c8190</span></span>  |
    |                       | <span data-ttu-id="27eb3-314">7273f1f9 — Лара</span><span class="sxs-lookup"><span data-stu-id="27eb3-314">7273f1f9-Lara</span></span>                                                                                                            |
    |                       | <span data-ttu-id="27eb3-315">SMTP: LaraN@northwindtraders \. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="27eb3-315">smtp:LaraN@northwindtraders\.onmicrosoft.com</span></span>                                                                              |
    |                       | <span data-ttu-id="27eb3-316">SMTP: Лара \. Newton@northwind.com</span><span class="sxs-lookup"><span data-stu-id="27eb3-316">SMTP:Lara\.Newton@northwind.com</span></span>                                                                                           |
    |||

   <span data-ttu-id="27eb3-317">Пример **исходного** объекта почтового ящика:</span><span class="sxs-lookup"><span data-stu-id="27eb3-317">Example **source** Mailbox object:</span></span>

   | <span data-ttu-id="27eb3-318">Атрибут</span><span class="sxs-lookup"><span data-stu-id="27eb3-318">Attribute</span></span>             | <span data-ttu-id="27eb3-319">Значение</span><span class="sxs-lookup"><span data-stu-id="27eb3-319">Value</span></span>                                                                    |
   |-----------------------|--------------------------------------------------------------------------|
   | <span data-ttu-id="27eb3-320">Alias</span><span class="sxs-lookup"><span data-stu-id="27eb3-320">Alias</span></span>                 | <span data-ttu-id="27eb3-321">ларан</span><span class="sxs-lookup"><span data-stu-id="27eb3-321">LaraN</span></span>                                                                    |
   | <span data-ttu-id="27eb3-322">RecipientType</span><span class="sxs-lookup"><span data-stu-id="27eb3-322">RecipientType</span></span>         | <span data-ttu-id="27eb3-323">UserMailbox</span><span class="sxs-lookup"><span data-stu-id="27eb3-323">UserMailbox</span></span>                                                              |
   | <span data-ttu-id="27eb3-324">RecipientTypeDetails</span><span class="sxs-lookup"><span data-stu-id="27eb3-324">RecipientTypeDetails</span></span>  | <span data-ttu-id="27eb3-325">UserMailbox</span><span class="sxs-lookup"><span data-stu-id="27eb3-325">UserMailbox</span></span>                                                              |
   | <span data-ttu-id="27eb3-326">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="27eb3-326">UserPrincipalName</span></span>     | <span data-ttu-id="27eb3-327">LaraN@contoso \. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="27eb3-327">LaraN@contoso\.onmicrosoft.com</span></span>                                            |
   | <span data-ttu-id="27eb3-328">PrimarySmtpAddress</span><span class="sxs-lookup"><span data-stu-id="27eb3-328">PrimarySmtpAddress</span></span>    | <span data-ttu-id="27eb3-329">Лара \. Newton@contoso.com</span><span class="sxs-lookup"><span data-stu-id="27eb3-329">Lara\.Newton@contoso.com</span></span>                                                  |
   | <span data-ttu-id="27eb3-330">ExchangeGuid</span><span class="sxs-lookup"><span data-stu-id="27eb3-330">ExchangeGuid</span></span>          | <span data-ttu-id="27eb3-331">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span><span class="sxs-lookup"><span data-stu-id="27eb3-331">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span></span>                                     |
   | <span data-ttu-id="27eb3-332">LegacyExchangeDN</span><span class="sxs-lookup"><span data-stu-id="27eb3-332">LegacyExchangeDN</span></span>      | <span data-ttu-id="27eb3-333">/o = First Organization/ou = административная группа Exchange</span><span class="sxs-lookup"><span data-stu-id="27eb3-333">/o=First Organization/ou=Exchange Administrative Group</span></span>                   |
   |                       | <span data-ttu-id="27eb3-334">(FYDIBOHF23SPDLT)/CN = Recipients/CN = d11ec1a2cacd4f81858c81907273f1f9Lara</span><span class="sxs-lookup"><span data-stu-id="27eb3-334">(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara</span></span>  |
   | <span data-ttu-id="27eb3-335">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="27eb3-335">EmailAddresses</span></span>        | <span data-ttu-id="27eb3-336">SMTP: LaraN@contoso \. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="27eb3-336">smtp:LaraN@contoso\.onmicrosoft.com</span></span> 
   |                       | <span data-ttu-id="27eb3-337">SMTP: Лара \. Newton@contoso.com</span><span class="sxs-lookup"><span data-stu-id="27eb3-337">SMTP:Lara\.Newton@contoso.com</span></span>          |
   |||

   - <span data-ttu-id="27eb3-338">Дополнительные атрибуты могут быть включены в гибридную запись гибридной записи Exchange.</span><span class="sxs-lookup"><span data-stu-id="27eb3-338">Additional attributes may be included in Exchange hybrid write back already.</span></span> <span data-ttu-id="27eb3-339">В противном случае они должны быть включены.</span><span class="sxs-lookup"><span data-stu-id="27eb3-339">If not, they should be included.</span></span> 
   - <span data-ttu-id="27eb3-340">msExchBlockedSendersHash — записывает данные из клиентов в локальный каталог Active Directory и заблокировали данные отправителя в оперативном режиме.</span><span class="sxs-lookup"><span data-stu-id="27eb3-340">msExchBlockedSendersHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>
   - <span data-ttu-id="27eb3-341">msExchSafeRecipientsHash — записывает данные из клиентов в локальный каталог Active Directory и заблокировали данные отправителя в оперативном режиме.</span><span class="sxs-lookup"><span data-stu-id="27eb3-341">msExchSafeRecipientsHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>
   - <span data-ttu-id="27eb3-342">msExchSafeSendersHash — записывает данные из клиентов в локальный каталог Active Directory и заблокировали данные отправителя в оперативном режиме.</span><span class="sxs-lookup"><span data-stu-id="27eb3-342">msExchSafeSendersHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>

2. <span data-ttu-id="27eb3-343">Если исходный почтовый ящик находится в Литигатионхолд, а размер элементов для восстановления исходного почтового ящика превышает размер базы данных по умолчанию (30 ГБ), перемещение не будет продолжено, так как Целевая квота меньше размера исходного почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="27eb3-343">If the source mailbox is on LitigationHold and the source mailbox Recoverable Items size is greater than our database default (30 GB), moves will not proceed since the target quota is less than the source mailbox size.</span></span> <span data-ttu-id="27eb3-344">Вы можете обновить целевой объект MailUser для переноса флагов почтовых ящиков ЕЛК из исходной среды в целевой, который запускает целевую систему для расширения квоты MailUser до 100 ГБ, позволяя перемещаться на целевую систему.</span><span class="sxs-lookup"><span data-stu-id="27eb3-344">You can update the target MailUser object to transition the ELC mailbox flags from the source environment to the target, which triggers the target system to expand the quota of the MailUser to 100 GB, thus allowing the move to the target.</span></span> <span data-ttu-id="27eb3-345">Эти инструкции будут работать только для гибридного удостоверения, на котором выполняется Azure AD Connect, так как команды Метки ЕЛК не предоставляются администраторам клиента.</span><span class="sxs-lookup"><span data-stu-id="27eb3-345">These instructions will work only for hybrid identity running Azure AD Connect, as the commands to stamp the ELC flags are not exposed to tenant administrators.</span></span>

    >[!Note]
    > <span data-ttu-id="27eb3-346">ПРИМЕР — БЕЗ ГАРАНТИЙ</span><span class="sxs-lookup"><span data-stu-id="27eb3-346">SAMPLE – AS IS, NO WARRANTY</span></span><br/><span data-ttu-id="27eb3-347">Этот сценарий предполагает подключение к исходному почтовому ящику (для получения исходных значений) и целевому локальному каталогу Active Directory (чтобы пометить объект ADUser).</span><span class="sxs-lookup"><span data-stu-id="27eb3-347">This script assumes a connection to both source mailbox (to get source values) and the target on-premises Active Directory (to stamp the ADUser object).</span></span> <span data-ttu-id="27eb3-348">Если в источнике включено судебное восстановление или восстановление отдельных элементов, задайте это значение для целевой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="27eb3-348">If source has litigation or single item recovery enabled, set this on the destination account.</span></span>  <span data-ttu-id="27eb3-349">При этом размер корзины конечного счета увеличится до 100 ГБ.</span><span class="sxs-lookup"><span data-stu-id="27eb3-349">This will increase the dumpster size of destination account to 100 GB.</span></span>

    ```powershell
    $ELCValue = 0 
    if ($source.LitigationHoldEnabled) {$ELCValue = $ELCValue + 8} if ($source.SingleItemRecoveryEnabled) {$ELCValue = $ELCValue + 16} if ($ELCValue -gt 0) {Set-ADUser -Server $domainController -Identity $destination.SamAccountName -Replace @{msExchELCMailboxFlags=$ELCValue}} 
    ```
3. <span data-ttu-id="27eb3-350">Негибридные целевые клиенты могут изменить квоту в папке "элементы с возможностью восстановления" для Маилусерс перед переносом, выполнив следующую команду, чтобы включить удержание для судебного разбирательства в объекте MailUser и увеличить квоту до 100 ГБ: `Set-MailUser -EnableLitigationHoldForMigration $TRUE` .</span><span class="sxs-lookup"><span data-stu-id="27eb3-350">Non-hybrid target tenants can modify the quota on the Recoverable Items folder for the MailUsers prior to migration by running the following command to enable Litigation Hold on the MailUser object and increasing the quota to 100 GB: `Set-MailUser -EnableLitigationHoldForMigration $TRUE`.</span></span> <span data-ttu-id="27eb3-351">Примечание Это не будет работать для клиентов в гибридной конфигурации.</span><span class="sxs-lookup"><span data-stu-id="27eb3-351">Note this will not work for tenants in hybrid.</span></span>

4. <span data-ttu-id="27eb3-352">Пользователям в целевой организации необходимо лицензировать соответствующие подписки на Exchange Online, применимые для Организации.</span><span class="sxs-lookup"><span data-stu-id="27eb3-352">Users in the target organization must be licensed with appropriate Exchange Online subscriptions applicable for the organization.</span></span> <span data-ttu-id="27eb3-353">Вы можете применить лицензию при перемещении почтового ящика, но только после того, как Целевая MailUser будет правильно настроена с ExchangeGUID и прокси-адресами.</span><span class="sxs-lookup"><span data-stu-id="27eb3-353">You may apply a license in advance of a mailbox move but ONLY once the target MailUser is properly set up with ExchangeGUID and proxy addresses.</span></span> <span data-ttu-id="27eb3-354">Применение лицензии перед применением ExchangeGUID приведет к созданию нового почтового ящика, подготовленного в целевой организации.</span><span class="sxs-lookup"><span data-stu-id="27eb3-354">Applying a license before the ExchangeGUID is applied will result in a new mailbox provisioned in target organization.</span></span> 

    > [!Note]
    > <span data-ttu-id="27eb3-355">Если вы применяете лицензию для объекта почтового ящика или MailUser, то все типы SMTP proxyAddresses будут очищены, чтобы убедиться, что в массив Exchange EmailAddresses включены только проверенные домены.</span><span class="sxs-lookup"><span data-stu-id="27eb3-355">When you apply a license on a Mailbox or MailUser object, all SMTP type proxyAddresses are scrubbed to ensure only verified domains are included in the Exchange EmailAddresses array.</span></span> 

5. <span data-ttu-id="27eb3-356">Необходимо убедиться, что в целевом MailUser нет предыдущего ExchangeGuid, которое не соответствует исходному ExchangeGuid.</span><span class="sxs-lookup"><span data-stu-id="27eb3-356">You must ensure that the target MailUser has no previous ExchangeGuid that does not match the Source ExchangeGuid.</span></span> <span data-ttu-id="27eb3-357">Это может произойти, если Целевая MEU была предварительно лицензирована для Exchange Online и подготовлена к работе с почтовым ящиком.</span><span class="sxs-lookup"><span data-stu-id="27eb3-357">This might occur if the target MEU was previously licensed for Exchange Online and provisioned a mailbox.</span></span> <span data-ttu-id="27eb3-358">Если целевая MailUser была предварительно лицензирована или ExchangeGuid, не соответствующая исходному ExchangeGuid, необходимо выполнить очистку облачного MEU.</span><span class="sxs-lookup"><span data-stu-id="27eb3-358">If the target MailUser was previously licensed for or had an ExchangeGuid that does not match the Source ExchangeGuid, you need to perform a cleanup of the cloud MEU.</span></span> <span data-ttu-id="27eb3-359">Для этих облачных Meu можно выполнить `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` команду.</span><span class="sxs-lookup"><span data-stu-id="27eb3-359">For these cloud MEUs, you can run the `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` command.</span></span> 

    > [!Caution]
    > <span data-ttu-id="27eb3-360">Этот процесс является необратимым.</span><span class="sxs-lookup"><span data-stu-id="27eb3-360">This process is irreversible.</span></span> <span data-ttu-id="27eb3-361">Если объект имеет почтовый ящик softDeleted, его невозможно восстановить после этой точки.</span><span class="sxs-lookup"><span data-stu-id="27eb3-361">If the object has a softDeleted mailbox, it cannot be restored after this point.</span></span> <span data-ttu-id="27eb3-362">Однако при снятом флажке вы можете синхронизировать правильный ExchangeGuid с целевым объектом, и MRS будет подключаться к новому почтовому ящику исходного почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="27eb3-362">Once cleared, however, you can sync the correct ExchangeGuid to the target object and MRS will connect the source mailbox to the newly created target mailbox.</span></span> <span data-ttu-id="27eb3-363">(Ссылка на блог EHLO на новом параметре.)</span><span class="sxs-lookup"><span data-stu-id="27eb3-363">(Reference EHLO blog on the new parameter.)</span></span> 
 
    <span data-ttu-id="27eb3-364">Поиск объектов, которые были ранее почтовыми ящиками, с помощью этой команды.</span><span class="sxs-lookup"><span data-stu-id="27eb3-364">Find objects that were previously mailboxes using this command.</span></span>

    ```powershell
    Get-User <identity> | select Name, *recipient* | ft -a**.
    ```
    <span data-ttu-id="27eb3-365">Пример:</span><span class="sxs-lookup"><span data-stu-id="27eb3-365">Here is an example.</span></span> 

    ```powershell
    PS demo> get-user John@northwindtraders.com |select name, *recipient*| ft -AutoSize 
 
    Name        PreviousRecipientTypeDetails     RecipientType RecipientTypeDetails 
    ----       ---------------------------- ------------- -------------------- 
    John       UserMailbox                  MailUser      MailUser 
    ```   
 
    <span data-ttu-id="27eb3-366">Очистка обратимо удаленного почтового ящика с помощью этой команды.</span><span class="sxs-lookup"><span data-stu-id="27eb3-366">Clear the soft-deleted mailbox using this command.</span></span>

    ````
    Set-User <identity> -PermanentlyClearPreviousMailboxInfo
    ```` 

    <span data-ttu-id="27eb3-367">Пример:</span><span class="sxs-lookup"><span data-stu-id="27eb3-367">Here is an example.</span></span>

    ```powershell
    PS demo> Set-User John@northwindtraders.com -PermanentlyClearPreviousMailboxInfo Confirm 
    Are you sure you want to perform this action? 
    Delete all existing information about user “John@northwindtraders.com"?. This operation will clear existing values from Previous home MDB and Previous Mailbox GUID of the user. After deletion, reconnecting to the previous mailbox that existed in the cloud will not be possible and any content it had will be unrecoverable PERMANENTLY. 
    Do you want to continue? 
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"): Y 
    ```

## <a name="perform-mailbox-migrations"></a><span data-ttu-id="27eb3-368">Выполнение миграции почтовых ящиков</span><span class="sxs-lookup"><span data-stu-id="27eb3-368">Perform mailbox migrations</span></span>

<span data-ttu-id="27eb3-369">Миграция почтовых ящиков Exchange между клиентами отправляются в виде пакетов миграции, инициированных из целевого клиента.</span><span class="sxs-lookup"><span data-stu-id="27eb3-369">Cross-tenant Exchange mailbox migrations are submitted as migration batches initiated from the target tenant.</span></span> <span data-ttu-id="27eb3-370">Это похоже на способ работы пакетов миграции при переходе с локальной организации Exchange на сервер Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="27eb3-370">This is similar to the way that on-boarding migration batches work when migrating from Exchange on-premises to Microsoft 365.</span></span> 

### <a name="create-migration-batches"></a><span data-ttu-id="27eb3-371">Создание пакетов миграции</span><span class="sxs-lookup"><span data-stu-id="27eb3-371">Create Migration batches</span></span>

<span data-ttu-id="27eb3-372">Ниже приведен пример командлета пакета миграции для запуска операций перемещения.</span><span class="sxs-lookup"><span data-stu-id="27eb3-372">Here is an example migration batch cmdlet for kicking off moves.</span></span>

```powershell
New-MigrationBatch -Name T2Tbatch-testforignitedemo -SourceEndpoint target_source_7977 -CSVData ([System.IO.File]::ReadAllBytes('users.csv')) -Autostart -TargetDeliveryDomain targetformoves.onmicrosoft.com -AutoComplete

Identity                   Status  Type               TotalCount
--------                   ------  ----               ----------
T2Tbatch-testforignitedemo Syncing ExchangeRemoteMove 1

```

> [!Note]
> <span data-ttu-id="27eb3-373">Адрес электронной почты в CSV-файле должен быть указан в целевом клиенте, а не в исходном клиенте.</span><span class="sxs-lookup"><span data-stu-id="27eb3-373">The email address in the CSV file must be the one specified in the target tenant, not the source tenant.</span></span>

<span data-ttu-id="27eb3-374">Отправка пакетов миграции также поддерживается в новом центре администрирования Exchange при выборе параметра кросс-клиент.</span><span class="sxs-lookup"><span data-stu-id="27eb3-374">Migration batch submission is also supported from the new Exchange Admin Center when selecting the cross-tenant option.</span></span>
 
#### <a name="update-on-premises-mailusers"></a><span data-ttu-id="27eb3-375">Обновление локальной Маилусерс</span><span class="sxs-lookup"><span data-stu-id="27eb3-375">Update on-premises MailUsers</span></span>

<span data-ttu-id="27eb3-376">После перемещения почтовых ящиков из источника в целевой необходимо убедиться, что локальные почтовые пользователи, а также исходный и целевой серверы, обновлены с помощью новой объекта targetAddress.</span><span class="sxs-lookup"><span data-stu-id="27eb3-376">Once the mailbox moves from source to target, you should ensure that the on-premises mail users, both Source and target, are updated with the new targetAddress.</span></span> <span data-ttu-id="27eb3-377">В примерах Таржетделиверидомаин используется в перемещении **contoso \. onmicrosoft.com**.</span><span class="sxs-lookup"><span data-stu-id="27eb3-377">In the examples, the targetDeliveryDomain used in the move is **contoso\.onmicrosoft.com**.</span></span> <span data-ttu-id="27eb3-378">Обновление почтовых пользователей с помощью этой targetAddress.</span><span class="sxs-lookup"><span data-stu-id="27eb3-378">Update the mail users with this targetAddress.</span></span>
 
## <a name="frequently-asked-questions"></a><span data-ttu-id="27eb3-379">Вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="27eb3-379">Frequently asked questions</span></span>
 
<span data-ttu-id="27eb3-380">**Требуется обновление Ремотемаилбоксес в локальной системе после перемещения?**</span><span class="sxs-lookup"><span data-stu-id="27eb3-380">**Do we need to update RemoteMailboxes in source on-premises after the move?**</span></span>
 
<span data-ttu-id="27eb3-381">Да, следует обновить объект targetAddress (RemoteRoutingAddress/ExternalEmailAddress) исходных локальных пользователей, когда почтовый ящик исходного клиента перемещается в Целевой клиент.</span><span class="sxs-lookup"><span data-stu-id="27eb3-381">Yes, you should update the targetAddress (RemoteRoutingAddress/ExternalEmailAddress) of the source on-premises users when the source tenant mailbox moves to target tenant.</span></span>  <span data-ttu-id="27eb3-382">Так как маршрутизация почты может подписаться на ссылки между несколькими почтовыми пользователями, имеющими разные Таржетаддрессес, Поиск сведений о доступности для почтовых пользователей должен быть предназначен для расположения пользователя почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="27eb3-382">While mail routing can follow the referrals across multiple mail users with different targetAddresses, Free/Busy lookups for mail users MUST target the location of the mailbox user.</span></span> <span data-ttu-id="27eb3-383">Поиск сведений о доступности не выполняется для нескольких перенаправлений.</span><span class="sxs-lookup"><span data-stu-id="27eb3-383">Free/Busy lookups will not chase multiple redirects.</span></span> 
 
<span data-ttu-id="27eb3-384">**Переносить ли содержимое папки чата в Teams?**</span><span class="sxs-lookup"><span data-stu-id="27eb3-384">**Does the Teams chat folder content migrate cross-tenant?**</span></span> 

<span data-ttu-id="27eb3-385">Нет, содержимое папки чата в Teams не переносит перекрестного клиента.</span><span class="sxs-lookup"><span data-stu-id="27eb3-385">No, the Teams chat folder content does not migrate cross-tenant.</span></span> 
 
<span data-ttu-id="27eb3-386">**Как можно увидеть только перемещения, которые являются передвижениями между клиентами, а не с переносом и отключением?**</span><span class="sxs-lookup"><span data-stu-id="27eb3-386">**How can I see just moves that are cross-tenant moves, not my onboarding and offboarding moves?**</span></span>

<span data-ttu-id="27eb3-387">Используйте `-flags` параметр.</span><span class="sxs-lookup"><span data-stu-id="27eb3-387">Use the `-flags` parameter.</span></span> <span data-ttu-id="27eb3-388">Пример:</span><span class="sxs-lookup"><span data-stu-id="27eb3-388">Here is an example.</span></span>

```powershell
Get-MoveRequest -Flags "CrossTenant" 
```
 
<span data-ttu-id="27eb3-389">**Можно предоставить примеры сценариев для копирования атрибутов, используемых при тестировании?**</span><span class="sxs-lookup"><span data-stu-id="27eb3-389">**Can you provide example scripts for copying attributes used in testing?**</span></span>

> [!Note]
> <span data-ttu-id="27eb3-390">ПРИМЕР — БЕЗ ГАРАНТИЙ</span><span class="sxs-lookup"><span data-stu-id="27eb3-390">SAMPLE – AS IS, NO WARRANTY</span></span><br/><span data-ttu-id="27eb3-391">В этом сценарии предполагается подключение к исходному почтовому ящику (для получения исходных значений) и целевой локальной доменной службе Active Directory (чтобы пометить объект ADUser).</span><span class="sxs-lookup"><span data-stu-id="27eb3-391">This script assumes a connection to both source mailbox (to get source values) and the target on-premises Active Directory Domain Services (to stamp the ADUser object).</span></span> <span data-ttu-id="27eb3-392">Если в источнике включено судебное восстановление или восстановление отдельных элементов, задайте это значение для целевой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="27eb3-392">If source has litigation or single item recovery enabled, set this on the destination account.</span></span>  <span data-ttu-id="27eb3-393">При этом размер корзины конечного счета увеличится до 100 ГБ.</span><span class="sxs-lookup"><span data-stu-id="27eb3-393">This will increase the dumpster size of destination account to 100 GB.</span></span>

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
<span data-ttu-id="27eb3-394">**Как получить доступ к Outlook в день 1 после перемещения почтового ящика использования?**</span><span class="sxs-lookup"><span data-stu-id="27eb3-394">**How do we access Outlook on Day 1 after the use mailbox is moved?**</span></span>

<span data-ttu-id="27eb3-395">Так как только один клиент может владеть доменом, бывший первичный SMTPAddress не будет связан с пользователем в целевом клиенте после завершения перемещения почтового ящика; только те домены, которые связаны с новым клиентом.</span><span class="sxs-lookup"><span data-stu-id="27eb3-395">Since only one tenant can own a domain, the former primary SMTPAddress will not be associated to the user in the target tenant when the mailbox move completes; only those domains associated with the new tenant.</span></span> <span data-ttu-id="27eb3-396">Outlook использует новое имя участника-пользователя для проверки подлинности в службе, а профиль Outlook ожидает, что устаревший основной SMTPAddress будет сопоставлен с почтовым ящиком в целевой системе.</span><span class="sxs-lookup"><span data-stu-id="27eb3-396">Outlook uses the users new UPN to authenticate to the service and the Outlook profile expects to find the legacy primary SMTPAddress to match the mailbox in the target system.</span></span> <span data-ttu-id="27eb3-397">Так как устаревший адрес не находится в целевой системе, подключается к профилю Outlook, чтобы найти только что перемещенный почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="27eb3-397">Since the legacy address is not in the target System the outlook profile will not connect to find the newly moved mailbox.</span></span> 

<span data-ttu-id="27eb3-398">Для этого первоначального развертывания пользователям потребуется перестроить свой профиль с помощью нового имени участника-пользователя, основного SMTP-адреса и повторной синхронизации OST-контента.</span><span class="sxs-lookup"><span data-stu-id="27eb3-398">For this initial deployment, users will need to rebuild their profile with their new UPN, primary SMTP address and re-sync OST content.</span></span> 

> [!Note]
> <span data-ttu-id="27eb3-399">Запланируйте в соответствии с тем, как вы отпланируете завершить работу пользователей.</span><span class="sxs-lookup"><span data-stu-id="27eb3-399">Plan accordingly as you batch your users for completion.</span></span> <span data-ttu-id="27eb3-400">Необходимо учитывать возможность использования и емкости сети при создании профилей клиентов Outlook, а также при загрузке последующих OST-файлов и файлов автономной адресной книги для клиентов.</span><span class="sxs-lookup"><span data-stu-id="27eb3-400">You need to account for network utilization and capacity when Outlook client profiles are created and subsequent OST and OAB files are downloaded to clients.</span></span> 
 
<span data-ttu-id="27eb3-401">**Какие роли Exchange RBAC должны быть участниками группы для настройки или завершения перемещения между клиентами?**</span><span class="sxs-lookup"><span data-stu-id="27eb3-401">**What Exchange RBAC roles do I need to be member of to set up or complete a cross-tenant move?**</span></span>
 
<span data-ttu-id="27eb3-402">При перемещении почтового ящика создается матрица ролей на основе предположения делегированных обязанностей.</span><span class="sxs-lookup"><span data-stu-id="27eb3-402">There a matrix of roles based on assumption of delegated duties when executing a mailbox move.</span></span> <span data-ttu-id="27eb3-403">В настоящее время требуются две роли:</span><span class="sxs-lookup"><span data-stu-id="27eb3-403">Currently, two roles are required:</span></span>  

- <span data-ttu-id="27eb3-404">Первая роль предназначена для одноразовой установки, которая устанавливает авторизацию перемещения контента в клиентской или организационной границе.</span><span class="sxs-lookup"><span data-stu-id="27eb3-404">The first role is for a one-time setup task that establishes the authorization of moving content into or out of your tenant/organizational boundary.</span></span> <span data-ttu-id="27eb3-405">Так как перемещение данных из организационного контроля является важнейшим аспектом для всех компаний, мы выбрали наиболее назначенную роль администратора организации (Оргадмин).</span><span class="sxs-lookup"><span data-stu-id="27eb3-405">As moving data out of your organizational control is a critical concern for all companies, we opted with the highest assigned role of Organization Administrator (OrgAdmin).</span></span> <span data-ttu-id="27eb3-406">Эта роль должна изменять или настраивать новый OrganizationRelationship, определяющий параметр Маилбоксмовекапабилити в удаленной организации.</span><span class="sxs-lookup"><span data-stu-id="27eb3-406">This role must alter or setup a new OrganizationRelationship that defines the -MailboxMoveCapability with the remote organization.</span></span> <span data-ttu-id="27eb3-407">Только Оргадмин может изменить параметр Маилбоксмовекапабилити, в то время как другие атрибуты Организатионрелатионхип могут управляться администратором федеративного общего доступа.</span><span class="sxs-lookup"><span data-stu-id="27eb3-407">Only the OrgAdmin can alter the MailboxMoveCapability setting, while other attributes on the OrganizationRelationhip can be managed by the Federated Sharing administrator.</span></span> 
 
- <span data-ttu-id="27eb3-408">Роль выполнения фактических команд перемещения может быть делегирована функции нижнего уровня.</span><span class="sxs-lookup"><span data-stu-id="27eb3-408">The role of executing the actual move commands can be delegated to a lower-level function.</span></span> <span data-ttu-id="27eb3-409">Роли почтовых ящиков назначена возможность перемещения почтовых ящиков в организации или из нее с помощью `-RemoteTenant` параметра.</span><span class="sxs-lookup"><span data-stu-id="27eb3-409">The role of Move Mailboxes is assigned the capability of moving mailboxes in or out of the organization by using the `-RemoteTenant` parameter.</span></span>  

<span data-ttu-id="27eb3-410">**Как мы нацелены на то, какой SMTP-адрес выбран для targetAddress (Таржетделиверидомаин) в преобразованном почтовом ящике (для преобразования MailUser)?**</span><span class="sxs-lookup"><span data-stu-id="27eb3-410">**How do we target which SMTP address is selected for targetAddress (TargetDeliveryDomain) on the converted mailbox (to MailUser conversion)?**</span></span>
 
<span data-ttu-id="27eb3-411">Почтовые ящики Exchange перемещаются с помощью MRS, создавая объект targetAddress в исходном почтовом ящике при преобразовании в MailUser, сопоставляя адрес электронной почты (proxyAddress) в целевом объекте.</span><span class="sxs-lookup"><span data-stu-id="27eb3-411">Exchange mailbox moves using MRS craft the targetAddress on the original source mailbox when converting to a MailUser by matching an email address (proxyAddress) on the target object.</span></span> <span data-ttu-id="27eb3-412">Процесс принимает значение-Таржетделиверидомаин, передаваемое в команду Move, а затем проверяет наличие на конечной стороне подходящего прокси-сервера для этого домена.</span><span class="sxs-lookup"><span data-stu-id="27eb3-412">The process takes the -TargetDeliveryDomain value passed into the move command, then checks for a matching proxy for that domain on the target side.</span></span> <span data-ttu-id="27eb3-413">Если найдено совпадение, для параметра ExternalEmailAddress (объект targetAddress) в преобразованном почтовом ящике (теперь MailUser) используется соответствующий proxyAddress.</span><span class="sxs-lookup"><span data-stu-id="27eb3-413">When we find a match, the matching proxyAddress is used to set the ExternalEmailAddress (targetAddress) on the converted mailbox (now MailUser) object.</span></span>
 
<span data-ttu-id="27eb3-414">**Как изменяется разрешение для почтового ящика?**</span><span class="sxs-lookup"><span data-stu-id="27eb3-414">**How do mailbox permissions transition?**</span></span>

<span data-ttu-id="27eb3-415">Разрешения почтового ящика включают отправку от имени пользователя и доступа к почтовому ящику:</span><span class="sxs-lookup"><span data-stu-id="27eb3-415">Mailbox permissions include Send on Behalf of and Mailbox Access:</span></span> 

- <span data-ttu-id="27eb3-416">Отправить от имени (AD: publicDelegates) — хранит различающееся имя получателей, имеющих доступ к почтовому ящику пользователя в качестве представителя.</span><span class="sxs-lookup"><span data-stu-id="27eb3-416">Send On Behalf Of (AD:publicDelegates) stores the DN of recipients with access to a user’s mailbox as a delegate.</span></span> <span data-ttu-id="27eb3-417">Это значение хранится в Active Directory, и в настоящее время не перемещается в процессе переноса почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="27eb3-417">This value is stored in Active Directory and currently does not move as part of the mailbox transition.</span></span> <span data-ttu-id="27eb3-418">Если для исходного почтового ящика задан publicDelegates, необходимо будет переметить publicDelegates в целевом почтовом ящике после завершения преобразования MEU в целевую среду с помощью `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` команды.</span><span class="sxs-lookup"><span data-stu-id="27eb3-418">If the source mailbox has publicDelegates set, you will need to restamp the publicDelegates on the target Mailbox once the MEU to Mailbox conversion completes in the target environment using the `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` command.</span></span> 
 
- <span data-ttu-id="27eb3-419">Разрешения почтового ящика, хранящиеся в почтовом ящике, будут перемещаться вместе с почтовым ящиком при перемещении участника и делегата в целевую систему.</span><span class="sxs-lookup"><span data-stu-id="27eb3-419">Mailbox Permissions that are stored in the mailbox will move with the mailbox when both the principal and the delegate are moved to the target system.</span></span> <span data-ttu-id="27eb3-420">Например, пользователю TestUser_7 предоставляется FullAccess TestUser_8 почтовых ящиков в SourceCompany.onmicrosoft.com клиента.</span><span class="sxs-lookup"><span data-stu-id="27eb3-420">For example, the user TestUser_7 is granted FullAccess to the mailbox TestUser_8 in the tenant SourceCompany.onmicrosoft.com.</span></span> <span data-ttu-id="27eb3-421">После завершения перемещения почтового ящика в TargetCompany.onmicrosoft.com те же разрешения настраиваются в целевом каталоге.</span><span class="sxs-lookup"><span data-stu-id="27eb3-421">After the mailbox move completes to TargetCompany.onmicrosoft.com, the same permissions are set up in the target directory.</span></span> <span data-ttu-id="27eb3-422">Примеры использования *Get – MailboxPermission* для TestUser_7 в исходном и целевом клиентах показаны ниже.</span><span class="sxs-lookup"><span data-stu-id="27eb3-422">Examples using *Get-MailboxPermission* for TestUser_7 in both source and target tenants are shown below.</span></span> <span data-ttu-id="27eb3-423">Командлеты Exchange имеют соответствующие исходные и целевые настройки.</span><span class="sxs-lookup"><span data-stu-id="27eb3-423">Exchange cmdlets are prefixed with source and target accordingly.</span></span> 
 
<span data-ttu-id="27eb3-424">Ниже приведен пример выходных данных разрешения для почтового ящика перед перемещением.</span><span class="sxs-lookup"><span data-stu-id="27eb3-424">Here's an example of the output of the mailbox permission before a move.</span></span> 

```powershell
PS C:\DEMO Get-SourceMailboxPermission testuser_7 |ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       False
TestUser_8@SourceCompany.onmicrosoft.com         {FullAccess}                                                            False       False....
```
<span data-ttu-id="27eb3-425">Ниже приведен пример выходных данных разрешения почтового ящика после перемещения.</span><span class="sxs-lookup"><span data-stu-id="27eb3-425">Here's an example of the output of the mailbox permission after the move.</span></span> 

```powershell
C:\DEMO> Get-TargetMailboxPermission testuser_7 | ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       FalseTestUser_8@TargetCompany.onmicrosoft.com         {FullAccess}                                                            False       False
```
 
> [!Note]
> <span data-ttu-id="27eb3-426">Разрешения для почтового ящика и календаря между клиентами не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="27eb3-426">Cross-tenant mailbox and calendar permissions are NOT supported.</span></span> <span data-ttu-id="27eb3-427">Вы должны систематизировать субъекты и делегаты в консолидированных пакетах перемещения, чтобы эти подключенные почтовые ящики одновременно перемещались из исходного клиента.</span><span class="sxs-lookup"><span data-stu-id="27eb3-427">You must organize principals and delegates into consolidated move batches so that these connected mailboxes are transitioned at the same time from the source tenant.</span></span> 
 
## <a name="known-issues"></a><span data-ttu-id="27eb3-428">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="27eb3-428">Known issues</span></span> 

-  <span data-ttu-id="27eb3-429">**Ошибка: не удается перенести автоматически развернутые архивы.**</span><span class="sxs-lookup"><span data-stu-id="27eb3-429">**Issue: Auto Expanded archives cannot be migrated.**</span></span> <span data-ttu-id="27eb3-430">Функция миграции между клиентами поддерживает миграцию основного и архивного почтового ящика для определенного пользователя.</span><span class="sxs-lookup"><span data-stu-id="27eb3-430">The cross-tenant migration feature support migrations of the primary mailbox and archive mailbox for a specific user.</span></span> <span data-ttu-id="27eb3-431">Если у пользователя в источнике есть автоматически развернутый Архив (то есть более одного архивного почтового ящика), то компонент не сможет перенести дополнительные архивы.</span><span class="sxs-lookup"><span data-stu-id="27eb3-431">If the user in the source however has an auto expanded archive – meaning more than one archive mailbox, the feature is unable to migrate the additional archives.</span></span>

- <span data-ttu-id="27eb3-432">**Вопрос: Cloud Маилусерс с proxyAddress, не принадлежащим владельцу, MRS перемещает фон.**</span><span class="sxs-lookup"><span data-stu-id="27eb3-432">**Issue: Cloud MailUsers with non-owned smtp proxyAddress block MRS moves background.**</span></span> <span data-ttu-id="27eb3-433">При создании объектов MailUser целевых клиентов необходимо убедиться, что все SMTP-адреса прокси принадлежат целевой организации клиента.</span><span class="sxs-lookup"><span data-stu-id="27eb3-433">When creating target tenant MailUser objects, you must ensure that all SMTP proxy addresses belong to the target tenant organization.</span></span> <span data-ttu-id="27eb3-434">Если proxyAddress SMTP существует на целевом почтовом пользователе, который не принадлежит локальному клиенту, преобразование MailUser в почтовый ящик запрещено.</span><span class="sxs-lookup"><span data-stu-id="27eb3-434">If an SMTP proxyAddress exists on the target mail user that does not belong to the local tenant, the conversion of the MailUser to Mailbox is prevented.</span></span> <span data-ttu-id="27eb3-435">Это связано с обеспечением гарантии того, что объекты почтовых ящиков могут отправлять почту только из доменов, для которых клиент является полномочным (домены, заявленные клиентом):</span><span class="sxs-lookup"><span data-stu-id="27eb3-435">This is due to our assurance that mailbox objects can only send mail from domains for which the tenant is authoritative (domains claimed by the tenant):</span></span> 
- 
   - <span data-ttu-id="27eb3-436">При синхронизации пользователей из локальной системы с помощью Azure AD Connect вы предоставляете локальные объекты MailUser с ExternalEmailAddress, указывающие на исходного клиента, где находится почтовый ящик (laran@contoso \. onmicrosoft.com), и вы отписываете PrimarySMTPAddress как домен, находящийся в целевом клиенте ( \. Lara.Newton@northwind com).</span><span class="sxs-lookup"><span data-stu-id="27eb3-436">When you sync users from on-premises using Azure AD Connect, you provision on-premises MailUser objects with ExternalEmailAddress pointing to the source tenant where the mailbox exists (laran@contoso\.onmicrosoft.com) and you stamp the PrimarySMTPAddress as a domain that resides in the target tenant (Lara.Newton@northwind\.com).</span></span> <span data-ttu-id="27eb3-437">Эти значения синхронизируются с клиентом, и подготавливается подготовка к миграции для соответствующего пользователя почты.</span><span class="sxs-lookup"><span data-stu-id="27eb3-437">These values sync down to the tenant and an appropriate mail user is provisioned and ready for migration.</span></span> <span data-ttu-id="27eb3-438">Пример объекта показан здесь.</span><span class="sxs-lookup"><span data-stu-id="27eb3-438">An example object is shown here.</span></span>
     ```powershell
     target/AADSynced user] PS C> Get-MailUser laran | select ExternalEmailAddress, EmailAddresses   
     ExternalEmailAddress               EmailAddresses 
     --------------------               -------------- 
     SMTP:laran@contoso.onmicrosoft.com {SMTP:lara.newton@northwind.com} 
     ```

   > [!Note]
   > <span data-ttu-id="27eb3-439">В массиве EmailAddresses/proxyAddresses *отсутствует* *\. com-адрес contoso. onmicrosoft* .</span><span class="sxs-lookup"><span data-stu-id="27eb3-439">The *contoso.onmicrosoft\.com* address is *not* present in the EmailAddresses/proxyAddresses array.</span></span>

- <span data-ttu-id="27eb3-440">**Вопрос: объекты MailUser с "внешними" основными SMTP-адресами изменены или сброшены на "внутренние" затребованные домены компании**</span><span class="sxs-lookup"><span data-stu-id="27eb3-440">**Issue: MailUser objects with “external” primary SMTP addresses are modified/reset to “internal” company claimed domains**</span></span>

   <span data-ttu-id="27eb3-441">Объекты MailUser — это указатели на нелокальные почтовые ящики.</span><span class="sxs-lookup"><span data-stu-id="27eb3-441">MailUser objects are pointers to non-local mailboxes.</span></span> <span data-ttu-id="27eb3-442">В случае переноса почтовых ящиков между клиентами мы используем объекты MailUser для представления исходного почтового ящика (с точки зрения целевой организации) или целевого почтового ящика (с точки зрения исходной организации).</span><span class="sxs-lookup"><span data-stu-id="27eb3-442">In the case for cross-tenant mailbox migrations, we use MailUser objects to represent either the source mailbox (from the target organization’s perspective) or target mailbox (from the source organization’s perspective).</span></span> <span data-ttu-id="27eb3-443">Маилусерс будет иметь ExternalEmailAddress (targetAddress), указывающую на SMTP-адрес реального почтового ящика (Прокситест \@ fabrikam \. onmicrosoft.com) и адрес примарисмтп, который представляет ОТОБРАЖАЕМЫЙ SMTP-адрес пользователя почтового ящика в каталоге.</span><span class="sxs-lookup"><span data-stu-id="27eb3-443">The MailUsers will have an ExternalEmailAddress (targetAddress) that points to the smtp address of the actual mailbox (ProxyTest\@fabrikam\.onmicrosoft.com) and primarySMTP address that represents the displayed SMTP address of the mailbox user in the directory.</span></span> <span data-ttu-id="27eb3-444">В некоторых организациях основной SMTP-адрес отображается как внешний SMTP-адрес, а не как адрес, принадлежащий или проверенный локальным клиентом (например, fabrikam.com, а не как contoso.com).</span><span class="sxs-lookup"><span data-stu-id="27eb3-444">Some organizations choose to display the primary SMTP address as an external SMTP address, not as an address owned/verified by the local tenant (such as fabrikam.com rather than as contoso.com).</span></span>  <span data-ttu-id="27eb3-445">Однако после применения объекта плана службы Exchange к MailUser через операции лицензирования основной SMTP-адрес изменяется для отображения в качестве домена, проверенного локальной организацией (contoso.com).</span><span class="sxs-lookup"><span data-stu-id="27eb3-445">However, once an Exchange service plan object is applied to the MailUser via licensing operations, the primary SMTP address is modified to show as a domain verified by the local organization (contoso.com).</span></span> <span data-ttu-id="27eb3-446">Существует две потенциальные причины:</span><span class="sxs-lookup"><span data-stu-id="27eb3-446">There are two potential reasons:</span></span>
   
   - <span data-ttu-id="27eb3-447">Когда любой план служб Exchange применяется к MailUser, процесс Azure AD начинает применять очистку прокси-сервера, чтобы локальная организация не могла отправлять почту, подделывать или почтовые сообщения от другого клиента.</span><span class="sxs-lookup"><span data-stu-id="27eb3-447">When any Exchange service plan is applied to a MailUser, the Azure AD process starts to enforce proxy scrubbing to ensure that the local organization is not able to send mail out, spoof, or mail from another tenant.</span></span> <span data-ttu-id="27eb3-448">Любой SMTP-адрес на объекте получателя с этими планами служб будет удален, если адрес не будет проверен локальной организацией.</span><span class="sxs-lookup"><span data-stu-id="27eb3-448">Any SMTP address on a recipient object with these service plans will be removed if the address is not verified by the local organization.</span></span> <span data-ttu-id="27eb3-449">Как и в примере, \. домен com ФАБИКАМ не проверяется \. клиентом Contoso onmicrosoft.com, поэтому очистка удаляет домен компании Fabrikam \. .</span><span class="sxs-lookup"><span data-stu-id="27eb3-449">As is the case in the example, the Fabikam\.com domain is NOT verified by the contoso\.onmicrosoft.com tenant, so the scrubbing removes that fabrikam\.com domain.</span></span> <span data-ttu-id="27eb3-450">Если вы хотите оставить этот внешний домен в MailUser до миграции или после миграции, необходимо изменить процессы миграции для удаления лицензий после завершения перемещения или до перемещения, чтобы убедиться, что применены ожидаемые внешние фирменные символики для пользователей.</span><span class="sxs-lookup"><span data-stu-id="27eb3-450">If you wish to persist these external domain on MailUser, either before the migration or after migration, you need to alter your migration processes to strip licenses after the move completes or before the move to ensure that the users have the expected external branding applied.</span></span> <span data-ttu-id="27eb3-451">Необходимо убедиться, что объект почтового ящика правильно лицензирован, чтобы не повлиять на почтовую службу.</span><span class="sxs-lookup"><span data-stu-id="27eb3-451">You will need to ensure that the mailbox object is properly licensed to not affect mail service.</span></span><br/><br/><span data-ttu-id="27eb3-452">Пример скрипта для удаления планов обслуживания на MailUser в \. клиенте Contoso onmicrosoft.com показан здесь.</span><span class="sxs-lookup"><span data-stu-id="27eb3-452">An example script to remove the service plans on a MailUser in the Contoso\.onmicrosoft.com tenant is shown here.</span></span>

    ```powershell
    $LO = New-MsolLicenseOptions -AccountSkuId "contoso:ENTERPRISEPREMIUM" DisabledPlans 
    "LOCKBOX_ENTERPRISE","EXCHANGE_S_ENTERPRISE","INFORMATION_BARRIERS","MIP_S_CLP2","
    MIP_S_CLP1","MYANALYTICS_P2","EXCHANGE_ANALYTICS","EQUIVIO_ANALYTICS","THREAT_INTE
    LLIGENCE","PAM_ENTERPRISE","PREMIUM_ENCRYPTION" 
    Set-MsolUserLicense -UserPrincipalName proxytest@contoso.com LicenseOptions $lo 
    ```

       <span data-ttu-id="27eb3-453">Результаты, указанные в наборе назначенных Сервицепланс, показаны здесь.</span><span class="sxs-lookup"><span data-stu-id="27eb3-453">Results in the set of ServicePlans assigned are shown here.</span></span>

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
 
       <span data-ttu-id="27eb3-454">PrimarySMTPAddress пользователя больше не очищен.</span><span class="sxs-lookup"><span data-stu-id="27eb3-454">The user’s PrimarySMTPAddress is no longer scrubbed.</span></span> <span data-ttu-id="27eb3-455">Домен fabrikam.com не принадлежит клиенту contoso.onmicrosoft.com и будет храниться в качестве основного SMTP-адреса, показанного в каталоге.</span><span class="sxs-lookup"><span data-stu-id="27eb3-455">The fabrikam.com domain is not owned by the contoso.onmicrosoft.com tenant and will persist as the primary SMTP address shown in the directory.</span></span>

       <span data-ttu-id="27eb3-456">Пример:</span><span class="sxs-lookup"><span data-stu-id="27eb3-456">Here is an example.</span></span>

    ```powershell
    get-recipient proxytest | ft -a userprin*, primary*, external*   
    PrimarySmtpAddress        ExternalDirectoryObjectId               ExternalEmailAddress 
    ------------------        -------------------------               -------------------- 
    proxytest@fabrikam.com    e2513482-1d5b-4066-936a-cbc7f8f6f817    SMTP:proxytest@fabrikam.com 
    ```

   - <span data-ttu-id="27eb3-457">Если для МсексчремотереЦипиенттипе задано значение 8 (Депровисионмаилбокс), для локальных Маилусерс, которые переносятся в Целевой клиент, логика очистки прокси в Azure удалит ненадлежащие домены и переустановит Примарисмтп в домен, принадлежащий к домену.</span><span class="sxs-lookup"><span data-stu-id="27eb3-457">When msExchRemoteRecipientType is set to 8 (DeprovisionMailbox), for on-premises MailUsers that are migrated to the target tenant, the proxy scrubbing logic in Azure will remove nonowned domains and reset the primarySMTP to an owned domain.</span></span> <span data-ttu-id="27eb3-458">При очистке МсексчремотереЦипиенттипе в локальной среде MailUser логика очистки прокси-серверов больше не применяется.</span><span class="sxs-lookup"><span data-stu-id="27eb3-458">By clearing msExchRemoteRecipientType in the on-premises MailUser, the proxy scrub logic no longer applies.</span></span> <br/><br><span data-ttu-id="27eb3-459">Ниже приведен полный набор возможных планов обслуживания, включающих Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="27eb3-459">Below is the full set of possible Service Plans that include Exchange Online.</span></span>

   | <span data-ttu-id="27eb3-460">Имя</span><span class="sxs-lookup"><span data-stu-id="27eb3-460">Name</span></span>                                              |
   |---------------------------------------------------|
   | <span data-ttu-id="27eb3-461">Расширенное хранилище данных обнаружения электронных данных (500 Гбайт)</span><span class="sxs-lookup"><span data-stu-id="27eb3-461">Advanced eDiscovery Storage (500GB)</span></span>               |
   | <span data-ttu-id="27eb3-462">Защищенное хранилище данных клиента</span><span class="sxs-lookup"><span data-stu-id="27eb3-462">Customer Lockbox</span></span>                                  |
   | <span data-ttu-id="27eb3-463">Защита от потери данных</span><span class="sxs-lookup"><span data-stu-id="27eb3-463">Data Loss Prevention</span></span>                              |
   | <span data-ttu-id="27eb3-464">Службы клиентской лицензии Exchange Enterprise (EOP, DLP)</span><span class="sxs-lookup"><span data-stu-id="27eb3-464">Exchange Enterprise CAL Services (EOP, DLP)</span></span>       |
   | <span data-ttu-id="27eb3-465">Основные сведения о Exchange</span><span class="sxs-lookup"><span data-stu-id="27eb3-465">Exchange Essentials</span></span>                               |
   | <span data-ttu-id="27eb3-466">Exchange Foundation</span><span class="sxs-lookup"><span data-stu-id="27eb3-466">Exchange Foundation</span></span>                               |
   | <span data-ttu-id="27eb3-467">Exchange Online (P1)</span><span class="sxs-lookup"><span data-stu-id="27eb3-467">Exchange Online (P1)</span></span>                              |
   | <span data-ttu-id="27eb3-468">Exchange Online (план 1)</span><span class="sxs-lookup"><span data-stu-id="27eb3-468">Exchange Online (Plan 1)</span></span>                          |
   | <span data-ttu-id="27eb3-469">Exchange Online (план 2)</span><span class="sxs-lookup"><span data-stu-id="27eb3-469">Exchange Online (Plan 2)</span></span>                          |
   | <span data-ttu-id="27eb3-470">Архивация на базе Exchange Online для Exchange Online</span><span class="sxs-lookup"><span data-stu-id="27eb3-470">Exchange Online Archiving for Exchange Online</span></span>     |
   | <span data-ttu-id="27eb3-471">Архивация на базе Exchange Online для Exchange Server</span><span class="sxs-lookup"><span data-stu-id="27eb3-471">Exchange Online Archiving for Exchange Server</span></span>     |
   | <span data-ttu-id="27eb3-472">Неактивные пользовательские надстройки Exchange Online</span><span class="sxs-lookup"><span data-stu-id="27eb3-472">Exchange Online Inactive User Add-on</span></span>              |
   | <span data-ttu-id="27eb3-473">Базовая подписка на Exchange Online</span><span class="sxs-lookup"><span data-stu-id="27eb3-473">Exchange Online Kiosk</span></span>                             |
   | <span data-ttu-id="27eb3-474">Exchange Online с поддержкой нескольких регионов</span><span class="sxs-lookup"><span data-stu-id="27eb3-474">Exchange Online Multi-Geo</span></span>                         |
   | <span data-ttu-id="27eb3-475">Exchange Online (план 1)</span><span class="sxs-lookup"><span data-stu-id="27eb3-475">Exchange Online Plan 1</span></span>                            |
   | <span data-ttu-id="27eb3-476">POP Exchange Online</span><span class="sxs-lookup"><span data-stu-id="27eb3-476">Exchange Online POP</span></span>                               |
   | <span data-ttu-id="27eb3-477">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="27eb3-477">Exchange Online Protection</span></span>                        |
   | <span data-ttu-id="27eb3-478">Препятствия для информации</span><span class="sxs-lookup"><span data-stu-id="27eb3-478">Information Barriers</span></span>                              |
   | <span data-ttu-id="27eb3-479">Защита данных для Office 365 — Premium</span><span class="sxs-lookup"><span data-stu-id="27eb3-479">Information Protection for Office 365 - Premium</span></span>   |
   | <span data-ttu-id="27eb3-480">Защита данных для Office 365 — Standard</span><span class="sxs-lookup"><span data-stu-id="27eb3-480">Information Protection for Office 365 - Standard</span></span>  |
   | <span data-ttu-id="27eb3-481">Аналитические сведения по MyAnalytics</span><span class="sxs-lookup"><span data-stu-id="27eb3-481">Insights by MyAnalytics</span></span>                           |
   | <span data-ttu-id="27eb3-482">Расширенный аудит Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="27eb3-482">Microsoft 365 Advanced Auditing</span></span>                   |
   | <span data-ttu-id="27eb3-483">Microsoft Bookings</span><span class="sxs-lookup"><span data-stu-id="27eb3-483">Microsoft Bookings</span></span>                                |
   | <span data-ttu-id="27eb3-484">Microsoft Business Center</span><span class="sxs-lookup"><span data-stu-id="27eb3-484">Microsoft Business Center</span></span>                         |
   | <span data-ttu-id="27eb3-485">Microsoft MyAnalytics (полнофункциональная версия)</span><span class="sxs-lookup"><span data-stu-id="27eb3-485">Microsoft MyAnalytics (Full)</span></span>                      |
   | <span data-ttu-id="27eb3-486">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="27eb3-486">Office 365 Advanced eDiscovery</span></span>                    |
   | <span data-ttu-id="27eb3-487">Защитник Майкрософт для Office 365 (план 1)</span><span class="sxs-lookup"><span data-stu-id="27eb3-487">Microsoft Defender for Office 365 (Plan 1)</span></span>    |
   | <span data-ttu-id="27eb3-488">Защитник Майкрософт для Office 365 (план 2)</span><span class="sxs-lookup"><span data-stu-id="27eb3-488">Microsoft Defender for Office 365 (Plan 2)</span></span>    |
   | <span data-ttu-id="27eb3-489">Office 365 Privileged Access Management</span><span class="sxs-lookup"><span data-stu-id="27eb3-489">Office 365 Privileged Access Management</span></span>           |
   | <span data-ttu-id="27eb3-490">Расширенное шифрование в Office 365</span><span class="sxs-lookup"><span data-stu-id="27eb3-490">Premium Encryption in Office 365</span></span>                  |
    
