---
title: Шифрование почты Exchange Online с помощью AD RMS
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/13/2017
audience: End User
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2c956776-0016-4be6-b4cd-133a237f4a9e
ms.custom:
- seo-marvel-apr2020
description: Узнайте, как настроить IRM Exchange Online для использования локальной службы управления правами Active Directory (AD RMS) для удовлетворения требований Организации.
ms.openlocfilehash: be53b54328c2c1e08e51a84b7251e23c3e7468c3
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "44815446"
---
# <a name="exchange-online-mail-encryption-with-ad-rms"></a>Шифрование почты Exchange Online с помощью AD RMS

Чтобы предотвратить утечку информации, служба Exchange Online использует функцию управления правами на доступ к данным (IRM), которая обеспечивает защиту сообщений и вложений в сети и вне сети. Вы можете настроить службу управления правами Exchange Online для использования локальной службы управления правами Active Directory (AD RMS), если это необходимо, для удовлетворения требований Организации. Это нетипичный сценарий. Если у вас нет требования использовать службу управления правами Active Directory, используйте [Шифрование сообщений Office 365](ome.md) . 

Защиту IRM могут применять пользователи (в Microsoft Outlook или Outlook в Интернете) и администраторы (с помощью правил защиты транспорта или правил защиты Outlook). IRM помогает администраторам и пользователям указывать, кто может открывать, пересылать, печатать и копировать конфиденциальные данные из электронной переписки.
  
## <a name="changes-to-how-irm-works-with-office-365-message-encryption-ome-and-azure-active-directory"></a>Изменения в работе IRM со службой шифрования сообщений Office 365 и Azure Active Directory

As of September 2017, when you set up the new Office 365 Message Encryption capabilities for your organization, you also set up IRM for use with Azure Rights Management (Azure RMS). You no longer set up IRM with Azure RMS separately. Instead, OME and rights management work seamlessly together. For more details about the new capabilities, see [Office 365 Message Encryption FAQ](https://docs.microsoft.com/microsoft-365/compliance/ome-faq). If you're ready to get started using the new OME capabilities within your organization, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities).
  
## <a name="how-irm-works-with-exchange-online-and-active-directory-rights-management-services"></a>Взаимодействие IRM с Exchange Online и службами Active Directory Rights Management

Exchange Online IRM uses on-premises Active Directory Rights Management Services (AD RMS), an information protection technology in Windows Server 2008 and later. IRM protection is applied to email by applying an AD RMS rights policy template to an email message. Rights are attached to the message itself so that protection occurs online and offline and inside and outside of your organization's firewall.
  
Users can apply a template to an email message to control the permissions that recipients have on a message. Actions, such as forwarding, extracting information from a message, saving a message or printing a message can be controlled by applying an AD RMS rights policy to the message.
  
Для защиты IRM можно использовать сервер AD RMS под управлением Windows Server 2008 или более поздней версии. Этот сервер можно использовать для управления шаблонами политики прав AD RMS в облачной организации. Сервер AD RMS также нужен, чтобы пользователи могли применять защиту IRM к отправляемым сообщениям. Дополнительные сведения см. в разделе [Configure IRM to use an on-premises AD RMS server](configure-irm-to-use-an-on-premises-ad-rms-server.md). 
  
После включения защиты IRM с ее помощью можно защищать сообщения следующим образом.
  
- **Users can manually apply a template using Outlook and Outlook on the web.** Users can apply an AD RMS rights policy template to an email message by selecting the template from the **Set permissions** list. When users send an IRM-protected message, any attached files that use a supported format also receive the same IRM protection as the message. IRM protection is applied to files associated with Word, Excel, and PowerPoint, as well as .xps files and attached email messages. 
    
- **Administrators can use transport protection rules to apply IRM protection automatically to both Outlook and Outlook on the web.** You can create transport protection rules to IRM-protect messages. Configure the transport protection rule action to apply an AD RMS rights policy template to messages that meet the rule condition. After you enable IRM, your organization's AD RMS rights policy templates are available to use with the transport protection rule action called **Apply rights protection to the message with**.
    
- **Administrators can create Outlook protection rules.** Outlook protection rules automatically apply IRM-protection to messages in Outlook 2010 (not Outlook on the web) based on message conditions that include the sender's department, who the message is sent to, and whether recipients are inside or outside your organization. For details, see [Create an Outlook Protection Rule](https://technet.microsoft.com/library/da64750d-faaf-44de-ad8c-888eba7fbdbf.aspx).
    

