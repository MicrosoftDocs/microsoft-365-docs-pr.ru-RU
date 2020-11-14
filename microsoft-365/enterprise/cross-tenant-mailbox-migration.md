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
ms.openlocfilehash: 1e2624fea7a93013e4b4de2dd4ede4144000f075
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073087"
---
# <a name="cross-tenant-mailbox-migration-preview"></a>Миграция почтовых ящиков между клиентами (Предварительная версия)

Ранее, когда клиенту Exchange Online требовалось переместить почтовые ящики на другой клиент в той же службе Exchange Online, им придется полностью переносе их в локальную систему, а затем подключить их к новому клиенту. С помощью новой функции переноса почтовых ящиков между клиентами Администраторы клиентов в исходном и целевом клиентах могут перемещать почтовые ящики между клиентами с минимальной зависимостью от инфраструктуры в локальных системах. Это избавляет от необходимости переносе и встроенные почтовые ящики.

Как правило, при слиянии или дивеститурес необходимо иметь возможность перемещать пользователей и содержимое в новый клиент. Когда администратор целевого клиента выполняет перемещение, он называется перемещением по запросу, как в локальной среде для миграции в облако.

Передвижения почтовых ящиков Exchange с перекрестными клиентами полностью обслуживаются администраторами клиентов, используя общедоступные интерфейсы, которые могут быть написаны в сценариях с большим количеством рабочих процессов, необходимых для переноса пользователей в новую организацию. Администраторы могут использовать `New-MigrationBatch` командлеты, доступные через роль управления перемещением почтовых ящиков, для выполнения перемещения между клиентами. Процесс перемещения включает проверки авторизации клиента во время синхронизации и завершения работы почтовых ящиков. 
 
Миграция пользователей должна присутствовать в целевой системе Exchange Online Server в виде Маилусерс, помеченной с определенными атрибутами, чтобы включить перемещение между клиентами. Система не будет перемещаться для пользователей, которые не были настроены должным образом в целевом клиенте. 

По завершении перемещений почтовый ящик исходной системы преобразуется в MailUser, а объект targetAddress (показанный как ExternalEmailAddress в Exchange) помечаются адресом маршрутизации в целевом клиенте. Этот процесс оставляет устаревший MailUser в исходном клиенте и разрешает период совместной работы и маршрутизации почты. Когда бизнес-процессы разрешаются, клиент источника может удалить исходный MailUser или преобразовать их в почтовый контакт. 

Миграция почтовых ящиков Exchange между клиентами поддерживается только для клиентов в гибридной среде или в облаке, а также в любом сочетании этих двух способов.

В этой статье описывается процесс перемещения почтовых ящиков между клиентами и приводятся инструкции по подготовке исходных и целевых клиентов к перемещению контента. 

## <a name="preparing-source-and-target-tenants"></a>Подготовка исходных и целевых клиентов

Для функции переноса почтовых ящиков Exchange между клиентами требуется авторизация и область видимости для межклиентской миграции. С помощью решений Azure Enterprise и хранилища ключей Администраторы клиентов теперь могут управлять отправкой и областью миграции почтовых ящиков Exchange Online от одного клиента к другому. При перемещении почтовых ящиков между клиентами поддерживается модель приглашения и согласия, чтобы создать приложение Azure Active Directory (Azure AD), используемое для проверки подлинности между клиентом. Также требуются дополнительные компоненты, такие как связь организации и конечная точка миграции.

