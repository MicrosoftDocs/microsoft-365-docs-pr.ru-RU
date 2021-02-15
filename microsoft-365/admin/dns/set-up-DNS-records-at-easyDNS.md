---
title: Создание записей DNS для Майкрософт на сайте easyDNS
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
- MET150
- MOE150
ms.assetid: 446babfe-2e08-4cc2-bbfb-c05b854933ac
description: Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at easyDNS for Microsoft.
ms.openlocfilehash: a971a722f071ef5df9ce0fba387cfacfeb409f5b
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656823"
---
# <a name="create-dns-records-at-easydns-for-microsoft"></a><span data-ttu-id="351d3-103">Создание записей DNS для Майкрософт на сайте easyDNS</span><span class="sxs-lookup"><span data-stu-id="351d3-103">Create DNS records at easyDNS for Microsoft</span></span>

<span data-ttu-id="351d3-104">Если вы не нашли нужную информацию, см. статью [Вопросы и ответы о доменах](../setup/domains-faq.yml).</span><span class="sxs-lookup"><span data-stu-id="351d3-104">[Check the Domains FAQ ](../setup/domains-faq.yml) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="351d3-105">Вам потребуется добавить все следующие записи DNS на веб-сайте регистратора, чтобы маршрутировать почту в корпорацию Майкрософт, использовать свой домен для Teams и Skype для бизнеса и так далее.</span><span class="sxs-lookup"><span data-stu-id="351d3-105">You'll need to add all of the following DNS records at your registrar's website to route mail to Microsoft, use your domain for Teams and Skype for Business, and so on.</span></span>
  
<span data-ttu-id="351d3-106">ПРИМЕЧАНИЕ. В настоящее время записи SRV доступны НЕ во всех пакетах службы EasyDNS.</span><span class="sxs-lookup"><span data-stu-id="351d3-106">NOTE: SRV Records are currently NOT available under all easyDNS service packages.</span></span> <span data-ttu-id="351d3-107">Может потребоваться обновление до более высокого уровня обслуживания с помощью easyDNS, чтобы добавить записи SRV, необходимые для Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="351d3-107">You may need to upgrade to a higher service level with easyDNS to add SRV records which are required for Skype for Business.</span></span>
  
## <a name="verify-that-you-own-the-domain-with-a-txt-record"></a><span data-ttu-id="351d3-108">Проверка владения доменом с записью TXT</span><span class="sxs-lookup"><span data-stu-id="351d3-108">Verify that you own the domain with a TXT record</span></span>

1. <span data-ttu-id="351d3-109">Войдите [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) в систему с помощью своих учетных данных.</span><span class="sxs-lookup"><span data-stu-id="351d3-109">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="351d3-110">Под **заголовком "Все домены"** выберите **DNS.**</span><span class="sxs-lookup"><span data-stu-id="351d3-110">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="351d3-111">Под **заголовком записей TXT** выберите кнопку редактирования (значок wrench).</span><span class="sxs-lookup"><span data-stu-id="351d3-111">Under the **TXT records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="351d3-112">Введите следующие записи в текстовые поля:</span><span class="sxs-lookup"><span data-stu-id="351d3-112">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="351d3-113">**Host**</span><span class="sxs-lookup"><span data-stu-id="351d3-113">**Host**</span></span>|<span data-ttu-id="351d3-114">**Text**</span><span class="sxs-lookup"><span data-stu-id="351d3-114">**Text**</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="351d3-115">MS=msXXXXXXXXXX (используйте значение, предоставленное на странице "Домены Центра администрирования")</span><span class="sxs-lookup"><span data-stu-id="351d3-115">MS=msXXXXXXXX (Use the value provided to you on the admin center Domains page)</span></span>  <br/> |
   
5. <span data-ttu-id="351d3-116">Выберите **"ДАЛЕе".**</span><span class="sxs-lookup"><span data-stu-id="351d3-116">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="351d3-117">Проверьте правильность записи и выберите **"ПОДТВЕРДИТЬ".**</span><span class="sxs-lookup"><span data-stu-id="351d3-117">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
7. <span data-ttu-id="351d3-118">Подождите несколько минут, прежде чем продолжить, чтобы созданная вами запись распространялась по Интернету и обнаруживалась корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="351d3-118">Wait a few minutes before you continue, so that the record you just created can propagate across the Internet and be detected by Microsoft.</span></span>
    
