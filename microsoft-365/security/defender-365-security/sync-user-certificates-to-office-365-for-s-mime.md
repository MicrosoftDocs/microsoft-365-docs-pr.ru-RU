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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 351c932e-99c1-4512-a6e8-788e90b7838f
ms.custom:
- seo-marvel-apr2020
description: В этой статье вы узнаете, как публиковать соответствующие сертификаты в Office 365 перед отправкой сообщений с защитой S/MIME в Exchange Online.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 387f9f405afd45254c6568aa92334a7ee5b4171f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071182"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a>Синхронизация сертификатов пользователей с Office 365 для S/MIME

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Перед отправкой сообщений, защищенных S/MIME в Exchange Online, необходимо настроить соответствующие сертификаты. Для отправки зашифрованных сообщений через Exchange Online приложение электронной почты отправитель использует общедоступный сертификат получателя для шифрования сообщения. Этот общедоступный сертификат X.509 необходимо опубликовать в Office 365.

## <a name="to-sync-certificates-that-support-smime"></a>Синхронизация сертификатов, поддерживающих S/MIME

Начните настройку S/MIME путем выдачи сертификатов и их публикации в локальной службе домена Active Directory. Дополнительные сведения см. в [обзоре служб сертификатов Active Directory.](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11))

После публикации сертификатов используйте средство Azure AD Connect для синхронизации данных пользователей из локальной среды Exchange в Office 365. Дополнительные сведения об этом процессе см. в [синхронизации Azure AD Connect: Понимание и настройка синхронизации.](/azure/active-directory/hybrid/how-to-connect-sync-whatis)

Наряду с синхронизацией других данных каталогов для целей S/MIME средство синхронизирует атрибуты  **userCertificate** и **userSMIMECertificate** для каждого объекта пользователя, чтобы эти данные можно было использовать для подписи и шифрования сообщений.

## <a name="more-information"></a>Дополнительная информация

[S/MIME для подписи и шифрования сообщений](s-mime-for-message-signing-and-encryption.md)

[Что такое Azure AD Connect?](/azure/active-directory/hybrid/whatis-azure-ad-connect)