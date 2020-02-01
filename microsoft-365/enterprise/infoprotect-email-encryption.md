---
title: Шаг 6. Настройка шифрования электронной почты
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: ''
description: В этой статье рассказывается, как настроить управление привилегированным доступом для Office 365.
ms.openlocfilehash: 252a5f76197deb1034d200553308a281ef079957
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600926"
---
# <a name="step-6-configure-email-encryption"></a><span data-ttu-id="de310-103">Шаг 6. Настройка шифрования электронной почты</span><span class="sxs-lookup"><span data-stu-id="de310-103">Step 6: Configure email encryption</span></span>

<span data-ttu-id="de310-104">*Этот этап не является обязательным. Он применяется к планам E3 и E5 Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="de310-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Этап 6. Защита данных](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="de310-106">В Microsoft 365 существует три типа шифрования электронной почты.</span><span class="sxs-lookup"><span data-stu-id="de310-106">There are three types of email encryption in Microsoft 365.</span></span>

|||
|:-------|:-----|
| <span data-ttu-id="de310-107">Шифрование сообщений Office (OME)</span><span class="sxs-lookup"><span data-stu-id="de310-107">Office Message Encryption (OME)</span></span> | <span data-ttu-id="de310-108">Шифрование для электронной почты Exchange Online, отправляемое за прев Организации.</span><span class="sxs-lookup"><span data-stu-id="de310-108">Encryption for Exchange Online email sent outside your organization.</span></span> |
| <span data-ttu-id="de310-109">(IRM) Управления Правами На Доступ К Данным</span><span class="sxs-lookup"><span data-stu-id="de310-109">Information Rights Management (IRM)</span></span> | <span data-ttu-id="de310-110">Шифрование и разрешения, которые передаются вместе с сообщением электронной почты.</span><span class="sxs-lookup"><span data-stu-id="de310-110">Encryption and permissions that travel with the email.</span></span> |
| <span data-ttu-id="de310-111">Secure/Multipurpose Internet Mail Extensions (S/MIME)</span><span class="sxs-lookup"><span data-stu-id="de310-111">Secure/Multipurpose Internet Mail Extensions (S/MIME)</span></span> | <span data-ttu-id="de310-112">Защита электронной почты с шифрованием и цифровыми подписями.</span><span class="sxs-lookup"><span data-stu-id="de310-112">Email protection with encryption and digital signatures.</span></span> |
|||

## <a name="office-365-message-encryption"></a><span data-ttu-id="de310-113">Шифрование сообщений Office 365</span><span class="sxs-lookup"><span data-stu-id="de310-113">Office 365 Message Encryption</span></span>

<span data-ttu-id="de310-114">С помощью OME организация может отправлять и получать зашифрованные сообщения электронной почты между людьми в Организации и за ее пределами.</span><span class="sxs-lookup"><span data-stu-id="de310-114">With OME, your organization can send and receive encrypted email messages between people inside and outside your organization.</span></span> <span data-ttu-id="de310-115">OME работает с Outlook.com, Yahoo!, Gmail и другими почтовыми службами.</span><span class="sxs-lookup"><span data-stu-id="de310-115">OME works with Outlook.com, Yahoo!, Gmail, and other email services.</span></span> <span data-ttu-id="de310-116">Шифрование сообщений электронной почты гарантирует, что только предназначенные получатели могут просматривать сообщение.</span><span class="sxs-lookup"><span data-stu-id="de310-116">Email message encryption helps ensure that only intended recipients can view the message.</span></span>

![Шифрование сообщений электронной почты OME](./media/infoprotect-email-encryption/ome-encryption.png)

<span data-ttu-id="de310-118">Вы настраиваете правила транспорта, определяющие условия для шифрования.</span><span class="sxs-lookup"><span data-stu-id="de310-118">You set up transport rules that define the conditions for encryption.</span></span> <span data-ttu-id="de310-119">Когда пользователь отправляет сообщение, соответствующее правилу, шифрование применяется автоматически.</span><span class="sxs-lookup"><span data-stu-id="de310-119">When a user sends a message that matches a rule, encryption is applied automatically.</span></span>