8. <span data-ttu-id="351d3-119">Теперь, когда запись добавлена на веб-сайт регистратора доменных имен, вернитесь в продукт корпорации Майкрософт и запросите эту запись.</span><span class="sxs-lookup"><span data-stu-id="351d3-119">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
    
9. <span data-ttu-id="351d3-120">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="351d3-120">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
10. <span data-ttu-id="351d3-121">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="351d3-121">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
11. <span data-ttu-id="351d3-122">На странице **"Установка"** выберите **"Начать установку".**</span><span class="sxs-lookup"><span data-stu-id="351d3-122">On the **Setup** page, select **Start setup.**</span></span>
    
12. <span data-ttu-id="351d3-123">На странице **Verify domain** (Проверка домена) выберите **Verify** (Проверить).</span><span class="sxs-lookup"><span data-stu-id="351d3-123">On the **Verify domain** page, select **Verify**.</span></span> 
    
## <a name="add-an-mx-record-to-route-email-to-microsoft"></a><span data-ttu-id="351d3-124">Добавление записи MX для маршрутки электронной почты в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="351d3-124">Add an MX record to route email to Microsoft</span></span>

1. <span data-ttu-id="351d3-125">Войдите [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) в систему с помощью своих учетных данных.</span><span class="sxs-lookup"><span data-stu-id="351d3-125">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="351d3-126">Под **заголовком "Все домены"** выберите **DNS.**</span><span class="sxs-lookup"><span data-stu-id="351d3-126">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="351d3-127">Под **заголовком записей MX** выберите кнопку редактирования (значок wrench).</span><span class="sxs-lookup"><span data-stu-id="351d3-127">Under the **MX records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="351d3-128">Введите следующие записи в текстовые поля:</span><span class="sxs-lookup"><span data-stu-id="351d3-128">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="351d3-129">**ПОЧТА ДЛЯ ЗОНЫ**</span><span class="sxs-lookup"><span data-stu-id="351d3-129">**MAIL FOR ZONE**</span></span>|<span data-ttu-id="351d3-130">**ПОЧТОВЫЙ СЕРВЕР**</span><span class="sxs-lookup"><span data-stu-id="351d3-130">**MAIL SERVER**</span></span>|<span data-ttu-id="351d3-131">**PREF**</span><span class="sxs-lookup"><span data-stu-id="351d3-131">**PREF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="351d3-132">\<domain-key\>.mail.protection.outlook.com (Получите \<domain-key\> значение со страницы "Домены Центра администрирования")</span><span class="sxs-lookup"><span data-stu-id="351d3-132">\<domain-key\>.mail.protection.outlook.com (Get your \<domain-key\> value from the admin center Domains page)</span></span>  <br/> |<span data-ttu-id="351d3-133">0</span><span class="sxs-lookup"><span data-stu-id="351d3-133">0</span></span>  <br/> |
   
2. <span data-ttu-id="351d3-134">Если вы хотите сохранить другие записи MX для резервного копирования, скопируйте их в другое место.</span><span class="sxs-lookup"><span data-stu-id="351d3-134">If you want to save your other MX records for backup purposes, copy them down somewhere.</span></span> <span data-ttu-id="351d3-135">Прежде чем двигаться дальше, удалите здесь все остальные записи MX.</span><span class="sxs-lookup"><span data-stu-id="351d3-135">Before moving on, remove all other MX records here.</span></span>
    
5. <span data-ttu-id="351d3-136">Выберите **"ДАЛЕе".**</span><span class="sxs-lookup"><span data-stu-id="351d3-136">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="351d3-137">Проверьте правильность записи и выберите **"ПОДТВЕРДИТЬ".**</span><span class="sxs-lookup"><span data-stu-id="351d3-137">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-the-required-cname-records"></a><span data-ttu-id="351d3-138">Добавление необходимых записей CNAME</span><span class="sxs-lookup"><span data-stu-id="351d3-138">Add the required CNAME records</span></span>

