---
title: Синхронизация сертификатов пользователей с Office 365 для S/MIME
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 351c932e-99c1-4512-a6e8-788e90b7838f
description: Чтобы отправлять сообщения, защищенные с помощью S/MIME, необходимо настроить соответствующие сертификаты. Для отправки зашифрованных сообщений через Exchange Online программа электронной почты отправителя использует общедоступный сертификат получателя для шифрования сообщений. Этот общедоступный сертификат X.509 необходимо опубликовать в Office 365.
ms.openlocfilehash: ad58b5663eaadf771ed1518edc01ce2f765f5202
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37091427"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a>Синхронизация сертификатов пользователей с Office 365 для S/MIME

Чтобы пользователи могли отправлять сообщения, защищенные с помощью S/MIME, в Exchange Online, необходимо настроить соответствующие сертификаты. Для отправки зашифрованных сообщений через Exchange Online почтовое приложение отправителя использует общедоступный сертификат получателя для шифрования сообщения. Этот общедоступный сертификат X.509 необходимо опубликовать в Office 365.

## <a name="to-sync-certificates-that-support-smime"></a>Синхронизация сертификатов, поддерживающих S/MIME

Начните настройку S/MIME путем выдачи сертификатов и их публикации в локальной службе домена Active Directory. Более подробную информацию об управлении сертификатами в Exchange Server можно узнать в статье [Digital Certificates and SSL](http://technet.microsoft.com/library/a9e2e08c-d46a-4135-a387-eb653212b676.aspx).

После публикации сертификатов используйте Средство синхронизации Azure Active Directory для синхронизации пользовательских данных из локальной среды Exchange с Office 365. Дополнительные сведения об этом процессе см. в статье [DirSync: журнал выпуска версий средства синхронизации каталогов](https://go.microsoft.com/fwlink/p/?LinkId=392587).

Вместе с синхронизацией других данных каталога для целей S/MIME средство будет синхронизировать атрибуты **USERCERTIFICATE** и **userSMIMECertificate** для каждого объекта User, чтобы эти данные можно было использовать для подписи и шифрования сообщений.

## <a name="more-information"></a>Дополнительные сведения

[S/MIME для подписи и шифрования сообщений](s-mime-for-message-signing-and-encryption.md)

[Средство синхронизации Azure Active Directory](https://go.microsoft.com/fwlink/p/?LinkId=392587)
