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
description: Отправка электронной почты в качестве списка рассылки в Microsoft 365, чтобы при ответе участника на сообщение оно было из списка рассылки.
ms.openlocfilehash: 01bff7e1d2515670c5a6faa199355e7de591f1fb
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624541"
---
# <a name="send-email-as-a-distribution-list"></a><span data-ttu-id="c651e-103">Отправка электронной почты в качестве списка рассылки</span><span class="sxs-lookup"><span data-stu-id="c651e-103">Send email as a distribution list</span></span>

<span data-ttu-id="c651e-104">В Microsoft 365 вы можете отправить электронную почту в качестве списка рассылки.</span><span class="sxs-lookup"><span data-stu-id="c651e-104">In Microsoft 365, you can send email as a distribution list.</span></span> <span data-ttu-id="c651e-105">Когда пользователь, включенный в список рассылки, отвечает на сообщение, адресованное этому списку, ответное сообщение отправляется от списка рассылки, а не от отдельного пользователя.</span><span class="sxs-lookup"><span data-stu-id="c651e-105">When a person who is a member of the distribution list replies to a message sent to the distribution list, the email appears to be from the distribution list, not from the individual user.</span></span> <span data-ttu-id="c651e-106">В этой статье рассказывается о том, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="c651e-106">This topic shows you how to do this.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="c651e-107">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="c651e-107">Before you begin</span></span>

