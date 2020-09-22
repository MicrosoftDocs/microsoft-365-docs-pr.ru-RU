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
description: В этой статье вы узнаете, как опубликовать соответствующие сертификаты в Office 365 перед отправкой сообщений S/MIME, защищенных с использованием MIME, в Exchange Online.
ms.openlocfilehash: 3551dbacc3cc6279d319860f1133d059216ae591
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202107"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a>Синхронизация сертификатов пользователей с Office 365 для S/MIME

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Чтобы пользователи могли отправлять сообщения, защищенные с помощью S/MIME, в Exchange Online, необходимо настроить соответствующие сертификаты. Для отправки зашифрованных сообщений через Exchange Online почтовое приложение отправителя использует общедоступный сертификат получателя для шифрования сообщения. Этот общедоступный сертификат X.509 необходимо опубликовать в Office 365.

## <a name="to-sync-certificates-that-support-smime"></a>Синхронизация сертификатов, поддерживающих S/MIME

Начните настройку S/MIME путем выдачи сертификатов и их публикации в локальной службе домена Active Directory. Для получения дополнительных сведений обратитесь к разделу [Обзор служб сертификации Active Directory](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11)).

После публикации сертификатов используйте средство Azure AD Connect для синхронизации пользовательских данных из локальной среды Exchange с Office 365. Дополнительные сведения об этом процессе см в статье [Azure AD Connect Sync: сведения и Настройка синхронизации](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).

Вместе с синхронизацией других данных каталога для целей S/MIME средство будет синхронизировать атрибуты  **USERCERTIFICATE** и **userSMIMECertificate** для каждого объекта User, чтобы эти данные можно было использовать для подписи и шифрования сообщений.

## <a name="more-information"></a>Дополнительная информация

[S/MIME для подписи и шифрования сообщений](s-mime-for-message-signing-and-encryption.md)

[Что такое Azure AD Connect?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)
