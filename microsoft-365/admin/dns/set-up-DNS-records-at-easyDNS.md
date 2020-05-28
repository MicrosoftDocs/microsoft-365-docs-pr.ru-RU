---
title: Создание записей DNS на сайте easyDNS для Майкрософт
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
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
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб по адресу easyDNS для Майкрософт.
ms.openlocfilehash: 24f477d240af936975141c53d382e114a24c0ac5
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400236"
---
# <a name="create-dns-records-at-easydns-for-microsoft"></a><span data-ttu-id="58528-103">Создание записей DNS на сайте easyDNS для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="58528-103">Create DNS records at easyDNS for Microsoft</span></span>

<span data-ttu-id="58528-104">Если вы не нашли нужную информацию, см. статью [Вопросы и ответы о доменах](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="58528-104">[Check the Domains FAQ ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="58528-105">Вам потребуется добавить все следующие записи DNS на веб-сайте регистратора, чтобы маршрутизировать почту в корпорацию Майкрософт, использовать домен для Teams и Skype для бизнеса и т. д.</span><span class="sxs-lookup"><span data-stu-id="58528-105">You'll need to add all of the following DNS records at your registrar's website to route mail to Microsoft, use your domain for Teams and Skype for Business, and so on.</span></span>
  
<span data-ttu-id="58528-106">NOTE: записи SRV в настоящее время недоступны в пакетах службы easyDNS.</span><span class="sxs-lookup"><span data-stu-id="58528-106">NOTE: SRV Records are currently NOT available under all easyDNS service packages.</span></span> <span data-ttu-id="58528-107">Для добавления записей SRV, необходимых для Skype для бизнеса, вам может потребоваться выполнить обновление до более высокого уровня обслуживания с easyDNS.</span><span class="sxs-lookup"><span data-stu-id="58528-107">You may need to upgrade to a higher service level with easyDNS to add SRV records which are required for Skype for Business.</span></span>
  
## <a name="verify-that-you-own-the-domain-with-a-txt-record"></a><span data-ttu-id="58528-108">Проверка принадлежности домена к записи TXT</span><span class="sxs-lookup"><span data-stu-id="58528-108">Verify that you own the domain with a TXT record</span></span>

1. <span data-ttu-id="58528-109">Перейдите на страницу [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) и войдите с помощью учетных данных.</span><span class="sxs-lookup"><span data-stu-id="58528-109">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="58528-110">В заголовке **все домены** выберите **DNS.**</span><span class="sxs-lookup"><span data-stu-id="58528-110">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="58528-111">В разделе **txt Records (записи TXT** ) нажмите кнопку Edit (значок вренч).</span><span class="sxs-lookup"><span data-stu-id="58528-111">Under the **TXT records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="58528-112">Введите в текстовые поля следующие записи:</span><span class="sxs-lookup"><span data-stu-id="58528-112">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="58528-113">**Host** (Узел)</span><span class="sxs-lookup"><span data-stu-id="58528-113">**Host**</span></span>|<span data-ttu-id="58528-114">**Text**</span><span class="sxs-lookup"><span data-stu-id="58528-114">**Text**</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="58528-115">MS = Мскскскскскскскскс (используйте значение, указанное на странице "домены центра администрирования")</span><span class="sxs-lookup"><span data-stu-id="58528-115">MS=msXXXXXXXX (Use the value provided to you on the admin center Domains page)</span></span>  <br/> |
   
5. <span data-ttu-id="58528-116">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="58528-116">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="58528-117">Убедитесь, что запись верна, а затем нажмите кнопку **подтвердить**.</span><span class="sxs-lookup"><span data-stu-id="58528-117">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
7. <span data-ttu-id="58528-118">Подождите несколько минут, прежде чем продолжить, чтобы созданная запись могла передаваться через Интернет и распознаются корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="58528-118">Wait a few minutes before you continue, so that the record you just created can propagate across the Internet and be detected by Microsoft.</span></span>
    
8. <span data-ttu-id="58528-119">Теперь, когда запись добавлена на веб-сайт регистратора доменных имен, вернитесь в продукт корпорации Майкрософт и запросите эту запись.</span><span class="sxs-lookup"><span data-stu-id="58528-119">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
    
9. <span data-ttu-id="58528-120">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="58528-120">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
10. <span data-ttu-id="58528-121">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="58528-121">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
11. <span data-ttu-id="58528-122">На странице **Настройка** выберите пункт **Запуск программы установки.**</span><span class="sxs-lookup"><span data-stu-id="58528-122">On the **Setup** page, select **Start setup.**</span></span>
    
12. <span data-ttu-id="58528-123">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="58528-123">On the **Verify domain** page, select **Verify**.</span></span> 
    
## <a name="add-an-mx-record-to-route-email-to-microsoft"></a><span data-ttu-id="58528-124">Добавление записи MX для маршрутизации электронной почты в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="58528-124">Add an MX record to route email to Microsoft</span></span>

1. <span data-ttu-id="58528-125">Перейдите на страницу [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) и войдите с помощью учетных данных.</span><span class="sxs-lookup"><span data-stu-id="58528-125">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="58528-126">В заголовке **все домены** выберите **DNS.**</span><span class="sxs-lookup"><span data-stu-id="58528-126">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="58528-127">В заголовке **MX Record (запись MX** ) нажмите кнопку Edit (значок вренч).</span><span class="sxs-lookup"><span data-stu-id="58528-127">Under the **MX records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="58528-128">Введите в текстовые поля следующие записи:</span><span class="sxs-lookup"><span data-stu-id="58528-128">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="58528-129">**ПОЧТА ДЛЯ ЗОНЫ**</span><span class="sxs-lookup"><span data-stu-id="58528-129">**MAIL FOR ZONE**</span></span>|<span data-ttu-id="58528-130">**ПОЧТОВЫЙ СЕРВЕР**</span><span class="sxs-lookup"><span data-stu-id="58528-130">**MAIL SERVER**</span></span>|<span data-ttu-id="58528-131">**преф**</span><span class="sxs-lookup"><span data-stu-id="58528-131">**PREF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="58528-132">\<domain-key\>. mail.protection.outlook.com (получите \<domain-key\> значение на странице "домены центра администрирования")</span><span class="sxs-lookup"><span data-stu-id="58528-132">\<domain-key\>.mail.protection.outlook.com (Get your \<domain-key\> value from the admin center Domains page)</span></span>  <br/> |<span data-ttu-id="58528-133">нуль</span><span class="sxs-lookup"><span data-stu-id="58528-133">0</span></span>  <br/> |
   
2. <span data-ttu-id="58528-134">Если вы хотите сохранить другие записи MX для целей резервного копирования, скопируйте их в любое место.</span><span class="sxs-lookup"><span data-stu-id="58528-134">If you want to save your other MX records for backup purposes, copy them down somewhere.</span></span> <span data-ttu-id="58528-135">Перед перемещением удалите все остальные записи MX здесь.</span><span class="sxs-lookup"><span data-stu-id="58528-135">Before moving on, remove all other MX records here.</span></span>
    
5. <span data-ttu-id="58528-136">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="58528-136">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="58528-137">Убедитесь, что запись верна, а затем нажмите кнопку **подтвердить**.</span><span class="sxs-lookup"><span data-stu-id="58528-137">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-the-required-cname-records"></a><span data-ttu-id="58528-138">Добавление необходимых записей CNAME</span><span class="sxs-lookup"><span data-stu-id="58528-138">Add the required CNAME records</span></span>

1. <span data-ttu-id="58528-139">Перейдите на страницу [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) и войдите с помощью учетных данных.</span><span class="sxs-lookup"><span data-stu-id="58528-139">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="58528-140">В заголовке **все домены** выберите **DNS.**</span><span class="sxs-lookup"><span data-stu-id="58528-140">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="58528-141">В разделе **записи CNAME/Alias** нажмите кнопку Изменить (значок вренч).</span><span class="sxs-lookup"><span data-stu-id="58528-141">Under the **CNAME/Alias records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="58528-142">Введите в текстовые поля следующие записи:</span><span class="sxs-lookup"><span data-stu-id="58528-142">Enter the following records in the text fields:</span></span>


    |<span data-ttu-id="58528-143">**HOST (УЗЕЛ)**</span><span class="sxs-lookup"><span data-stu-id="58528-143">**HOST**</span></span>|<span data-ttu-id="58528-144">**Address (должен заканчиваться на ".")**</span><span class="sxs-lookup"><span data-stu-id="58528-144">**Address (Must end with a ".")**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="58528-145">autodiscover</span><span class="sxs-lookup"><span data-stu-id="58528-145">autodiscover</span></span>  <br/> |<span data-ttu-id="58528-146">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="58528-146">autodiscover.outlook.com.</span></span>  <br/> |
    |<span data-ttu-id="58528-147">sip</span><span class="sxs-lookup"><span data-stu-id="58528-147">sip</span></span>  <br/> |<span data-ttu-id="58528-148">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="58528-148">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="58528-149">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="58528-149">lyncdiscover</span></span>  <br/> |<span data-ttu-id="58528-150">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="58528-150">webdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="58528-151">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="58528-151">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="58528-152">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="58528-152">enterpriseregistration.windows.net.</span></span>  <br/> |
    |<span data-ttu-id="58528-153">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="58528-153">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="58528-154">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="58528-154">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |
   
5. <span data-ttu-id="58528-155">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="58528-155">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="58528-156">Убедитесь, что запись верна, а затем нажмите кнопку **подтвердить**.</span><span class="sxs-lookup"><span data-stu-id="58528-156">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="58528-157">Добавьте запись TXT для SPF, чтобы предотвратить рассылку спама</span><span class="sxs-lookup"><span data-stu-id="58528-157">Add a TXT record for SPF to help prevent email spam</span></span>

1. <span data-ttu-id="58528-158">Перейдите на страницу [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) и войдите с помощью учетных данных.</span><span class="sxs-lookup"><span data-stu-id="58528-158">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="58528-159">В заголовке **все домены** выберите **DNS.**</span><span class="sxs-lookup"><span data-stu-id="58528-159">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="58528-160">В разделе **txt Records (записи TXT** ) нажмите кнопку Edit (значок вренч).</span><span class="sxs-lookup"><span data-stu-id="58528-160">Under the **TXT records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="58528-161">Введите в текстовые поля следующие записи:</span><span class="sxs-lookup"><span data-stu-id="58528-161">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="58528-162">**Host** (Узел)</span><span class="sxs-lookup"><span data-stu-id="58528-162">**Host**</span></span>|<span data-ttu-id="58528-163">**Text**</span><span class="sxs-lookup"><span data-stu-id="58528-163">**Text**</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="58528-164">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="58528-164">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> |
   
5. <span data-ttu-id="58528-165">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="58528-165">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="58528-166">Убедитесь, что запись верна, а затем нажмите кнопку **подтвердить**.</span><span class="sxs-lookup"><span data-stu-id="58528-166">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="58528-167">Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="58528-167">Add the two SRV records that are required for Microsoft</span></span>

<span data-ttu-id="58528-168">NOTE: записи SRV в настоящее время недоступны в easyDNS "домен и служба".</span><span class="sxs-lookup"><span data-stu-id="58528-168">NOTE: SRV Records are currently NOT available under easyDNS' Domain Plus service level.</span></span> <span data-ttu-id="58528-169">Для добавления записей SRV может потребоваться выполнить обновление до более высокого уровня обслуживания с easyDNS</span><span class="sxs-lookup"><span data-stu-id="58528-169">You may need to upgrade to a higher service level with easyDNS to add SRV records</span></span> 
  
1. <span data-ttu-id="58528-170">Перейдите на страницу [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) и войдите с помощью учетных данных.</span><span class="sxs-lookup"><span data-stu-id="58528-170">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="58528-171">В заголовке **все домены** выберите **DNS.**</span><span class="sxs-lookup"><span data-stu-id="58528-171">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="58528-172">В разделе **SRV Records (записи SRV** ) нажмите кнопку Edit (значок вренч).</span><span class="sxs-lookup"><span data-stu-id="58528-172">Under the **SRV records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="58528-173">Введите в текстовые поля следующие записи:</span><span class="sxs-lookup"><span data-stu-id="58528-173">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="58528-174">**SERVICE (СЛУЖБА)**</span><span class="sxs-lookup"><span data-stu-id="58528-174">**SERVICE**</span></span>|<span data-ttu-id="58528-175">**ЗАДАННОЕ**</span><span class="sxs-lookup"><span data-stu-id="58528-175">**PROTO**</span></span>|<span data-ttu-id="58528-176">**HOST (УЗЕЛ)**</span><span class="sxs-lookup"><span data-stu-id="58528-176">**HOST**</span></span>|<span data-ttu-id="58528-177">**ОСНОВНОЙ**</span><span class="sxs-lookup"><span data-stu-id="58528-177">**PRI**</span></span>|<span data-ttu-id="58528-178">**вгт**</span><span class="sxs-lookup"><span data-stu-id="58528-178">**WGT**</span></span>|<span data-ttu-id="58528-179">**PORT (ПОРТ)**</span><span class="sxs-lookup"><span data-stu-id="58528-179">**PORT**</span></span>|<span data-ttu-id="58528-180">**TARGET (должно оканчиваться на ".")**</span><span class="sxs-lookup"><span data-stu-id="58528-180">**TARGET(Must end with a ".")**</span></span>|<span data-ttu-id="58528-181">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="58528-181">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="58528-182">_sip</span><span class="sxs-lookup"><span data-stu-id="58528-182">_sip</span></span>  <br/> |<span data-ttu-id="58528-183">TLS</span><span class="sxs-lookup"><span data-stu-id="58528-183">TLS</span></span>  <br/> |@  <br/> |<span data-ttu-id="58528-184">100</span><span class="sxs-lookup"><span data-stu-id="58528-184">100</span></span>  <br/> |<span data-ttu-id="58528-185">1 </span><span class="sxs-lookup"><span data-stu-id="58528-185">1</span></span>  <br/> |<span data-ttu-id="58528-186">443</span><span class="sxs-lookup"><span data-stu-id="58528-186">443</span></span>  <br/> |<span data-ttu-id="58528-187">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="58528-187">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="58528-188">1800</span><span class="sxs-lookup"><span data-stu-id="58528-188">1800</span></span>  <br/> |
    |<span data-ttu-id="58528-189">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="58528-189">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="58528-190">TCP</span><span class="sxs-lookup"><span data-stu-id="58528-190">TCP</span></span>  <br/> |@  <br/> |<span data-ttu-id="58528-191">100</span><span class="sxs-lookup"><span data-stu-id="58528-191">100</span></span>  <br/> |<span data-ttu-id="58528-192">1 </span><span class="sxs-lookup"><span data-stu-id="58528-192">1</span></span>  <br/> |<span data-ttu-id="58528-193">5061</span><span class="sxs-lookup"><span data-stu-id="58528-193">5061</span></span>  <br/> |<span data-ttu-id="58528-194">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="58528-194">sipfed.online.lync.com.</span></span>  <br/> |<span data-ttu-id="58528-195">1800</span><span class="sxs-lookup"><span data-stu-id="58528-195">1800</span></span>  <br/> |
   
5. <span data-ttu-id="58528-196">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="58528-196">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="58528-197">Убедитесь, что запись верна, а затем нажмите кнопку **подтвердить**.</span><span class="sxs-lookup"><span data-stu-id="58528-197">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    

