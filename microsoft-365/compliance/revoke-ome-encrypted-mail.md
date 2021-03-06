---
title: Отзовет электронную почту, шифруемую с помощью предварительного шифрования сообщений
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 06/11/2020
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: Как администратор и отправитель сообщений можно отослать некоторые электронные сообщения, зашифрованные с помощью Расширенное шифрование сообщений Office 365.
ms.openlocfilehash: 340a9e73dba50e28223ee561db749a089c649df6
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051721"
---
# <a name="revoke-email-encrypted-by-advanced-message-encryption"></a>Отзовет электронную почту, шифруемую с помощью предварительного шифрования сообщений

Отзыв электронной почты предлагается в рамках Расширенное шифрование сообщений Office 365. Расширенное шифрование сообщений Office 365 входит в Microsoft 365 корпоративный [E5,](https://www.microsoft.com/microsoft-365/enterprise/home)Office 365 E5, Microsoft 365 E5 (некоммерческие цены персонала), Office 365 корпоративный E5 (некоммерческие цены персонала) и Office 365 для образования A5. Если в вашей организации есть подписка, не включаемая Расширенное шифрование сообщений Office 365, ее можно приобрести с надстройки Соответствие требованиям Microsoft 365 E5 SKU для Microsoft 365 E3, Microsoft 365 E3 (некоммерческие цены на персонал) или надстройки Office 365 Advanced Compliance SKU для Microsoft 365 E3, Microsoft 365 E3 (некоммерческие цены персонала) или Office 365 SKUs.

Эта статья является частью более крупной серии статей о шифрование сообщений Office 365 [.](ome.md)

Если сообщение было зашифровано с Расширенное шифрование сообщений Office 365, а вы администратор Microsoft 365 или отправитель сообщения, вы можете отослать сообщение при определенных условиях. Администраторы отзовет сообщения с помощью PowerShell. Отправитель отзовет сообщение, отправленное непосредственно из Outlook в Интернете. В этой статье описываются обстоятельства, при которых возможно отозов, и как это сделать.
  
## <a name="encrypted-emails-that-you-can-revoke"></a>Зашифрованные сообщения электронной почты, которые можно отоискить

Администраторы и отправители сообщений могут отослать зашифрованные сообщения, если получатель получил зашифрованную электронную почту на основе ссылок. Если получатель получил родной inline-опыт в поддерживаемом клиенте Outlook, вы не можете отоокить сообщение.

Независимо от того, получает ли получатель опыт на основе ссылок или в линию, зависит от типа удостоверения получателя: Office 365 и получатели учетных записей Майкрософт (например, outlook.com пользователей) получают рядное впечатление в поддерживаемых Outlook клиентах. Все другие типы получателей, такие как получатели Gmail и Yahoo, получают ссылку.

Администраторы и отправители сообщений могут отослать зашифрованные сообщения с помощью шифрования, примененного непосредственно Outlook в Интернете. Например, сообщения, зашифрованные с помощью параметра Шифровать только.

:::image type="content" source="../media/adhocencryptionrevoke.png" alt-text="Снимок экрана, показывающий параметр Шифровать Outlook в Интернете.":::

## <a name="recipient-experience-for-revoked-encrypted-emails"></a>Опыт получателей для отозванных зашифрованных сообщений электронной почты

После отзыва электронной почты получатель получает ошибку при доступе к зашифрованной электронной почте через портал шифрование сообщений Office 365: "Сообщение было отозвано отправителю".

![Снимок экрана, на который показан отозванный зашифрованный адрес электронной почты.](../media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-message-that-you-sent"></a>Как отоскить зашифрованное сообщение, отправленное

Вы можете отоискить почту, отправленную одному получателю, использующему социальную учетную запись, например gmail.com или yahoo.com. Другими словами, вы можете отоискить сообщение электронной почты, отправленное одному получателю, который получил ссылку.

Нельзя отоскить почту, отправленную получателю, использующему учетную запись в Office 365 или Microsoft 365 или пользователю, использующему учетную запись Майкрософт, например outlook.com учетную запись. 

Чтобы отоискить отправленное зашифрованное сообщение, выполните эти действия.

1. В Outlook интернете в папке **Sent** просмотрите сообщение, которое необходимо отооперить.

   Если почта отменяется, в верхней части сообщения вы увидите ссылку "Удаление внешнего доступа".

    :::image type="content" source="../media/infoprotect-email-encryption/adhocencryptionrevokesentmsg.png" alt-text="Снимок экрана, показывающий зашифрованную почту, которую Outlook в Интернете.":::

2. Нажмите **кнопку Удалить внешний доступ** для отзова сообщения.

   В сообщении показано, что его состояние отозвано.

   :::image type="content" source="../media/adhocencryptionrevokedmsg.png" alt-text="Снимок экрана, показывающий отозванное зашифрованное сообщение Outlook в Интернете.":::

## <a name="how-to-revoke-an-encrypted-message-as-an-administrator"></a>Как отоскить зашифрованное сообщение в качестве администратора

Microsoft 365 администраторы следуют этим общим шагам, чтобы отоиметь доступную зашифрованную электронную почту:

- Получите ID сообщения электронной почты.
- Убедитесь, что вы можете отоокить сообщение.
- Отзови почту.

### <a name="step-1-obtain-the-message-id-of-the-email"></a>Этап 1. Получение ID сообщения электронной почты

Прежде чем отоискить зашифрованную почту, соберем код сообщения. MessageId обычно имеет формат:

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

Существует несколько способов поиска ID сообщения электронной почты, отозоваемой. В этом разделе описаны несколько вариантов, но вы можете использовать любой метод, который предоставляет ID.

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a>Определение ID сообщения электронной почты, которое необходимо отоискить с помощью трассировки сообщений в Центре соответствия &amp; требованиям безопасности.

1. Поиск электронной почты отправителю или получателю с помощью [New Message Trace в центре & безопасности.](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)

2. После того, как вы найме электронной почты, выберите его, чтобы привести в итоге области сведений **о трассировке** сообщения. **Разойдите дополнительные** сведения, чтобы найти ID сообщения.

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a>Идентификация идентификации сообщения электронной почты, отозоваемой с помощью отчетов Office шифрования сообщений в Центре соответствия &amp; требованиям безопасности

1. В Центре соответствия &amp; требованиям безопасности перейдите к отчету о **шифровании сообщений.** Сведения об этом отчете см. в обзоре отчетов о безопасности электронной почты [в Центре соответствия требованиям &amp; безопасности.](../security/defender-365-security/view-email-security-reports.md)

2. Выберите **таблицу сведений** о представлении и определите сообщение, которое необходимо отоискить.

3. Дважды щелкните сообщение, чтобы просмотреть сведения, включаю в себя ID сообщения.

### <a name="step-2-verify-that-the-mail-is-revocable"></a>Шаг 2. Убедитесь, что почта является отзывной

Чтобы проверить, можно ли отоискить сообщение, проверьте, отображается ли поле "Статус отзыва" в отчете шифрования в таблице Details в Центре соответствия требованиям  &amp; безопасности.

Чтобы проверить, можно ли отоискить определенное сообщение электронной почты с помощью Windows PowerShell, выполните эти действия.

1. С помощью учетной записи работы или школы, которая имеет глобальные разрешения администратора в организации, запустите сеанс Windows PowerShell и подключите к Exchange Online. Инструкции см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Выполните Get-OMEMessageStatus следующим образом:

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   Эта команда возвращает тему сообщения и является ли сообщение отзывным. Пример.

     ```console
     Subject        IsRevocable
     -------        -----------
     "Test message" True
     ```

### <a name="step-3-revoke-the-mail"></a>Этап 3. Отоимка почты

После того, как вы узнаете ID сообщения электронной почты, которое требуется отооскить, и убедились, что сообщение является отзывным, вы можете отоискить сообщение с помощью Центра соответствия требованиям безопасности &amp; или Windows PowerShell.

Для отзова сообщения с помощью Центра соответствия &amp; требованиям безопасности

1. С помощью учетной записи для работы или учебного заведения с глобальными разрешениями администратора в организации подключись к Центру & соответствия требованиям.

2. В **отчете Шифрование** в таблице **Details** для сообщения выберите **сообщение Revoke**.

Для отзова электронной почты с помощью Windows PowerShell используйте Set-OMEMessageRevocation.

1. Используя учетную запись для работы или школы, которая имеет глобальные разрешения администратора в [организации, Подключение Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Выполните Set-OMEMessageRevocation следующим образом:

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. Чтобы проверить, было ли отозвано сообщение, выполните Get-OMEMessageStatus следующим образом:

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    Если отзыв был успешным, этот комдлет возвращает следующий результат:  

     ```console
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a>Дополнительные сведения о Расширенное шифрование сообщений Office 365

- [Расширенное шифрование сообщений Office 365](ome-advanced-message-encryption.md)

- [Расширенное шифрование сообщений Office 365 - срок действия электронной почты](ome-advanced-expiration.md)

- [Описание политики сообщений и службы соответствия требованиям](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)