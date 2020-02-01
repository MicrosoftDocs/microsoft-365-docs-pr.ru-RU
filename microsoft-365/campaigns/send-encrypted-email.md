---
title: Отправка зашифрованных писем
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 9/20/2018
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Узнайте, как отправлять зашифрованную электронную почту с помощью Outlook.
ms.openlocfilehash: 1a450a9891d47a136798432fdb919349fb82e097
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41594740"
---
# <a name="encrypt-or-label-your-sensitive-email"></a><span data-ttu-id="a28fb-103">Шифрование или маркировка конфиденциальной электронной почты</span><span class="sxs-lookup"><span data-stu-id="a28fb-103">Encrypt or label your sensitive email</span></span>

<span data-ttu-id="a28fb-104">Данные и сведения о кампании важны и часто конфиденциальны.</span><span class="sxs-lookup"><span data-stu-id="a28fb-104">Your data and campaign information is important and often confidential.</span></span> <span data-ttu-id="a28fb-105">Защитите эти конфиденциальные данные с помощью меток шифрования и конфиденциальности, чтобы вы и ваши получатели электронной почты израбатывали информацию с учетом требуемой чувствительности.</span><span class="sxs-lookup"><span data-stu-id="a28fb-105">Help protect this sensitive information by using encryption and sensitivity labels so you and your email recipients treat the information with the sensitivity it requires.</span></span>


## <a name="best-practices"></a><span data-ttu-id="a28fb-106">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="a28fb-106">Best practices</span></span>

<span data-ttu-id="a28fb-107">Перед отправкой сообщения электронной почты с конфиденциальной или конфиденциальной информацией рекомендуется включить:</span><span class="sxs-lookup"><span data-stu-id="a28fb-107">Before you send email with confidential or sensitive information, consider turning on:</span></span>

- <span data-ttu-id="a28fb-108">**Шифрование:** Вы можете зашифровать электронную почту, чтобы защитить конфиденциальность сведений в сообщении электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a28fb-108">**Encryption:** You can encrypt your email to protect the privacy of the information in the email.</span></span> <span data-ttu-id="a28fb-109">При шифровании сообщения электронной почты оно преобразуется из читаемого обычного текста в зашифрованный текст цифер.</span><span class="sxs-lookup"><span data-stu-id="a28fb-109">When you encrypt an email message, it's converted from readable plain text into scrambled cypher text.</span></span> <span data-ttu-id="a28fb-110">Только получатель с закрытым ключом, который соответствует открытому ключу, использованному для шифрования сообщения, может расшифровать сообщение для чтения.</span><span class="sxs-lookup"><span data-stu-id="a28fb-110">Only the recipient who has the private key that matches the public key used to encrypt the message can decipher the message for reading.</span></span> <span data-ttu-id="a28fb-111">Однако любой получатель без соответствующего закрытого ключа видит нечитаемый текст.</span><span class="sxs-lookup"><span data-stu-id="a28fb-111">Any recipient without the corresponding private key, however, sees indecipherable text.</span></span> <span data-ttu-id="a28fb-112">Администратор может определить правила для автоматического шифрования сообщений, удовлетворяющих определенным условиям.</span><span class="sxs-lookup"><span data-stu-id="a28fb-112">Your admin can define rules to automatically encrypt messages that meet certain criteria.</span></span> <span data-ttu-id="a28fb-113">Например, администратор может создать правило, которое шифрует все сообщения, отправляемые за прев Организации, или все сообщения, в которых упоминаются определенные слова или фразы.</span><span class="sxs-lookup"><span data-stu-id="a28fb-113">For instance, your admin can create a rule that encrypts all messages sent outside your organization or all messages that mention specific words or phrases.</span></span> <span data-ttu-id="a28fb-114">Все правила шифрования будут применяться автоматически.</span><span class="sxs-lookup"><span data-stu-id="a28fb-114">Any encryption rules will be applied automatically.</span></span>
- <span data-ttu-id="a28fb-115">**Метки конфиденциальности:** В кампании также можно настроить метки конфиденциальности, которые можно применить к файлам и электронной почте, чтобы они были совместимы с политиками защиты информации кампании.</span><span class="sxs-lookup"><span data-stu-id="a28fb-115">**Sensitivity labels:** Your campaign can also set up sensitivity labels that you can apply to your files and email to keep them compliant with your campaign's information protection policies.</span></span> <span data-ttu-id="a28fb-116">Когда вы задаете метку, эта метка сохраняется вместе с сообщением, даже если оно отправлено, например, в виде заголовка сообщения.</span><span class="sxs-lookup"><span data-stu-id="a28fb-116">When you set a label, the label persists with your email, even when it's sent - for example, by appearing as a header to your message.</span></span>

![Схема сообщения электронной почты с выносками для меток и шифрования](media/m365-campaign-email-encrypt.png)


## <a name="set-it-up"></a><span data-ttu-id="a28fb-118">Настройка</span><span class="sxs-lookup"><span data-stu-id="a28fb-118">Set it up</span></span>