1. <span data-ttu-id="351d3-139">Войдите [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) в систему с помощью своих учетных данных.</span><span class="sxs-lookup"><span data-stu-id="351d3-139">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="351d3-140">Под **заголовком "Все домены"** выберите **DNS.**</span><span class="sxs-lookup"><span data-stu-id="351d3-140">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="351d3-141">В **заголовке записей CNAME/Alias** выберите кнопку редактирования (значок wrench).</span><span class="sxs-lookup"><span data-stu-id="351d3-141">Under the **CNAME/Alias records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="351d3-142">Введите следующие записи в текстовые поля:</span><span class="sxs-lookup"><span data-stu-id="351d3-142">Enter the following records in the text fields:</span></span>


    |<span data-ttu-id="351d3-143">**HOST (УЗЕЛ)**</span><span class="sxs-lookup"><span data-stu-id="351d3-143">**HOST**</span></span>|<span data-ttu-id="351d3-144">**Address (Must end with a ".")**</span><span class="sxs-lookup"><span data-stu-id="351d3-144">**Address (Must end with a ".")**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="351d3-145">autodiscover</span><span class="sxs-lookup"><span data-stu-id="351d3-145">autodiscover</span></span>  <br/> |<span data-ttu-id="351d3-146">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="351d3-146">autodiscover.outlook.com.</span></span>  <br/> |
    |<span data-ttu-id="351d3-147">sip</span><span class="sxs-lookup"><span data-stu-id="351d3-147">sip</span></span>  <br/> |<span data-ttu-id="351d3-148">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="351d3-148">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="351d3-149">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="351d3-149">lyncdiscover</span></span>  <br/> |<span data-ttu-id="351d3-150">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="351d3-150">webdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="351d3-151">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="351d3-151">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="351d3-152">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="351d3-152">enterpriseregistration.windows.net.</span></span>  <br/> |
    |<span data-ttu-id="351d3-153">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="351d3-153">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="351d3-154">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="351d3-154">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |
   
5. <span data-ttu-id="351d3-155">Выберите **"ДАЛЕе".**</span><span class="sxs-lookup"><span data-stu-id="351d3-155">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="351d3-156">Проверьте правильность записи и выберите **"ПОДТВЕРДИТЬ".**</span><span class="sxs-lookup"><span data-stu-id="351d3-156">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="351d3-157">Добавление записи TXT для SPF, предотвращающей рассылку спама</span><span class="sxs-lookup"><span data-stu-id="351d3-157">Add a TXT record for SPF to help prevent email spam</span></span>

1. <span data-ttu-id="351d3-158">Войдите [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) в систему с помощью своих учетных данных.</span><span class="sxs-lookup"><span data-stu-id="351d3-158">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="351d3-159">Под **заголовком "Все домены"** выберите **DNS.**</span><span class="sxs-lookup"><span data-stu-id="351d3-159">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="351d3-160">Под **заголовком записей TXT** выберите кнопку редактирования (значок wrench).</span><span class="sxs-lookup"><span data-stu-id="351d3-160">Under the **TXT records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="351d3-161">Введите следующие записи в текстовые поля:</span><span class="sxs-lookup"><span data-stu-id="351d3-161">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="351d3-162">**Host**</span><span class="sxs-lookup"><span data-stu-id="351d3-162">**Host**</span></span>|<span data-ttu-id="351d3-163">**Text**</span><span class="sxs-lookup"><span data-stu-id="351d3-163">**Text**</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="351d3-164">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="351d3-164">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> |
   
5. <span data-ttu-id="351d3-165">Выберите **"ДАЛЕе".**</span><span class="sxs-lookup"><span data-stu-id="351d3-165">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="351d3-166">Проверьте правильность записи и выберите **"ПОДТВЕРДИТЬ".**</span><span class="sxs-lookup"><span data-stu-id="351d3-166">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="351d3-167">Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="351d3-167">Add the two SRV records that are required for Microsoft</span></span>

<span data-ttu-id="351d3-168">ПРИМЕЧАНИЕ. В настоящее время записи SRV НЕДОСТУПНЫ на уровне службы easyDNS "Домен плюс".</span><span class="sxs-lookup"><span data-stu-id="351d3-168">NOTE: SRV Records are currently NOT available under easyDNS' Domain Plus service level.</span></span> <span data-ttu-id="351d3-169">Для добавления записей SRV может потребоваться обновление до более высокого уровня обслуживания с помощью easyDNS</span><span class="sxs-lookup"><span data-stu-id="351d3-169">You may need to upgrade to a higher service level with easyDNS to add SRV records</span></span> 
  
