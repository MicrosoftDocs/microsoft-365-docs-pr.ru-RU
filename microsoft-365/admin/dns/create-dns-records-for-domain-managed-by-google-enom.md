---
title: Создание записей DNS, когда доменом управляет Google (eNom)
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 3c490fbf-7833-4e43-be34-ed0dc3cce5e3
description: Узнайте, как получить доступ к eNom и создать DNS на странице "Домены Google".
ms.openlocfilehash: 3294be667653c568fbbd1a911bcfab9b6ea7788b
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656859"
---
# <a name="create-dns-records-when-your-domain-is-managed-by-google-enom"></a><span data-ttu-id="81e84-103">Создание записей DNS, когда доменом управляет Google (eNom)</span><span class="sxs-lookup"><span data-stu-id="81e84-103">Create DNS records when your domain is managed by Google (eNom)</span></span>

 <span data-ttu-id="81e84-104">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="81e84-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="81e84-105">Чтобы перенести почтовые учетные записи в Корпорацию Майкрософт, необходимо создать запись DNS у регистратора доменных имен.</span><span class="sxs-lookup"><span data-stu-id="81e84-105">To migrate your mail accounts to Microsoft, you need to create a DNS record at your domain registrar.</span></span>
  
<span data-ttu-id="81e84-106">Если вы приобрели домен через Google при регистрации учетной записи **Google Apps for Work,** ваши записи DNS управляются Google, но зарегистрированы в eNom.</span><span class="sxs-lookup"><span data-stu-id="81e84-106">If you purchased your domain through Google while signing up for your **Google Apps for Work** account, your DNS records are managed by Google but registered with eNom.</span></span> 
  
<span data-ttu-id="81e84-107">Вы можете получить доступ к eNom и создать DNS на странице **"Домены** Google".</span><span class="sxs-lookup"><span data-stu-id="81e84-107">You can access eNom, and create DNS, through the Google **Domains** page.</span></span> <span data-ttu-id="81e84-108">Просто выполните действия, описанные в этой статье.</span><span class="sxs-lookup"><span data-stu-id="81e84-108">Just follow the steps in this article.</span></span> 
  
## <a name="create-the-dns-record"></a><span data-ttu-id="81e84-109">Создание DNS-записи</span><span class="sxs-lookup"><span data-stu-id="81e84-109">Create the DNS record</span></span>

