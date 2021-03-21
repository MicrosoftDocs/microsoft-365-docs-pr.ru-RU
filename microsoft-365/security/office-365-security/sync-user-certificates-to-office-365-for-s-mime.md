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
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916458"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a><span data-ttu-id="d47da-103">Синхронизация сертификатов пользователей с Office 365 для S/MIME</span><span class="sxs-lookup"><span data-stu-id="d47da-103">Sync user certificates to Office 365 for S/MIME</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="d47da-104">Перед отправкой сообщений, защищенных S/MIME в Exchange Online, необходимо настроить соответствующие сертификаты.</span><span class="sxs-lookup"><span data-stu-id="d47da-104">Before anyone can send S/MIME-protected messages in Exchange Online, the appropriate certificates must be set up.</span></span> <span data-ttu-id="d47da-105">Для отправки зашифрованных сообщений через Exchange Online приложение электронной почты отправитель использует общедоступный сертификат получателя для шифрования сообщения.</span><span class="sxs-lookup"><span data-stu-id="d47da-105">To send encrypted messages through Exchange Online, the sender's email app uses the public certificate of the recipient to encrypt the message.</span></span> <span data-ttu-id="d47da-106">Этот общедоступный сертификат X.509 необходимо опубликовать в Office 365.</span><span class="sxs-lookup"><span data-stu-id="d47da-106">This public X.509 certificate has to be published to Office 365.</span></span>

## <a name="to-sync-certificates-that-support-smime"></a><span data-ttu-id="d47da-107">Синхронизация сертификатов, поддерживающих S/MIME</span><span class="sxs-lookup"><span data-stu-id="d47da-107">To Sync certificates that support S/MIME</span></span>

<span data-ttu-id="d47da-108">Начните настройку S/MIME путем выдачи сертификатов и их публикации в локальной службе домена Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d47da-108">Begin setting up S/MIME by issuing certificates and publishing them in your local Active Directory Domain Service.</span></span> <span data-ttu-id="d47da-109">Дополнительные сведения см. в [обзоре служб сертификатов Active Directory.](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="d47da-109">For more information, see [Active Directory Certificate Services Overview](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11)).</span></span>

<span data-ttu-id="d47da-110">После публикации сертификатов используйте средство Azure AD Connect для синхронизации данных пользователей из локальной среды Exchange в Office 365.</span><span class="sxs-lookup"><span data-stu-id="d47da-110">After your certificates are published, use the Azure AD Connect tool to synchronize user data from your on-premises Exchange environment to Office 365.</span></span> <span data-ttu-id="d47da-111">Дополнительные сведения об этом процессе см. в [синхронизации Azure AD Connect: Понимание и настройка синхронизации.](/azure/active-directory/hybrid/how-to-connect-sync-whatis)</span><span class="sxs-lookup"><span data-stu-id="d47da-111">For more information on this process, see [Azure AD Connect sync: Understand and customize synchronization](/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span></span>

<span data-ttu-id="d47da-112">Наряду с синхронизацией других данных каталогов для целей S/MIME средство синхронизирует атрибуты  **userCertificate** и **userSMIMECertificate** для каждого объекта пользователя, чтобы эти данные можно было использовать для подписи и шифрования сообщений.</span><span class="sxs-lookup"><span data-stu-id="d47da-112">Along with synchronizing other directory data, for S/MIME purposes, the tool will synchronize the  **userCertificate** and **userSMIMECertificate** attributes for each user object so the data can be used to sign and encrypt messages.</span></span>

## <a name="more-information"></a><span data-ttu-id="d47da-113">Дополнительная информация</span><span class="sxs-lookup"><span data-stu-id="d47da-113">More Information</span></span>

[<span data-ttu-id="d47da-114">S/MIME для подписи и шифрования сообщений</span><span class="sxs-lookup"><span data-stu-id="d47da-114">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="d47da-115">Что такое Azure AD Connect?</span><span class="sxs-lookup"><span data-stu-id="d47da-115">What is Azure AD Connect?</span></span>](/azure/active-directory/hybrid/whatis-azure-ad-connect)