<span data-ttu-id="de310-120">Для просмотра зашифрованных сообщений получатели могут либо получить одноразовый пароль, войти с помощью учетной записи Майкрософт, либо войти с помощью рабочей или учебной учетной записи, сопоставленной с Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="de310-120">To view encrypted messages, recipients can either get a one-time passcode, sign in with a Microsoft account, or sign in with a work or school account associated with Microsoft 365.</span></span> <span data-ttu-id="de310-121">Получатели также могут отправлять зашифрованные ответы.</span><span class="sxs-lookup"><span data-stu-id="de310-121">Recipients can also send encrypted replies.</span></span> <span data-ttu-id="de310-122">Для просмотра зашифрованных сообщений и отправки зашифрованных ответов им не требуется собственная подписка на Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="de310-122">They don't need their own Microsoft 365 subscription to view encrypted messages or send encrypted replies.</span></span>

<span data-ttu-id="de310-123">Дополнительные сведения см. в статье [Шифрование сообщений Office 365](https://docs.microsoft.com/Office365/SecurityCompliance/ome).</span><span class="sxs-lookup"><span data-stu-id="de310-123">For more information, see [Office 365 Message Encryption](https://docs.microsoft.com/Office365/SecurityCompliance/ome).</span></span>

## <a name="irm"></a><span data-ttu-id="de310-124">IRM</span><span class="sxs-lookup"><span data-stu-id="de310-124">IRM</span></span>

<span data-ttu-id="de310-125">Служба управления правами на доступ к данным (IRM) в Microsoft 365 помогает защитить информацию с помощью дополнительного шифрования и применением интеллектуальной политики, указывающей, кто может выполнять эти действия.</span><span class="sxs-lookup"><span data-stu-id="de310-125">IRM in Microsoft 365 helps you secure your information with additional encryption and by applying an intelligent policy that specifies who has access what they can do.</span></span> <span data-ttu-id="de310-126">Для сообщений электронной почты можно использовать IRM для шифрования и применять ограничения использования.</span><span class="sxs-lookup"><span data-stu-id="de310-126">For email messages, you can use IRM for encryption and to apply usage restrictions.</span></span> <span data-ttu-id="de310-127">Например, вы можете указать, что некоторые получатели имеют все возможности по управлению электронной почтой, а у некоторых нет возможности печатать или пересылать электронную почту.</span><span class="sxs-lookup"><span data-stu-id="de310-127">For example, you can specify that some recipients have all abilities to manage the email and some do not have the ability to print or forward the email.</span></span> 

<span data-ttu-id="de310-128">Политики управления правами на доступ к данным настраиваются в Microsoft 365 и могут применяться к документам в SharePoint Online и сообщениям электронной почты.</span><span class="sxs-lookup"><span data-stu-id="de310-128">IRM policies are configured within Microsoft 365 and can apply to documents in SharePoint Online and email messages.</span></span> <span data-ttu-id="de310-129">Электронная почта с защитой IRM включает примененные параметры политики и передается вместе с ней.</span><span class="sxs-lookup"><span data-stu-id="de310-129">An IRM-protected email includes the applied policy settings applied and travel with it.</span></span> 

![Защита IRM в сообщениях электронной почты](./media/infoprotect-email-encryption/irm-protection.png)

<span data-ttu-id="de310-131">Когда получатель открывает сообщение электронной почты с включенной политикой, параметры политики используются для расшифровки сообщения и определения того, что может делать получатель.</span><span class="sxs-lookup"><span data-stu-id="de310-131">When the recipient opens the email with the included policy, the policy settings are used to decrypt the message and determine what the recipient can do with it.</span></span> 

<span data-ttu-id="de310-132">Дополнительные сведения см. в разделе [Управление правами на доступ к данным в Exchange Online]( https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online).</span><span class="sxs-lookup"><span data-stu-id="de310-132">For more information, see [Information Rights Management in Exchange Online]( https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online).</span></span>

## <a name="smime"></a><span data-ttu-id="de310-133">S/MIME;</span><span class="sxs-lookup"><span data-stu-id="de310-133">S/MIME</span></span>

<span data-ttu-id="de310-134">S/MIME это решение для защиты электронной почты на основе цифровых сертификатов, которое позволяет выполнять шифрование и цифровую подпись сообщения.</span><span class="sxs-lookup"><span data-stu-id="de310-134">S/MIME is a digital certificate-based email-based protection solution that allows you to both encrypt and digitally sign a message.</span></span> <span data-ttu-id="de310-135">Шифрование сообщений гарантирует, что только указанный получатель сможет открыть и прочитать сообщение.</span><span class="sxs-lookup"><span data-stu-id="de310-135">The message encryption helps ensure that only the intended recipient can open and read the message.</span></span> <span data-ttu-id="de310-136">Цифровая подпись помогает получателю проверить подлинность отправителя и определить, что она была отправлена только отправителю.</span><span class="sxs-lookup"><span data-stu-id="de310-136">A digital signature helps the recipient validate the identity of the sender and determine that only the sender could have sent it.</span></span>

![Защита сообщений электронной почты с протоколом S/MIME](./media/infoprotect-email-encryption/smime-protection.png)

<span data-ttu-id="de310-138">S/MIME можно использовать для электронной почты с другими почтовыми ящиками в вашей подписке на Microsoft 365 или внешним пользователям.</span><span class="sxs-lookup"><span data-stu-id="de310-138">S/MIME can be used for email to other mailboxes in your Microsoft 365 subscription or to external users.</span></span>
<span data-ttu-id="de310-139">Шифрование сообщений и Цифровые подписи возможны благодаря использованию цифровых сертификатов, которые содержат открытые и закрытые ключи для шифрования и расшифровки сообщений, а также для создания и проверки цифровых подписей.</span><span class="sxs-lookup"><span data-stu-id="de310-139">Both message encryption and digital signatures are made possible through the use of digital certificates that contain the public and private keys for encrypting or decrypting messages and creating and verifying digital signatures.</span></span>
<span data-ttu-id="de310-140">Чтобы использовать S/MIME, необходимо иметь общедоступные ключи для каждого получателя.</span><span class="sxs-lookup"><span data-stu-id="de310-140">To use S/MIME, you must have the public keys for each recipient.</span></span> <span data-ttu-id="de310-141">Получатели сохраняют собственные закрытые ключи, которые должны быть защищены.</span><span class="sxs-lookup"><span data-stu-id="de310-141">Recipients maintain their own private keys, which must remain secure.</span></span> <span data-ttu-id="de310-142">Если закрытый ключ скомпрометирован, необходимо получить новый цифровой сертификат и перераспределить общедоступные ключи всем потенциальным отправителям.</span><span class="sxs-lookup"><span data-stu-id="de310-142">If your private key is compromised, you need to get a new digital certificate and redistribute public keys to all potential senders.</span></span>

<span data-ttu-id="de310-143">Дополнительные сведения см. в статье [S/MIME для подписи и шифрования сообщений](https://docs.microsoft.com/Exchange/policy-and-compliance/smime).    </span><span class="sxs-lookup"><span data-stu-id="de310-143">For more information, see [S/MIME for message signing and encryption](https://docs.microsoft.com/Exchange/policy-and-compliance/smime).</span></span>


<span data-ttu-id="de310-144">Прежде чем перейти к следующему шагу, проверьте [условия](infoprotect-exit-criteria.md#crit-infoprotect-step6), при выполнении которых можно считать данный шаг завершенным.</span><span class="sxs-lookup"><span data-stu-id="de310-144">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step6) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="de310-145">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="de310-145">Next step</span></span>

|||
|:-------|:-----|
|![Шаг 7](./media/stepnumbers/Step7.png)|[<span data-ttu-id="de310-147">Настройка управления привилегированным доступом для Office 365</span><span class="sxs-lookup"><span data-stu-id="de310-147">Configure privileged access management for Office 365</span></span>](infoprotect-configure-privileged-access-management.md)|
