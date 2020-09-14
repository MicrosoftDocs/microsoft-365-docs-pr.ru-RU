---
title: Настройка новых возможностей шифрования сообщений
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/30/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 7ff0c040-b25c-4378-9904-b1b50210d00e
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Узнайте о новых возможностях шифрования сообщений Office 365, позволяющих защитить переписку с людьми внутри и за пределами вашей организации.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4102611d3be43a5bedffc83fba5c83c0b648ca42
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547621"
---
# <a name="set-up-new-message-encryption-capabilities"></a>Настройка новых возможностей шифрования сообщений

Новые возможности шифрования сообщений в Office 365 (OME) позволяют организациям обмениваться защищенными сообщениями с кем угодно с любого устройства. Пользователи могут обмениваться защищенными сообщениями с другими организациями Microsoft 365, а также с сотрудниками других организаций, использующих Outlook.com, Gmail и прочие почтовые службы.

Чтобы убедиться, что новые возможности OME доступны в вашей организации, выполните указанные ниже действия.

## <a name="verify-that-azure-rights-management-is-active"></a>Проверьте, активна ли служба Azure Rights Management

Новые возможности OME используют функции защиты в [службе управления правами Azure (Azure RMS)](https://docs.microsoft.com/azure/information-protection/what-is-information-protection) — технологию, используемую службой [Azure Information Protection](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms) для защиты электронной почты и документов с помощью шифрования и управления доступом.

Единственное обязательное условие для использования новых возможностей OME — [служба управления правами Azure](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms) должна быть активирована в клиенте вашей организации. Если это так, Microsoft 365 автоматически активирует новые возможности OME, а от вас не потребуется никаких действий.

Кроме того, служба Azure RMS автоматически активируется для большинства соответствующих планов. В этом случае от вас тоже не потребуется никаких действий. Дополнительные сведения см. в статье [Активация службы управления правами Azure](https://docs.microsoft.com/azure/information-protection/activate-service).

>[!IMPORTANT]
>Если вы используете службу управления правами Active Directory (AD RMS) в Exchange Online, перед использованием новых возможностей OME необходимо [перейти на службу Azure Information Protection](https://docs.microsoft.com/azure/information-protection/migrate-from-ad-rms-to-azure-rms). Служба OME не совместима с AD RMS.  

Дополнительные сведения см. в указанных ниже статьях.

- [Какие подписки необходимо использовать для новых возможностей OME?](ome-faq.md#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities) Эта статья поможет вам убедиться, что ваш план подписки включает службу Azure Information Protection (которая включает функции Azure RMS).
- Сведения о приобретении соответствующей подписки см. в статье [Azure Information Protection](https://azure.microsoft.com/services/information-protection/).  

### <a name="manually-activating-azure-rights-management"></a>Активация службы управления правами Azure вручную

Если вы отключили службу Azure RMS или по какой-либо причине она не была активирована автоматически, вы можете активировать ее вручную, используя одно из указанных ниже средств.

- **Центр администрирования Microsoft 365**. Инструкции см. в статье [Активация службы управления правами Azure в Центре администрирования](https://docs.microsoft.com/azure/information-protection/activate-office365).
- **Портал Azure**. Инструкции см. в статье [Активация службы управления правами Azure на портале Azure](https://docs.microsoft.com/azure/information-protection/activate-azure).

## <a name="configure-management-of-your-azure-information-protection-tenant-key"></a>Настройка управления ключом клиента для службы Azure Information Protection

Это действие не является обязательным. По умолчанию корпорации Майкрософт разрешено управлять корневым ключом для службы Azure Information Protection. Этот вариант рекомендуется для большинства организаций. В таком случае от вас не требуется никаких действий.

Существует множество причин, по которым вам может потребоваться создать собственный корневой ключ (BYOK), а также управлять им, например для обеспечения соответствия требованиям. В таком случае перед настройкой новых возможностей OME рекомендуется выполнить необходимые действия. Дополнительные сведения см. в статье [Планирование и реализация ключа клиента Azure Information Protection](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key).

## <a name="verify-new-ome-configuration-in-exchange-online-powershell"></a>Проверка новой конфигурации OME в Exchange Online PowerShell

Вы можете убедиться, что клиент Microsoft 365 настроен для использования новых возможностей OME, с помощью [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell).
  
1. [Подключитесь к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) с помощью учетной записи с разрешениями глобального администратора в клиенте Microsoft 365.

2. Запустите командлет Get-IRMConfiguration.

     Для параметра AzureRMSLicensingEnabled должно быть задано значение $True, указывающее, что в клиенте настроены возможности OME. В противном случае используйте командлет Set-IRMConfiguration, чтобы задать для параметра AzureRMSLicensingEnabled значение $True и включить OME.

3. Запустите командлет Test-IRMConfiguration, используя приведенный ниже синтаксис.

     ```powershell
     Test-IRMConfiguration [-Sender <email address >]
     ```  

   **Пример**.

     ```powershell
     Test-IRMConfiguration -Sender securityadmin@contoso.com
     ```

     - Указывать электронный адрес отправителя необязательно, но это позволит системе выполнить дополнительные проверки. Используйте электронный адрес любого пользователя в клиенте Microsoft 365.

     Результаты должны выглядеть примерно так:

     ```text
     Results : Acquiring RMS Templates ...
                - PASS: RMS Templates acquired.  Templates available: Contoso  - Confidential View Only, Contoso  - Confidential, Do Not
            Forward.
            Verifying encryption ...
                - PASS: Encryption verified successfully.
            Verifying decryption ...
                - PASS: Decryption verified successfully.
            Verifying IRM is enabled ...
                - PASS: IRM verified successfully.

            OVERALL RESULT: PASS
     ```

   - Название вашей организации заменит *Contoso*.

   - Заданные по умолчанию имена шаблонов могут отличаться от указанных выше. Дополнительные сведения см. в статье [Настройка шаблонов для Azure Information Protection и управление ими](https://docs.microsoft.com/azure/information-protection/configure-policy-templates).

4. Выполните командлет Remove-PSSession, чтобы отключиться от службы управления правами.

     ```powershell
     Remove-PSSession $session
     ```

## <a name="next-steps-define-mail-flow-rules-to-use-new-ome-capabilities"></a>Дальнейшие действия: определение правил потока обработки почты для использования новых возможностей OME

Если правила потока обработки почты для шифрования почты в организации уже настроены, то для использования новых возможностей OME их необходимо обновить. Для выполнения новых развертываний необходимо создать новые правила потока обработки почты.

>[!IMPORTANT]
>Если не обновить существующие правила потока обработки почты, пользователи будут и дальше получать зашифрованные сообщения с вложениями в формате HTML без новых возможностей OME.

Правила потока обработки почты определяют, при каких условиях нужно шифровать электронную почту, а также условия для отмены такого шифрования. Если задать действие для правила, все сообщения, которые удовлетворяют его условиям, будут шифроваться при отправке.
  
Дополнительные сведения о создании правил потока обработки почты для OME см. в статье [Определение правил потока обработки почты для шифрования сообщений в Office 365](define-mail-flow-rules-to-encrypt-email.md).

Чтобы обновить существующие правила и использовать новые возможности OME, выполните указанные ниже действия.

1. В Центре администрирования Microsoft 365 выберите пункты **Центры администрирования > Exchange**.
2. В Центре администрирования Exchange выберите **Поток обработки почты > Правила**.
3. Повторите представленную ниже процедуру для каждого правила в разделе **Выполнить следующие действия**.
    - Выберите **Изменить безопасность сообщения**.
    - Выберите **Применить шифрование сообщений Office 365 и защиту с помощью прав**.
    - Выберите шаблон RMS из списка.
    - Нажмите кнопку **Сохранить**.
    - Нажмите кнопку **ОК**.