В этом разделе не приведены действия, необходимые для подготовки объектов пользователя MailUser в целевом каталоге, а также пример команды для подтверждения пакета миграции. Сведения о том, как [подготовить объекты конечного пользователя к миграции](#prepare-target-user-objects-for-migration) , можно найти в этой статье.

## <a name="prerequisites"></a>Предварительные условия

Для функции перемещения почтовых ящиков с несколькими клиентами требуется [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/basic-concepts) для создания приложения Azure с особым набором клиентов для безопасного хранения и доступа к сертификату или секрету, используемому для проверки подлинности и авторизации миграции почтовых ящиков от одного клиента к другому, удаляя любые требования для совместного использования сертификатов и секретов между клиентами. 

Прежде чем начать, убедитесь, что у вас есть необходимые разрешения для запуска скриптов развертывания, чтобы настроить Azure Key Vault, переместить приложение почтового ящика, конечную точку миграции EXO и связь организации EXO. Как правило, глобальный администратор имеет разрешение на выполнение всех действий по настройке.

Кроме того, перед запуском программы установки необходимы группы безопасности с включенной поддержкой почты в исходном клиенте. Эти группы используются для определения списка почтовых ящиков, которые могут перемещаться от источника к конечному клиенту (или иногда называются в качестве ресурса). Это позволяет администратору клиента системы ограничить или ограничить область применения определенного набора почтовых ящиков, которые необходимо переместить, предотвращая миграцию нежелательных пользователей. Вложенные группы не поддерживаются.

Кроме того, вам потребуется общаться с доверенной компанией-партнером (с помощью которой будут перемещаться почтовые ящики), чтобы получить идентификатор клиента Microsoft 365. Этот идентификатор клиента используется в поле "связь организации" `DomainName` .

Чтобы получить идентификатор клиента для подписки, войдите в центр администрирования Microsoft 365 и перейдите по адресу [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) . Щелкните значок "Копировать" для свойства "идентификатор клиента", чтобы скопировать его в буфер обмена.

Ниже показано, как работает процесс.

:::image type="content" source="../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png" alt-text="Подготовка клиента к миграции почтовых ящиков.":::

[Ознакомьтесь с более крупной версией этого изображения](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png).

<!--
[![Tenant preparation for mailbox migration](../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)
--> 

### <a name="prepare-tenants"></a>Подготовка клиентов

На высоком уровне при выполнении сценариев установки выполняются следующие действия по настройке.

Подготовка целевого клиента:

1. Если не указана существующая группа ресурсов Azure, создается новая (SCRIPT).
2. Если существующее ключевое хранилище не предоставлено, создается новый объект (SCRIPT).
3. Для приложения переноса почтовых ящиков Office 365 Exchange Online создается новая политика доступа (сценарий).
4. Создается новый сертификат (или, если он указан) для хранения секрета для приложения переноса (сценария).
5. Создается новое приложение Azure AD (SCRIPT).
6. Сертификат/секрет отправляется в приложение миграции (скрипт).
7. Разрешения на миграцию почтовых ящиков назначаются приложению (СЦЕНАРию).
8. Скрипт развертывания приостанавливается до тех пор, пока целевой администратор не отправил в собственное приложение (сценарий).
9. Целевой администратор клиента отправляется на разрешения, предоставленные приложению (вручную).
10. Связь организации создается для целевого клиента (сценария).
11. Создается конечная точка миграции для извлечения почтовых ящиков на целевой клиент (сценарий).

Подготовка исходного клиента:

1. Администратор исходного клиента принимает согласие на приглашение приложения переноса почтовых ящиков от целевого клиента (вручную).
2. Администратор исходного клиента создает группу безопасности с включенной поддержкой почты в своем клиенте, чтобы включить список почтовых ящиков, разрешенных для перемещения приложением миграции (вручную).
3. В целевом клиенте создается связь организации, указывающая на необходимость использования приложения переноса почтовых ящиков для проверки OAuth, чтобы принять запрос на перемещение (сценарий).

#### <a name="step-by-step-instructions-for-the-target-tenant-admin"></a>Пошаговые инструкции для администратора целевого клиента

1. Скачайте скрипт SetupCrossTenantRelationshipForTargetTenant.ps1 для установки целевого клиента из [репозитория GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview). 
2. Сохраните сценарий (SetupCrossTenantRelationshipForTargetTenant.ps1) на компьютере, с которого будет выполняться сценарий.
3. Создайте удаленное подключение PowerShell к конечному клиенту Exchange Online. Опять же, убедитесь, что у вас есть необходимые разрешения для запуска скриптов развертывания, чтобы настроить хранилище и сертификат Azure Key Vault, переместить приложение почтового ящика, конечную точку миграции EXO и связь организации EXO.
4. Измените каталог папки файлов на расположение скрипта или убедитесь, что сценарий в текущий момент сохранен в удаленном сеансе PowerShell.
5. Выполните скрипт со следующими параметрами и значениями.

    | Параметр | Значение | Обязательный или необязательный
    |---------------------------------------------|-----------------|--------------|
    | — Ресаурцетенантдомаин                       | Исходный домен клиента, например fabrikam \. onmicrosoft.com. | Обязательный |
    | — Ресаурцетенантадминемаил                   | Адрес электронной почты администратора исходного клиента. Это исходный администратор клиента, который будет отослано использовать приложение переноса почтовых ящиков, отправленное от целевого администратора. Это администратор, который будет получать приглашение на получение электронной почты для приложения. | Обязательный |
    | — Таржеттенантдомаин                         | Целевой домен клиента, например contoso \. onmicrosoft.com. | Обязательный |
    | — Ресаурцетенантид                           | Идентификатор исходной организации клиента (GUID). | Обязательный |
    | — SubscriptionId                             | Подписка на Azure, используемая для создания ресурсов. | Обязательный |
    | — ResourceGroup                              | Имя группы ресурсов Azure, которое содержит или будет содержать Key Vault. | Обязательный |
    | — Кэйваултнаме                               | Экземпляр Azure Key Vault, который будет хранить сертификат и секрет приложения переноса почтовых ящиков. | Обязательный |
    | — CertificateName                            | Имя сертификата при создании или поиске сертификата в ключе Vault. | Обязательный |
    | — CertificateSubject                         | Имя субъекта сертификата Azure Key Vault, например CN = contoso_fabrikam. | Обязательный |
    | — Ексистингаппликатионид                      | Приложение переноса почты, которое будет использоваться, если оно уже было создано. | Необязательный |
    | — Азуреапппермиссионс                        | Разрешения, которые необходимо предоставить для приложения переноса почтовых ящиков, например Exchange или MSGraph (Exchange для перемещения почтовых ящиков, MSGraph, чтобы использовать это приложение для отправки приглашения на согласие для клиента ресурсов). | Обязательный |
    | — Усеаппандцертженератедфорсендингинвитатион | Параметр для использования приложения, созданного для миграции, для отправки приглашения на предоставление разрешения на отправку приглашения для ссылки на администратора исходного клиента. Если этот параметр отсутствует, будет предложено ввести учетные данные конечного администратора для подключения к диспетчеру приглашений Azure и отправить приглашение в качестве целевого администратора. | Необязательный |
    | — Кэйваултаудитсторажеаккаунтнаме            | Учетная запись хранения, в которой будут храниться журналы аудита для основного хранилища. | Необязательный |
    | — Кэйваултаудитсторажересаурцеграуп          | Группа ресурсов, содержащая учетную запись хранения для хранения журналов аудита ключевых хранилищ. | Необязательный |
    ||||

6. Сценарий приостанавливает или предложит принять или подтвердить согласие на приложение миграции почтовых ящиков Exchange, созданное в ходе этого процесса. Пример:

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

7. URL-адрес будет отображаться в удаленном сеансе PowerShell. Скопируйте ссылку, предоставленную для вашего согласия клиента, и вставьте ее в веб-браузер.

8. Войдите с помощью учетных данных глобального администратора. Когда появится следующий экран, нажмите кнопку **принять**.

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-dialog.png" alt-text="Диалоговое окно &quot;принятие разрешений&quot;":::
    
9. Вернитесь к удаленному сеансу PowerShell и нажмите клавишу ВВОД, чтобы продолжить.

10. В сценарии будут настроены оставшиеся объекты программы установки. Пример:

    ```powershell
    Successfully sent invitation to admin@contoso.onmicrosoft.com
    Setting up exchange components on target tenant: fabrikam.onmicrosoft.com
    MigrationEndpoint created in fabrikam.onmicrosoft.com for target contoso.onmicrosoft.com
    Exchange setup complete. Migration endpoint details are available in $MigrationEndpoint variable
    ```

Настройка целевого администратора теперь завершена.

#### <a name="step-by-step-instructions-for-the-source-tenant-admin"></a>Пошаговые инструкции для администратора исходного клиента

1.  Войдите в свой почтовый ящик как параметр – Ресаурцетенантадминемаил, заданный целевым администратором во время установки. Найдите приглашение от целевого клиента и нажмите кнопку **Get Start** (начало работы).

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/invited-by-target-tenant.png" alt-text="Диалоговое окно с приглашением":::

2. Нажмите кнопку **принять** , чтобы принять приглашение.

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-accept.png" alt-text="Диалоговое окно для принятия разрешений":::

   > [!NOTE]
   > Если вы не получаете это сообщение электронной почты или не можете найти его, администратору целевого клиента предоставляется прямой URL-адрес, который можно предоставить для принятия приглашения. URL-адрес должен находиться в разделе в записи удаленного сеанса PowerShell администратора целевого клиента.

3. В центре администрирования Microsoft 365 или удаленном сеансе PowerShell создайте одну или несколько групп безопасности с включенной поддержкой почты, чтобы управлять списком почтовых ящиков, разрешенных целевым клиентом для получения (перемещения) из исходного клиента в Целевой клиент. Вам не нужно заполнять эту группу заранее, но для запуска процедуры установки (скрипт) необходимо предоставить хотя бы одну группу. Группы вложений не поддерживаются. 

4. Скачайте скрипт SetupCrossTenantRelationshipForTargetResource.ps1 для установки исходного клиента из репозитория GitHub [здесь](https://github.com/microsoft/cross-tenant/releases/tag/Preview). 

5. Создайте удаленное подключение PowerShell к исходному клиенту с разрешениями администратора Exchange. Разрешения глобального администратора не являются обязательными для настройки исходного клиента, только целевой клиент из-за процесса создания приложения Azure.

6. Измените каталог на расположение скрипта или убедитесь, что сценарий в текущий момент сохранен в удаленном сеансе PowerShell.

7. Выполните скрипт со следующими обязательными параметрами и значениями.

    | Параметр | Значение |
    |-----|------|
    | — Саурцемаилбоксмовепублишедскопес | Группа безопасности с включенной поддержкой почты, созданная исходным клиентом для удостоверений и почтовых ящиков, которые находятся в области для миграции. |
    | — Ресаурцетенантдомаин | Имя домена исходного клиента, например fabrikam \. onmicrosoft.com. |
    | — Таржеттенантдомаин | Имя конечного домена клиента, например contoso \. onmicrosoft.com. |
    | — ApplicationId | Идентификатор приложения Azure (GUID) приложения, используемого для миграции. Идентификатор приложения доступен на портале Azure (Azure AD, корпоративные приложения, имя приложения, идентификатор приложения) или включено в приглашение.  |
    | — Таржеттенантид | Идентификатор клиента целевого клиента. Например, идентификатор клиента Azure AD для \. клиента contoso onmicrosoft.com. |
    |||
    
    Пример:
    ```powershell
    SetupCrossTenantRelationshipForResourceTenant.ps1 -SourceMailboxMovePublishedScopes "MigScope","MyGroup" -ResourceTenantDomain contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ApplicationId sdf5e87sa-0753-dd88-ad35-c71a15cs8e44c -TargetTenantId 4sdkfo933-3904-sd93-bf9a-sdi39402834
    Exchange setup complete.

    ```

Настройка администратора источника теперь завершена.

### <a name="verify-setup"></a>Проверка программы установки

Убедитесь, что связи Организации в исходном и целевом клиентах и конечных точках миграции в целевом объекте успешно созданы.

#### <a name="target-tenant"></a>Целевой клиент

**Организационная связь**

Убедитесь, что объект связи Организации был создан и настроен с помощью этой команды.

```powershell
Get-OrganizationRelationship <source tenant organization name> | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability
```
Вот пример:

```powershell
PS C:\Users\Admin\scripts\T2TMovesV2> Get-OrganizationRelationship fabrikam_contoso_1178 | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability

Name                  : fabrikam_contoso_1123
DomainNames           : {sd0933me9f-9304-s903-s093-s093mfi903m4}
MailboxMoveEnabled    : True
MailboxMoveCapability : Inbound

```

**Конечная точка миграции**

Убедитесь, что объект конечной точки миграции был создан и настроен с помощью этой команды.

```powershell
Get-MigrationEndpoint "<fabrikam_contoso_1123> | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl
```

Пример:

```powershell
PS C:\Users\Admin\scripts\T2TMovesV2> Get-MigrationEndpoint fabrikam_contoso_1123 | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl


Identity             : fabrikam_contoso_1123
RemoteTenant         : contoso.onmicrosoft.com
ApplicationId        : s93mf93-das9-dq24-dq234-dada9033904m
AppSecretKeyVaultUrl : https://cross-tenantmyvaultformoves.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ae79348mx94384c288c5a3dfsioepw308

```

#### <a name="source-tenant"></a>Клиент источника

**Организационная связь**

Убедитесь, что объект связи Организации был создан и настроен с помощью этой команды.

```powershell
Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId
```
Пример:

```powershell
PS C:\Users\Admin\scripts\T2TMovesV2> Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId


Name                       : fabrikam_contoso_001
MailboxMoveEnabled         : True
MailboxMoveCapability      : RemoteOutbound
MailboxMovePublishedScopes : {MigScope}
OAuthApplicationId         : sd9890342-3243-3242-fe3w2-fsdade93m0
```

### <a name="move-mailboxes-back-to-the-original-source"></a>Перемещение почтовых ящиков обратно в исходный источник

Если почтовые ящики перемещаются обратно в исходный клиент, необходимо выполнить один и тот же набор действий и сценариев в новом исходном и новом целевом клиенте. Существующий объект связи Организации будет обновлен или добавлен, а не создан повторно.

## <a name="prepare-target-user-objects-for-migration"></a>Подготовка объектов целевого пользователя к миграции

Миграция пользователей должна присутствовать в целевом клиенте и в системе Exchange Online (как Маилусерс), помеченные определенными атрибутами, чтобы включить перемещение между клиентами. Система не будет перемещаться для пользователей, которые не были настроены должным образом в целевом клиенте. В следующем разделе описываются требования к объекту MailUser для целевого клиента.

### <a name="prerequisites"></a>Предварительные условия
  
В целевой организации необходимо убедиться в том, что в целевой организации установлены следующие объекты и атрибуты.  

1. Для всех почтовых ящиков, перемещаемых из исходной организации, необходимо подготовить объект MailUser в целевой организации: 
   - Целевой MailUser должен иметь эти атрибуты из исходного почтового ящика или назначаться новому объекту User:
      - ExchangeGUID (прямой Flow от источника к целевому) — GUID почтового ящика должен быть соответствующим. Процесс перемещения не будет продолжаться, если он отсутствует в целевом объекте. 
      - Свойств archiveguid (прямой Flow от источника к целевому) — GUID архива должен быть соответствующим. Процесс перемещения не будет продолжаться, если он отсутствует в целевом объекте. (Это необходимо только в том случае, если для исходного почтового ящика включена архивация). 
      - LegacyExchangeDN (Flow AS proxyAddress, "x500: <LegacyExchangeDN> ") — legacyExchangeDN должен присутствовать в целевом MailUser как x500: ProxyAddress. Процессы перемещения не будут продолжаться, если они отсутствуют в целевом объекте. 
      - UserPrincipalName — имя участника-пользователя будет выровнено с новым удостоверением или целевой компанией пользователя (например, user@northwindtraders.onmicrosoft.com). 
      - Основной SMTP-адрес SMTPAddress — основной SMTP-адрес, который будет выровнен по новой компании пользователя (например, user@northwind.com). 
      - TargetAddress/ExternalEmailAddress – MailUser будет ссылаться на текущий почтовый ящик пользователя, размещенный в исходном клиенте (например, user@contoso.onmicrosoft.com). При назначении этого значения убедитесь, что вы также назначаете PrimarySMTPAddress или это значение задает PrimarySMTPAddress, что приведет к сбоям перемещения. 
      - Невозможно добавить устаревшие SMTP-адреса прокси-сервера из исходного почтового ящика в целевой MailUser. Например, нельзя поддерживать contoso.com в MEU в объектах клиента fabrikam.onmicrosoft.com). Домены связаны только с одним клиентом Azure AD или Exchange Online.
 
    Пример **целевого** объекта MailUser:
 
    | Атрибут             | Значение                                                                                                                    |
    |-----------------------|--------------------------------------------------------------------------------------------------------------------------|
    | Alias                 | ларан                                                                                                                    |
    | RecipientType         | MailUser                                                                                                                 |
    | RecipientTypeDetails  | MailUser                                                                                                                 |
    | UserPrincipalName     | LaraN@northwintraders \. onmicrosoft.com                                                                                    |
    | PrimarySmtpAddress    | Лара \. Newton@northwind.com                                                                                                |
    | ExternalEmailAddress  | SMTP: LaraN@contoso \. onmicrosoft.com                                                                                       |
    | ExchangeGuid          | 1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8                                                                                     |
    | LegacyExchangeDN      | /o = First Organization/ou = административная группа Exchange                                                                   |
    |                       | (FYDIBOHF23SPDLT)/CN = Recipients/CN = 74e5385fce4b46d19006876949855035Lara                                                  |
    | EmailAddresses        | x500:/o = First Organization/OU = Exchange Administrative Group (FYDIBOHF23SPDLT)/CN = Recipients/CN = d11ec1a2cacd4f81858c8190  |
    |                       | 7273f1f9 — Лара                                                                                                            |
    |                       | SMTP: LaraN@northwindtraders \. onmicrosoft.com                                                                              |
    |                       | SMTP: Лара \. Newton@northwind.com                                                                                           |
    |||

   Пример **исходного** объекта почтового ящика:

   | Атрибут             | Значение                                                                    |
   |-----------------------|--------------------------------------------------------------------------|
   | Alias                 | ларан                                                                    |
   | RecipientType         | UserMailbox                                                              |
   | RecipientTypeDetails  | UserMailbox                                                              |
   | UserPrincipalName     | LaraN@contoso \. onmicrosoft.com                                            |
   | PrimarySmtpAddress    | Лара \. Newton@contoso.com                                                  |
   | ExchangeGuid          | 1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8                                     |
   | LegacyExchangeDN      | /o = First Organization/ou = административная группа Exchange                   |
   |                       | (FYDIBOHF23SPDLT)/CN = Recipients/CN = d11ec1a2cacd4f81858c81907273f1f9Lara  |
   | EmailAddresses        | SMTP: LaraN@contoso \. onmicrosoft.com 
   |                       | SMTP: Лара \. Newton@contoso.com          |
   |||

   - Дополнительные атрибуты могут быть включены в гибридную запись гибридной записи Exchange. В противном случае они должны быть включены. 
   - msExchBlockedSendersHash — записывает данные из клиентов в локальный каталог Active Directory и заблокировали данные отправителя в оперативном режиме.
   - msExchSafeRecipientsHash — записывает данные из клиентов в локальный каталог Active Directory и заблокировали данные отправителя в оперативном режиме.
   - msExchSafeSendersHash — записывает данные из клиентов в локальный каталог Active Directory и заблокировали данные отправителя в оперативном режиме.

2. Если исходный почтовый ящик находится в Литигатионхолд, а размер элементов для восстановления исходного почтового ящика превышает размер базы данных по умолчанию (30 ГБ), перемещение не будет продолжено, так как Целевая квота меньше размера исходного почтового ящика. Вы можете обновить целевой объект MailUser для переноса флагов почтовых ящиков ЕЛК из исходной среды в целевой, который запускает целевую систему для расширения квоты MailUser до 100 ГБ, позволяя перемещаться на целевую систему. Эти инструкции будут работать только для гибридного удостоверения, на котором выполняется Azure AD Connect, так как команды Метки ЕЛК не предоставляются администраторам клиента.

    >[!Note]
    > ПРИМЕР — БЕЗ ГАРАНТИЙ<br/>Этот сценарий предполагает подключение к исходному почтовому ящику (для получения исходных значений) и целевому локальному каталогу Active Directory (чтобы пометить объект ADUser). Если в источнике включено судебное восстановление или восстановление отдельных элементов, задайте это значение для целевой учетной записи.  При этом размер корзины конечного счета увеличится до 100 ГБ.

    ```powershell
    $ELCValue = 0 
    if ($source.LitigationHoldEnabled) {$ELCValue = $ELCValue + 8} if ($source.SingleItemRecoveryEnabled) {$ELCValue = $ELCValue + 16} if ($ELCValue -gt 0) {Set-ADUser -Server $domainController -Identity $destination.SamAccountName -Replace @{msExchELCMailboxFlags=$ELCValue}} 
    ```
3. Негибридные целевые клиенты могут изменить квоту в папке "элементы с возможностью восстановления" для Маилусерс перед переносом, выполнив следующую команду, чтобы включить удержание для судебного разбирательства в объекте MailUser и увеличить квоту до 100 ГБ: `Set-MailUser -EnableLitigationHoldForMigration $TRUE` . Примечание Это не будет работать для клиентов в гибридной конфигурации.

4. Пользователям в целевой организации необходимо лицензировать соответствующие подписки на Exchange Online, применимые для Организации. Вы можете применить лицензию при перемещении почтового ящика, но только после того, как Целевая MailUser будет правильно настроена с ExchangeGUID и прокси-адресами. Применение лицензии перед применением ExchangeGUID приведет к созданию нового почтового ящика, подготовленного в целевой организации. 

    > [!Note]
    > Если вы применяете лицензию для объекта почтового ящика или MailUser, то все типы SMTP proxyAddresses будут очищены, чтобы убедиться, что в массив Exchange EmailAddresses включены только проверенные домены. 

5. Необходимо убедиться, что в целевом MailUser нет предыдущего ExchangeGuid, которое не соответствует исходному ExchangeGuid. Это может произойти, если Целевая MEU была предварительно лицензирована для Exchange Online и подготовлена к работе с почтовым ящиком. Если целевая MailUser была предварительно лицензирована или ExchangeGuid, не соответствующая исходному ExchangeGuid, необходимо выполнить очистку облачного MEU. Для этих облачных Meu можно выполнить `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` команду. 

    > [!Caution]
    > Этот процесс является необратимым. Если объект имеет почтовый ящик softDeleted, его невозможно восстановить после этой точки. Однако при снятом флажке вы можете синхронизировать правильный ExchangeGuid с целевым объектом, и MRS будет подключаться к новому почтовому ящику исходного почтового ящика. (Ссылка на блог EHLO на новом параметре.) 
 
    Поиск объектов, которые были ранее почтовыми ящиками, с помощью этой команды.

    ```powershell
    Get-User <identity> | select Name, *recipient* | ft -a**.
    ```
    Пример: 

    ```powershell
    PS demo> get-user John@northwindtraders.com |select name, *recipient*| ft -AutoSize 
 
    Name        PreviousRecipientTypeDetails     RecipientType RecipientTypeDetails 
    ----       ---------------------------- ------------- -------------------- 
    John       UserMailbox                  MailUser      MailUser 
    ```   
 
    Очистка обратимо удаленного почтового ящика с помощью этой команды.

    ````
    Set-User <identity> -PermanentlyClearPreviousMailboxInfo
    ```` 

    Пример:

    ```powershell
    PS demo> Set-User John@northwindtraders.com -PermanentlyClearPreviousMailboxInfo Confirm 
    Are you sure you want to perform this action? 
    Delete all existing information about user “John@northwindtraders.com"?. This operation will clear existing values from Previous home MDB and Previous Mailbox GUID of the user. After deletion, reconnecting to the previous mailbox that existed in the cloud will not be possible and any content it had will be unrecoverable PERMANENTLY. 
    Do you want to continue? 
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"): Y 
    ```

## <a name="perform-mailbox-migrations"></a>Выполнение миграции почтовых ящиков

Миграция почтовых ящиков Exchange между клиентами отправляются в виде пакетов миграции, инициированных из целевого клиента. Это похоже на способ работы пакетов миграции при переходе с локальной организации Exchange на сервер Microsoft 365. 

### <a name="create-migration-batches"></a>Создание пакетов миграции

Ниже приведен пример командлета пакета миграции для запуска операций перемещения.

```powershell
New-MigrationBatch -Name T2Tbatch-testforignitedemo -SourceEndpoint target_source_7977 -CSVData ([System.IO.File]::ReadAllBytes('users.csv')) -Autostart -TargetDeliveryDomain targetformoves.onmicrosoft.com -AutoComplete

Identity                   Status  Type               TotalCount
--------                   ------  ----               ----------
T2Tbatch-testforignitedemo Syncing ExchangeRemoteMove 1

```

> [!Note]
> Адрес электронной почты в CSV-файле должен быть указан в целевом клиенте, а не в исходном клиенте.

Отправка пакетов миграции также поддерживается в новом центре администрирования Exchange при выборе параметра кросс-клиент.
 
#### <a name="update-on-premises-mailusers"></a>Обновление локальной Маилусерс

После перемещения почтовых ящиков из источника в целевой необходимо убедиться, что локальные почтовые пользователи, а также исходный и целевой серверы, обновлены с помощью новой объекта targetAddress. В примерах Таржетделиверидомаин используется в перемещении **contoso \. onmicrosoft.com**. Обновление почтовых пользователей с помощью этой targetAddress.
 
## <a name="frequently-asked-questions"></a>Вопросы и ответы
 
**Требуется обновление Ремотемаилбоксес в локальной системе после перемещения?**
 
Да, следует обновить объект targetAddress (RemoteRoutingAddress/ExternalEmailAddress) исходных локальных пользователей, когда почтовый ящик исходного клиента перемещается в Целевой клиент.  Так как маршрутизация почты может подписаться на ссылки между несколькими почтовыми пользователями, имеющими разные Таржетаддрессес, Поиск сведений о доступности для почтовых пользователей должен быть предназначен для расположения пользователя почтового ящика. Поиск сведений о доступности не выполняется для нескольких перенаправлений. 
 
**Переносить ли содержимое папки чата в Teams?** 

Нет, содержимое папки чата в Teams не переносит перекрестного клиента. 
 
**Как можно увидеть только перемещения, которые являются передвижениями между клиентами, а не с переносом и отключением?**

Используйте `-flags` параметр. Пример:

```powershell
Get-MoveRequest -Flags "CrossTenant" 
```
 
**Можно предоставить примеры сценариев для копирования атрибутов, используемых при тестировании?**

> [!Note]
> ПРИМЕР — БЕЗ ГАРАНТИЙ<br/>В этом сценарии предполагается подключение к исходному почтовому ящику (для получения исходных значений) и целевой локальной доменной службе Active Directory (чтобы пометить объект ADUser). Если в источнике включено судебное восстановление или восстановление отдельных элементов, задайте это значение для целевой учетной записи.  При этом размер корзины конечного счета увеличится до 100 ГБ.

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
**Как получить доступ к Outlook в день 1 после перемещения почтового ящика использования?**

Так как только один клиент может владеть доменом, бывший первичный SMTPAddress не будет связан с пользователем в целевом клиенте после завершения перемещения почтового ящика; только те домены, которые связаны с новым клиентом. Outlook использует новое имя участника-пользователя для проверки подлинности в службе, а профиль Outlook ожидает, что устаревший основной SMTPAddress будет сопоставлен с почтовым ящиком в целевой системе. Так как устаревший адрес не находится в целевой системе, подключается к профилю Outlook, чтобы найти только что перемещенный почтовый ящик. 

Для этого первоначального развертывания пользователям потребуется перестроить свой профиль с помощью нового имени участника-пользователя, основного SMTP-адреса и повторной синхронизации OST-контента. 

> [!Note]
> Запланируйте в соответствии с тем, как вы отпланируете завершить работу пользователей. Необходимо учитывать возможность использования и емкости сети при создании профилей клиентов Outlook, а также при загрузке последующих OST-файлов и файлов автономной адресной книги для клиентов. 
 
**Какие роли Exchange RBAC должны быть участниками группы для настройки или завершения перемещения между клиентами?**
 
При перемещении почтового ящика создается матрица ролей на основе предположения делегированных обязанностей. В настоящее время требуются две роли:  

- Первая роль предназначена для одноразовой установки, которая устанавливает авторизацию перемещения контента в клиентской или организационной границе. Так как перемещение данных из организационного контроля является важнейшим аспектом для всех компаний, мы выбрали наиболее назначенную роль администратора организации (Оргадмин). Эта роль должна изменять или настраивать новый OrganizationRelationship, определяющий параметр Маилбоксмовекапабилити в удаленной организации. Только Оргадмин может изменить параметр Маилбоксмовекапабилити, в то время как другие атрибуты Организатионрелатионхип могут управляться администратором федеративного общего доступа. 
 
- Роль выполнения фактических команд перемещения может быть делегирована функции нижнего уровня. Роли почтовых ящиков назначена возможность перемещения почтовых ящиков в организации или из нее с помощью `-RemoteTenant` параметра.  

**Как мы нацелены на то, какой SMTP-адрес выбран для targetAddress (Таржетделиверидомаин) в преобразованном почтовом ящике (для преобразования MailUser)?**
 
Почтовые ящики Exchange перемещаются с помощью MRS, создавая объект targetAddress в исходном почтовом ящике при преобразовании в MailUser, сопоставляя адрес электронной почты (proxyAddress) в целевом объекте. Процесс принимает значение-Таржетделиверидомаин, передаваемое в команду Move, а затем проверяет наличие на конечной стороне подходящего прокси-сервера для этого домена. Если найдено совпадение, для параметра ExternalEmailAddress (объект targetAddress) в преобразованном почтовом ящике (теперь MailUser) используется соответствующий proxyAddress.
 
**Как изменяется разрешение для почтового ящика?**

Разрешения почтового ящика включают отправку от имени пользователя и доступа к почтовому ящику: 

- Отправить от имени (AD: publicDelegates) — хранит различающееся имя получателей, имеющих доступ к почтовому ящику пользователя в качестве представителя. Это значение хранится в Active Directory, и в настоящее время не перемещается в процессе переноса почтовых ящиков. Если для исходного почтового ящика задан publicDelegates, необходимо будет переметить publicDelegates в целевом почтовом ящике после завершения преобразования MEU в целевую среду с помощью `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` команды. 
 
- Разрешения почтового ящика, хранящиеся в почтовом ящике, будут перемещаться вместе с почтовым ящиком при перемещении участника и делегата в целевую систему. Например, пользователю TestUser_7 предоставляется FullAccess TestUser_8 почтовых ящиков в SourceCompany.onmicrosoft.com клиента. После завершения перемещения почтового ящика в TargetCompany.onmicrosoft.com те же разрешения настраиваются в целевом каталоге. Примеры использования *Get – MailboxPermission* для TestUser_7 в исходном и целевом клиентах показаны ниже. Командлеты Exchange имеют соответствующие исходные и целевые настройки. 
 
Ниже приведен пример выходных данных разрешения для почтового ящика перед перемещением. 

```powershell
PS C:\DEMO Get-SourceMailboxPermission testuser_7 |ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       False
TestUser_8@SourceCompany.onmicrosoft.com         {FullAccess}                                                            False       False....
```
Ниже приведен пример выходных данных разрешения почтового ящика после перемещения. 

```powershell
C:\DEMO> Get-TargetMailboxPermission testuser_7 | ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       FalseTestUser_8@TargetCompany.onmicrosoft.com         {FullAccess}                                                            False       False
```
 
> [!Note]
> Разрешения для почтового ящика и календаря между клиентами не поддерживаются. Вы должны систематизировать субъекты и делегаты в консолидированных пакетах перемещения, чтобы эти подключенные почтовые ящики одновременно перемещались из исходного клиента. 
 
## <a name="known-issues"></a>Известные проблемы 

-  **Ошибка: не удается перенести автоматически развернутые архивы.** Функция миграции между клиентами поддерживает миграцию основного и архивного почтового ящика для определенного пользователя. Если у пользователя в источнике есть автоматически развернутый Архив (то есть более одного архивного почтового ящика), то компонент не сможет перенести дополнительные архивы.

- **Вопрос: Cloud Маилусерс с proxyAddress, не принадлежащим владельцу, MRS перемещает фон.** При создании объектов MailUser целевых клиентов необходимо убедиться, что все SMTP-адреса прокси принадлежат целевой организации клиента. Если proxyAddress SMTP существует на целевом почтовом пользователе, который не принадлежит локальному клиенту, преобразование MailUser в почтовый ящик запрещено. Это связано с обеспечением гарантии того, что объекты почтовых ящиков могут отправлять почту только из доменов, для которых клиент является полномочным (домены, заявленные клиентом): 
- 
   - При синхронизации пользователей из локальной системы с помощью Azure AD Connect вы предоставляете локальные объекты MailUser с ExternalEmailAddress, указывающие на исходного клиента, где находится почтовый ящик (laran@contoso \. onmicrosoft.com), и вы отписываете PrimarySMTPAddress как домен, находящийся в целевом клиенте ( \. Lara.Newton@northwind com). Эти значения синхронизируются с клиентом, и подготавливается подготовка к миграции для соответствующего пользователя почты. Пример объекта показан здесь.
     ```powershell
     target/AADSynced user] PS C> Get-MailUser laran | select ExternalEmailAddress, EmailAddresses   
     ExternalEmailAddress               EmailAddresses 
     --------------------               -------------- 
     SMTP:laran@contoso.onmicrosoft.com {SMTP:lara.newton@northwind.com} 
     ```

   > [!Note]
   > В массиве EmailAddresses/proxyAddresses *отсутствует* *\. com-адрес contoso. onmicrosoft* .

- **Вопрос: объекты MailUser с "внешними" основными SMTP-адресами изменены или сброшены на "внутренние" затребованные домены компании**

   Объекты MailUser — это указатели на нелокальные почтовые ящики. В случае переноса почтовых ящиков между клиентами мы используем объекты MailUser для представления исходного почтового ящика (с точки зрения целевой организации) или целевого почтового ящика (с точки зрения исходной организации). Маилусерс будет иметь ExternalEmailAddress (targetAddress), указывающую на SMTP-адрес реального почтового ящика (Прокситест \@ fabrikam \. onmicrosoft.com) и адрес примарисмтп, который представляет ОТОБРАЖАЕМЫЙ SMTP-адрес пользователя почтового ящика в каталоге. В некоторых организациях основной SMTP-адрес отображается как внешний SMTP-адрес, а не как адрес, принадлежащий или проверенный локальным клиентом (например, fabrikam.com, а не как contoso.com).  Однако после применения объекта плана службы Exchange к MailUser через операции лицензирования основной SMTP-адрес изменяется для отображения в качестве домена, проверенного локальной организацией (contoso.com). Существует две потенциальные причины:
   
   - Когда любой план служб Exchange применяется к MailUser, процесс Azure AD начинает применять очистку прокси-сервера, чтобы локальная организация не могла отправлять почту, подделывать или почтовые сообщения от другого клиента. Любой SMTP-адрес на объекте получателя с этими планами служб будет удален, если адрес не будет проверен локальной организацией. Как и в примере, \. домен com ФАБИКАМ не проверяется \. клиентом Contoso onmicrosoft.com, поэтому очистка удаляет домен компании Fabrikam \. . Если вы хотите оставить этот внешний домен в MailUser до миграции или после миграции, необходимо изменить процессы миграции для удаления лицензий после завершения перемещения или до перемещения, чтобы убедиться, что применены ожидаемые внешние фирменные символики для пользователей. Необходимо убедиться, что объект почтового ящика правильно лицензирован, чтобы не повлиять на почтовую службу.<br/><br/>Пример скрипта для удаления планов обслуживания на MailUser в \. клиенте Contoso onmicrosoft.com показан здесь.

    ```powershell
    $LO = New-MsolLicenseOptions -AccountSkuId "contoso:ENTERPRISEPREMIUM" DisabledPlans 
    "LOCKBOX_ENTERPRISE","EXCHANGE_S_ENTERPRISE","INFORMATION_BARRIERS","MIP_S_CLP2","
    MIP_S_CLP1","MYANALYTICS_P2","EXCHANGE_ANALYTICS","EQUIVIO_ANALYTICS","THREAT_INTE
    LLIGENCE","PAM_ENTERPRISE","PREMIUM_ENCRYPTION" 
    Set-MsolUserLicense -UserPrincipalName proxytest@contoso.com LicenseOptions $lo 
    ```

       Результаты, указанные в наборе назначенных Сервицепланс, показаны здесь.

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
 
       PrimarySMTPAddress пользователя больше не очищен. Домен fabrikam.com не принадлежит клиенту contoso.onmicrosoft.com и будет храниться в качестве основного SMTP-адреса, показанного в каталоге.

       Пример:

    ```powershell
    get-recipient proxytest | ft -a userprin*, primary*, external*   
    PrimarySmtpAddress        ExternalDirectoryObjectId               ExternalEmailAddress 
    ------------------        -------------------------               -------------------- 
    proxytest@fabrikam.com    e2513482-1d5b-4066-936a-cbc7f8f6f817    SMTP:proxytest@fabrikam.com 
    ```

   - Если для МсексчремотереЦипиенттипе задано значение 8 (Депровисионмаилбокс), для локальных Маилусерс, которые переносятся в Целевой клиент, логика очистки прокси в Azure удалит ненадлежащие домены и переустановит Примарисмтп в домен, принадлежащий к домену. При очистке МсексчремотереЦипиенттипе в локальной среде MailUser логика очистки прокси-серверов больше не применяется. <br/><br>Ниже приведен полный набор возможных планов обслуживания, включающих Exchange Online.

   | Имя                                              |
   |---------------------------------------------------|
   | Расширенное хранилище данных обнаружения электронных данных (500 Гбайт)               |
   | Защищенное хранилище                                  |
   | Защита от потери данных                              |
   | Службы клиентской лицензии Exchange Enterprise (EOP, DLP)       |
   | Основные сведения о Exchange                               |
   | Exchange Foundation                               |
   | Exchange Online (P1)                              |
   | Exchange Online (план 1)                          |
   | Exchange Online (план 2)                          |
   | Архивация на базе Exchange Online для Exchange Online     |
   | Архивация на базе Exchange Online для Exchange Server     |
   | Неактивные пользовательские надстройки Exchange Online              |
   | Базовая подписка на Exchange Online                             |
   | Exchange Online с поддержкой нескольких регионов                         |
   | Exchange Online (план 1)                            |
   | POP Exchange Online                               |
   | Exchange Online Protection                        |
   | Препятствия для информации                              |
   | Защита данных для Office 365 — Premium   |
   | Защита данных для Office 365 — Standard  |
   | Аналитические сведения по MyAnalytics                           |
   | Расширенный аудит Microsoft 365                   |
   | Microsoft Bookings                                |
   | Microsoft Business Center                         |
   | Microsoft MyAnalytics (полнофункциональная версия)                      |
   | Office 365 Advanced eDiscovery                    |
   | Защитник Майкрософт для Office 365 (план 1)    |
   | Защитник Майкрософт для Office 365 (план 2)    |
   | Office 365 Privileged Access Management           |
   | Расширенное шифрование в Office 365                  |
    
