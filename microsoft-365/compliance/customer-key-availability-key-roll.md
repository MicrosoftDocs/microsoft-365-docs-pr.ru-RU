---
title: Смена или ротация ключа клиента или ключа доступности
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/05/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Узнайте, как свернуть корневые ключи клиента, хранимые в хранилище Azure Key Vault, которые используются с ключом клиента. Службы включают файлы Exchange Online, Skype для бизнеса, SharePoint Online, OneDrive для бизнеса и Teams.
ms.openlocfilehash: 29a36636253f5f01181f231941d0c3a9e26abacc
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633646"
---
# <a name="roll-or-rotate-a-customer-key-or-an-availability-key"></a>Смена или ротация ключа клиента или ключа доступности

> [!CAUTION]
> Откат ключа шифрования, который вы используете с ключом клиента, только в том случае, если требования безопасности и соответствия требованиям определяют необходимость его ската. Кроме того, не удаляйте ключи, связанные с политиками. При откате ключей содержимое будет зашифровано с помощью предыдущих ключей. Например, хотя активные почтовые ящики часто шифруются повторно, неактивные, отключенные и отключенные почтовые ящики могут по-прежнему шифроваться с помощью предыдущих ключей. SharePoint Online выполняет резервное копирование контента в целях восстановления и восстановления, поэтому может по-прежнему архивироваться контент с использованием старых ключей.

## <a name="about-rolling-the-availability-key"></a>Развертывание ключа доступности

Корпорация Майкрософт не предоставляет клиентам прямое управление ключом доступности. Например, вы можете свернуть (поворачивать) только ключи, которые вы владеете в Azure Key Vault. Microsoft 365 перекатит ключи доступности по внутренне определенному расписанию. Для этих ключевых ключей не существует соглашения об уровне обслуживания с клиентом. Microsoft 365 поворачивает ключ доступности с помощью кода службы Microsoft 365 в автоматическом, не ручном процессе. Администраторы Майкрософт могут инициировать процесс ската. Ключ свернут с помощью автоматизированных механизмов без прямого доступа к хранилище ключей. Доступ к окнам секрета ключа доступности не предусмотрен для администраторов Майкрософт. Накат ключа доступности использует тот же механизм, который использовался для первоначального создания ключа. Дополнительные сведения о ключе доступности см. в [этой теме.](customer-key-availability-key-understand.md)

> [!IMPORTANT]
> Ключи доступности Exchange Online и Skype для бизнеса могут эффективно перекатываться клиентами, создав новую технологию DEP, так как для каждого создаваемого DEP создается уникальный ключ доступности. Ключи доступности для файлов SharePoint Online, OneDrive для бизнеса и Teams существуют на уровне леса и являются общими для dePs и клиентов, что означает, что развертывание происходит только по внутренне определенному графику Майкрософт. Чтобы снизить риск того, что ключ доступности не будет развертываться каждый раз, когда будет создан новый DEP, SharePoint, OneDrive и Teams будут развертывать промежуточный ключ клиента (TIK), ключ, завернутый корневыми ключами клиента и ключом доступности, каждый раз, когда создается новая DEP.

## <a name="request-a-new-version-of-each-existing-root-key-you-want-to-roll"></a>Запрос новой версии каждого существующего корневого ключа, который необходимо свернуть

При откате ключа запрашивается новая версия существующего ключа. Чтобы запросить новую версию существующего ключа, используйте тот же самый cmdlet, [Add-AzKeyVaultKey,](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey)с тем же синтаксисом, который использовался для создания ключа в первую очередь. Завершив развертывание любого ключа, связанного с политикой шифрования данных (DEP), запустите другой cmdlet, чтобы убедиться, что ключ клиента начинает использовать новый ключ. Сделайте это на каждом этапе Azure Key Vault (AKV).

Пример:

1. Sign in to your Azure subscription with Azure PowerShell. Инструкции см. в [документе "Вход с помощью Azure PowerShell".](https://docs.microsoft.com/powershell/azure/authenticate-azureps)

2. Запустите Add-AzKeyVaultKey, как показано в следующем примере:

   ```powershell
   Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
   ```

   В этом примере, так как в хранилище **Contoso-O365EX-NA-VaultA1-Key001** существует ключ с именем **Contoso-O365EX-NA-VaultA1,** он создает новую версию ключа. Эта операция сохраняет предыдущие основные версии ключа в истории версий. Для расшифровки данных, которые она по-прежнему шифрует, необходима предыдущая версия ключа. Завершив развертывание любого ключа, связанного с DEP, выполните дополнительный cmdlet, чтобы убедиться, что ключ клиента начинает использовать новый ключ. В следующих разделах эти cmdlets описываются более подробно.
  
## <a name="update-the-customer-key-for-exchange-online-and-skype-for-business"></a>Обновление ключа клиента для Exchange Online и Skype для бизнеса

При откате любого из ключей Azure Key Vault, связанных с DEP, используемым с Exchange Online и Skype для бизнеса, необходимо обновить DEP, чтобы указать на новый ключ. Это не повернет клавишу доступности.

Чтобы поручить ключу клиента использовать новый ключ для шифрования почтовых ящиков, выполните Set-DataEncryptionPolicy следующим образом:

1. Запустите Set-DataEncryptionPolicy в Azure PowerShell:
  
   ```powershell
   Set-DataEncryptionPolicy -Identity <DataEncryptionPolicyID> -Refresh
   ```

   В течение 72 часов активные почтовые ящики, связанные с этим DEP, шифруются с помощью нового ключа.

2. Чтобы проверить значение свойства DataEncryptionPolicyID для почтового ящика, воспользуйтесь действиями в области "Определение DEP, назначенного [почтовому ящику".](customer-key-manage.md#determine-the-dep-assigned-to-a-mailbox) Значение этого свойства изменяется после того, как служба применяет обновленный ключ.
  
## <a name="update-the-customer-key-for-sharepointonlineonedriveforbusinessandteamsfiles"></a>Обновление ключа клиента для файлов SharePoint Online, OneDrive для бизнеса и Teams

SharePoint Online позволяет одновременно откатывать только по одной клавише. Если вы хотите откатить оба ключа в хранилище ключей, дождись завершения первой операции. Во избежание этой проблемы корпорация Майкрософт рекомендует вам поочередать операции. При откате любого из ключей Azure Key Vault, связанных с DEP, используемым с SharePoint Online и OneDrive для бизнеса, необходимо обновить DEP, чтобы указать на новый ключ. Это не повернет клавишу доступности.

1. Выполните Update-SPODataEncryptionPolicy следующим образом:
  
   ```powershell
   Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
   ```

   Хотя этот cmdlet запускает операцию переката ключей для SharePoint Online и OneDrive для бизнеса, действие не завершается немедленно.

2. Чтобы увидеть ход выполнения операции переката ключей, выполните Get-SPODataEncryptionPolicy следующим образом:

   ```powershell
   Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
   ```

## <a name="related-articles"></a>Статьи по теме

- [Шифрование службы с помощью ключа клиента для Office 365](customer-key-overview.md)

- [Настройка ключа клиента для Office 365](customer-key-set-up.md)

- [Управление ключом клиента для Office 365](customer-key-manage.md)

- [Узнайте о ключе доступности](customer-key-availability-key-understand.md)
