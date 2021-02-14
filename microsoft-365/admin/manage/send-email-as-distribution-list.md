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
description: Узнайте, как отправлять электронную почту как список рассылки в Microsoft 365.
ms.openlocfilehash: a917e59bbac40846fa289a97465f6d6e065b87ee
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399594"
---
# <a name="send-email-as-a-distribution-list"></a><span data-ttu-id="e9210-103">Отправка электронной почты в качестве списка рассылки</span><span class="sxs-lookup"><span data-stu-id="e9210-103">Send email as a distribution list</span></span>

<span data-ttu-id="e9210-104">В Microsoft 365 вы можете отправлять электронную почту в качестве списка рассылки.</span><span class="sxs-lookup"><span data-stu-id="e9210-104">In Microsoft 365, you can send email as a distribution list.</span></span> <span data-ttu-id="e9210-105">Когда пользователь, включенный в список рассылки, отвечает на сообщение, адресованное этому списку, ответное сообщение отправляется от списка рассылки, а не от отдельного пользователя.</span><span class="sxs-lookup"><span data-stu-id="e9210-105">When a person who is a member of the distribution list replies to a message sent to the distribution list, the email appears to be from the distribution list, not from the individual user.</span></span> <span data-ttu-id="e9210-106">В этой статье рассказывается о том, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="e9210-106">This topic shows you how to do this.</span></span>
  
## <a name="send-email-as-a-distribution-list"></a><span data-ttu-id="e9210-107">Отправка электронной почты в качестве списка рассылки</span><span class="sxs-lookup"><span data-stu-id="e9210-107">Send email as a distribution list</span></span>

<span data-ttu-id="e9210-108">Перед выполнением этих действий убедитесь, что вы добавлены в список рассылки Microsoft 365 и вам предоставлено разрешение "Отправить как" для него.</span><span class="sxs-lookup"><span data-stu-id="e9210-108">Before you perform these steps, make sure you've been added to a Microsoft 365 distribution list and you've have been granted Send as permission on it.</span></span>
  
 <span data-ttu-id="e9210-109">**Администраторы:** убедитесь, что вы следовали шагам в списке "Добавление пользователя Или контакта [Microsoft 365"](../email/add-user-or-contact-to-distribution-list.md) и "Разрешить участникам отправлять электронную почту в качестве разделов группы [Microsoft 365"](../create-groups/allow-members-to-send-as-or-send-on-behalf-of-group.md#allow-members-to-send-email-as-a-group) и добавили в список рассылки правильных людей.</span><span class="sxs-lookup"><span data-stu-id="e9210-109">**Admins**: Make sure you've followed the steps in the [Add a Microsoft 365 user or contact to a list](../email/add-user-or-contact-to-distribution-list.md) and [Allow members to send email as a Microsoft 365 Group](../create-groups/allow-members-to-send-as-or-send-on-behalf-of-group.md#allow-members-to-send-email-as-a-group) topics, and added the correct people to the distribution list.</span></span>
  
1. <span data-ttu-id="e9210-110">Откройте Outlook в Интернете и войдите в почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="e9210-110">Open Outlook on the web and go to your inbox.</span></span> 
    
2. <span data-ttu-id="e9210-111">Откройте сообщение, адресованное списку рассылки.</span><span class="sxs-lookup"><span data-stu-id="e9210-111">Open a message that was sent to the distribution list.</span></span> 
    
3. <span data-ttu-id="e9210-112">Выберите **"Ответить"**.</span><span class="sxs-lookup"><span data-stu-id="e9210-112">Select **Reply**.</span></span> 
    
4. <span data-ttu-id="e9210-113">At the bottom of the message, select **More** \> **Show from**.</span><span class="sxs-lookup"><span data-stu-id="e9210-113">At the bottom of the message, select **More** \> **Show from**.</span></span><br/> <span data-ttu-id="e9210-114">![Select More and then choose Show From](../../media/534f13b7-9f15-48ea-8835-ea2ed1863ece.png)</span><span class="sxs-lookup"><span data-stu-id="e9210-114">![Select More and then choose Show From](../../media/534f13b7-9f15-48ea-8835-ea2ed1863ece.png)</span></span>
  
5. <span data-ttu-id="e9210-115">Щелкните правой кнопкой мыши адрес "От" и `Ina@weewalter.me` выберите **"Удалить".**</span><span class="sxs-lookup"><span data-stu-id="e9210-115">Right-click on the From address - such as `Ina@weewalter.me` - and choose **Remove**.</span></span><br/> <span data-ttu-id="e9210-116">![Удаление псевдонима FROM](../../media/9b8d8e8f-dc46-499c-89bd-0a480603bf1f.png)</span><span class="sxs-lookup"><span data-stu-id="e9210-116">![Remove the FROM alias](../../media/9b8d8e8f-dc46-499c-89bd-0a480603bf1f.png)</span></span>
  
6. <span data-ttu-id="e9210-117">Затем введите адрес списка рассылки, например support@contoso.com, и отправьте сообщение.</span><span class="sxs-lookup"><span data-stu-id="e9210-117">Then type the distribution list address such as support@contoso.com, and send the message.</span></span> <span data-ttu-id="e9210-118">При следующем ответе из списка рассылки его адрес будет  отображаться в списке "От".</span><span class="sxs-lookup"><span data-stu-id="e9210-118">The next time you reply from the distribution list, its address will appear as an option in the **From** list.</span></span><br/><span data-ttu-id="e9210-119">![Появится псевдоним общего почтового ящика](../../media/f7632a9a-9cab-446c-9e37-23ef50c5b975.png)</span><span class="sxs-lookup"><span data-stu-id="e9210-119">![Alias of the shared mailbox appears](../../media/f7632a9a-9cab-446c-9e37-23ef50c5b975.png)</span></span>
  