1. <span data-ttu-id="351d3-170">Войдите [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) в систему с помощью своих учетных данных.</span><span class="sxs-lookup"><span data-stu-id="351d3-170">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="351d3-171">Под **заголовком "Все домены"** выберите **DNS.**</span><span class="sxs-lookup"><span data-stu-id="351d3-171">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="351d3-172">Под **заголовком записей SRV** выберите кнопку редактирования (значок wrench).</span><span class="sxs-lookup"><span data-stu-id="351d3-172">Under the **SRV records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="351d3-173">Введите следующие записи в текстовые поля:</span><span class="sxs-lookup"><span data-stu-id="351d3-173">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="351d3-174">**SERVICE (СЛУЖБА)**</span><span class="sxs-lookup"><span data-stu-id="351d3-174">**SERVICE**</span></span>|<span data-ttu-id="351d3-175">**PROTO**</span><span class="sxs-lookup"><span data-stu-id="351d3-175">**PROTO**</span></span>|<span data-ttu-id="351d3-176">**HOST (УЗЕЛ)**</span><span class="sxs-lookup"><span data-stu-id="351d3-176">**HOST**</span></span>|<span data-ttu-id="351d3-177">**PRI**</span><span class="sxs-lookup"><span data-stu-id="351d3-177">**PRI**</span></span>|<span data-ttu-id="351d3-178">**WGT**</span><span class="sxs-lookup"><span data-stu-id="351d3-178">**WGT**</span></span>|<span data-ttu-id="351d3-179">**PORT (ПОРТ)**</span><span class="sxs-lookup"><span data-stu-id="351d3-179">**PORT**</span></span>|<span data-ttu-id="351d3-180">**TARGET(Must end with a ".")**</span><span class="sxs-lookup"><span data-stu-id="351d3-180">**TARGET(Must end with a ".")**</span></span>|<span data-ttu-id="351d3-181">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="351d3-181">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="351d3-182">_sip</span><span class="sxs-lookup"><span data-stu-id="351d3-182">_sip</span></span>  <br/> |<span data-ttu-id="351d3-183">TLS</span><span class="sxs-lookup"><span data-stu-id="351d3-183">TLS</span></span>  <br/> |@  <br/> |<span data-ttu-id="351d3-184">100</span><span class="sxs-lookup"><span data-stu-id="351d3-184">100</span></span>  <br/> |<span data-ttu-id="351d3-185">1 </span><span class="sxs-lookup"><span data-stu-id="351d3-185">1</span></span>  <br/> |<span data-ttu-id="351d3-186">443</span><span class="sxs-lookup"><span data-stu-id="351d3-186">443</span></span>  <br/> |<span data-ttu-id="351d3-187">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="351d3-187">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="351d3-188">1800</span><span class="sxs-lookup"><span data-stu-id="351d3-188">1800</span></span>  <br/> |
    |<span data-ttu-id="351d3-189">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="351d3-189">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="351d3-190">TCP</span><span class="sxs-lookup"><span data-stu-id="351d3-190">TCP</span></span>  <br/> |@  <br/> |<span data-ttu-id="351d3-191">100</span><span class="sxs-lookup"><span data-stu-id="351d3-191">100</span></span>  <br/> |<span data-ttu-id="351d3-192">1 </span><span class="sxs-lookup"><span data-stu-id="351d3-192">1</span></span>  <br/> |<span data-ttu-id="351d3-193">5061</span><span class="sxs-lookup"><span data-stu-id="351d3-193">5061</span></span>  <br/> |<span data-ttu-id="351d3-194">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="351d3-194">sipfed.online.lync.com.</span></span>  <br/> |<span data-ttu-id="351d3-195">1800</span><span class="sxs-lookup"><span data-stu-id="351d3-195">1800</span></span>  <br/> |
   
5. <span data-ttu-id="351d3-196">Выберите **"ДАЛЕе".**</span><span class="sxs-lookup"><span data-stu-id="351d3-196">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="351d3-197">Проверьте правильность записи и выберите **"ПОДТВЕРДИТЬ".**</span><span class="sxs-lookup"><span data-stu-id="351d3-197">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    