1. <span data-ttu-id="81e84-110">В консоли [администратора Google](https://www.google.com/work/apps/business)выберите **"Войти"**.</span><span class="sxs-lookup"><span data-stu-id="81e84-110">At the [Google Admin console](https://www.google.com/work/apps/business), select **Sign In**.</span></span>
    
    ![Google-Apps-Configure-1-1-0](../../media/37a6e9f6-319e-4c02-aa18-d8d06df7953d.png)
  
2. <span data-ttu-id="81e84-112">Введите доменное имя и выберите **"Перейти".**</span><span class="sxs-lookup"><span data-stu-id="81e84-112">Enter your domain name, and then select **Go**.</span></span>
    
    ![Google-Apps-Configure-1-1-1](../../media/2caf8dcb-4d40-4cfa-bc40-d634e454e699.png)
  
3. <span data-ttu-id="81e84-114">В нижней части страницы выберите **"Дополнительные элементы управления".**</span><span class="sxs-lookup"><span data-stu-id="81e84-114">At the bottom of the page, select **More controls**.</span></span>
    
    ![Google-Apps-Configure-1-2-0](../../media/1518ff78-035b-423e-85a3-c16d7faa0968.png)
  
4. <span data-ttu-id="81e84-116">Выберите раздел **Домены**.</span><span class="sxs-lookup"><span data-stu-id="81e84-116">Select **Domains**.</span></span>
    
    ![Google-Apps-Configure-1-2-1](../../media/c2972c06-9bca-43bd-9876-2cee63043bf1.png)
  
5. <span data-ttu-id="81e84-118">На странице **"Домены"** выберите **"Добавить или удалить домены".**</span><span class="sxs-lookup"><span data-stu-id="81e84-118">On the **Domains** page, select **Add/remove domains**.</span></span>
    
    ![Google-Apps-Configure-1-2-2](../../media/07b8068f-9a05-40aa-a041-fc495c729a18.png)
  
6. <span data-ttu-id="81e84-120">На странице **"Домены"** выберите **дополнительные параметры DNS.**</span><span class="sxs-lookup"><span data-stu-id="81e84-120">On the **Domains** page, select **Advanced DNS settings**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="81e84-121">Если вы не приобрели доменное имя у Google при регистрации учетной записи **Google Apps for Work**, элемент **Дополнительные настройки DNS** не отображается на вашей странице **Домены**.</span><span class="sxs-lookup"><span data-stu-id="81e84-121">If you didn't purchase a domain name through Google while signing up for your **Google Apps for Work** account, you won't have **Advanced DNS settings** on your **Domains** page.</span></span> <span data-ttu-id="81e84-122">В этом случае, чтобы добраться до параметров DNS и выполнить это и последующие действия, вам нужно перейти непосредственно на веб-сайт узла домена.</span><span class="sxs-lookup"><span data-stu-id="81e84-122">Instead, you must go directly to your domain host's web site to access your DNS settings and to perform this and the following steps.</span></span> <span data-ttu-id="81e84-123">Дополнительные [сведения см.](https://support.google.com/a/answer/54693?hl=en) в параметрах домена Access для G Suite.</span><span class="sxs-lookup"><span data-stu-id="81e84-123">See [Access your G Suite domain settings](https://support.google.com/a/answer/54693?hl=en) for more information.</span></span> 
  
    ![Google-Apps-eNom-Configure-1-3](../../media/b244b29c-e479-40be-b380-4ffa0f74b421.png)
  
7. <span data-ttu-id="81e84-125">На странице **"Дополнительные параметры DNS"** выберите **"Войти в консоль DNS".**</span><span class="sxs-lookup"><span data-stu-id="81e84-125">On the **Advanced DNS settings** page, select **Sign in to DNS Console**.</span></span> <span data-ttu-id="81e84-126">Запомните **учетное имя** и **пароль**.</span><span class="sxs-lookup"><span data-stu-id="81e84-126">Note the **Sign-in name** and **Password** information.</span></span> <span data-ttu-id="81e84-127">Они вам понадобится на следующем шаге.</span><span class="sxs-lookup"><span data-stu-id="81e84-127">You'll need it in the next step.</span></span> 
    
    ![Google-Apps-eNom-Configure-1-4](../../media/056a2767-462f-4847-acee-d01e3f773add.png)
  
8. <span data-ttu-id="81e84-129">Используя значения параметров **Учетное имя** и **Пароль** со страницы **Дополнительные настройки DNS**, войдите в **диспетчер доменов** Google.</span><span class="sxs-lookup"><span data-stu-id="81e84-129">Log in to the Google **Domain Manager** using the **Sign-in name** and **Password** from the **Advanced DNS settings** page.</span></span> 
    
    ![Google-Apps-eNom-Configure-1-5](../../media/08b74652-8cdb-4560-a5fd-0899f86deee8.png)
  
9. <span data-ttu-id="81e84-131">На странице domain_name _, в разделе ***_Host* Records,** выберите "Изменить". </span><span class="sxs-lookup"><span data-stu-id="81e84-131">On the **_domain_name_*_ page, in the _\* Host Records*\* section, select **Edit**.</span></span>
    
    ![Google-Apps-eNom-Configure-1-6](../../media/d54fec18-b9d1-4796-8397-0393c964eade.png)
  
10. <span data-ttu-id="81e84-133">В разделе **"Записи хоста"** выберите **"Добавить новые".**</span><span class="sxs-lookup"><span data-stu-id="81e84-133">In the **Host Records** section, select **Add New**.</span></span>
    
    ![Google-Apps-eNom-Configure-1-7](../../media/3562806a-4328-4e60-a717-0566841204cf.png)
  
11. <span data-ttu-id="81e84-135">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="81e84-135">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="81e84-136">**HOST (УЗЕЛ)**</span><span class="sxs-lookup"><span data-stu-id="81e84-136">**HOST**</span></span>|<span data-ttu-id="81e84-137">**TXT VALUE**</span><span class="sxs-lookup"><span data-stu-id="81e84-137">**TXT VALUE**</span></span>|<span data-ttu-id="81e84-138">**ТИП ЗАПИСИ**</span><span class="sxs-lookup"><span data-stu-id="81e84-138">**RECORD TYPE**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> ||<span data-ttu-id="81e84-139">TXT</span><span class="sxs-lookup"><span data-stu-id="81e84-139">TXT</span></span>  <br/> |

    > [!NOTE]
    > <span data-ttu-id="81e84-140">This is an example.</span><span class="sxs-lookup"><span data-stu-id="81e84-140">This is an example.</span></span> <span data-ttu-id="81e84-141">Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="81e84-141">Use your specific **Destination or Points to Address** value here, from the table.</span></span> 
  
    [<span data-ttu-id="81e84-142">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="81e84-142">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)
  
12. <span data-ttu-id="81e84-143">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="81e84-143">Select **Save**.</span></span>
    
    ![Google-Apps-eNom-Configure-1-9](../../media/7a6f7b45-8f79-487b-afe4-05949c2c04e8.png)
  
13. <span data-ttu-id="81e84-145">Выберите **"Сохранить изменения"**.</span><span class="sxs-lookup"><span data-stu-id="81e84-145">Select **Save Changes**.</span></span>
    
    ![Google-Apps-Configure-1-11](../../media/7f321236-33fb-4a7d-9d03-26605e9e558c.png)
  
> [!NOTE]
>  <span data-ttu-id="81e84-p105">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="81e84-p105">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
