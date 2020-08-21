---
title: Синхронизация сертификатов пользователей с Office 365 для S/MIME
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 351c932e-99c1-4512-a6e8-788e90b7838f
ms.custom:
- seo-marvel-apr2020
description: В этой статье вы узнаете, как опубликовать соответствующие сертификаты в Office 365, прежде чем отправлять сообщения, защищенные с помощью S/MIME, в Exchange Online.
ms.openlocfilehash: 634b65e45b01186a27f9ae61c91d4b27f1a11635
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826485"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a>Синхронизация сертификатов пользователей с Office 365 для S/MIME

Чтобы отправлять сообщения, защищенные с помощью S/MIME, в Exchange Online, необходимо настроить соответствующие сертификаты. Для отправки зашифрованных сообщений через Exchange Online приложение электронной почты отправителя использует общедоступный сертификат получателя для шифрования сообщений. Этот общедоступный сертификат X.509 необходимо опубликовать в Office 365.

## <a name="to-sync-certificates-that-support-smime"></a>Синхронизация сертификатов, поддерживающих S/MIME

Начните настройку S/MIME путем выдачи сертификатов и их публикации в локальной службе домена Active Directory. Дополнительные сведения см. в статье ["Обзор служб сертификатов Active Directory".](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11))

После публикации сертификатов используйте средство Azure AD Connect для синхронизации пользовательских данных из локальной среды Exchange с Office 365. Дополнительные сведения об этом процессе см. в разделе ["Синхронизация Azure AD Connect: анализ и настройка синхронизации".](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)

Этот инструмент наряду с синхронизацией данных других каталогов в целях поддержки S/MIME синхронизации атрибутов  **userCertificate** **и userSMIMECertificate** для каждого объекта-пользователя содержит данные, чтобы с помощью данные можно было подписывать и шифровать сообщения.

## <a name="more-information"></a>Дополнительная информация

[S/MIME для подписи и шифрования сообщений](s-mime-for-message-signing-and-encryption.md)

[Что такое Azure AD Connect?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)
