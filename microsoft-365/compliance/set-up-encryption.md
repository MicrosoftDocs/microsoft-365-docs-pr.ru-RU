---
title: Настройка шифрования в Office 365 корпоративный
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/2/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e86fc991-0161-4f01-9c1c-d25e87733d06
description: С Office 365 некоторые возможности шифрования включены по умолчанию; другие возможности можно настроить для соответствия определенным требованиям или требованиям законодательства.
ms.openlocfilehash: 78831446f3d56f64c05ff2f27e376a609bdd6419
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919485"
---
# <a name="set-up-encryption-in-office-365-enterprise"></a>Настройка шифрования в Office 365 корпоративный

Шифрование может защитить содержимое от чтения несанкционированными пользователями. Поскольку [шифрование в Office 365](encryption.md) можно сделать с помощью различных технологий и методов, не существует ни одного места, где можно включить или настроить шифрование. В этой статье содержится информация о различных способах настройки или настройки шифрования в рамках стратегии защиты информации.
  
> [!TIP]
> Дополнительные технические сведения о шифровании см. в материале [Technical reference details about encryption in Office 365.](technical-reference-details-about-encryption.md)
  
В Office 365 по умолчанию доступно несколько возможностей шифрования. Дополнительные возможности шифрования можно настроить для соответствия определенным требованиям или требованиям законодательства. В следующей таблице описано несколько методов шифрования для различных сценариев.
  
|**Сценарий**|**Методы шифрования**|
|:-----|:-----|
|Файлы сохраняются на компьютерах Windows  <br/> |Шифрование на уровне компьютера можно сделать с помощью BitLocker на устройствах Windows. Как администратор предприятия или ИТ-специалисты вы можете настроить это с помощью службы развертывания Майкрософт набор средств (MDT). См. [в настройках MDT для BitLocker.](/windows/deployment/deploy-windows-mdt/set-up-mdt-for-bitlocker)  <br/> |
|Файлы сохраняются на мобильных устройствах  <br/> |Некоторые виды мобильных устройств шифруют файлы, которые сохраняются на этих устройствах по умолчанию. С помощью возможностей встроенного управления мобильными устройствами для [Office 365](https://support.microsoft.com/en-us/office/capabilities-of-built-in-mobile-device-management-for-microsoft-365-a1da44e5-7475-4992-be91-9ccec25905b0)можно установить политики, определяющее, следует ли разрешить мобильным устройствам доступ к данным в Office 365. Например, можно установить политику, которая позволяет только устройствам, шифруя контент, получать доступ к данным Office 365. См. [в руб. Создание и развертывание политик безопасности устройств.](https://support.microsoft.com/office/create-and-deploy-device-security-policies-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6)  <br/> Дополнительный контроль взаимодействия мобильных устройств с Office 365 можно использовать для добавления [Microsoft Intune.](/mem/intune/fundamentals/setup-steps)  <br/> |
|Необходим контроль над ключами шифрования, используемыми для шифрования данных в центрах обработки данных Майкрософт  <br/> | Будучи администратором Office 365, вы можете управлять ключами шифрования организации, а затем настроить Office 365, чтобы использовать их для шифрования данных в центрах обработки данных Майкрософт.  <br/> [Шифрование службы с помощью ключа клиента в Office 365](customer-key-overview.md) <br/> |
|Люди общаются по электронной почте (Exchange Online)  <br/> | Как администратор Exchange Online у вас есть несколько вариантов настройки шифрования электронной почты. Такие законодательные акты перечислены ниже.  <br/>  Использование шифрования сообщений [Office 365 с](set-up-new-message-encryption-capabilities.md) помощью Azure Rights Management (Azure RMS), чтобы позволить пользователям отправлять зашифрованные сообщения в организации или за ее пределами.  <br/>  Использование [S/MIME для подписания сообщений](../security/office-365-security/s-mime-for-message-signing-and-encryption.md) и шифрования для шифрования и цифрового подписания сообщений электронной почты  <br/>  Использование TLS для [настроить соединители для безопасного потока почты с другой организацией](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner) <br/>  См. [шифрование электронной почты в Office 365](./email-encryption.md).  <br/> |
|Доступ к файлам из сайтов группы или библиотек документов (OneDrive для бизнеса или SharePoint Online)  <br/> |При работе с файлами, сохраненными в OneDrive для бизнеса или SharePoint Online, используются TLS-подключения. Это встроено в Office 365 автоматически. См. [раздел Шифрование данных в OneDrive для бизнеса и SharePoint Online.](./data-encryption-in-odb-and-spo.md)  <br/> |
|Файлы делятся в онлайн-собраниях и беседах по чату (Skype для бизнеса Online)  <br/> |При работе с файлами с помощью Skype для бизнеса Online для подключения используется TLS. Это встроено в Office 365 автоматически. См. в сводке "Безопасность [и архивативка" (Skype для бизнеса в Интернете).](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features)  <br/> |
|Файлы делятся в онлайн-собраниях и беседах по чату (Microsoft Teams)  <br/> |При работе с файлами с помощью Microsoft Teams для подключения используется TLS. Это встроено в Office 365 автоматически. Microsoft Teams в настоящее время не поддерживает отрисовку зашифрованной электронной почты. Чтобы зашифрованная электронная почта не приземлилась в Microsoft Teams как зашифрованная, см. в [faq шифрования сообщений.](./ome-faq.md?view=o365-worldwide#can-i-automatically-remove-encryption-on-incoming-and-outgoing-mail)  <br/> 

## <a name="additional-information"></a>Дополнительные сведения

Дополнительные материалы о решениях защиты файлов, которые включают параметры шифрования, см. в материалах [File Protection Solutions в Office 365.](https://www.microsoft.com/download/details.aspx?id=55523)
