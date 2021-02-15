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
# <a name="cross-tenant-mailbox-migration-preview"></a>Миграция почтовых ящиков между клиентами (предварительная версия)

Ранее, когда клиенту Exchange Online требовалось переместить почтовые ящики в другой клиент в той же службе Exchange Online, им придется полностью отключить их в локальной сети, а затем перенести их в новый клиент. С помощью новой функции миграции почтовых ящиков между клиентами администраторы клиентов в исходных и целевых клиентах могут перемещать почтовые ящики между клиентами с минимальными зависимостями инфраструктуры в своих локальной системе. Это устраняет необходимость в отходящих и входящих почтовых ящиках.

Как правило, во время слияния или инклюзности требуется возможность перемещения пользователей и контента в новый клиент. Когда администратор целевого клиента выполняет перемещение, оно называется перемещением pull, аналогично локальной миграции в облачную миграцию.

Перемещение почтовых ящиков Exchange между клиентами полностью поддерживается администраторами клиентов с помощью хорошо известных интерфейсов, которые могут быть запрошены в более крупные процессы, необходимые для перехода пользователей в новую организацию. Администраторы могут использовать для выполнения перемещения между арендаторами с помощью роли управления "Перемещение почтовых `New-MigrationBatch` ящиков". Процесс перемещения включает проверки авторизации клиента во время синхронизации и finalization почтового ящика. 
 
Переносимые пользователи должны присутствовать в системе целевого клиента Exchange Online как mailUsers, помеченные определенными атрибутами для обеспечения перемещения между арендаторами. Система не сможет двигаться для пользователей, которые неправильно настроены в целевом клиенте.  

После завершения перемещения исходный системный почтовый ящик преобразуется в MailUser, а адрес targetAddress (как ExternalEmailAddress в Exchange) помещен адресом маршрутации в целевой клиент. Этот процесс оставляет устаревший mailUser в клиенте-источнике и позволяет в течение определенного периода сосуществования и маршрутизации почты. Если бизнес-процессы позволяют, исходный клиент может удалить исходный сервер MailUser или преобразовать его в почтовый контакт. 

Миграция почтовых ящиков Exchange между клиентами поддерживается только для клиентов в гибридной или облачной службе или любой комбинации этих двух вариантов.

В этой статье описывается процесс перемещения почтовых ящиков между клиентами и данная статья содержит инструкции по подготовке исходных и целевых клиентов для перемещения содержимого.  

## <a name="preparing-source-and-target-tenants"></a>Подготовка исходных и целевых клиентов

Для функции миграции почтовых ящиков Exchange между клиентами требуется авторизация и разрешение для миграции между клиентами. С помощью решений для хранения данных azure Enterprise и Key Vault администраторы клиентов теперь могут управлять как авторизацией, так и разрешением миграции почтовых ящиков Exchange Online из одного клиента в другой. Перемещение почтовых ящиков между клиентами поддерживает модель приглашений и согласия на создание приложения Azure Active Directory (Azure AD), используемого для проверки подлинности между парой клиента. Также требуются дополнительные компоненты, такие как связь организации и конечная точка миграции.

