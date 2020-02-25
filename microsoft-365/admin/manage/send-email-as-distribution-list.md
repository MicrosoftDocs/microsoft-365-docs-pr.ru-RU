---
title: Отправление сообщений электронной почты от списков рассылки в Office 365
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a7c98273-067e-4162-b3a1-4ba081796012
description: Узнайте, как отправлять сообщения электронной почты от списков рассылки в Office 365.
ms.openlocfilehash: f165279cf6cfbedda4f122f453c2321c16f412d3
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42254850"
---
# <a name="send-email-as-a-distribution-list-in-office-365"></a><span data-ttu-id="67443-103">Отправление сообщений электронной почты от списков рассылки в Office 365</span><span class="sxs-lookup"><span data-stu-id="67443-103">Send email as a distribution list in Office 365</span></span>

<span data-ttu-id="67443-p101">Вы можете отправлять сообщения электронной почты от списков рассылки в Office 365. Когда пользователь, включенный в список рассылки, отвечает на сообщение, адресованное этому списку, ответное сообщение отправляется от списка рассылки, а не от отдельного пользователя. В этой статье рассказывается о том, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="67443-p101">In Office 365, you can send email as a distribution list. When a person who is a member of the distribution list replies to a message sent to the distribution list, the email appears to be from the distribution list, not from the individual user. This topic shows you how to do this.</span></span>
  
## <a name="send-email-as-a-distribution-list"></a><span data-ttu-id="67443-107">Отправка электронной почты в виде списка рассылки</span><span class="sxs-lookup"><span data-stu-id="67443-107">Send email as a distribution list</span></span>

<span data-ttu-id="67443-108">Перед выполнением этих действий убедитесь, что вы добавили в список рассылки Office 365 и у вас есть разрешение "Отправить как".</span><span class="sxs-lookup"><span data-stu-id="67443-108">Before you perform these steps, make sure you've been added to an Office 365 distribution list and you've have been granted Send as permission on it.</span></span>
  
 <span data-ttu-id="67443-109">**Администраторы**: Убедитесь, что вы выполнили действия, описанные в статье [Добавление пользователя или контакта Office 365 в список](../email/add-user-or-contact-to-distribution-list.md) и [предоставление участникам разрешения на отправку электронной почты в виде разделов группы Office 365](../create-groups/allow-members-to-send-as-or-send-on-behalf-of-group.md#allow-members-to-send-email-as-a-group) , и добавление в список рассылки нужных людей.</span><span class="sxs-lookup"><span data-stu-id="67443-109">**Admins**: Make sure you've followed the steps in the [Add an Office 365 user or contact to a list](../email/add-user-or-contact-to-distribution-list.md) and [Allow members to send email as an Office 365 Group](../create-groups/allow-members-to-send-as-or-send-on-behalf-of-group.md#allow-members-to-send-email-as-a-group) topics, and added the correct people to the distribution list.</span></span>
  
1. <span data-ttu-id="67443-110">Откройте Outlook в Интернете и войдите в почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="67443-110">Open Outlook on the web and go to your inbox.</span></span> 
    
2. <span data-ttu-id="67443-111">Откройте сообщение, адресованное списку рассылки.</span><span class="sxs-lookup"><span data-stu-id="67443-111">Open a message that was sent to the distribution list.</span></span> 
    
3. <span data-ttu-id="67443-112">Выберите пункт **ответить**.</span><span class="sxs-lookup"><span data-stu-id="67443-112">Select **Reply**.</span></span> 
    
4. <span data-ttu-id="67443-113">В нижней части сообщения нажмите **Дополнительно** \> **Показать из**.</span><span class="sxs-lookup"><span data-stu-id="67443-113">At the bottom of the message, select **More** \> **Show from**.</span></span><br/> <span data-ttu-id="67443-114">![Нажмите кнопку Дополнительно, а затем выберите пункт Показать из](../media/534f13b7-9f15-48ea-8835-ea2ed1863ece.png)</span><span class="sxs-lookup"><span data-stu-id="67443-114">![Select More and then choose Show From](../media/534f13b7-9f15-48ea-8835-ea2ed1863ece.png)</span></span>
  
5. <span data-ttu-id="67443-115">Щелкните правой кнопкой мыши адрес от адреса, например `Ina@weewalter.me` , и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="67443-115">Right-click on the From address - such as `Ina@weewalter.me` - and choose **Remove**.</span></span><br/> <span data-ttu-id="67443-116">![Удаление псевдонима](../media/9b8d8e8f-dc46-499c-89bd-0a480603bf1f.png)</span><span class="sxs-lookup"><span data-stu-id="67443-116">![Remove the FROM alias](../media/9b8d8e8f-dc46-499c-89bd-0a480603bf1f.png)</span></span>
  
6. <span data-ttu-id="67443-117">Затем введите адрес списка рассылки, например support@contoso.com, и отправьте сообщение.</span><span class="sxs-lookup"><span data-stu-id="67443-117">Then type the distribution list address such as support@contoso.com, and send the message.</span></span> <span data-ttu-id="67443-118">В следующий раз, когда вы ответите из списка рассылки, его адрес будет отображаться в списке " **от** ".</span><span class="sxs-lookup"><span data-stu-id="67443-118">The next time you reply from the distribution list, its address will appear as an option in the **From** list.</span></span><br/><span data-ttu-id="67443-119">![Псевдоним общего почтового ящика отображается](../media/f7632a9a-9cab-446c-9e37-23ef50c5b975.png)</span><span class="sxs-lookup"><span data-stu-id="67443-119">![Alias of the shared mailbox appears](../media/f7632a9a-9cab-446c-9e37-23ef50c5b975.png)</span></span>
  

