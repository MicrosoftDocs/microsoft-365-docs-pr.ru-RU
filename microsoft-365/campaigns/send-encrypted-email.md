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
- m365solution-smb
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
ms.openlocfilehash: af34d632ead2ae1e6ed81845c56b95b95af1dc51
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911987"
---
# <a name="encrypt-or-label-your-sensitive-email"></a><span data-ttu-id="0417c-103">Шифрование или обозначение конфиденциальной электронной почты</span><span class="sxs-lookup"><span data-stu-id="0417c-103">Encrypt or label your sensitive email</span></span>

<span data-ttu-id="0417c-104">Ваши данные и сведения о кампании важны и часто конфиденциальны.</span><span class="sxs-lookup"><span data-stu-id="0417c-104">Your data and campaign information is important and often confidential.</span></span> <span data-ttu-id="0417c-105">Помогите защитить эту конфиденциальную информацию с помощью меток шифрования и конфиденциальности, чтобы вы и получатели электронной почты относились к данным с необходимой чувствительностью.</span><span class="sxs-lookup"><span data-stu-id="0417c-105">Help protect this sensitive information by using encryption and sensitivity labels so you and your email recipients treat the information with the sensitivity it requires.</span></span>

## <a name="best-practices"></a><span data-ttu-id="0417c-106">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="0417c-106">Best practices</span></span>

<span data-ttu-id="0417c-107">Перед отправкой электронной почты с конфиденциальной или конфиденциальной информацией необходимо включить:</span><span class="sxs-lookup"><span data-stu-id="0417c-107">Before you send email with confidential or sensitive information, consider turning on:</span></span>

- <span data-ttu-id="0417c-108">**Шифрование:** Вы можете шифровать электронную почту, чтобы защитить конфиденциальность сведений в электронной почте.</span><span class="sxs-lookup"><span data-stu-id="0417c-108">**Encryption:** You can encrypt your email to protect the privacy of the information in the email.</span></span> <span data-ttu-id="0417c-109">Когда вы шифруете сообщение электронной почты, оно преобразуется из читаемого простого текста в текст шифра.</span><span class="sxs-lookup"><span data-stu-id="0417c-109">When you encrypt an email message, it's converted from readable plain text into scrambled cypher text.</span></span> <span data-ttu-id="0417c-110">Расшифровать сообщение для чтения может только получатель, у которого есть закрытый ключ, совпадавший с общедоступным ключом, используемым для шифрования сообщения.</span><span class="sxs-lookup"><span data-stu-id="0417c-110">Only the recipient who has the private key that matches the public key used to encrypt the message can decipher the message for reading.</span></span> <span data-ttu-id="0417c-111">Однако любой получатель без соответствующего закрытого ключа видит неопределяемый текст.</span><span class="sxs-lookup"><span data-stu-id="0417c-111">Any recipient without the corresponding private key, however, sees indecipherable text.</span></span> <span data-ttu-id="0417c-112">Администратор может определять правила автоматического шифрования сообщений, которые соответствуют определенным критериям.</span><span class="sxs-lookup"><span data-stu-id="0417c-112">Your admin can define rules to automatically encrypt messages that meet certain criteria.</span></span> <span data-ttu-id="0417c-113">Например, администратор может создать правило, которое шифрует все сообщения, отправленные за пределами организации, или все сообщения, в которых упоминаются конкретные слова или фразы.</span><span class="sxs-lookup"><span data-stu-id="0417c-113">For instance, your admin can create a rule that encrypts all messages sent outside your organization or all messages that mention specific words or phrases.</span></span> <span data-ttu-id="0417c-114">Любые правила шифрования будут применяться автоматически.</span><span class="sxs-lookup"><span data-stu-id="0417c-114">Any encryption rules will be applied automatically.</span></span>
- <span data-ttu-id="0417c-115">**Метки чувствительности:** В вашей кампании также можно настроить метки конфиденциальности, которые можно применить к файлам и электронной почте, чтобы они соответствовали политикам защиты информации вашей кампании.</span><span class="sxs-lookup"><span data-stu-id="0417c-115">**Sensitivity labels:** Your campaign can also set up sensitivity labels that you can apply to your files and email to keep them compliant with your campaign's information protection policies.</span></span> <span data-ttu-id="0417c-116">При наборе метки метка сохраняется при отправке электронной почты, например, в качестве загона в сообщении.</span><span class="sxs-lookup"><span data-stu-id="0417c-116">When you set a label, the label persists with your email, even when it's sent - for example, by appearing as a header to your message.</span></span>

![Схема электронной почты с вызовами для меток и шифрования](../media/m365-campaign-email-encrypt.png)

## <a name="set-it-up"></a><span data-ttu-id="0417c-118">Настройка</span><span class="sxs-lookup"><span data-stu-id="0417c-118">Set it up</span></span>

