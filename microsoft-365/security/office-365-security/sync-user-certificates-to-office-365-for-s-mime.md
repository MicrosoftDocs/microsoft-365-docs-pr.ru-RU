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
# <a name="sync-user-certificates-to-office-365-for-smime"></a><span data-ttu-id="c5046-103">Синхронизация сертификатов пользователей с Office 365 для S/MIME</span><span class="sxs-lookup"><span data-stu-id="c5046-103">Sync user certificates to Office 365 for S/MIME</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="c5046-104">Чтобы пользователи могли отправлять сообщения, защищенные с помощью S/MIME, в Exchange Online, необходимо настроить соответствующие сертификаты.</span><span class="sxs-lookup"><span data-stu-id="c5046-104">Before anyone can send S/MIME-protected messages in Exchange Online, the appropriate certificates must be set up.</span></span> <span data-ttu-id="c5046-105">Для отправки зашифрованных сообщений через Exchange Online почтовое приложение отправителя использует общедоступный сертификат получателя для шифрования сообщения.</span><span class="sxs-lookup"><span data-stu-id="c5046-105">To send encrypted messages through Exchange Online, the sender's email app uses the public certificate of the recipient to encrypt the message.</span></span> <span data-ttu-id="c5046-106">Этот общедоступный сертификат X.509 необходимо опубликовать в Office 365.</span><span class="sxs-lookup"><span data-stu-id="c5046-106">This public X.509 certificate has to be published to Office 365.</span></span>

## <a name="to-sync-certificates-that-support-smime"></a><span data-ttu-id="c5046-107">Синхронизация сертификатов, поддерживающих S/MIME</span><span class="sxs-lookup"><span data-stu-id="c5046-107">To Sync certificates that support S/MIME</span></span>

<span data-ttu-id="c5046-108">Начните настройку S/MIME путем выдачи сертификатов и их публикации в локальной службе домена Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c5046-108">Begin setting up S/MIME by issuing certificates and publishing them in your local Active Directory Domain Service.</span></span> <span data-ttu-id="c5046-109">Для получения дополнительных сведений обратитесь к разделу [Обзор служб сертификации Active Directory](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="c5046-109">For more information, see [Active Directory Certificate Services Overview](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11)).</span></span>

<span data-ttu-id="c5046-110">После публикации сертификатов используйте средство Azure AD Connect для синхронизации пользовательских данных из локальной среды Exchange с Office 365.</span><span class="sxs-lookup"><span data-stu-id="c5046-110">After your certificates are published, use the Azure AD Connect tool to synchronize user data from your on-premises Exchange environment to Office 365.</span></span> <span data-ttu-id="c5046-111">Дополнительные сведения об этом процессе см в статье [Azure AD Connect Sync: сведения и Настройка синхронизации](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span><span class="sxs-lookup"><span data-stu-id="c5046-111">For more information on this process, see [Azure AD Connect sync: Understand and customize synchronization](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span></span>

<span data-ttu-id="c5046-112">Вместе с синхронизацией других данных каталога для целей S/MIME средство будет синхронизировать атрибуты  **USERCERTIFICATE** и **userSMIMECertificate** для каждого объекта User, чтобы эти данные можно было использовать для подписи и шифрования сообщений.</span><span class="sxs-lookup"><span data-stu-id="c5046-112">Along with synchronizing other directory data, for S/MIME purposes, the tool will synchronize the  **userCertificate** and **userSMIMECertificate** attributes for each user object so the data can be used to sign and encrypt messages.</span></span>

## <a name="more-information"></a><span data-ttu-id="c5046-113">Дополнительная информация</span><span class="sxs-lookup"><span data-stu-id="c5046-113">More Information</span></span>

[<span data-ttu-id="c5046-114">S/MIME для подписи и шифрования сообщений</span><span class="sxs-lookup"><span data-stu-id="c5046-114">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="c5046-115">Что такое Azure AD Connect?</span><span class="sxs-lookup"><span data-stu-id="c5046-115">What is Azure AD Connect?</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)
