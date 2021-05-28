---
title: Миграция почтовых ящиков между клиентами
description: Перемещение почтовых ящиков между Microsoft 365 или Office 365 клиентов.
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
ms.openlocfilehash: f9a4b7679a33d6722336ee5412e4992389ba915f
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694417"
---
# <a name="cross-tenant-mailbox-migration-preview"></a>Миграция почтовых ящиков с перекрестным клиентом (предварительный просмотр)

Раньше, когда Exchange Online должен был переместить почтовые ящики другому клиенту в той же службе Exchange Online, ему придется полностью отключить их в локальное помещение, а затем на борту их для нового клиента. С помощью новой функции миграции почтовых ящиков между клиентами администраторы клиентов в исходных и целевых клиентах могут перемещать почтовые ящики между арендаторами с минимальными зависимостями инфраструктуры в локальной системе. Это устраняет необходимость в бортовых и бортовых почтовых ящиках.

Как правило, во время слияний или отгрузок требуется возможность перемещения пользователей и контента в нового клиента. Когда целевой администратор клиента выполняет этот шаг, он называется перемещением Pull, аналогично локальному переносу облачных бортовых данных.

Перекрестные перемещения Exchange почтовых ящиков полностью самообслуживаются администраторами клиентов, используя хорошо известные интерфейсы, которые можно скриптить в более крупные процессы, необходимые для перехода пользователей в новую организацию. Администраторы могут использовать комлет, доступный через роль управления почтовыми ящиками Move, для выполнения `New-MigrationBatch` перекрестных ходов клиента. Процесс перемещения включает проверки авторизации клиента во время синхронизации и финализации почтовых ящиков. 
 
Миграция пользователей должна присутствовать в целевой системе Exchange Online клиента в качестве MailUsers, отмеченных определенными атрибутами для обеспечения перекрестного перемещения клиента. Система сбой ходов для пользователей, которые не правильно настроены в целевом клиенте.  

Когда ходы завершались, почтовый ящик исходных систем преобразуется в MailUser, а адрес targetAddress (показано как ExternalEmailAddress в Exchange) штампуется адресом маршрутки для клиента назначения. Этот процесс оставляет устаревший MailUser в клиенте источника и позволяет на период сосуществования и маршрутизации почты. Когда бизнес-процессы позволяют, клиент-источник может удалить исходный MailUser или преобразовать их в почтовый контакт. 

Переносы Exchange почтовых ящиков поддерживаются только в гибридном или облачном варианте или в любой комбинации.

В этой статье описывается процесс перемещения почтовых ящиков между клиентами и содержится руководство по подготовке исходных и целевых клиентов для перемещения контента.  

## <a name="preparing-source-and-target-tenants"></a>Подготовка исходных и целевых клиентов

Функция переноса Exchange почтовых ящиков с Exchange требует авторизации и скопирования для перекрестных миграций клиента. С помощью решений Enterprise Azure и хранилища key Vault администраторы клиентов теперь уполномочены управлять как авторизацией, так и Exchange Online миграцией почтовых ящиков из одного клиента в другой. Перемещение почтовых ящиков между клиентами поддерживает модель приглашения и согласия для создания приложения Azure Active Directory Azure AD, используемого для проверки подлинности между парой клиентов. Кроме того, требуются дополнительные компоненты, такие как отношение к организации и конечная точка миграции.