<span data-ttu-id="c651e-108">Перед выполнением этих действий убедитесь, что вы были добавлены в список Microsoft 365 рассылки и вам было предоставлено отправить в качестве разрешения на него.</span><span class="sxs-lookup"><span data-stu-id="c651e-108">Before you perform these steps, make sure you've been added to a Microsoft 365 distribution list and you've have been granted Send as permission on it.</span></span>
  
 <span data-ttu-id="c651e-109">**Администраторы.** Убедитесь, что вы следовали шагам в списке Добавить пользователя [Microsoft 365](../email/add-user-or-contact-to-distribution-list.md) или связаться со списком и разрешить пользователям отправлять электронную почту в качестве [темы Microsoft 365 группы,](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md#allow-members-to-send-email-as-a-group) и добавьте правильных людей в список рассылки.</span><span class="sxs-lookup"><span data-stu-id="c651e-109">**Admins**: Make sure you've followed the steps in the [Add a Microsoft 365 user or contact to a list](../email/add-user-or-contact-to-distribution-list.md) and [Allow members to send email as a Microsoft 365 Group](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md#allow-members-to-send-email-as-a-group) topics, and added the correct people to the distribution list.</span></span>
  
## <a name="outlook-on-the-web"></a><span data-ttu-id="c651e-110">Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="c651e-110">Outlook on the web</span></span>

1. <span data-ttu-id="c651e-111">Откройте Outlook в Интернете и войдите в почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="c651e-111">Open Outlook on the web and go to your inbox.</span></span> 
    
2. <span data-ttu-id="c651e-112">Откройте сообщение, адресованное списку рассылки.</span><span class="sxs-lookup"><span data-stu-id="c651e-112">Open a message that was sent to the distribution list.</span></span> 
    
3. <span data-ttu-id="c651e-113">Выберите **ответ**.</span><span class="sxs-lookup"><span data-stu-id="c651e-113">Select **Reply**.</span></span> 
    
4. <span data-ttu-id="c651e-114">В нижней части сообщения выберите **Дополнительные** \> **показать из**.</span><span class="sxs-lookup"><span data-stu-id="c651e-114">At the bottom of the message, select **More** \> **Show from**.</span></span><br/> <span data-ttu-id="c651e-115">![Выберите Дополнительные и выберите Показать из](../../media/534f13b7-9f15-48ea-8835-ea2ed1863ece.png)</span><span class="sxs-lookup"><span data-stu-id="c651e-115">![Select More and then choose Show From](../../media/534f13b7-9f15-48ea-8835-ea2ed1863ece.png)</span></span>
  
5. <span data-ttu-id="c651e-116">Щелкните правой кнопкой мыши по адресу From `Ina@weewalter.me` (например, удалить) и выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="c651e-116">Right-click on the From address - such as `Ina@weewalter.me` - and choose **Remove**.</span></span><br/> <span data-ttu-id="c651e-117">![Удаление псевдонима FROM](../../media/9b8d8e8f-dc46-499c-89bd-0a480603bf1f.png)</span><span class="sxs-lookup"><span data-stu-id="c651e-117">![Remove the FROM alias](../../media/9b8d8e8f-dc46-499c-89bd-0a480603bf1f.png)</span></span>
  
6. <span data-ttu-id="c651e-118">Затем введите адрес списка рассылки, например support@contoso.com, и отправьте сообщение.</span><span class="sxs-lookup"><span data-stu-id="c651e-118">Then type the distribution list address such as support@contoso.com, and send the message.</span></span> <span data-ttu-id="c651e-119">При следующем ответе из списка рассылки его адрес будет отображаться в качестве параметра в **списке From.**</span><span class="sxs-lookup"><span data-stu-id="c651e-119">The next time you reply from the distribution list, its address will appear as an option in the **From** list.</span></span><br/><span data-ttu-id="c651e-120">![Появляется псевдоним общего почтового ящика](../../media/f7632a9a-9cab-446c-9e37-23ef50c5b975.png)</span><span class="sxs-lookup"><span data-stu-id="c651e-120">![Alias of the shared mailbox appears](../../media/f7632a9a-9cab-446c-9e37-23ef50c5b975.png)</span></span>

## <a name="outlook"></a><span data-ttu-id="c651e-121">Outlook</span><span class="sxs-lookup"><span data-stu-id="c651e-121">Outlook</span></span>

1. <span data-ttu-id="c651e-122">Откройте Outlook настольного клиента.</span><span class="sxs-lookup"><span data-stu-id="c651e-122">Open Outlook desktop client.</span></span>

2. <span data-ttu-id="c651e-123">Сопишите новое сообщение электронной почты.</span><span class="sxs-lookup"><span data-stu-id="c651e-123">Compose a New Email.</span></span> <span data-ttu-id="c651e-124">Щелкните **поле From** и выберите другой адрес **электронной почты.**</span><span class="sxs-lookup"><span data-stu-id="c651e-124">Click the **From** field and select **Other email address**.</span></span> <span data-ttu-id="c651e-125">Если вы не видите поле From, перейдите в **Параметры** и выберите **В** разделе Поля Показать.</span><span class="sxs-lookup"><span data-stu-id="c651e-125">If you do not see the From field, navigate to **Options** and select **From** in the Show fields section.</span></span>

3. <span data-ttu-id="c651e-126">Выберите адрес **списка рассылки** из глобального списка адресов.</span><span class="sxs-lookup"><span data-stu-id="c651e-126">Select the **Distribution List** address from the Global Address List.</span></span>

4. <span data-ttu-id="c651e-127">Отправка электронной почты.</span><span class="sxs-lookup"><span data-stu-id="c651e-127">Send the email.</span></span>

## <a name="related-content"></a><span data-ttu-id="c651e-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="c651e-128">Related content</span></span>

<span data-ttu-id="c651e-129">[Создание, редактирование](../email/create-edit-or-delete-a-security-group.md) или удаление группы безопасности в центре администрирования Microsoft 365 (статья)</span><span class="sxs-lookup"><span data-stu-id="c651e-129">[Create, edit, or delete a security group in the Microsoft 365 admin center](../email/create-edit-or-delete-a-security-group.md) (article)</span></span>\
<span data-ttu-id="c651e-130">[Совместная работа по](../email/email-collaboration.md) электронной почте (статья)</span><span class="sxs-lookup"><span data-stu-id="c651e-130">[Email collaboration](../email/email-collaboration.md) (article)</span></span>\
[<span data-ttu-id="c651e-131">Добавление пользователя или контакта в группу рассылки</span><span class="sxs-lookup"><span data-stu-id="c651e-131">Add a user or contact to a distribution group</span></span>](../email/add-user-or-contact-to-distribution-list.md)