<span data-ttu-id="0417c-119">Если вы хотите зашифровать сообщение, которое не соответствует заранее определенному правилу или администратор не настроил никаких правил, перед отправкой сообщения можно применить различные правила шифрования.</span><span class="sxs-lookup"><span data-stu-id="0417c-119">If you want to encrypt a message that doesn't meet a pre-defined rule or your admin hasn't set up any rules, you can apply a variety of different encryption rules before you send the message.</span></span> <span data-ttu-id="0417c-120">Чтобы отправить зашифрованное сообщение из Outlook 2013 или 2016 или Outlook 2016 для Mac, выберите Параметры > **разрешения,** а затем выберите необходимый параметр защиты.</span><span class="sxs-lookup"><span data-stu-id="0417c-120">To send an encrypted message from Outlook 2013 or 2016, or Outlook 2016 for Mac, select **Options > Permissions**, then select the protection option you need.</span></span> <span data-ttu-id="0417c-121">Кроме того, вы можете отправить зашифрованное сообщение, выбрав кнопку **Protect** в Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="0417c-121">You can also send an encrypted message by selecting the **Protect** button in Outlook on the web.</span></span> <span data-ttu-id="0417c-122">Дополнительные сведения см. в [тексте Отправка, просмотр](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)и ответ на зашифрованные сообщения в Outlook для ПК.</span><span class="sxs-lookup"><span data-stu-id="0417c-122">For more information, see [Send, view, and reply to encrypted messages in Outlook for PC](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980).</span></span>

## <a name="admin-settings"></a><span data-ttu-id="0417c-123">Параметры администратора</span><span class="sxs-lookup"><span data-stu-id="0417c-123">Admin settings</span></span>

<span data-ttu-id="0417c-124">Вы можете узнать все о настройке шифрования электронной почты в шифровании электронной [почты в Microsoft 365](../compliance/email-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="0417c-124">You can learn all about setting up email encryption at [Email encryption in Microsoft 365](../compliance/email-encryption.md).</span></span>

### <a name="automatically-encrypt-email-messages"></a><span data-ttu-id="0417c-125">Автоматическое шифрование сообщений электронной почты</span><span class="sxs-lookup"><span data-stu-id="0417c-125">Automatically encrypt email messages</span></span>

<span data-ttu-id="0417c-126">Администраторы могут создавать правила потока почты для автоматической защиты сообщений электронной почты, отправленных и полученных из вашей кампании.</span><span class="sxs-lookup"><span data-stu-id="0417c-126">Admins can create mail flow rules to automatically protect email messages that are sent and received from your campaign.</span></span> <span data-ttu-id="0417c-127">Настройка правил для шифрования исходяющих сообщений электронной почты и удаления шифрования из зашифрованных сообщений, исходяющих из организации или из ответов на зашифрованные сообщения, отправленные из организации.</span><span class="sxs-lookup"><span data-stu-id="0417c-127">Set up rules to encrypt any outgoing email messages, and remove encryption from encrypted messages coming from inside your organization or from replies to encrypted messages sent from your organization.</span></span>

<span data-ttu-id="0417c-128">Вы создаете правила потока почты для шифрования сообщений электронной почты с помощью новых возможностей шифрования сообщений Office 365.</span><span class="sxs-lookup"><span data-stu-id="0417c-128">You create mail flow rules to encrypt email messages with the new Office 365 Message Encryption (OME) capabilities.</span></span> <span data-ttu-id="0417c-129">Определите правила потока почты для запуска шифрования сообщений с помощью новых возможностей OME с помощью Центра администрирования Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="0417c-129">Define mail flow rules for triggering message encryption with the new OME capabilities by using the Exchange Admin Center (EAC).</span></span> 

1. <span data-ttu-id="0417c-130">В веб-браузере, используя учетную запись для работы или школы, которая получила разрешения глобального администратора, вопишите.</span><span class="sxs-lookup"><span data-stu-id="0417c-130">In a web browser, using a work or school account that has been granted global administrator permissions, sign in.</span></span>
2. <span data-ttu-id="0417c-131">Выберите плитку администрирования.</span><span class="sxs-lookup"><span data-stu-id="0417c-131">Choose the Admin tile.</span></span>
3. <span data-ttu-id="0417c-132">В центре администрирования выберите **центры администрирования > Exchange**.</span><span class="sxs-lookup"><span data-stu-id="0417c-132">In the admin center, choose **Admin centers > Exchange**.</span></span>

<span data-ttu-id="0417c-133">Дополнительные сведения см. в [тексте Определение правил потока почты для шифрования сообщений электронной почты.](../compliance/define-mail-flow-rules-to-encrypt-email.md)</span><span class="sxs-lookup"><span data-stu-id="0417c-133">For more information, see [Define mail flow rules to encrypt email messages](../compliance/define-mail-flow-rules-to-encrypt-email.md).</span></span>

### <a name="brand-your-encryption-messages"></a><span data-ttu-id="0417c-134">Марка сообщений шифрования</span><span class="sxs-lookup"><span data-stu-id="0417c-134">Brand your encryption messages</span></span>

<span data-ttu-id="0417c-135">Вы также можете применить брендинг кампании, чтобы настроить внешний вид и текст в сообщениях электронной почты.</span><span class="sxs-lookup"><span data-stu-id="0417c-135">You can also apply your campaign branding to customize the look and the text in the email messages.</span></span> <span data-ttu-id="0417c-136">Дополнительные сведения см. в [сообщении Add your organization's brand to your encrypted messages.](../compliance/email-encryption.md)</span><span class="sxs-lookup"><span data-stu-id="0417c-136">For more information, see [Add your organization's brand to your encrypted messages](../compliance/email-encryption.md).</span></span>