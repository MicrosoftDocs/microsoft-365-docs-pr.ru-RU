---
title: Создание записей DNS при управлении доменом с помощью Google (eNom Central)
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 3c490fbf-7833-4e43-be34-ed0dc3cce5e3
description: Узнайте, как получить доступ к eNom Central и создать DNS через страницу Google Domains.
ms.openlocfilehash: 7a1de0887b96678fb95372633b621d96f7855225
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42245144"
---
# <a name="create-dns-records-when-your-domain-is-managed-by-google-enom"></a><span data-ttu-id="09176-103">Создание записей DNS при управлении доменом с помощью Google (eNom Central)</span><span class="sxs-lookup"><span data-stu-id="09176-103">Create DNS records when your domain is managed by Google (eNom)</span></span>

 <span data-ttu-id="09176-104">**[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="09176-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="09176-105">Для переноса почтовых учетных записей в Office 365 необходимо создать DNS-запись у регистратора доменных имен.</span><span class="sxs-lookup"><span data-stu-id="09176-105">To migrate your mail accounts to Office 365, you need to create a DNS record at your domain registrar.</span></span>
  
<span data-ttu-id="09176-106">Если вы приобрели свой домен с помощью Google при регистрации учетной записи **Google Apps for work** , ваши записи DNS будут управляться Google, но зарегистрированы в eNom Central.</span><span class="sxs-lookup"><span data-stu-id="09176-106">If you purchased your domain through Google while signing up for your **Google Apps for Work** account, your DNS records are managed by Google but registered with eNom.</span></span> 
  
<span data-ttu-id="09176-107">Вы можете получить доступ к eNom Central и создать DNS через страницу Google **Domains** .</span><span class="sxs-lookup"><span data-stu-id="09176-107">You can access eNom, and create DNS, through the Google **Domains** page.</span></span> <span data-ttu-id="09176-108">Просто выполните действия, описанные в этой статье.</span><span class="sxs-lookup"><span data-stu-id="09176-108">Just follow the steps in this article.</span></span> 
  
## <a name="create-the-dns-record"></a><span data-ttu-id="09176-109">Создание DNS-записи</span><span class="sxs-lookup"><span data-stu-id="09176-109">Create the DNS record</span></span>

1. <span data-ttu-id="09176-110">В [консоли администратора Google](https://www.google.com/work/apps/business)нажмите кнопку **войти**.</span><span class="sxs-lookup"><span data-stu-id="09176-110">At the [Google Admin console](https://www.google.com/work/apps/business), select **Sign In**.</span></span>
    
    ![Google-Apps-Configure-1-1-0](../media/37a6e9f6-319e-4c02-aa18-d8d06df7953d.png)
  
2. <span data-ttu-id="09176-112">Введите имя домена, а затем нажмите кнопку **Перейти**.</span><span class="sxs-lookup"><span data-stu-id="09176-112">Enter your domain name, and then select **Go**.</span></span>
    
    ![Google-Apps-Configure-1-1-1](../media/2caf8dcb-4d40-4cfa-bc40-d634e454e699.png)
  
3. <span data-ttu-id="09176-114">В нижней части страницы выберите пункт **Дополнительные элементы управления**.</span><span class="sxs-lookup"><span data-stu-id="09176-114">At the bottom of the page, select **More controls**.</span></span>
    
    ![Google-Apps-Configure-1-2-0](../media/1518ff78-035b-423e-85a3-c16d7faa0968.png)
  
4. <span data-ttu-id="09176-116">Выберите раздел **Домены**.</span><span class="sxs-lookup"><span data-stu-id="09176-116">Select **Domains**.</span></span>
    
    ![Google-Apps-Configure-1-2-1](../media/c2972c06-9bca-43bd-9876-2cee63043bf1.png)
  
5. <span data-ttu-id="09176-118">На странице **домены** выберите **Добавить или удалить домены**.</span><span class="sxs-lookup"><span data-stu-id="09176-118">On the **Domains** page, select **Add/remove domains**.</span></span>
    
    ![Google-Apps-Configure-1-2-2](../media/07b8068f-9a05-40aa-a041-fc495c729a18.png)
  
6. <span data-ttu-id="09176-120">На странице **домены** выберите пункт **Дополнительные параметры DNS**.</span><span class="sxs-lookup"><span data-stu-id="09176-120">On the **Domains** page, select **Advanced DNS settings**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="09176-121">Если вы не приобрели доменное имя у Google при регистрации учетной записи **Google Apps for Work**, элемент **Дополнительные настройки DNS** не отображается на вашей странице **Домены**.</span><span class="sxs-lookup"><span data-stu-id="09176-121">If you didn't purchase a domain name through Google while signing up for your **Google Apps for Work** account, you won't have **Advanced DNS settings** on your **Domains** page.</span></span> <span data-ttu-id="09176-122">В этом случае, чтобы добраться до параметров DNS и выполнить это и последующие действия, вам нужно перейти непосредственно на веб-сайт узла домена.</span><span class="sxs-lookup"><span data-stu-id="09176-122">Instead, you must go directly to your domain host's web site to access your DNS settings and to perform this and the following steps.</span></span> <span data-ttu-id="09176-123">Для получения дополнительных сведений ознакомьтесь со статьей [доступ к параметрам домена G Suite](https://support.google.com/a/answer/54693?hl=en) .</span><span class="sxs-lookup"><span data-stu-id="09176-123">See [Access your G Suite domain settings](https://support.google.com/a/answer/54693?hl=en) for more information.</span></span> 
  
    ![Google — Apps — eNom Central – configure – 1-3](../media/b244b29c-e479-40be-b380-4ffa0f74b421.png)
  
7. <span data-ttu-id="09176-125">На странице **Advanced DNS (дополнительные параметры DNS** ) выберите пункт **Вход в консоль DNS**.</span><span class="sxs-lookup"><span data-stu-id="09176-125">On the **Advanced DNS settings** page, select **Sign in to DNS Console**.</span></span> <span data-ttu-id="09176-126">Запомните **учетное имя** и **пароль**.</span><span class="sxs-lookup"><span data-stu-id="09176-126">Note the **Sign-in name** and **Password** information.</span></span> <span data-ttu-id="09176-127">Они вам понадобится на следующем шаге.</span><span class="sxs-lookup"><span data-stu-id="09176-127">You'll need it in the next step.</span></span> 
    
    ![Google — Apps — eNom Central – configure – 1-4](../media/056a2767-462f-4847-acee-d01e3f773add.png)
  
8. <span data-ttu-id="09176-129">Используя значения параметров **Учетное имя** и **Пароль** со страницы **Дополнительные настройки DNS**, войдите в **диспетчер доменов** Google.</span><span class="sxs-lookup"><span data-stu-id="09176-129">Log in to the Google **Domain Manager** using the **Sign-in name** and **Password** from the **Advanced DNS settings** page.</span></span> 
    
    ![Google — Apps — eNom Central – configure – 1-5](../media/08b74652-8cdb-4560-a5fd-0899f86deee8.png)
  
9. <span data-ttu-id="09176-131">На странице " ***domain_name*** " в разделе **записи узла** нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="09176-131">On the ***domain_name*** page, in the **Host Records** section, select **Edit**.</span></span>
    
    ![Google — Apps — eNom Central – configure – 1-6](../media/d54fec18-b9d1-4796-8397-0393c964eade.png)
  
10. <span data-ttu-id="09176-133">В разделе **записи узла** нажмите кнопку **Добавить новый**.</span><span class="sxs-lookup"><span data-stu-id="09176-133">In the **Host Records** section, select **Add New**.</span></span>
    
    ![Google — Apps — eNom Central – configure – 1-7](../media/3562806a-4328-4e60-a717-0566841204cf.png)
  
11. <span data-ttu-id="09176-135">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="09176-135">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="09176-136">**HOST (УЗЕЛ)**</span><span class="sxs-lookup"><span data-stu-id="09176-136">**HOST**</span></span>|<span data-ttu-id="09176-137">**TXT VALUE**</span><span class="sxs-lookup"><span data-stu-id="09176-137">**TXT VALUE**</span></span>|<span data-ttu-id="09176-138">**ТИП ЗАПИСИ**</span><span class="sxs-lookup"><span data-stu-id="09176-138">**RECORD TYPE**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> ||<span data-ttu-id="09176-139">TXT</span><span class="sxs-lookup"><span data-stu-id="09176-139">TXT</span></span>  <br/> |

    > [!NOTE]
    > <span data-ttu-id="09176-140">This is an example.</span><span class="sxs-lookup"><span data-stu-id="09176-140">This is an example.</span></span> <span data-ttu-id="09176-141">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span><span class="sxs-lookup"><span data-stu-id="09176-141">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> 
  
    [<span data-ttu-id="09176-142">Как найти это значение?</span><span class="sxs-lookup"><span data-stu-id="09176-142">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)
  
12. <span data-ttu-id="09176-143">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="09176-143">Select **Save**.</span></span>
    
    ![Google — Apps — eNom Central – configure – 1-9](../media/7a6f7b45-8f79-487b-afe4-05949c2c04e8.png)
  
13. <span data-ttu-id="09176-145">Нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="09176-145">Select **Save Changes**.</span></span>
    
    ![Google-Apps-Configure-1-11](../media/7f321236-33fb-4a7d-9d03-26605e9e558c.png)
  
> [!NOTE]
>  <span data-ttu-id="09176-p105">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="09176-p105">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