<span data-ttu-id="a28fb-119">Если вы хотите зашифровать сообщение, которое не соответствует предварительно определенному правилу, или администратор не настроил правила, можно применить различные правила шифрования перед отправкой сообщения.</span><span class="sxs-lookup"><span data-stu-id="a28fb-119">If you want to encrypt a message that doesn't meet a pre-defined rule or your admin hasn't set up any rules, you can apply a variety of different encryption rules before you send the message.</span></span> <span data-ttu-id="a28fb-120">Чтобы отправить зашифрованное сообщение из Outlook 2013 или 2016 или Outlook 2016 для Mac, выберите **параметры > разрешений**, а затем выберите необходимый вариант защиты.</span><span class="sxs-lookup"><span data-stu-id="a28fb-120">To send an encrypted message from Outlook 2013 or 2016, or Outlook 2016 for Mac, select **Options > Permissions**, then select the protection option you need.</span></span> <span data-ttu-id="a28fb-121">Вы также можете отправить зашифрованное сообщение, нажав кнопку **защитить** в Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="a28fb-121">You can also send an encrypted message by selecting the **Protect** button in Outlook on the web.</span></span> <span data-ttu-id="a28fb-122">Дополнительные сведения см. [в статье отправка, просмотр и ответ на зашифрованные сообщения в Outlook для компьютера](https://support.office.com/article/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980?ui=en-US&rs=en-US&ad=US).</span><span class="sxs-lookup"><span data-stu-id="a28fb-122">For more information, see [Send, view, and reply to encrypted messages in Outlook for PC](https://support.office.com/article/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980?ui=en-US&rs=en-US&ad=US).</span></span>

## <a name="admin-settings"></a><span data-ttu-id="a28fb-123">Параметры администрирования</span><span class="sxs-lookup"><span data-stu-id="a28fb-123">Admin settings</span></span>

<span data-ttu-id="a28fb-124">Вы можете узнать все о настройке шифрования электронной почты при [шифровании электронной почты в Office 365](https://docs.microsoft.com/office365/securitycompliance/email-encryption).</span><span class="sxs-lookup"><span data-stu-id="a28fb-124">You can learn all about setting up email encryption at [Email encryption in Office 365](https://docs.microsoft.com/office365/securitycompliance/email-encryption).</span></span>

### <a name="automatically-encrypt-email-messages"></a><span data-ttu-id="a28fb-125">Автоматическое шифрование сообщений электронной почты</span><span class="sxs-lookup"><span data-stu-id="a28fb-125">Automatically encrypt email messages</span></span>

<span data-ttu-id="a28fb-126">Администраторы могут создавать правила для почтового процесса для автоматической защиты сообщений электронной почты, отправленных и полученных из кампании.</span><span class="sxs-lookup"><span data-stu-id="a28fb-126">Admins can create mail flow rules to automatically protect email messages that are sent and received from your campaign.</span></span> <span data-ttu-id="a28fb-127">Настройте правила для шифрования всех исходящих сообщений электронной почты и удалите шифрование из зашифрованных сообщений, поступающих из вашей организации, или из ответов на зашифрованные сообщения, отправленные из вашей организации.</span><span class="sxs-lookup"><span data-stu-id="a28fb-127">Set up rules to encrypt any outgoing email messages, and remove encryption from encrypted messages coming from inside your organization or from replies to encrypted messages sent from your organization.</span></span> 

<span data-ttu-id="a28fb-128">Правила для обработки почтового ящика создаются для шифрования сообщений электронной почты с помощью новых возможностей шифрования сообщений Office 365 (OME).</span><span class="sxs-lookup"><span data-stu-id="a28fb-128">You create mail flow rules to encrypt email messages with the new Office 365 Message Encryption (OME) capabilities.</span></span> <span data-ttu-id="a28fb-129">Определите правила для почтового процесса для запуска шифрования сообщений с новыми возможностями OME с помощью центра администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="a28fb-129">Define mail flow rules for triggering message encryption with the new OME capabilities by using the Exchange Admin Center (EAC).</span></span> 

1. <span data-ttu-id="a28fb-130">В веб-браузере с помощью рабочей или учебной учетной записи, которой предоставлены разрешения глобального администратора, войдите в Office 365.</span><span class="sxs-lookup"><span data-stu-id="a28fb-130">In a web browser, using a work or school account that has been granted global administrator permissions, sign in to Office 365.</span></span> 
2. <span data-ttu-id="a28fb-131">Выберите плитку администратор.</span><span class="sxs-lookup"><span data-stu-id="a28fb-131">Choose the Admin tile.</span></span> 
3. <span data-ttu-id="a28fb-132">В центре администрирования выберите **центр администрирования > Exchange**.</span><span class="sxs-lookup"><span data-stu-id="a28fb-132">In the admin center, choose **Admin centers > Exchange**.</span></span> 

<span data-ttu-id="a28fb-133">Дополнительную информацию можно узнать в статье [Определение правил обработки почтового процесса для шифрования сообщений электронной почты в Office 365](https://docs.microsoft.com/office365/securitycompliance/define-mail-flow-rules-to-encrypt-email).</span><span class="sxs-lookup"><span data-stu-id="a28fb-133">For more information, see [Define mail flow rules to encrypt email messages in Office 365](https://docs.microsoft.com/office365/securitycompliance/define-mail-flow-rules-to-encrypt-email).</span></span>

### <a name="brand-your-encryption-messages"></a><span data-ttu-id="a28fb-134">Фирменная символика сообщений шифрования</span><span class="sxs-lookup"><span data-stu-id="a28fb-134">Brand your encryption messages</span></span>

<span data-ttu-id="a28fb-135">Вы также можете применить фирменную символику кампании для настройки внешнего вида и текста в сообщениях электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a28fb-135">You can also apply your campaign branding to customize the look and the text in the email messages.</span></span> <span data-ttu-id="a28fb-136">Дополнительную информацию можно узнать [в статье Добавление фирменной символики Организации к зашифрованным сообщениям](https://docs.microsoft.com/office365/securitycompliance/email-encryption).</span><span class="sxs-lookup"><span data-stu-id="a28fb-136">For more information, see [Add your organization's brand to your encrypted messages](https://docs.microsoft.com/office365/securitycompliance/email-encryption).</span></span>