В этом разделе не содержатся конкретные действия, необходимые для подготовки объектов пользователя MailUser в целевом каталоге, а также пример команды отправки пакета миграции. См. [в этой информации подготовка целевых объектов пользователя к](#prepare-target-user-objects-for-migration) миграции.

## <a name="prerequisites"></a>Необходимые условия

Функция перемещения почтовых ящиков между клиентами требует от [Azure Key Vault](/azure/key-vault/basic-concepts) создать приложение Azure для безопасного хранения и доступа к сертификату/секрету, используемого для проверки подлинности и авторизации миграции почтовых ящиков из одного клиента в другой, с удалением любых требований для обмена сертификатами и секретами между клиентами. 

Перед запуском убедитесь, что у вас есть необходимые разрешения для запуска сценариев развертывания для настройки хранилища ключей Azure, приложения Move Mailbox, конечной точки миграции EXO и отношения организации EXO. Как правило, у глобального администратора есть разрешение на выполнение всех действий по настройке.

Кроме того, группы безопасности с включенной почтой в клиенте-источнике требуются перед запуском установки. Эти группы используются для охвата списка почтовых ящиков, которые могут перемещаться из клиента источника (или иногда именуемого как ресурс) в целевого клиента. Это позволяет администратору-источнику клиента ограничить или ограничить область действия определенного набора почтовых ящиков, которые необходимо перенести, чтобы предотвратить миграцию нежелательных пользователей. Вложенные группы не поддерживаются.

Вам также потребуется связаться с доверенными партнерами (с которыми будут перемещены почтовые ящики), чтобы получить Microsoft 365 клиента. Этот ID клиента используется в поле Отношения `DomainName` организации.

Чтобы получить паспорт клиента подписки, войдите в центр администрирования Microsoft 365 и перейдите в [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) . Щелкните значок копирования для свойства Tenant ID, чтобы скопировать его в буфер обмена.

Вот как работает процесс.

:::image type="content" source="../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png" alt-text="Подготовка клиента к миграции почтовых ящиков.":::

[См. более крупную версию этого изображения.](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)

<!--
[![Tenant preparation for mailbox migration](../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)
--> 

### <a name="prepare-tenants"></a>Подготовка клиентов

На высоком уровне при выполнении скриптов настройки выполняются следующие действия конфигурации.

Подготовка целевого клиента:

1. Если существующая группа ресурсов Azure не предоставлена, создается новая (SCRIPT).
2. Если существующее хранилище ключей не предоставлено, создается новый (SCRIPT).
3. Новая политика доступа создается для приложения миграции Office 365 Exchange Online почтовых ящиков (SCRIPT).
4. Для удержания секрета в приложении Migration (SCRIPT) создается новый сертификат (или существующий, если задан).
5. Создается новое приложение Azure AD (SCRIPT).
6. Сертификат/секрет загружается в приложение миграции (SCRIPT).
7. Разрешения на миграцию почтовых ящиков назначены приложению (SCRIPT).
8. Сценарий развертывания останавливается до тех пор, пока целевой администратор не согласится на собственное приложение (SCRIPT).
9. Администратор целевого клиента соглашается на разрешения, выданные приложению (MANUAL).
10. Создается отношение организации к целевому клиенту (SCRIPT).
11. Для переноса почтовых ящиков к целевому клиенту (SCRIPT) создается конечная точка миграции.

Подготовка клиента-источника:

1. Администратор исходных клиентов принимает согласие на приглашение приложения миграции почтовых ящиков от целевого клиента (MANUAL).
2. Администратор исходных клиентов создает группу безопасности с включенной почтой в клиенте, чтобы содержать список почтовых ящиков, разрешенных к перемещению приложением миграции (MANUAL).
3. Для проверки OAuth для приемки запроса на перемещение (SCRIPT) создается связь организации с целевым клиентом, указывающий, что приложение миграции почтовых ящиков должно использоваться для проверки OAuth.

#### <a name="step-by-step-instructions-for-the-target-tenant-admin"></a>Пошаговая инструкция для целевого администратора клиента

1. Скачайте SetupCrossTenantRelationshipForTargetTenant.ps1 для целевой установки клиента из [репозиторий GitHub.](https://github.com/microsoft/cross-tenant/releases/tag/Preview) 
2. Сохраните сценарий (SetupCrossTenantRelationshipForTargetTenant.ps1) на компьютере, с которого будет выполняться сценарий.
3. Создание удаленного подключения PowerShell к целевому Exchange Online клиенту. Кроме того, убедитесь, что у вас есть необходимые разрешения для запуска сценариев развертывания для настройки хранилища и сертификата хранилища ключей Azure, приложения Move Mailbox, конечной точки миграции EXO и отношения организации EXO.
4. Измените каталог папки файлов на расположение скрипта или убедитесь, что сценарий сохранен в настоящее время в вашем сеансе Удаленной PowerShell.
5. Запустите сценарий со следующими параметрами и значениями.

    | Параметр | Значение | Обязательный или необязательный
    |---------------------------------------------|-----------------|--------------|
    | -TargetTenantDomain                         | Целевой домен клиента, например fabrikam \. onmicrosoft.com. | Обязательный |
    | -ResourceTenantDomain                       | Домен исходный клиент, например contoso \. onmicrosoft.com. | Обязательный |
    | -ResourceTenantAdminEmail                   | Исходный адрес электронной почты администратора клиента. Это исходный администратор клиента, который будет соглашаться на использование приложения миграции почтовых ящиков, отправленного от целевого администратора. Это администратор, который получит приглашение по электронной почте для приложения. | Обязательный |
    | -ResourceTenantId                           | Код организации-клиента источника (GUID). | Обязательный |
    | -SubscriptionId                             | Подписка Azure, используемая для создания ресурсов. | Обязательный |
    | -ResourceGroup                              | Имя группы ресурсов Azure, которая содержит или будет содержать хранилище ключей. | Обязательный |
    | -KeyVaultName                               | Экземпляр Хранилища ключей Azure, который будет хранить сертификат/секрет приложения миграции почтовых ящиков. | Обязательный |
    | -CertificateName                            | Имя сертификата при создании или поиске сертификата в хранилище ключей. | Обязательный |
    | -CertificateSubject                         | Имя субъекта сертификата Хранилища ключей Azure, например CN=contoso_fabrikam. | Обязательный |
    | -AzureResourceLocation                      | Расположение группы ресурсов Azure и хранилища ключей. | Обязательный |
    | -ExistingApplicationId                      | Приложение миграции почты для использования, если уже создано. | Необязательный |
    | -AzureAppPermissions                        | Разрешения, необходимые для приложения миграции почтовых ящиков, такие как Exchange или MSGraph (Exchange для перемещения почтовых ящиков, MSGraph для использования этого приложения для отправки приглашения ссылки на согласие клиента ресурса). | Обязательный |
    | -UseAppAndCertGeneratedForSendingInvitation | Параметр для использования приложения, созданного для миграции, которое будет использоваться для отправки приглашения ссылки согласия на исходный администратор клиента. В случае неявки это поможет учетным данным целевого администратора подключиться к диспетчеру приглашений Azure и отправить приглашение в качестве целевого администратора. | Необязательный |
    | -KeyVaultAuditStorageAccountName            | Учетная запись хранилища, в которой будут храниться журналы аудита Key Vault. | Необязательный |
    | -KeyVaultAuditStorageResourceGroup          | Группа ресурсов, которая содержит учетную запись хранилища для хранения журналов аудита Key Vault. | Необязательный |
    ||||

    >[!Note]
    > Убедитесь, что перед запуском скриптов установлен модуль Azure AD PowerShell. Пожалуйста, обратитесь ![ сюда ](/powershell/azure/install-az-ps?view=azps-5.1.0) для действий по установке

6. Скрипт приостановит и попросит вас принять или дать согласие на Exchange почтового ящика, созданного в ходе этого процесса. Пример:

    ```powershell
    PS C:\PowerShell\> .\SetupCrossTenantRelationshipForTargetTenant.ps1 -ResourceTenantDomain contoso.onmicrosoft.com -ResourceTenantAdminEmail admin@contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ResourceTenantId ksagjid39-ede2-4d2c-98ae-874709325b00 -SubscriptionId e4ssd05d-a327-49ss-849a-sd0932439023 -ResourceGroup "Cross-TenantMoves" -KeyVaultName "Cross-TenantMovesVault" -CertificateName "Contoso-Fabrikam-cert" -CertificateSubject "CN=Contoso_Fabrikam" -AzureResourceLocation "Brazil Southeast" -AzureAppPermissions Exchange, MSGraph -UseAppAndCertGeneratedForSendingInvitation -KeyVaultAuditStorageAccountName "t2tstorageaccount" -KeyVaultAuditStorageResourceGroup "Demo"

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

7. URL-адрес будет отображаться в сеансе Remote PowerShell. Скопируйте ссылку, предоставленную для согласия клиента, и вклейте ее в веб-браузер.

8. Войте учетные данные глобального администратора. Когда будет представлен следующий экран, выберите **Accept**.

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-dialog.png" alt-text="Диалоговое окно &quot;Прием разрешений&quot;":::

9. Перейдите к сеансу Remote PowerShell и нажмите ввод для перехода.

10. Скрипт будет настраивать оставшиеся объекты установки. Пример:

    ```powershell
    Successfully sent invitation to admin@contoso.onmicrosoft.com
    Setting up exchange components on target tenant: fabrikam.onmicrosoft.com
    MigrationEndpoint created in fabrikam.onmicrosoft.com for target contoso.onmicrosoft.com
    Exchange setup complete. Migration endpoint details are available in $MigrationEndpoint variable
    ```

Настройка целевого администратора завершена!

#### <a name="step-by-step-instructions-for-the-source-tenant-admin"></a>Пошаговая инструкция для администратора исходных клиентов

1.  Вопишите в почтовый ящик в качестве -ResourceTenantAdminEmail, указанного целевым администратором во время их установки. Найдите приглашение электронной почты от целевого клиента и выберите **кнопку Начало работы.**

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/invited-by-target-tenant.png" alt-text="Вы были приглашены диалоговое окно":::

2. Выберите **Принять** приглашение.

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-accept.png" alt-text="Диалоговое окно для получения разрешений":::

   > [!NOTE]
   > Если вы не получили это письмо или не можете найти его, целевому администратору клиента был предоставлен прямой URL-адрес, который может быть предоставлен для получения приглашения. URL-адрес должен быть в расшифровке сеанса удаленной powerShell администратора целевого клиента.

3. В центре администрирования Microsoft 365 или сеансе Удаленной powerShell создайте одну или несколько групп безопасности с поддержкой почты для управления списком почтовых ящиков, разрешенных целевым клиентом для перемещения (перемещения) из клиента-источника в целевого клиента. Вам не нужно заранее заполнять эту группу, но для запуска этапов установки (скрипта) должна быть предоставлена по крайней мере одна группа. Группы Nest не поддерживаются. 

4. Скачайте SetupCrossTenantRelationshipForResourceTenant.ps1 для установки исходных клиентов из репозиторий GitHub: [https://github.com/microsoft/cross-tenant/releases/tag/Preview](https://github.com/microsoft/cross-tenant/releases/tag/Preview) . 

5. Создание удаленного подключения PowerShell к клиенту-источнику с разрешениями Exchange администратора. Глобальные разрешения администратора не требуются для настройки клиента источника, только целевого клиента из-за процесса создания приложений Azure.

6. Измените каталог на расположение скрипта или убедитесь, что сценарий в настоящее время сохранен в расположении в сеансе Удаленной PowerShell.

7. Запустите сценарий со следующими требуемой параметрами и значениями.

    | Параметр | Значение |
    |-----|------|
    | -SourceMailboxMovePublishedScopes | Группа безопасности с включенной почтой, созданная клиентом-источником для идентификаторов и почтовых ящиков, которые находятся в области миграции. |
    | -ResourceTenantDomain | Доменное имя источника клиента, например contoso \. onmicrosoft.com. |
    | -ApplicationId | Azure application ID (GUID) приложения, используемого для миграции. ID приложения, доступный на портале Azure (Azure AD, Enterprise applications, имя приложения, ID приложения) или включен в ваше приглашение по электронной почте.  |
    | -TargetTenantDomain | Целевое доменное имя клиента, например fabrikam \. onmicrosoft.com. |
    | -TargetTenantId | ID клиента целевого клиента. Например, ID клиента Azure AD клиента contoso \. onmicrosoft.com клиента. |
    |||

    Пример:
    ```powershell
    SetupCrossTenantRelationshipForResourceTenant.ps1 -SourceMailboxMovePublishedScopes "MigScope","MyGroup" -ResourceTenantDomain contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ApplicationId sdf5e87sa-0753-dd88-ad35-c71a15cs8e44c -TargetTenantId 4sdkfo933-3904-sd93-bf9a-sdi39402834
    Exchange setup complete.

    ```

Настройка администратора источника завершена!

### <a name="verify-setup"></a>Проверка установки

Убедитесь, что отношения организации в исходных и целевых клиентах и конечной точке миграции в целевом объекте были созданы успешно.

#### <a name="target-tenant"></a>Целевой клиент

**Организационная связь**

Убедитесь, что объект связи организации был создан и настроен с помощью этой команды.

```powershell
Get-OrganizationRelationship <source tenant organization name> | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability
```
Пример:

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship fabrikam_contoso_1178 | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability

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
PS C:\PowerShell\> Get-MigrationEndpoint fabrikam_contoso_1123 | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl


Identity             : fabrikam_contoso_1123
RemoteTenant         : contoso.onmicrosoft.com
ApplicationId        : s93mf93-das9-dq24-dq234-dada9033904m
AppSecretKeyVaultUrl : https://cross-tenantmyvaultformoves.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ae79348mx94384c288c5a3dfsioepw308

```

#### <a name="source-tenant"></a>Клиент источника

**Организационная связь**

Убедитесь, что объект связи организации был создан и настроен с помощью этой команды.

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

Если при настройке источника или целевого клиента будут допущены какие-либо ошибки, [](https://github.com/microsoft/cross-tenant/releases/tag/Preview) можно запустить VerifySetup.ps1, расположенный на GitHub, и просмотреть выходные данные.

Вот пример запуска VerifySetup.ps1 целевого клиента:

```powershell
VerifySetup.ps1 -PartnerTenantId <SourceTenantId> -ApplicationId <AADApplicationId> -ApplicationKeyVaultUrl <appKeyVaultUrl> -PartnerTenantDomain <PartnerTenantDomain> -Verbose
```

Вот пример того, как VerifySetup.ps1 исходный клиент:

```powershell
VerifySetup.ps1 -PartnerTenantId <TargetTenantId> -ApplicationId <AADApplicationId>
```

### <a name="move-mailboxes-back-to-the-original-source"></a>Перемещение почтовых ящиков обратно в исходный источник

Если почтовый ящик возвращается к исходному исходному клиенту, необходимо выполнить один и тот же набор действий и сценариев как в новом источнике, так и в новых целевых клиентах. Существующий объект Отношения организации будет обновляться или примеся, а не воспроизводиться.

## <a name="prepare-target-user-objects-for-migration"></a>Подготовка целевых пользовательских объектов для миграции

Мигрирующие пользователи должны присутствовать в целевом клиенте и Exchange Online (как MailUsers), отмеченных определенными атрибутами, чтобы включить перекрестные перемещения клиента. Система сбой ходов для пользователей, которые не правильно настроены в целевом клиенте. В следующем разделе подробные сведения о требованиях к объекту MailUser для целевого клиента.

### <a name="prerequisites"></a>Необходимые условия
  
Необходимо убедиться, что в целевой организации установлены следующие объекты и атрибуты.  

1. Для любого почтового ящика, перемещаемой из организации-источника, необходимо укачить объект MailUser в целевой организации: 

   - Целевой mailUser должен иметь эти атрибуты из почтового ящика источника или назначен с новым объектом Пользователя:
      - ExchangeGUID (прямой поток из источника в целевой) — GUID почтового ящика должен соответствовать. Процесс перемещения не будет продолжаться, если он не присутствует на целевом объекте. 
      - ArchiveGUID (прямой поток из источника в целевой) — GUID архива должен соответствовать. Процесс перемещения не будет продолжаться, если он не присутствует на целевом объекте. (Это необходимо только в том случае, если исходный почтовый ящик включен в архиве). 
      - LegacyExchangeDN (поток в качестве proxyAddress, "x500: ") — LegacyExchangeDN должен присутствовать в целевом <LegacyExchangeDN> MailUser как x500: proxyAddress. Процессы перемещения не будут продолжаться, если этого нет на целевом объекте. 
      - UserPrincipalName — UPN будет совпадать с новым удостоверением пользователя или целевой компанией (например, user@northwindtraders.onmicrosoft.com). 
      - Основной SMTPAddress — основной smTP-адрес будет совпадать с новой компанией пользователя (например, user@northwind.com). 
      - TargetAddress/ExternalEmailAddress — MailUser будет ссылаться на текущий почтовый ящик пользователя, который был в клиенте источника (например, user@contoso.onmicrosoft.com). При назначении этого значения убедитесь, что у вас есть/также назначается PrimarySMTPAddress или это значение задает PrimarySMTPAddress, что приведет к сбоям в движении. 
      - Нельзя добавлять устаревшие прокси-адреса smtp из исходных почтовых ящиков в адрес MailUser. Например, нельзя поддерживать contoso.com meU в fabrikam.onmicrosoft.com объектах клиента). Домены связаны только с одним клиентом Azure AD или Exchange Online клиентом.
 
     Пример **целевого** объекта MailUser:
 
     | Атрибут             | Значение                                                                                                                    |
     |-----------------------|--------------------------------------------------------------------------------------------------------------------------|
     | Alias                 | LaraN                                                                                                                    |
     | RecipientType         | MailUser                                                                                                                 |
     | RecipientTypeDetails  | MailUser                                                                                                                 |
     | UserPrincipalName     | LaraN@northwintraders.onmicrosoft.com                                                                                    |
     | PrimarySmtpAddress    | Lara.Newton@northwind.com                                                                                                |
     | ExternalEmailAddress  | SMTP:LaraN@contoso.onmicrosoft.com                                                                                       |
     | ExchangeGuid          | 1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8                                                                                     |
     | LegacyExchangeDN      | /o=First Organization/ou=Exchange административной группы                                                                   |
     |                       | (FYDIBOHF23SPDLT)/cn=Recipients/cn=74e5385fce4b46d19006876949855035Lara                                                  |
     | EmailAddresses        | x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c8190  |
     |                       | 7273f1f9-Lara                                                                                                            |
     |                       | smtp:LaraN@northwindtraders.onmicrosoft.com                                                                              |
     |                       | SMTP:Lara.Newton@northwind.com                                                                                           |
     |||

     Пример **объекта исходный** почтовый ящик:

     | Атрибут             | Значение                                                                    |
     |-----------------------|--------------------------------------------------------------------------|
     | Alias                 | LaraN                                                                    |
     | RecipientType         | UserMailbox                                                              |
     | RecipientTypeDetails  | UserMailbox                                                              |
     | UserPrincipalName     | LaraN@contoso.onmicrosoft.com                                            |
     | PrimarySmtpAddress    | Lara.Newton@contoso.com                                                  |
     | ExchangeGuid          | 1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8                                     |
     | LegacyExchangeDN      | /o=First Organization/ou=Exchange административной группы                   |
     |                       | (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara  |
     | EmailAddresses        | smtp:LaraN@contoso.onmicrosoft.com 
     |                       | SMTP:Lara.Newton@contoso.com          |
     |||

   - Дополнительные атрибуты могут быть включены в Exchange гибридной записи уже. Если нет, они должны быть включены. 
   - msExchBlockedSendersHash — записывает в интернете безопасные и заблокированные данные отправителей от клиентов в локальном Active Directory.
   - msExchSafeRecipientsHash — записывает в интернете безопасные и заблокированные данные отправитель от клиентов в локальном Active Directory.
   - msExchSafeSendersHash — записывает в интернете безопасные и заблокированные данные отправителей от клиентов в локальном Active Directory.

2. Если исходный почтовый ящик находится на LitigationHold, а размер источника извлекаемых элементов превышает размер базы данных по умолчанию (30 ГБ), ходы не будут продолжаться, так как целевая квота меньше размера исходных почтовых ящиков. Можно обновить целевой объект MailUser, чтобы перенести флаги почтовых ящиков ELC из исходных сред в целевую, что запускает целевую систему для расширения квоты MailUser до 100 ГБ, что позволяет перейти к цели. Эти инструкции будут работать только для гибридного удостоверения под управлением Azure AD Подключение, так как команды по штамповке флагов ELC не подвергаются воздействию администраторов клиентов.

    >[!Note]
    > ПРИМЕР — КАК ЕСТЬ, БЕЗ ГАРАНТИИ<br/>Этот сценарий предполагает подключение как к исходным почтовым ящикам (для получения исходных значений), так и к целевому локальному объекту Active Directory (для штамповки объекта ADUser). Если в источнике включено судебное разбирательство или включено восстановление одного элемента, установите это в учетной записи назначения.  Это увеличит размер учетной записи контейнера до 100 ГБ.

    ```powershell
    $ELCValue = 0 
    if ($source.LitigationHoldEnabled) {$ELCValue = $ELCValue + 8} if ($source.SingleItemRecoveryEnabled) {$ELCValue = $ELCValue + 16} if ($ELCValue -gt 0) {Set-ADUser -Server $domainController -Identity $destination.SamAccountName -Replace @{msExchELCMailboxFlags=$ELCValue}} 
    ```

3. Не гибридная целевая клиенты могут изменить квоту на папку "Извлекаемые элементы" для mailUsers до миграции, выразив следующую команду, чтобы включить удержание судебного разбирательства на объекте MailUser и увеличить квоту до 100 ГБ: `Set-MailUser -EnableLitigationHoldForMigration $TRUE` . Обратите внимание, что это не будет работать для клиентов в гибридном варианте.

4. Пользователи в целевой организации должны иметь лицензии с соответствующими Exchange Online, применимыми к организации. Вы можете применить лицензию перед перемещением почтовых ящиков, но только после правильной работы целевого MailUser с exchangeGUID и прокси-адресами. Применение лицензии до применения ExchangeGUID приведет к новому почтовому ящику, предусмотренном в целевой организации. 

    > [!Note]
    > При применении лицензии на объекте Почтовый ящик или MailUser все прокси-серверы типа SMTP будут стираться, чтобы убедиться, что в массив Exchange EmailAddresses включены только проверенные домены. 

5. Необходимо убедиться, что целевой MailUser не имеет предыдущего ExchangeGuid, который не соответствует Source ExchangeGuid. Это может произойти, если целевой MEU был ранее лицензирован для Exchange Online и заранее был предусмотрен почтовый ящик. Если целевой MailUser ранее имел лицензию на ExchangeGuid, не совпадавший с Source ExchangeGuid, необходимо выполнить очистку облачного MEU. Для этих облачных meUs можно запустить `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` .  

    > [!Caution]
    > Этот процесс необратим. Если у объекта есть почтовый ящик softDeleted, он не может быть восстановлен после этой точки. Однако после очистки можно синхронизировать правильный ExchangeGuid с целевым объектом, и MRS соединит исходный почтовый ящик с вновь созданным целевым почтовым ящиком. (Ссылка на блог EHLO по новому параметру.)  

    Найдите объекты, которые ранее были почтовыми ящиками с помощью этой команды.

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

    Удаляем электронный почтовый ящик с помощью этой команды.

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

Переносы Exchange почтовых ящиков с перекрестным клиентом будут отправлены в качестве пакетов миграции, инициированных из целевого клиента. Это похоже на то, как работают пакеты переноса на борт при миграции из Exchange локального в Microsoft 365. 

### <a name="create-migration-batches"></a>Создание пакетов миграции

Вот пример пакетного комлета миграции для начала ходов.

```powershell
New-MigrationBatch -Name T2Tbatch-testforignitedemo -SourceEndpoint target_source_7977 -CSVData ([System.IO.File]::ReadAllBytes('users.csv')) -Autostart -TargetDeliveryDomain targetformoves.onmicrosoft.com -AutoComplete

Identity                   Status  Type               TotalCount
--------                   ------  ----               ----------
T2Tbatch-testforignitedemo Syncing ExchangeRemoteMove 1

```

> [!Note]
> Адрес электронной почты в CSV-файле должен быть указанным в целевом клиенте, а не исходным клиентом.

Отправка пакета миграции также поддерживается из центра администрирования Exchange при выборе параметра перекрестного клиента.

#### <a name="update-on-premises-mailusers"></a>Обновление локального mailUsers

После перемещения почтового ящика из источника в целевой следует убедиться, что пользователи локальной почты, как источник, так и целевые, обновляются с помощью нового targetAddress. В примерах целевой объектDeliveryDomain, используемый в движении, contoso.onmicrosoft.com **.** Обновим пользователей почты с помощью этого targetAddress.

## <a name="frequently-asked-questions"></a>Вопросы и ответы

**Необходимо ли обновлять удаленные почтовые ящики в локальном источнике после перемещения?**

Да, следует обновить targetAddress (RemoteRoutingAddress/ExternalEmailAddress) локального источника пользователей, когда исходный почтовый ящик клиента перемещается в целевой клиент.  В то время как маршрутия почты может следовать рефералам для нескольких пользователей почты с различными targetAddresses, бесплатные/загруженные запросы для пользователей почты должны быть ориентированы на расположение пользователя почтового ящика. Free/Busy lookups не будет преследовать несколько перенаправлений. 

**Перенос Teams с перекрестным клиентом?**  

Собрания будут перемещаться, Teams URL-адрес собрания не обновляется при переносе элементов поперемя клиента. Так как URL-адрес будет недействительным в целевом клиенте, необходимо удалить и воссоздать Teams собрания.

**Миграция Teams папки чата с перекрестным клиентом?**  

Нет, содержимое Teams папки чата не переносит перекрестный клиент.  

**Как я могу видеть только перемещения, которые являются перемещениями с перекрестным клиентом, а не перемещениями с борта и вне посадки?**

Используйте `-flags` параметр. Пример:

```powershell
Get-MoveRequest -Flags "CrossTenant"  
```

**Можете ли вы привести примеры сценариев копирования атрибутов, используемых при тестировании?**

> [!Note]
> ПРИМЕР — КАК ЕСТЬ, БЕЗ ГАРАНТИИ<br/>Этот сценарий предполагает подключение как к исходным почтовым ящикам (для получения исходных значений), так и к целевым локальному домену Active Directory Services (для штамповки объекта ADUser). Если в источнике включено судебное разбирательство или включено восстановление одного элемента, установите это в учетной записи назначения.  Это увеличит размер учетной записи контейнера до 100 ГБ.

```powershell
#Dumps out the test mailboxes from SourceTenant 
#Note, the filter applied on Get-Mailbox is for an attribute set on CustomAttribute1 = "ProjectKermit" 
#These are the ‘target’ users to be moved to the Northwind org tenant #################################################################  
$outFileUsers = "$home\desktop\userstomigrate.txt"
$outFileUsersXML = "$home\desktop\userstomigrate.xml"
#output the test objects 
Get-Mailbox -Filter "CustomAttribute1 -like 'ProjectKermit'" -ResultSize Unlimited | Select-Object -ExpandProperty Alias | Out-File $outFileUsers
$mailboxes = Get-Content $outFileUsers
$mailboxes | ForEach-Object {Get-Mailbox $_} | Select-Object PrimarySMTPAddress,Alias,SamAccountName,FirstName,LastName,DisplayName,Name,ExchangeGuid,ArchiveGuid,LegacyExchangeDn,EmailAddresses | Export-Clixml $outFileUsersXML

################################################################# 
#Copy the file $outfile to the desktop of the target on-premises 
#then run the below to create MEU in Target 
#################################################################  
$mailboxes = Import-Clixml $home\desktop\userstomigrate.xml

foreach ($m in $mailboxes) {
    $organization = "@contoso.onmicrosoft.com"
    $mosi = $m.Alias+$organization
    $Password = [System.Web.Security.Membership]::GeneratePassword(16,4) | ConvertTo-SecureString -AsPlainText -Force
    $x500 = "x500:" +$m.LegacyExchangeDn
    $tmpUser = New-MailUser -MicrosoftOnlineServicesID $mosi -PrimarySmtpAddress $mosi -ExternalEmailAddress $m.PrimarySmtpAddress -FirstName $m.FirstName -LastName $m.LastName -Name $m.Name -DisplayName $m.DisplayName -Alias $m.Alias -Password $Password
    $tmpUser | Set-MailUser -EmailAddresses @{add=$x500} -ExchangeGuid $m.ExchangeGuid -ArchiveGuid $m.ArchiveGuid -CustomAttribute1 "ProjectKermit"
    $tmpx500 = $m.EmailAddresses | ?{$_ -match "x500"}
    $tmpx500 | %{Set-MailUser $m.Alias -EmailAddresses @{add="$_"}}
    }

################################################################# 
# On AADSync machine, run AADSync 
#################################################################  
Start-ADSyncSyncCycle 
 
#AADSync and FWDSync will create the target MEUs in the Target tenant 
```
**Как получить доступ Outlook 1-й день после перемещении почтового ящика?**

Так как только один клиент может владеть доменом, прежний основной SMTPAddress не будет связан с пользователем в целевом клиенте по завершению перемещения почтового ящика; только те домены, связанные с новым клиентом. Outlook для проверки подлинности службы использует новый upN пользователей, а профиль Outlook ожидает найти устаревший основной SMTPAddress, чтобы соответствовать почтовому ящику в целевой системе. Так как устаревший адрес не находится в целевой системе, профиль outlook не подключается для поиска вновь перемещенного почтового ящика. 

Для этого начального развертывания пользователям потребуется восстановить свой профиль с помощью нового upN- основного SMTP-адреса и повторной синхронизации содержимого OST. 

> [!Note]
> Планирование, соответственно, при пакете ваших пользователей для завершения. Необходимо учитывать использование сети и емкость, когда Outlook клиентские профили и последующие файлы OST и OAB загружаются клиентам. 
 
**Какие Exchange RBAC мне нужно быть участником, чтобы настроить или завершить перемещение по клиенту?**
 
Существует матрица ролей, основанная на предположении делегирования обязанностей при выполнении перемещения почтового ящика. В настоящее время требуется две роли:  

- Первая роль — это разовая задача установки, которая устанавливает авторизацию перемещения контента в или из вашей границы клиента или организации. Так как перемещение данных из системы управления организацией является критически важной проблемой для всех компаний, мы выбрали наивысшую роль администратора организации (OrgAdmin). Эта роль должна изменить или настроить новый корабль OrganizationRelationship, который определяет функцию -MailboxMoveCapability с удаленной организацией. Только OrgAdmin может изменить параметр MailboxMoveCapability, а другие атрибуты в OrganizationRelationhip могут управляться администратором Федеративного совместного доступа. 
 
- Роль выполнения фактических команд перемещения может быть делегирована на функцию более низкого уровня. Роли почтовых ящиков Move назначена возможность перемещения почтовых ящиков в организации или из организации с помощью `-RemoteTenant` параметра.  

**Как выбрать адрес SMTP для targetAddress (TargetDeliveryDomain) в преобразованном почтовом ящике (для преобразования MailUser)?**
 
Exchange почтовый ящик перемещается с помощью mrs craft targetAddress на исходном исходном почтовом ящике при преобразовании в MailUser путем совпадения адреса электронной почты (proxyAddress) на целевом объекте. Этот процесс принимает значение -TargetDeliveryDomain, переданное в команду перемещения, а затем проверяет соответствие прокси-сервера для этого домена на целевой стороне. При поиске совпадения для объекта ExternalEmailAddress (targetAddress) для преобразованного почтового ящика (теперь MailUser) используется совпадающий прокси-сервер.
 
**Как переход разрешений почтовых ящиков?**

Разрешения почтовых ящиков включают отправку от имени и доступ к почтовым ящикам: 

- Отправка от имени (AD:publicDelegates) хранит DN получателей с доступом к почтовому ящику пользователя в качестве делегата. Это значение хранится в Active Directory и в настоящее время не перемещается в рамках перехода почтового ящика. Если исходный почтовый ящик имеет набор publicDelegates, необходимо будет перенастроить общедоступныеDelegates на целевом почтовом ящике после завершения преобразования MEU для почтовых ящиков в целевой среде с помощью запуска `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` . 
 
- Разрешения почтовых ящиков, хранимые в почтовом ящике, будут перемещаться вместе с почтовым ящиком при перемещении основного и делегата в целевую систему. Например, пользователю TestUser_7 fullAccess для почтового ящика TestUser_8 в клиентской SourceCompany.onmicrosoft.com. После завершения перемещения почтового ящика TargetCompany.onmicrosoft.com в целевом каталоге устанавливаются те же разрешения. Ниже показаны примеры *использования Get-MailboxPermission* для TestUser_7 как в исходных, так и в целевых клиентах. Exchange будут префиксы с исходным и целевым соответственно. 
 
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
> Почтовый ящик и разрешения календаря между клиентом не поддерживаются. Необходимо упорядочить директоров и делегатов в консолидированные пакеты перемещения, чтобы эти подключенные почтовые ящики одновременно перемещались из основного клиента. 

**Какой прокси-сервер X500 должен быть добавлен в целевые прокси-адреса MailUser для обеспечения миграции?**  

Миграция почтовых ящиков между клиентами требует, чтобы значение LegacyExchangeDN объекта исходных почтовых ящиков было штампована как адрес электронной почты x500 на целевом объекте MailUser.  

Пример.  
```powershell
LegacyExchangeDN value on source mailbox is:  
/o=First Organization/ou=Exchange Administrative Group(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara  

so the x500 email address to be added to target MailUser object would be:  
x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9-Lara  
```

> [!Note]  
> В дополнение к прокси-серверу X500 необходимо скопировать все прокси-серверы X500 из почтового ящика в источнике в почтовый ящик в целевом.  

**Где начать устранение неполадок, если ходы не работают?**  

Начните с запуска VerifySetup.ps1, расположенного [на](https://github.com/microsoft/cross-tenant/releases/tag/Preview) GitHub, и просмотрите вывод.

Вот пример запуска VerifySetup.ps1 целевого клиента:

```powershell
VerifySetup.ps1 -PartnerTenantId <SourceTenantId> -ApplicationId <AADApplicationId> -ApplicationKeyVaultUrl <appKeyVaultUrl> -PartnerTenantDomain <PartnerTenantDomain> -Verbose
```

Вот eExample запуска VerifySetup.ps1 клиента источника:

```powershell
VerifySetup.ps1 -PartnerTenantId <TargetTenantId> -ApplicationId <AADApplicationId>
```

**Может ли источник и целевой клиент использовать одно и то же доменное имя?**  

Нет. Имена доменов источника и целевого клиента должны быть уникальными. Например, исходный домен contoso.com и целевой домен fourthcoffee.com.

**Будут ли общие почтовые ящики двигаться и работать?**

Да, однако мы храним только разрешения магазина, как описано в этих статьях:

- [Microsoft Docs | Управление разрешениями для получателей в Exchange Online](/exchange/recipients-in-exchange-online/manage-permissions-for-recipients)

- [Поддержка Майкрософт | Предоставление разрешений Exchange и Outlook почтовых ящиков в Office 365 выделенных](https://support.microsoft.com/topic/how-to-grant-exchange-and-outlook-mailbox-permissions-in-office-365-dedicated-bac01b2c-08ff-2eac-e1c8-6dd01cf77287)

**Требуется ли хранилище ключей Azure и когда будут сделаны транзакции?**  

Да, подписка Azure необходима для хранения сертификата для авторизации миграции с помощью Key Vault. В отличие от переноса бортовых данных, в которых для проверки подлинности & имя пользователя используется пароль для проверки подлинности источника, миграции почтовых ящиков между клиентами используют OAuth и этот сертификат в качестве секрета/учетных данных. Доступ к хранилище ключей должен поддерживаться во всех миграциях почтовых ящиков, поскольку к нему можно получить доступ один раз в начале и после окончания миграции, а также один раз в 24 часа во время постепенной синхронизации. Сведения о стоимости AKV можно просмотреть [здесь.]( https://azure.microsoft.com/en-us/pricing/details/key-vault/)  

**Есть ли у вас рекомендации для пакетов?**  

Не превышать 2000 почтовых ящиков на одну партию. Мы настоятельно рекомендуем отправку пакетов за две недели до даты среза, так как при синхронизации конечным пользователям не будет никакого влияния. Если вам нужно руководство для почтовых ящиков с количеством более 50 000, вы можете связаться со списком рассылки инженерных отзывов по crosstenantmigrationpreview@service.microsoft.com.

**Что делать, если я использую шифрование службы с ключом клиента?**

Перед перемещением почтовый ящик будет расшифровываться. Убедитесь, что клиентский ключ настроен в целевом клиенте, если он по-прежнему требуется. [Дополнительные](../compliance/customer-key-overview.md) сведения см. здесь.  

**Какое предполагаемое время миграции?**

Чтобы помочь вам спланировать [](/exchange/mailbox-migration/office-365-migration-best-practices#estimated-migration-times) миграцию, в таблице, которая представлена здесь, показаны рекомендации о том, когда следует ожидать массовых миграций почтовых ящиков или отдельных миграций. Эти оценки основаны на анализе данных предыдущих миграций клиентов. Поскольку каждая среда уникальна, то точная скорость миграции может отличаться.  

Помните, что эта функция в настоящее время находится в предварительном просмотре, а SLA и любые применимые уровни служб не применяются к любым вопросам производительности или доступности во время предварительного просмотра этой функции.

## <a name="known-issues"></a>Известные проблемы  

-  **Проблема. Автоматические расширенные архивы не могут быть перенесены.** Функция перекрестной миграции клиента поддерживает миграции основного почтового ящика и архивного почтового ящика для определенного пользователя. Если у пользователя в источнике, однако, есть автоматический расширенный архив, то есть несколько архивных почтовых ящиков, функция не сможет перенести дополнительные архивы и должна выйти из строя.

- **Проблема. Облачные mailUsers с невладными smtp proxyAddress блок MRS перемещает фон.** При создании объектов целевого клиента MailUser необходимо убедиться, что все прокси-адреса SMTP принадлежат целевой организации-клиента. Если прокси-сервер SMTP существует на целевом пользователе почты, который не принадлежит локальному клиенту, преобразование MailUser в почтовый ящик предотвращается. Это связано с нашей гарантией того, что объекты почтовых ящиков могут отправлять почту только из доменов, для которых клиент является авторитетным (домены, заявленные клиентом): 

   - Когда вы синхронизируете пользователей с локальной помощью Azure AD Подключение, вы в качестве домена, расположенного в целевом клиенте (Lara.Newton@northwind.com), ввести локальное предоставление объектов MailUser с помощью ExternalEmailAd laran@contoso.onmicrosoft.com dress. Эти значения синхронизируются с клиентом, и соответствующий пользователь почты готов и готов к миграции. Пример объекта показан здесь.
     ```powershell
     target/AADSynced user] PS C> Get-MailUser laran | select ExternalEmailAddress, EmailAddresses   
     ExternalEmailAddress               EmailAddresses 
     --------------------               -------------- 
     SMTP:laran@contoso.onmicrosoft.com {SMTP:lara.newton@northwind.com} 
     ```

   > [!Note]
   > Адрес *contoso.onmicrosoft.com* не *присутствует* в массиве EmailAddresses/proxyAddresses.

- **Проблема: объекты MailUser с "внешними" основными SMTP-адресами изменены или сброшены на "внутренние" заявленные домены компании**

   Объекты MailUser являются указателями на не локальные почтовые ящики. В случае переноса почтовых ящиков между клиентами мы используем объекты MailUser для представления источника почтового ящика (с точки зрения целевой организации) или целевого почтового ящика (с точки зрения организации-источника). У mailUsers будет внешнийEmailAddress (targetAddress), который указывает на smtp-адрес фактического почтового ящика (ProxyTest@fabrikam.onmicrosoft.com) и основной SMTP-адрес, который представляет отображаемую SMTP-адрес пользователя почтового ящика в каталоге. Некоторые организации предпочитают отображать основной SMTP-адрес в качестве внешнего SMTP-адреса, а не как адрес, который принадлежит локальному клиенту (например, fabrikam.com, а не как contoso.com).  Однако после того как объект Exchange плана службы применяется к MailUser с помощью операций лицензирования, основной smTP-адрес изменен, чтобы показать его как домен, проверенный локальной организацией (contoso.com). Существует две возможные причины:
   
   - При применении Exchange службы к MailUser процесс Azure AD начинает применять очистку прокси-серверов, чтобы убедиться, что местная организация не может отправлять почту, подмену или почту от другого клиента. Любой SMTP-адрес объекта получателя с этими планами службы будет удален, если адрес не будет проверен локальной организацией. Как и в примере, Fabikam.com не проверяется клиентом contoso.onmicrosoft.com, поэтому очистка удаляет fabrikam.com домена. Если вы хотите сохранить этот внешний домен в MailUser до миграции или после миграции, вам необходимо изменить процессы миграции, чтобы лишить лицензии после завершения перемещения или до перехода, чтобы убедиться, что пользователи должны применяться внешние брендинги. Необходимо убедиться, что объект почтового ящика имеет правильную лицензию, чтобы не влиять на службу почты.<br/><br/>Пример сценария удаления планов службы в MailUser в Contoso.onmicrosoft.com показан здесь.

    ```powershell
    $LO = New-MsolLicenseOptions -AccountSkuId "contoso:ENTERPRISEPREMIUM" DisabledPlans 
    "LOCKBOX_ENTERPRISE","EXCHANGE_S_ENTERPRISE","INFORMATION_BARRIERS","MIP_S_CLP2","
    MIP_S_CLP1","MYANALYTICS_P2","EXCHANGE_ANALYTICS","EQUIVIO_ANALYTICS","THREAT_INTE
    LLIGENCE","PAM_ENTERPRISE","PREMIUM_ENCRYPTION" 
    Set-MsolUserLicense -UserPrincipalName proxytest@contoso.com LicenseOptions $lo 
    ```

       Результаты в наборе назначенных ServicePlans показаны здесь.

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
 
       Первичный интерфейс primarySMTPAddress пользователя больше не будет очисткой. Домен fabrikam.com не принадлежит клиенту contoso.onmicrosoft.com и будет сохраняться в качестве основного SMTP-адреса, показанного в каталоге.

       Пример:

    ```powershell
    get-recipient proxytest | ft -a userprin*, primary*, external*   
    PrimarySmtpAddress        ExternalDirectoryObjectId               ExternalEmailAddress 
    ------------------        -------------------------               -------------------- 
    proxytest@fabrikam.com    e2513482-1d5b-4066-936a-cbc7f8f6f817    SMTP:proxytest@fabrikam.com 
    ```

   - Когда msExchRemoteRecipientType задает 8 (DeprovisionMailbox), для локального mailUsers, которые переносились в целевой клиент, логика очистки прокси в Azure удаляет бесхозные домены и сбрасывает первичные ДОМЕНЫ в собственный домен. Очищая msExchRemoteRecipientType в локальном MailUser, логика прокси-очистки больше не применяется. <br/><br>Ниже приведен полный набор возможных планов обслуживания, которые включают Exchange Online.

   | Имя                                              |
   |---------------------------------------------------|
   | Advanced eDiscovery служба хранилища (500 ГБ)               |
   | Защищенное хранилище                                  |
   | Защита от потери данных                              |
   | Exchange Enterprise cal Services (EOP, DLP)       |
   | Exchange Основные                               |
   | Exchange Foundation                               |
   | Exchange Online (P1)                              |
   | Exchange Online (план 1)                          |
   | Exchange Online (план 2)                          |
   | Exchange Online Archiving для Exchange Online     |
   | Exchange Online Archiving для Exchange Server     |
   | Exchange Online Неактивное пользовательское надстройка              |
   | Базовая подписка на Exchange Online                             |
   | Exchange Online с поддержкой нескольких регионов                         |
   | Exchange Online (план 1)                            |
   | Exchange Online POP                               |
   | Exchange Online Protection                        |
   | Информационные барьеры                              |
   | Защита данных для Office 365 — Premium   |
   | Защита данных для Office 365 — Standard  |
   | Сведения по MyAnalytics                           |
   | Microsoft 365 Расширенный аудит                   |
   | Microsoft Bookings                                |
   | Microsoft Business Center                         |
   | Microsoft MyAnalytics (полнофункциональная версия)                      |
   | Office 365 Advanced eDiscovery                    |
   | Защитник Майкрософт для Office 365 (план 1)    |
   | Защитник Майкрософт для Office 365 (План 2)    |
   | Office 365 Privileged Access Management           |
   | Premium Шифрование в Office 365                  |
