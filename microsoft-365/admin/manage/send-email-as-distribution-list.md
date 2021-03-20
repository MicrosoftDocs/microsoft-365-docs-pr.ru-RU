---
title: Отправка электронной почты в качестве списка рассылки
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a7c98273-067e-4162-b3a1-4ba081796012
description: Узнайте, как отправлять электронную почту в качестве списка рассылки в Microsoft 365.
ms.openlocfilehash: 379f2471fd38da5098bf8f2ca82f4f76ee82bd8e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915162"
---
# <a name="send-email-as-a-distribution-list"></a><span data-ttu-id="a0606-103">Отправка электронной почты в качестве списка рассылки</span><span class="sxs-lookup"><span data-stu-id="a0606-103">Send email as a distribution list</span></span>

<span data-ttu-id="a0606-104">В Microsoft 365 можно отправить электронную почту в качестве списка рассылки.</span><span class="sxs-lookup"><span data-stu-id="a0606-104">In Microsoft 365, you can send email as a distribution list.</span></span> <span data-ttu-id="a0606-105">Когда пользователь, включенный в список рассылки, отвечает на сообщение, адресованное этому списку, ответное сообщение отправляется от списка рассылки, а не от отдельного пользователя.</span><span class="sxs-lookup"><span data-stu-id="a0606-105">When a person who is a member of the distribution list replies to a message sent to the distribution list, the email appears to be from the distribution list, not from the individual user.</span></span> <span data-ttu-id="a0606-106">В этой статье рассказывается о том, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="a0606-106">This topic shows you how to do this.</span></span>
  
## <a name="send-email-as-a-distribution-list"></a><span data-ttu-id="a0606-107">Отправка электронной почты в качестве списка рассылки</span><span class="sxs-lookup"><span data-stu-id="a0606-107">Send email as a distribution list</span></span>

<span data-ttu-id="a0606-108">Перед выполнением этих действий убедитесь, что вы были добавлены в список рассылки Microsoft 365 и вам было предоставлено отправить в качестве разрешения на него.</span><span class="sxs-lookup"><span data-stu-id="a0606-108">Before you perform these steps, make sure you've been added to a Microsoft 365 distribution list and you've have been granted Send as permission on it.</span></span>
  
 <span data-ttu-id="a0606-109">**Администраторы.** Убедитесь, что вы следовали шагам пользователя Или контакта [Microsoft 365](../email/add-user-or-contact-to-distribution-list.md) к списку и разрешить пользователям отправлять электронную почту в качестве [темы группы Microsoft 365,](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md#allow-members-to-send-email-as-a-group) и добавьте правильных людей в список рассылки.</span><span class="sxs-lookup"><span data-stu-id="a0606-109">**Admins**: Make sure you've followed the steps in the [Add a Microsoft 365 user or contact to a list](../email/add-user-or-contact-to-distribution-list.md) and [Allow members to send email as a Microsoft 365 Group](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md#allow-members-to-send-email-as-a-group) topics, and added the correct people to the distribution list.</span></span>
  
1. <span data-ttu-id="a0606-110">Откройте Outlook в Интернете и войдите в почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="a0606-110">Open Outlook on the web and go to your inbox.</span></span> 
    
2. <span data-ttu-id="a0606-111">Откройте сообщение, адресованное списку рассылки.</span><span class="sxs-lookup"><span data-stu-id="a0606-111">Open a message that was sent to the distribution list.</span></span> 
    
3. <span data-ttu-id="a0606-112">Выберите **ответ**.</span><span class="sxs-lookup"><span data-stu-id="a0606-112">Select **Reply**.</span></span> 
    
4. <span data-ttu-id="a0606-113">В нижней части сообщения выберите **Дополнительные** \> **показать из**.</span><span class="sxs-lookup"><span data-stu-id="a0606-113">At the bottom of the message, select **More** \> **Show from**.</span></span><br/> <span data-ttu-id="a0606-114">![Выберите Дополнительные и выберите Показать из](../../media/534f13b7-9f15-48ea-8835-ea2ed1863ece.png)</span><span class="sxs-lookup"><span data-stu-id="a0606-114">![Select More and then choose Show From](../../media/534f13b7-9f15-48ea-8835-ea2ed1863ece.png)</span></span>
  
5. <span data-ttu-id="a0606-115">Щелкните правой кнопкой мыши по адресу From `Ina@weewalter.me` (например, удалить) и выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="a0606-115">Right-click on the From address - such as `Ina@weewalter.me` - and choose **Remove**.</span></span><br/> <span data-ttu-id="a0606-116">![Удаление псевдонима FROM](../../media/9b8d8e8f-dc46-499c-89bd-0a480603bf1f.png)</span><span class="sxs-lookup"><span data-stu-id="a0606-116">![Remove the FROM alias](../../media/9b8d8e8f-dc46-499c-89bd-0a480603bf1f.png)</span></span>
  
6. <span data-ttu-id="a0606-117">Затем введите адрес списка рассылки, например support@contoso.com, и отправьте сообщение.</span><span class="sxs-lookup"><span data-stu-id="a0606-117">Then type the distribution list address such as support@contoso.com, and send the message.</span></span> <span data-ttu-id="a0606-118">При следующем ответе из списка рассылки его адрес будет отображаться в качестве параметра в **списке From.**</span><span class="sxs-lookup"><span data-stu-id="a0606-118">The next time you reply from the distribution list, its address will appear as an option in the **From** list.</span></span><br/><span data-ttu-id="a0606-119">![Появляется псевдоним общего почтового ящика](../../media/f7632a9a-9cab-446c-9e37-23ef50c5b975.png)</span><span class="sxs-lookup"><span data-stu-id="a0606-119">![Alias of the shared mailbox appears](../../media/f7632a9a-9cab-446c-9e37-23ef50c5b975.png)</span></span>