В этом разделе не содержатся конкретные действия, необходимые для подготовки объектов пользователей MailUser в целевом каталоге, а также пример команды для отправки пакета миграции. Эти сведения [см. в подготовьте](#prepare-target-user-objects-for-migration) целевые объекты пользователей к миграции.

## <a name="prerequisites"></a>Предварительные условия

Для перемещения почтовых ящиков между клиентами [требуется,](https://docs.microsoft.com/azure/key-vault/basic-concepts) чтобы azure Key Vault использовал приложение Azure для безопасного хранения сертификата и секрета, используемого для проверки подлинности и авторизации миграции почтовых ящиков из одного клиента в другой, что позволяет удалить все требования к совместному хранимым сертификатам и секретам между клиентами. 

Перед началом работы убедитесь, что у вас есть необходимые разрешения для запуска сценариев развертывания для настройки хранилища Azure Key Vault, приложения перемещения почтовых ящиков, конечной точки миграции EXO и связи организации EXO. Как правило, глобальный администратор имеет разрешение на выполнение всех действий по настройке.

Кроме того, группы безопасности с включенной поддержкой почты в клиенте-источнике необходимы перед запуском программы установки. Эти группы используются для области списка почтовых ящиков, которые могут перемещаться из клиента источника (или иногда называется ресурсом) в целевой клиент. Это позволяет администратору клиента-источника ограничить или ограничить область действия определенного набора почтовых ящиков, которые необходимо перенести, не позволяя непреднамеренным пользователям перенести их. Вложенные группы не поддерживаются.

Вам также потребуется связаться с надежной партнерской компанией (с которой будут перемещены почтовые ящики), чтобы получить их ИД клиента Microsoft 365. Этот ИД клиента используется в поле "Связь `DomainName` организации".

Чтобы получить ИД клиента подписки, войдите в Центр администрирования Microsoft 365 и перейдите в [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) . Щелкните значок копирования свойства Tenant ID, чтобы скопировать его в буфер обмена.

Вот как работает этот процесс.

:::image type="content" source="../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png" alt-text="Подготовка клиента к миграции почтовых ящиков.":::

[См. более крупную версию этого изображения.](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)

<!--
[![Tenant preparation for mailbox migration](../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)
--> 

### <a name="prepare-tenants"></a>Подготовка клиентов

На высоком уровне при выполнении скриптов установки выполняются следующие действия по настройке.

Подготовьте целевой клиент:

1. Если существующая группа ресурсов Azure не предоставлена, создается новая группа (SCRIPT).
2. Если существующее хранилище Key Vault не предоставлено, создается новое хранилище (SCRIPT).
3. Для приложения миграции почтовых ящиков Office 365 Exchange Online (SCRIPT) создается новая политика доступа.
4. Создается новый сертификат (или существующий, если он указан) для снесения секрета в приложение миграции (SCRIPT).
5. Создается новое приложение Azure AD (SCRIPT).
6. Сертификат/секрет загружается в приложение миграции (SCRIPT).
7. Приложению (SCRIPT) назначены разрешения на миграцию почтовых ящиков.
8. Сценарий развертывания приостанавливовка до тех пор, пока целевой администратор не согласится на использование собственного приложения (SCRIPT).
9. Администратор целевого клиента соглашается на разрешения, которые даются приложению (MANUAL).
10. Создается связь организации с целевым клиентом (SCRIPT).
11. Создается конечная точка миграции, которая извлекает почтовые ящики в целевой клиент (SCRIPT).

Подготовьте исходный клиент:

1. Администратор клиента-источника принимает согласие на приглашение приложения миграции почтовых ящиков из целевого клиента (MANUAL).
2. Администратор клиента-источника создает в клиенте группу безопасности с включенной поддержкой почты, включаемую в список почтовых ящиков, которые могут быть перемещены приложением миграции (MANUAL).
3. Создается связь организации с целевым клиентом, указывав, что приложение миграции почтовых ящиков должно использоваться для проверки OAuth, чтобы принять запрос на перемещение (SCRIPT).

#### <a name="step-by-step-instructions-for-the-target-tenant-admin"></a>Пошаговая инструкция для администратора целевого клиента

1. Скачайте SetupCrossTenantRelationshipForTargetTenant.ps1 для настройки целевого клиента из [репозитория GitHub.](https://github.com/microsoft/cross-tenant/releases/tag/Preview) 
2. Сохраните сценарий (SetupCrossTenantRelationshipForTargetTenant.ps1) на компьютере, с которого будет выполняться сценарий.
3. Создайте удаленное подключение PowerShell к целевому клиенту Exchange Online. Опять же, убедитесь, что у вас есть необходимые разрешения для запуска сценариев развертывания для настройки хранилища и сертификата Azure Key Vault, приложения перемещения почтовых ящиков, конечной точки миграции EXO и связи организации EXO.
4. Измените каталог папки файлов на расположение сценария или убедитесь, что сценарий в данный момент сохранен в расположении, в настоящее время в сеансе Удаленной powerShell.
5. Запустите сценарий со следующими параметрами и значениями.

    | Параметр | Значение | Обязательный или необязательный
    |---------------------------------------------|-----------------|--------------|
    | -TargetTenantDomain                         | Целевой домен клиента, например contoso \. onmicrosoft.com. | Обязательна |
    | -ResourceTenantDomain                       | Исходный домен клиента, например fabrikam \. onmicrosoft.com. | Обязательна |
    | -ResourceTenantAdminEmail                   | Адрес электронной почты администратора клиента источника. Это исходный администратор клиента, который будет соглашаться на использование приложения миграции почтовых ящиков, отправленного от целевого администратора. Это администратор, который получит приглашение по электронной почте для приложения. | Обязательна |
    | -ResourceTenantId                           | Код организации-источника клиента (GUID). | Обязательна |
    | -SubscriptionId                             | Подписка Azure, используемая для создания ресурсов. | Обязательна |
    | -ResourceGroup                              | Имя группы ресурсов Azure, которая содержит хранилище Key Vault или будет содержать его. | Обязательна |
    | -KeyVaultName                               | Экземпляр Azure Key Vault, в который будет храниться сертификат/секрет приложения миграции почтовых ящиков. | Обязательна |
    | -CertificateName                            | Имя сертификата при создании или поиске сертификата в хранилище ключей. | Обязательна |
    | -CertificateSubject                         | Имя субъекта сертификата Azure Key Vault, например CN=contoso_fabrikam. | Обязательна |
    | -ExistingApplicationId                      | Приложение миграции почты, которое будет использовать, если приложение уже создано. | Необязательна |
    | -AzureAppPermissions                        | Разрешения, необходимые для приложения миграции почтовых ящиков, такие как Exchange или MSGraph (Exchange для перемещения почтовых ящиков, MSGraph для использования этого приложения для отправки приглашения ссылки на согласие в клиент ресурсов). | Обязательна |
    | -UseAppAndCertGeneratedForSendingInvitation | Параметр для использования приложения, созданного для миграции, который будет использоваться для отправки приглашения ссылки на согласие администратору клиента-источника. Если этот запрос не затмеен, учетные данные целевого администратора будут предложены подключиться к диспетчеру приглашений Azure и отправить приглашение от имени целевого администратора. | Необязательна |
    | -KeyVaultAuditStorageAccountName            | Учетная запись хранения, в которой будут храниться журналы аудита Хранилища Key Vault. | Необязательна |
    | -KeyVaultAuditStorageResourceGroup          | Группа ресурсов, которая содержит учетную запись хранения для хранения журналов аудита Key Vault. | Необязательна |
    ||||

    >[!Note]
    > Перед запуском сценариев убедитесь, что вы установили модуль Azure AD PowerShell. Действия по установке можно найти ![ ](https://docs.microsoft.com/powershell/azure/install-az-ps?view=azps-5.1.0) здесь

6. Сценарий приостановит и попросит вас принять или дать согласие приложению для миграции почтовых ящиков Exchange, созданному в ходе этого процесса. Пример:

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

7. URL-адрес будет отображаться в удаленном сеансе PowerShell. Скопируйте ссылку, предоставленную для согласия клиента, и вберите ее в веб-браузер.

8. Во входе с помощью учетных данных глобального администратора. При отобраии следующего экрана выберите **"Принять".**

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-dialog.png" alt-text="Диалоговое окно &quot;Принятие разрешений&quot;":::

9. Переключиться обратно в удаленный сеанс PowerShell и нажать ввод, чтобы продолжить.

10. Скрипт настроит оставшиеся объекты установки. Пример:

    ```powershell
    Successfully sent invitation to admin@contoso.onmicrosoft.com
    Setting up exchange components on target tenant: fabrikam.onmicrosoft.com
    MigrationEndpoint created in fabrikam.onmicrosoft.com for target contoso.onmicrosoft.com
    Exchange setup complete. Migration endpoint details are available in $MigrationEndpoint variable
    ```

Настройка целевого администратора завершена!

#### <a name="step-by-step-instructions-for-the-source-tenant-admin"></a>Пошаговая инструкция для администратора клиента-источника

1.  Во sign in to your mailbox as the -ResourceTenantAdminEmail specified by the target admin during their setup. Найдите приглашение по электронной почте из целевого клиента и выберите кнопку **"Начало** работы".

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/invited-by-target-tenant.png" alt-text="Вы были приглашены в диалоговое окно":::

2. Выберите **"Принять",** чтобы принять приглашение.

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-accept.png" alt-text="Диалоговое окно для принятие разрешений":::

   > [!NOTE]
   > Если вы не получили это сообщение электронной почты или не нашли его, администратору целевого клиента был предоставлен прямой URL-адрес, который можно дать вам принять приглашение. URL-адрес должен быть указан в записи удаленного сеанса PowerShell администратора целевого клиента.

3. В Центре администрирования Microsoft 365 или удаленном сеансе PowerShell создайте одну или несколько групп безопасности с включенной поддержкой почты, чтобы управлять списком почтовых ящиков, разрешенных целевым клиентом для инициалистики (перемещения) из клиента-источника в целевой. Не нужно заполнять эту группу заранее, но для запуска действий по настройке (сценария) необходимо у вас по крайней мере одна группа. Вложенные группы не поддерживаются. 

4. Скачайте скрипт SetupCrossTenantRelationshipForResourceTenant.ps1 для настройки клиента источника из репозитория GitHub [https://github.com/microsoft/cross-tenant/releases/tag/Preview](https://github.com/microsoft/cross-tenant/releases/tag/Preview) здесь: 

5. Создайте удаленное подключение PowerShell к клиенту-источнику с разрешениями администратора Exchange. Для настройки клиента-источника не требуются разрешения глобального администратора, а только целевой клиент из-за процесса создания приложения Azure.

6. Измените каталог на расположение сценария или убедитесь, что сценарий в данный момент сохранен в расположении в сеансе Удаленной powerShell.

7. Запустите сценарий с помощью следующих необходимых параметров и значений.

    | Параметр | Значение |
    |-----|------|
    | -SourceMailboxMovePublishedScopes | Группа безопасности с включенной поддержкой почты, созданная клиентом-источником для удостоверений и почтовых ящиков, которые находятся в области миграции. |
    | -ResourceTenantDomain | Доменное имя клиента-источника, например fabrikam \. onmicrosoft.com. |
    | -ApplicationId | GuID приложения Azure, используемого для миграции. ИД приложения, доступный на портале Azure (Azure AD, корпоративные приложения, имя приложения, ИД приложения) или включенный в приглашение.  |
    | -TargetTenantDomain | Доменное имя целевого клиента, например contoso \. onmicrosoft.com. |
    | -TargetTenantId | ИД целевого клиента. Например, ИД клиента Azure AD клиента contoso \. onmicrosoft.com клиента. |
    |||

    Пример:
    ```powershell
    SetupCrossTenantRelationshipForResourceTenant.ps1 -SourceMailboxMovePublishedScopes "MigScope","MyGroup" -ResourceTenantDomain contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ApplicationId sdf5e87sa-0753-dd88-ad35-c71a15cs8e44c -TargetTenantId 4sdkfo933-3904-sd93-bf9a-sdi39402834
    Exchange setup complete.

    ```

Настройка администратора источника завершена!

### <a name="verify-setup"></a>Проверка настройки

Убедитесь, что связи организации в исходных и целевых клиентах и конечной точке миграции в целевом объекте созданы успешно.

#### <a name="target-tenant"></a>Целевой клиент

**Организационная связь**

Убедитесь, что объект связи организации создан и настроен с помощью этой команды.

```powershell
Get-OrganizationRelationship <source tenant organization name> | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability
```
Вот пример:

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship fabrikam_contoso_1178 | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability

Name                  : fabrikam_contoso_1123
DomainNames           : {sd0933me9f-9304-s903-s093-s093mfi903m4}
MailboxMoveEnabled    : True
MailboxMoveCapability : Inbound

```

**Конечная точка миграции**

Убедитесь, что объект конечной точки миграции создан и настроен с помощью этой команды.

```powershell
Get-MigrationEndpoint "<fabrikam_contoso_1123> | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl
```

Пример:

```powershell
PS C:\PowerShell\> Get-MigrationEndpoint fabrikam_contoso_1123 | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl


Identity             : fabrikam_contoso_1123
RemoteTenant         : contoso.onmicrosoft.com
ApplicationId        : s93mf93-das9-dq24-dq234-dada9033904m
AppSecretKeyVaultUrl : https://cross-tenantmyvaultformoves.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ae79348mx94384c288c5a3dfsioepw308

```

#### <a name="source-tenant"></a>Исходный клиент

**Организационная связь**

Убедитесь, что объект связи организации создан и настроен с помощью этой команды.

```powershell
Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId
```

Пример:

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId


Name                       : fabrikam_contoso_001
MailboxMoveEnabled         : True
MailboxMoveCapability      : RemoteOutbound
MailboxMovePublishedScopes : {MigScope}
OAuthApplicationId         : sd9890342-3243-3242-fe3w2-fsdade93m0
```

#### <a name="verify-setup-script"></a>Проверка сценария установки

Если во время настройки исходных или целевых клиентов будут ошибки, можно запустить сценарий VerifySetup.ps1, расположенный на [GitHub,](https://github.com/microsoft/cross-tenant/releases/tag/Preview) и просмотреть выходные данные.

Вот пример запуска VerifySetup.ps1 в целевом клиенте:

```powershell
VerifySetup.ps1 -PartnerTenantId <SourceTenantId> -ApplicationId <AADApplicationId> -ApplicationKeyVaultUrl <appKeyVaultUrl> -PartnerTenantDomain <PartnerTenantDomain> -Verbose
```

Вот пример того, как VerifySetup.ps1 в клиенте-источнике:

```powershell
VerifySetup.ps1 -PartnerTenantId <TargetTenantId> -ApplicationId <AADApplicationId>
```

### <a name="move-mailboxes-back-to-the-original-source"></a>Перемещение почтовых ящиков обратно в исходный источник

Если требуется переместить почтовый ящик обратно в исходный клиент, необходимо выполнить один и тот же набор действий и сценариев как в новых исходных, так и в новых целевых клиентах. Существующий объект Связи организации будет обновлен или примеен, а не воссоздан.

## <a name="prepare-target-user-objects-for-migration"></a>Подготовка целевых объектов пользователей к миграции

Миграция пользователей должна присутствовать в целевом клиенте и системе Exchange Online (как MailUsers), помеченной определенными атрибутами, чтобы включить перемещение между клиентами. Система не сможет двигаться для пользователей, которые неправильно настроены в целевом клиенте. В следующем разделе подробно ются требования к объекту MailUser для целевого клиента.

### <a name="prerequisites"></a>Предварительные условия
  
Необходимо убедиться, что в целевой организации установлены следующие объекты и атрибуты.  

1. Для любого почтового ящика, перемещаемой из организации-источника, необходимо подготовка объекта MailUser в целевой организации: 

   - Целевой mailUser должен иметь эти атрибуты из исходных почтовых ящиков или иметь новый объект User:
      - ExchangeGUID (прямой поток от источника к целевому) — GUID почтового ящика должен совпадать. Процесс перемещения не будет продолжаться, если он не присутствует в целевом объекте. 
      - ArchiveGUID (прямой поток от источника к целевому) — guID архива должен совпадать. Процесс перемещения не будет продолжаться, если он не присутствует в целевом объекте. (Это необходимо, только если для исходных почтовых ящиков включен архив). 
      - LegacyExchangeDN (поток в качестве proxyAddress, "x500: ") — legacyExchangeDN должен присутствовать в <LegacyExchangeDN> целевом MailUser как x500: proxyAddress. Процессы перемещения не будут продолжаться, если они не присутствуют в целевом объекте. 
      - UserPrincipalName — upN будет согласовываться с новым удостоверением пользователя или целевой компанией (например, user@northwindtraders.onmicrosoft.com). 
      - Primary SMTPAddress — основной SMTP-адрес будет согласован с новой компанией пользователя (например, user@northwind.com). 
      - TargetAddress/ExternalEmailAddress — MailUser будет ссылаться на текущий почтовый ящик пользователя, который был в клиенте источника (например, user@contoso.onmicrosoft.com). При назначении этого значения убедитесь, что вы также назначаете PrimarySMTPAddress или это значение задает PrimarySMTPAddress, что приведет к сбоям перемещения. 
      - Вы не можете добавлять устаревшие прокси-адреса smtp из исходных почтовых ящиков в целевой почтовый ящик MailUser. Например, нельзя поддерживать contoso.com MEU в fabrikam.onmicrosoft.com объектах клиента). Домены связаны только с одним клиентом Azure AD или Exchange Online.
 
     Пример **целевого** объекта MailUser:
 
     | Атрибут             | Значение                                                                                                                    |
     |-----------------------|--------------------------------------------------------------------------------------------------------------------------|
     | Alias                 | Лараан                                                                                                                    |
     | RecipientType         | MailUser                                                                                                                 |
     | RecipientTypeDetails  | MailUser                                                                                                                 |
     | UserPrincipalName     | LaraN@northwintraders.onmicrosoft.com                                                                                    |
     | PrimarySmtpAddress    | Lara.Newton@northwind.com                                                                                                |
     | ExternalEmailAddress  | SMTP:LaraN@contoso.onmicrosoft.com                                                                                       |
     | ExchangeGuid          | 1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8                                                                                     |
     | LegacyExchangeDN      | /o=First Organization/ou=Exchange Administrative Group                                                                   |
     |                       | (FYDIBOHF23SPDLT)/cn=Recipients/cn=74e5385fce4b46d19006876949855035Lara                                                  |
     | EmailAddresses        | x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c8190  |
     |                       | 7273f1f9-Lara                                                                                                            |
     |                       | smtp:LaraN@northwindtraders.onmicrosoft.com                                                                              |
     |                       | SMTP:Lara.Newton@northwind.com                                                                                           |
     |||

     Пример **объекта source** Mailbox:

     | Атрибут             | Значение                                                                    |
     |-----------------------|--------------------------------------------------------------------------|
     | Alias                 | Лараан                                                                    |
     | RecipientType         | UserMailbox                                                              |
     | RecipientTypeDetails  | UserMailbox                                                              |
     | UserPrincipalName     | LaraN@contoso.onmicrosoft.com                                            |
     | PrimarySmtpAddress    | Lara.Newton@contoso.com                                                  |
     | ExchangeGuid          | 1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8                                     |
     | LegacyExchangeDN      | /o=First Organization/ou=Exchange Administrative Group                   |
     |                       | (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara  |
     | EmailAddresses        | smtp:LaraN@contoso.onmicrosoft.com 
     |                       | SMTP:Lara.Newton@contoso.com          |
     |||

   - Дополнительные атрибуты могут быть уже включены в гибридную функцию записи Exchange. Если нет, их следует включить. 
   - msExchBlockedSendersHash — записывает данные надежных и заблокированных отправителей из интернета из клиентов в локальной службе Active Directory.
   - msExchSafeRecipientsHash — записывает данные о надежных и заблокированных отправляях из интернета из клиентов в локальное каталог Active Directory.
   - msExchSafeSendersHash — записывает данные надежных и заблокированных отправителей из интернета из клиентов в локальной службе Active Directory.

2. Если исходный почтовый ящик находится на litigationHold, а размер элементов для восстановления в исходных почтовых ящиках превышает размер базы данных по умолчанию (30 ГБ), перемещение не будет продолжаться, так как целевая квота меньше размера исходных почтовых ящиков. Можно обновить целевой объект MailUser, чтобы переместить флаги почтовых ящиков ELC из среды источника в целевую, что активирует целевую систему для расширения квоты MailUser до 100 ГБ, что позволяет перейти к целевому объекту. Эти инструкции будут работать только для гибридных удостоверений, запускающих Azure AD Connect, так как команды по пометке флагов ELC не огосят администраторам клиентов.

    >[!Note]
    > ПРИМЕР — КАК ЕСТЬ, БЕЗ ГАРАНТИИ<br/>Этот сценарий предполагает подключение как к исходным почтовым ящикам (для получения исходных значений), так и к целевому локальному каталогу Active Directory (чтобы пометь объект ADUser). Если в источнике включено восстановление для судебного разбирательства или отдельного элемента, установите его для учетной записи назначения.  Это увеличит размер контейнера конечной учетной записи до 100 ГБ.

    ```powershell
    $ELCValue = 0 
    if ($source.LitigationHoldEnabled) {$ELCValue = $ELCValue + 8} if ($source.SingleItemRecoveryEnabled) {$ELCValue = $ELCValue + 16} if ($ELCValue -gt 0) {Set-ADUser -Server $domainController -Identity $destination.SamAccountName -Replace @{msExchELCMailboxFlags=$ELCValue}} 
    ```

3. Негигитовые целевые клиенты могут изменить квоту папки "Элементы с возможностью восстановления" для mailUsers перед миграцией, выдав следующую команду, чтобы включить удержание для судебного разбирательства для объекта MailUser и увеличить квоту до 100 `Set-MailUser -EnableLitigationHoldForMigration $TRUE` ГБ: Обратите внимание, что это не будет работать для клиентов в гибридной данной модели.

4. Пользователи в целевой организации должны иметь лицензии на соответствующие подписки Exchange Online, применимые к организации. Вы можете применить лицензию перед перемещением почтового ящика, но только после того, как целевой mailUser правильно настроен с помощью ExchangeGUID и прокси-адресов. Применение лицензии перед применением ExchangeGUID приведет к предоставлению нового почтового ящика в целевой организации. 

    > [!Note]
    > При применении лицензии к объекту Mailbox или MailUser все адреса proxyAddresses типа SMTP проверяются, чтобы в массив Exchange EmailAddresses включались только проверенные домены. 

5. Необходимо убедиться, что целевой mailUser не имеет предыдущего ExchangeGuid, который не соответствует source ExchangeGuid. Это может произойти, если целевой MEU ранее был лицензирован для Exchange Online и был предусмотрен почтовый ящик. Если целевой mailUser ранее был лицензирован для ExchangeGuid или имел его, не совпадавший с Исходным кодом ExchangeGuid, необходимо выполнить очистку облачного MEU. Для этих облачных MEUS можно запустить `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` .  

    > [!Caution]
    > Этот процесс необратим. Если у объекта есть почтовый ящик softDeleted, его нельзя восстановить после этой точки. Однако после очистки можно синхронизировать правильный Объект ExchangeGuid с целевым объектом, и служба MRS подключит исходный почтовый ящик к созданному целевому почтовому ящику. (Ссылаясь на блог EHLO о новом параметре.)  

    Найдите объекты, которые ранее были почтовыми ящиками, с помощью этой команды.

    ```powershell
    Get-User <identity> | select Name, *recipient* | ft -AutoSize
    ```

    Пример: 

    ```powershell
    PS demo> get-user John@northwindtraders.com |select name, *recipient*| ft -AutoSize  

    Name        PreviousRecipientTypeDetails     RecipientType RecipientTypeDetails  
    ----       ---------------------------- ------------- --------------------  
    John       UserMailbox                  MailUser      MailUser  
    ```  

    Удаляем почтовый ящик с помощью этой команды.

    ```powershell
    Set-User <identity> -PermanentlyClearPreviousMailboxInfo
    ```

    Пример:

    ```powershell
    PS demo> Set-User John@northwindtraders.com -PermanentlyClearPreviousMailboxInfo Confirm 
    Are you sure you want to perform this action? 
    Delete all existing information about user “John@northwindtraders.com"?. This operation will clear existing values from Previous home MDB and Previous Mailbox GUID of the user. After deletion, reconnecting to the previous mailbox that existed in the cloud will not be possible and any content it had will be unrecoverable PERMANENTLY.  
    Do you want to continue? 
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"): Y  
    ```

## <a name="perform-mailbox-migrations"></a>Выполнение миграции почтовых ящиков

Миграция почтовых ящиков Exchange между клиентами передается в качестве пакетов миграции, инициированных из целевого клиента. Это аналогично тому, как работают пакеты миграции при миграции из локальной службы Exchange в Microsoft 365. 

### <a name="create-migration-batches"></a>Создание пакетов миграции

Вот пример пакета миграции для начала перемещения.

```powershell
New-MigrationBatch -Name T2Tbatch-testforignitedemo -SourceEndpoint target_source_7977 -CSVData ([System.IO.File]::ReadAllBytes('users.csv')) -Autostart -TargetDeliveryDomain targetformoves.onmicrosoft.com -AutoComplete

Identity                   Status  Type               TotalCount
--------                   ------  ----               ----------
T2Tbatch-testforignitedemo Syncing ExchangeRemoteMove 1

```

> [!Note]
> Адрес электронной почты в CSV-файле должен быть указан в целевом клиенте, а не в клиенте-источнике.

Пакетная отправка миграции также поддерживается из нового Центра администрирования Exchange при выборе меж клиента.

#### <a name="update-on-premises-mailusers"></a>Обновление локального почтового ящика

После перемещения почтового ящика из источника в целевой следует убедиться, что пользователи локальной почты, как исходные, так и целевые, обновлены с помощью нового targetAddress. В примерах targetDeliveryDomain, используемый в движении, contoso.onmicrosoft.com **.** Обновим почтовых пользователей с помощью этого targetAddress.

## <a name="frequently-asked-questions"></a>Вопросы и ответы

**Нужно ли обновлять удаленные почтовые ящики в локальном источнике после перемещения?**

Да, необходимо обновить targetAddress (RemoteRoutingAddress/ExternalEmailAddress) для исходных пользователей локальной системы, когда исходный почтовый ящик клиента перемещается в целевой клиент.  Маршруты почты могут следовать рекомендации для нескольких пользователей почты с разными адресами targetAddresses, но запросы о занятости для почтовых пользователей должны быть нацелены на расположение пользователя почтового ящика. При подыском о занятости не будет гоняться несколько перенаправлений. 

**Переносит ли содержимое папки чата Teams между клиентами?**  

Нет, содержимое папки чата Teams не переносит содержимое между клиентами.  

**Как можно увидеть только перемещения, которые являются перемещениями между арендаторами, а не переходами с других клиентов?**

Используйте `-flags` параметр. Пример:

```powershell
Get-MoveRequest -Flags "CrossTenant"  
```

**Можно ли предоставить примеры сценариев для копирования атрибутов, используемых при тестировании?**

> [!Note]
> ПРИМЕР — КАК ЕСТЬ, БЕЗ ГАРАНТИИ<br/>Этот сценарий предполагает подключение как к исходным почтовым ящикам (для получения исходных значений), так и к целевым доменным службам Active Directory (чтобы пометь объект ADUser). Если в источнике включено восстановление для судебного разбирательства или отдельного элемента, установите его для учетной записи назначения.  Это увеличит размер контейнера конечной учетной записи до 100 ГБ.

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
**Как получить доступ к Outlook на день 1 после того, как почтовый ящик использования будет перемещен?**

Так как только один клиент может владеть доменом, прежний основной адрес SMTPAddress не будет связан с пользователем в целевом клиенте после завершения перемещения почтового ящика; только те домены, которые связаны с новым клиентом. Outlook использует новое upN пользователей для проверки подлинности в службе, а профиль Outlook ожидает найти основной SMTP-адрес, который соответствует почтовому ящику в целевой системе. Так как устаревший адрес не находится в целевой системе, профиль Outlook не будет подключаться для поиска только что перемещенного почтового ящика. 

Для этого начального развертывания пользователям потребуется перестроить свой профиль с помощью нового upN, основного SMTP-адреса и повторно синхронизировать содержимое OST. 

> [!Note]
> Планируйте соответствующим образом по мере того, как вы будете пакетировать пользователей для завершения. При использовании сети и емкости необходимо учитывать при создании профилей клиентов Outlook и загрузке последующих файлов OST и OAB на клиенты. 
 
**Какие роли Exchange RBAC необходимы для выполнения перекрестного перемещения клиентов?**
 
Существует матрица ролей, основанная на допущении делегирования обязанностей при выполнении перемещения почтового ящика. В настоящее время требуются две роли:  

- Первая роль — это разовая задача установки, которая устанавливает авторизацию перемещения контента в клиент или организацию или из нее. Так как перемещение данных из системы контроля организации является критически важной проблемой для всех компаний, мы выбрали наивысшую назначенную роль администратора организации (OrgAdmin). Эта роль должна изменить или настроить новую организацию OrganizationRelationship, которая определяет -MailboxMoveCapability в удаленной организации. Только OrgAdmin может изменять параметр MailboxMoveCapability, а другими атрибутами в OrganizationRelationhip может управлять администратор федеративного общего доступа. 
 
- Роль выполнения фактических команд перемещения можно делегировать функции нижнего уровня. Роли перемещения почтовых ящиков назначена возможность перемещения почтовых ящиков в организации или из нее с помощью `-RemoteTenant` параметра.  

**Как выбрать адрес SMTP для targetAddress (TargetDeliveryDomain) в преобразованном почтовом ящике (в преобразование MailUser)?**
 
Перемещения почтовых ящиков Exchange с помощью MRS создают targetAddress исходного исходного почтового ящика при преобразовании в MailUser путем совпадения адреса электронной почты (proxyAddress) в целевом объекте. Этот процесс принимает значение -TargetDeliveryDomain, переданное в команду перемещения, а затем проверяет наличие совпадающих прокси-серверов для этого домена на целевой стороне. При поиске совпадения совпадающий прокси-адрес используется для того, чтобы установить externalEmailAddress (targetAddress) для преобразованного объекта почтового ящика (теперь MailUser).
 
**Как меняются разрешения для почтового ящика?**

К разрешениям для почтовых ящиков относятся "Отправить от имени" и "Доступ к почтовым ящикам": 

- Send On Behalf of (AD:publicDelegates) хранит DN получателей с доступом к почтовому ящику пользователя в качестве делегата. Это значение хранится в Active Directory и в настоящее время не перемещается в рамках перехода почтового ящика. Если исходный почтовый ящик имеет открытые объекты publicDelegates, вам потребуется переустанавлить publicDelegates в целевом почтовом ящике, когда преобразование MEU в почтовый ящик будет завершено в целевой среде. `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` 
 
- Разрешения почтового ящика, хранимые в почтовом ящике, перемещаются вместе с почтовым ящиком при перемещении основного и делегата в целевую систему. Например, пользователю TestUser_7 полный доступ к почтовому ящику TestUser_8 в клиенте SourceCompany.onmicrosoft.com. После завершения перемещения почтового ящика в TargetCompany.onmicrosoft.com эти же разрешения устанавливаются в целевом каталоге. Примеры использования *Get-MailboxPermission* для TestUser_7 в исходных и целевых клиентах показаны ниже. К ним примещается префикс "источник" и "целевой". 
 
Вот пример вывода разрешения почтового ящика перед перемещением. 

```powershell
PS C:\PowerShell\> Get-SourceMailboxPermission testuser_7 |ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       False
TestUser_8@SourceCompany.onmicrosoft.com         {FullAccess}                                                            False       False....
```
Вот пример вывода разрешения почтового ящика после перемещения. 

```powershell
PS C:\PowerShell\> Get-TargetMailboxPermission testuser_7 | ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       FalseTestUser_8@TargetCompany.onmicrosoft.com         {FullAccess}                                                            False       False
```
 
> [!Note]
> Разрешения для почтовых ящиков и календаря между клиентами НЕ поддерживаются. Необходимо упорядочить участников и делегатов в консолидированные пакеты перемещения, чтобы эти подключенные почтовые ящики одновременно перемещались из клиента-источника. 

**Какой прокси-сервер X500 следует добавить к целевым прокси-адресам MailUser, чтобы включить миграцию?**  

Для миграции почтовых ящиков между клиентами необходимо, чтобы значение LegacyExchangeDN объекта исходных почтовых ящиков было помещено как адрес электронной почты x500 в целевом объекте MailUser.  

Пример.  
```powershell
LegacyExchangeDN value on source mailbox is:  
/o=First Organization/ou=Exchange Administrative Group(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara  

so the x500 email address to be added to target MailUser object would be:  
x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9-Lara  
```

> [!Note]  
> Помимо этого прокси-сервера X500 вам потребуется скопировать все прокси-серверы X500 из почтового ящика в источнике в почтовый ящик в целевом.  

**Где начать устранение неполадок, если перемещения не работают?**  

Для начала запустите сценарий VerifySetup.ps1, расположенный на [GitHub,](https://github.com/microsoft/cross-tenant/releases/tag/Preview) и просмотрите выходные данные.

Вот пример запуска VerifySetup.ps1 в целевом клиенте:

```powershell
VerifySetup.ps1 -PartnerTenantId <SourceTenantId> -ApplicationId <AADApplicationId> -ApplicationKeyVaultUrl <appKeyVaultUrl> -PartnerTenantDomain <PartnerTenantDomain> -Verbose
```

Вот пример eExample запуска VerifySetup.ps1 в клиенте-источнике:

```powershell
VerifySetup.ps1 -PartnerTenantId <TargetTenantId> -ApplicationId <AADApplicationId>
```

**Может ли исходный и целевой клиент использовать одно и то же доменное имя?**  

Нет. Имена доменов источника и целевого клиента должны быть уникальными. Например, исходный домен contoso.com и целевой домен fourthcoffee.com.

**Будут ли общие почтовые ящики перемещаться и по-прежнему работать?**

Да, но мы сохраняем только разрешения на хранение, как описано в этих статьях:

- [Microsoft Docs | Управление разрешениями для получателей в Exchange Online](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients)

- [Служба поддержки Майкрософт | Предоставление разрешений для почтовых ящиков Exchange и Outlook в Выделенном Office 365](https://support.microsoft.com/topic/how-to-grant-exchange-and-outlook-mailbox-permissions-in-office-365-dedicated-bac01b2c-08ff-2eac-e1c8-6dd01cf77287)

**Требуется ли Azure Key Vault и когда будут выполнены транзакции?**  

Да, для хранения сертификата для авторизации миграции необходима подписка Azure с использованием Key Vault. В отличие от миграций с использованием имени пользователя & пароля для проверки подлинности в источнике, при миграции почтовых ящиков между клиентами в качестве секрета и учетных данных используется OAuth и этот сертификат. Доступ к хранилищу Key Vault должен поддерживаться во всех миграциях почтовых ящиков, так как доступ к нему должен быть один раз в начале и после окончания миграции, а также один раз в 24 часа во время добавонной синхронизации. Здесь вы можете просмотреть []( https://azure.microsoft.com/en-us/pricing/details/key-vault/)сведения о стоимости AKV.  

**Есть ли какие-либо рекомендации по пакетам?**  

Не более 2000 почтовых ящиков на пакет. Мы настоятельно рекомендуем отправку пакетов за две недели до даты вырезания, так как они не влияют на конечных пользователей во время синхронизации. Если вам требуется руководство по количеству почтовых ящиков более 50 000, вы можете связаться со списком рассылки отзывов по техническим вопросам по crosstenantmigrationpreview@service.microsoft.com.

**Что делать, если я использую шифрование службы с ключом клиента?**

Почтовый ящик будет расшифровываться перед перемещением. Убедитесь, что ключ клиента настроен в целевом клиенте, если он по-прежнему требуется. Дополнительные [сведения см.](https://docs.microsoft.com/microsoft-365/compliance/customer-key-overview) здесь.  

**Каково предполагаемое время миграции?**

Чтобы помочь вам спланировать [](https://docs.microsoft.com/exchange/mailbox-migration/office-365-migration-best-practices#estimated-migration-times) миграцию, в таблице ниже представлены рекомендации по поводу того, когда следует ожидать завершения массовой миграции почтовых ящиков или отдельных миграций. Эти оценки основаны на анализе данных предыдущих миграций клиентов. Так как каждая среда уникальна, точная скорость миграции может отличаться.  

Помните, что эта функция в настоящее время находится в предварительной версии, а SLA и применимые уровни обслуживания не применяются к любым вопросам производительности или доступности во время просмотра состояния этой функции.

## <a name="known-issues"></a>Известные проблемы  

-  **Проблема: невозможно перенести автоматически расширившие архивы.** Функция миграции между клиентами поддерживает миграцию основного и архивного почтовых ящиков для определенного пользователя. Если у пользователя в источнике есть автоматически расширенный архив , то есть несколько архивных почтовых ящиков, функция не сможет перенести дополнительные архивы и не сможет ее перенести.

- **Проблема: cloud MailUsers с ненанимателями smtp proxyAddress блок MRS перемещает фон.** При создании объектов MailUser целевого клиента необходимо убедиться, что все прокси-адреса SMTP принадлежат целевой организации клиента. Если прокси-адрес SMTP существует для целевого почтового пользователя, который не принадлежит локальному арендатору, преобразование MailUser в Mailbox будет предотвращено. Это связано с тем, что объекты почтовых ящиков могут отправлять почту только из доменов, для которых клиент является достоверным (домены, заявленные клиентом): 

   - При синхронизации пользователей из локальной сети с помощью Azure AD Connect вы подаете локально объекты MailUser с помощью ExternalEmailAddress, указывая на исходный клиент, в котором существует почтовый ящик (laran@contoso.onmicrosoft.com), и помечаете PrimarySMTPAddress как домен, который находится в целевом клиенте (Lara.Newton@northwind.com). Эти значения синхронизируются с клиентом, и соответствующий почтовый пользователь готов к миграции. Пример объекта показан здесь.
     ```powershell
     target/AADSynced user] PS C> Get-MailUser laran | select ExternalEmailAddress, EmailAddresses   
     ExternalEmailAddress               EmailAddresses 
     --------------------               -------------- 
     SMTP:laran@contoso.onmicrosoft.com {SMTP:lara.newton@northwind.com} 
     ```

   > [!Note]
   > Адрес *contoso.onmicrosoft.com* нет *в* массиве EmailAddresses /proxyAddresses.

- **Проблема: объекты MailUser с "внешними" основными SMTP-адресами изменены или сброшены в "внутренние" домены компании**

   Объекты MailUser — это указатели на не локальные почтовые ящики. В случае миграции почтовых ящиков между клиентами мы используем объекты MailUser, чтобы представлять исходный почтовый ящик (с точки зрения целевой организации) или целевой почтовый ящик (с точки зрения организации-источника). У mailUsers будет адрес ExternalEmailAddress (targetAddress), который указывает на smtp-адрес фактического почтового ящика (ProxyTest@fabrikam.onmicrosoft.com) и основной адресSMTP, который представляет smTP-адрес пользователя почтового ящика в каталоге. В некоторых организациях основной SMTP-адрес отображается как внешний SMTP-адрес, а не как адрес, владельцем или проверенным локальным клиентом (например, fabrikam.com, а не как contoso.com).  Однако после того как объект плана обслуживания Exchange будет применен к MailUser с помощью операций лицензирования, основной SMTP-адрес будет изменен, чтобы показать его как домен, проверенный локальной организацией (contoso.com). Существует две возможные причины:
   
   - Когда к MailUser применяется какой-либо план обслуживания Exchange, процесс Azure AD начинает принудительно выполнять очистку прокси-серверов, чтобы убедиться, что локализованная организация не может отправлять почту, спуфинг или почту из другого клиента. Любой SMTP-адрес объекта получателя с этими планами обслуживания будет удален, если адрес не проверен локальной организацией. Как и в примере, Fabikam.com не проверяется клиентом contoso.onmicrosoft.com, поэтому при очистке этот fabrikam.com домен. Если вы хотите сохранить эти внешние домены в MailUser до миграции или после миграции, необходимо изменить процессы миграции, чтобы отодвинуть лицензии после завершения перемещения или перед перемещением, чтобы убедиться, что к пользователям применена ожидаемая внешняя фирменая марка. Необходимо убедиться, что объект почтового ящика имеет правильную лицензию, чтобы не влиять на службу почты.<br/><br/>Ниже показан пример сценария для удаления планов обслуживания для MailUser в Contoso.onmicrosoft.com клиента.

    ```powershell
    $LO = New-MsolLicenseOptions -AccountSkuId "contoso:ENTERPRISEPREMIUM" DisabledPlans 
    "LOCKBOX_ENTERPRISE","EXCHANGE_S_ENTERPRISE","INFORMATION_BARRIERS","MIP_S_CLP2","
    MIP_S_CLP1","MYANALYTICS_P2","EXCHANGE_ANALYTICS","EQUIVIO_ANALYTICS","THREAT_INTE
    LLIGENCE","PAM_ENTERPRISE","PREMIUM_ENCRYPTION" 
    Set-MsolUserLicense -UserPrincipalName proxytest@contoso.com LicenseOptions $lo 
    ```

       Здесь показаны результаты в наборе назначенных servicePlans.

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
 
       Основное имя пользователя PrimarySMTPAddress больше не будет удалено. Домен fabrikam.com не принадлежит contoso.onmicrosoft.com и будет сохраняться в качестве основного SMTP-адреса, показанного в каталоге.

       Пример:

    ```powershell
    get-recipient proxytest | ft -a userprin*, primary*, external*   
    PrimarySmtpAddress        ExternalDirectoryObjectId               ExternalEmailAddress 
    ------------------        -------------------------               -------------------- 
    proxytest@fabrikam.com    e2513482-1d5b-4066-936a-cbc7f8f6f817    SMTP:proxytest@fabrikam.com 
    ```

   - Если для msExchRemoteRecipientType установлено 8 (DeprovisionMailbox) для локальной службы MailUsers, перенесенной в целевой клиент, логика очистки прокси в Azure удалит невторизированные домены и сбросит primarySMTP в собственный домен. При очистке msExchRemoteRecipientType в локальном mailUser логика прокси-очистки больше не применяется. <br/><br>Ниже приведен полный набор возможных планов обслуживания, включая Exchange Online.

   | Имя                                              |
   |---------------------------------------------------|
   | Advanced eDiscovery Storage (500 ГБ)               |
   | Защищенное хранилище                                  |
   | Защита от потери данных                              |
   | Exchange Enterprise CAL Services (EOP, DLP)       |
   | Exchange Essentials                               |
   | Exchange Foundation                               |
   | Exchange Online (P1)                              |
   | Exchange Online (план 1)                          |
   | Exchange Online (план 2)                          |
   | Архивация на базе Exchange Online для Exchange Online     |
   | Архивация на базе Exchange Online для Exchange Server     |
   | Надстройка неактивного пользователя Exchange Online              |
   | Базовая подписка на Exchange Online                             |
   | Exchange Online с поддержкой нескольких регионов                         |
   | Exchange Online (план 1)                            |
   | Exchange Online POP                               |
   | Exchange Online Protection                        |
   | Информационные барьеры                              |
   | Защита данных для Office 365 — Premium   |
   | Защита данных для Office 365 — Standard  |
   | Аналитика myAnalytics                           |
   | Расширенный аудит Microsoft 365                   |
   | Microsoft Bookings                                |
   | Microsoft Business Center                         |
   | Microsoft MyAnalytics (полнофункциональная версия)                      |
   | Office 365 Advanced eDiscovery                    |
   | Microsoft Defender для Office 365 (план 1)    |
   | Microsoft Defender для Office 365 (план 2)    |
   | Office 365 Privileged Access Management           |
   | Шифрование premium в Office 365                  |
    
