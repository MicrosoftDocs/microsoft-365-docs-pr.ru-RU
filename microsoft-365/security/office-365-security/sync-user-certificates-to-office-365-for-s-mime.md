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
ms.openlocfilehash: e03d7be2a7a1fcb8c5ef56395b4046442802cf2a
ms.sourcegitcommit: 2468bcb01625f97a322459814d81b9faad717859
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "39872025"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a><span data-ttu-id="925b6-105">Синхронизация сертификатов пользователей с Office 365 для S/MIME</span><span class="sxs-lookup"><span data-stu-id="925b6-105">Sync user certificates to Office 365 for S/MIME</span></span>

<span data-ttu-id="925b6-106">Чтобы пользователи могли отправлять сообщения, защищенные с помощью S/MIME, в Exchange Online, необходимо настроить соответствующие сертификаты.</span><span class="sxs-lookup"><span data-stu-id="925b6-106">Before anyone can send S/MIME-protected messages in Exchange Online, the appropriate certificates must be set up.</span></span> <span data-ttu-id="925b6-107">Для отправки зашифрованных сообщений через Exchange Online почтовое приложение отправителя использует общедоступный сертификат получателя для шифрования сообщения.</span><span class="sxs-lookup"><span data-stu-id="925b6-107">To send encrypted messages through Exchange Online, the sender's email app uses the public certificate of the recipient to encrypt the message.</span></span> <span data-ttu-id="925b6-108">Этот общедоступный сертификат X.509 необходимо опубликовать в Office 365.</span><span class="sxs-lookup"><span data-stu-id="925b6-108">This public X.509 certificate has to be published to Office 365.</span></span>

## <a name="to-sync-certificates-that-support-smime"></a><span data-ttu-id="925b6-109">Синхронизация сертификатов, поддерживающих S/MIME</span><span class="sxs-lookup"><span data-stu-id="925b6-109">To Sync certificates that support S/MIME</span></span>

<span data-ttu-id="925b6-110">Начните настройку S/MIME путем выдачи сертификатов и их публикации в локальной службе домена Active Directory.</span><span class="sxs-lookup"><span data-stu-id="925b6-110">Begin setting up S/MIME by issuing certificates and publishing them in your local Active Directory Domain Service.</span></span> <span data-ttu-id="925b6-111">Для получения дополнительных сведений обратитесь к разделу [Обзор служб сертификации Active Directory](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="925b6-111">For more information, see [Active Directory Certificate Services Overview](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11)).</span></span>

<span data-ttu-id="925b6-p104">После публикации сертификатов используйте Средство синхронизации Azure Active Directory для синхронизации пользовательских данных из локальной среды Exchange с Office 365. Дополнительные сведения об этом процессе см. в статье [DirSync: журнал выпуска версий средства синхронизации каталогов](https://go.microsoft.com/fwlink/p/?LinkId=392587).</span><span class="sxs-lookup"><span data-stu-id="925b6-p104">After your certificates are published, use the Azure Active Directory Sync tool to synchronize user data from your on-premises Exchange environment to Office 365. For more information on this process, see [DirSync: Directory Sync Tool Version Release History](https://go.microsoft.com/fwlink/p/?LinkId=392587).</span></span>

<span data-ttu-id="925b6-114">Вместе с синхронизацией других данных каталога для целей S/MIME средство будет синхронизировать атрибуты **USERCERTIFICATE** и **userSMIMECertificate** для каждого объекта User, чтобы эти данные можно было использовать для подписи и шифрования сообщений.</span><span class="sxs-lookup"><span data-stu-id="925b6-114">Along with synchronizing other directory data, for S/MIME purposes, the tool will synchronize the  **userCertificate** and **userSMIMECertificate** attributes for each user object so the data can be used to sign and encrypt messages.</span></span>

## <a name="more-information"></a><span data-ttu-id="925b6-115">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="925b6-115">More Information</span></span>

[<span data-ttu-id="925b6-116">S/MIME для подписи и шифрования сообщений</span><span class="sxs-lookup"><span data-stu-id="925b6-116">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="925b6-117">Средство синхронизации Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="925b6-117">Azure Active Directory Sync tool</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=392587)
