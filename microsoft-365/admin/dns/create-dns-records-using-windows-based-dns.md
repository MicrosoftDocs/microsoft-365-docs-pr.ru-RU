---
title: Создание записей DNS для Microsoft с помощью DNS на основе Windows
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
ms.assetid: 9eec911d-5773-422c-9593-40e1147ffbde
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб в DNS для Microsoft на основе Windows.
ms.openlocfilehash: fd7c56b6db9fe5f5dbb0637ad5abcb40a64bef8f
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2021
ms.locfileid: "51876353"
---
# <a name="create-dns-records-for-microsoft-using-windows-based-dns"></a><span data-ttu-id="f6a5b-103">Создание записей DNS для Microsoft с помощью DNS на основе Windows</span><span class="sxs-lookup"><span data-stu-id="f6a5b-103">Create DNS records for Microsoft using Windows-based DNS</span></span>

 <span data-ttu-id="f6a5b-104">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
   
<span data-ttu-id="f6a5b-105">Если у вас есть записи DNS, созданные с помощью DNS на базе Windows, в этой статье приведены сведения о том, как настроить записи для электронной почты, Skype для бизнеса online и т. д.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-105">If you host your own DNS records using Windows-based DNS, follow the steps in this article to set up your records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="f6a5b-106">Чтобы начать работу, необходимо найти записи DNS в DNS на основе [Windows,](#find-your-dns-records-in-windows-based-dns) чтобы можно было их обновить.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-106">To get started, you need to [find your DNS records in Windows-based DNS](#find-your-dns-records-in-windows-based-dns) so you can update them.</span></span> <span data-ttu-id="f6a5b-107">Кроме того, если вы планируете синхронизировать локальное active Directory с Корпорацией Майкрософт, см. в нем неавтируемый электронный адрес, используемый в качестве upN в локальном каталоге [Active Directory.](#non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory)</span><span class="sxs-lookup"><span data-stu-id="f6a5b-107">Also, if you're planning to synchronize your on-premises Active Directory with Microsoft, see [Non-routable email address used as a UPN in your on-prem Active Directory](#non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory).</span></span>
  
<span data-ttu-id="f6a5b-108">Проблемы с потоком почты или другими неполадками после добавления записей DNS см. в выпуске Устранение неполадок после изменения имени домена или [записей DNS.](../get-help-with-domains/find-and-fix-issues.md)</span><span class="sxs-lookup"><span data-stu-id="f6a5b-108">Trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="find-your-dns-records-in-windows-based-dns"></a><span data-ttu-id="f6a5b-109">Поиск DNS-записей в службе DNS на основе Windows</span><span class="sxs-lookup"><span data-stu-id="f6a5b-109">Find your DNS records in Windows-based DNS</span></span>
<span data-ttu-id="f6a5b-110"><a name="BKMK_find_your_dns_1"></a> Перейдите на страницу с записями DNS для вашего домена.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-110"><a name="BKMK_find_your_dns_1"> </a> Go to the page that has the DNS records for your domain.</span></span> <span data-ttu-id="f6a5b-111">Если вы работаете в Windows Server 2008, перейдите к   >  **запуску** запуска .</span><span class="sxs-lookup"><span data-stu-id="f6a5b-111">If you're working in Windows Server 2008, go to **Start** > **Run**.</span></span> <span data-ttu-id="f6a5b-112">Если вы работаете в Windows Server 2012, нажмите клавишу Windows и **r**.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-112">If you're working in Windows Server 2012, press the Windows key and **r**.</span></span> <span data-ttu-id="f6a5b-113">Введите **dnsmgmnt.msc** и выберите **ОК.**</span><span class="sxs-lookup"><span data-stu-id="f6a5b-113">Type **dnsmgmnt.msc**, and then select **OK**.</span></span> <span data-ttu-id="f6a5b-114">В диспетчере DNS **\<DNS server name\> \> раздвигать зоны досмотра.**</span><span class="sxs-lookup"><span data-stu-id="f6a5b-114">In DNS Manager, expand **\<DNS server name\>  \> Forward Lookup Zones**.</span></span> <span data-ttu-id="f6a5b-115">Выберите домен.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-115">Select your domain.</span></span> <span data-ttu-id="f6a5b-116">You're now ready to create the DNS records.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-116">You're now ready to create the DNS records.</span></span>
   
## <a name="add-mx-record"></a><span data-ttu-id="f6a5b-117">Добавление MX-записи</span><span class="sxs-lookup"><span data-stu-id="f6a5b-117">Add MX record</span></span>
<span data-ttu-id="f6a5b-118"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="f6a5b-118"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="f6a5b-119">Добавьте запись MX, чтобы сообщение электронной почты для домена пришло в Корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-119">Add an MX record so email for your domain will come to Microsoft.</span></span>
- <span data-ttu-id="f6a5b-120">Запись MX, которую вы добавим, включает значение (значение Points **to address),** которое выглядит так: .mail.protection.outlook.com, где это значение, как \<MX token\> \<MX token\> MSxxxxxx.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-120">The MX record you'll add includes a value (the **Points to address** value) that looks something like this: \<MX token\>.mail.protection.outlook.com, where \<MX token\> is a value like MSxxxxxxx.</span></span> 
- <span data-ttu-id="f6a5b-121">Из строки MX в разделе Exchange Online на странице Добавить записи DNS в Microsoft скопируйте значение, перечисленное в разделе Пункты для адреса.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-121">From the MX row in the Exchange Online section of the Add DNS records page in Microsoft, copy the value listed under Points to address.</span></span> <span data-ttu-id="f6a5b-122">Это значение будет использоваться в записи, которую вы создаете в этой задаче.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-122">You'll use this value in the record you're creating in this task.</span></span> 
- <span data-ttu-id="f6a5b-123">На странице Диспетчер DNS для домена перейдите к **exchanger** почты действий  >  **(MX).**</span><span class="sxs-lookup"><span data-stu-id="f6a5b-123">On the DNS Manager page for the domain, go to **Action** > **Mail Exchanger (MX)**.</span></span> <span data-ttu-id="f6a5b-124">Чтобы найти эту страницу для домена, см. в странице [Find your DNS records in Windows-based DNS.](#find-your-dns-records-in-windows-based-dns)</span><span class="sxs-lookup"><span data-stu-id="f6a5b-124">To find this page for the domain, see [Find your DNS records in Windows-based DNS](#find-your-dns-records-in-windows-based-dns).</span></span>  
- <span data-ttu-id="f6a5b-125">В **диалоговом окне Запись** новых ресурсов убедитесь, что поля задают следующие значения:</span><span class="sxs-lookup"><span data-stu-id="f6a5b-125">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span> 
    - <span data-ttu-id="f6a5b-126">Host Name (Имя узла): </span><span class="sxs-lookup"><span data-stu-id="f6a5b-126">Host Name:</span></span> 
    - <span data-ttu-id="f6a5b-127">@Address: вклеить пункты для адреса значения, которое вы только что скопировали из Microsoft здесь.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-127">@Address: Paste the Points to address  value that you just copied from Microsoft here.</span></span>  
    - <span data-ttu-id="f6a5b-128">Преф:</span><span class="sxs-lookup"><span data-stu-id="f6a5b-128">Pref:</span></span> 
- <span data-ttu-id="f6a5b-129">Выберите **Сохранить изменения.**</span><span class="sxs-lookup"><span data-stu-id="f6a5b-129">Select **Save Changes**.</span></span>
- <span data-ttu-id="f6a5b-130">Удалите устаревшие записи MX.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-130">Remove any obsolete MX records.</span></span> <span data-ttu-id="f6a5b-131">Если у вас есть какие-либо старые записи MX для этого домена, маршрут электронной почты в другом месте, выберите контрольный ящик рядом с каждой старой записью, а затем выберите **Удалить**  >  **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-131">If you have any old MX records for this domain that route email somewhere else, select the check box next to each old record, and then select **Delete** > **OK**.</span></span> 
   
## <a name="add-cname-records"></a><span data-ttu-id="f6a5b-132">Добавление записей CNAME</span><span class="sxs-lookup"><span data-stu-id="f6a5b-132">Add CNAME records</span></span>
<span data-ttu-id="f6a5b-133"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="f6a5b-133"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="f6a5b-134">Добавьте записи CNAME, необходимые для Корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-134">Add the CNAME records that are required for Microsoft.</span></span> <span data-ttu-id="f6a5b-135">Если дополнительные записи CNAME перечислены в Microsoft, добавьте те, которые перечислены ниже.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-135">If additional CNAME records are listed in Microsoft, add those following the same general steps shown here.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f6a5b-136">Если у вас есть управление мобильными устройствами (MDM) для Microsoft, необходимо создать две дополнительные записи CNAME.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-136">If you have Mobile Device Management (MDM) for Microsoft, then you must create two additional CNAME records.</span></span> <span data-ttu-id="f6a5b-137">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-137">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> <span data-ttu-id="f6a5b-138">(Если у вас нет MDM, вы можете пропустить этот шаг.)</span><span class="sxs-lookup"><span data-stu-id="f6a5b-138">(If you do not have MDM, you can skip this step.)</span></span> 

- <span data-ttu-id="f6a5b-139">На странице Диспетчер DNS для домена перейдите к **действию**  >  **CNAME (CNAME).**</span><span class="sxs-lookup"><span data-stu-id="f6a5b-139">On the DNS Manager page for the domain, go to **Action** > **CNAME (CNAME)**.</span></span>
- <span data-ttu-id="f6a5b-140">В **диалоговом окне Запись** новых ресурсов убедитесь, что поля задают следующие значения:</span><span class="sxs-lookup"><span data-stu-id="f6a5b-140">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    - <span data-ttu-id="f6a5b-141">Имя хозяина: автонаружить</span><span class="sxs-lookup"><span data-stu-id="f6a5b-141">Host Name: autodiscover</span></span>
    - <span data-ttu-id="f6a5b-142">Тип:</span><span class="sxs-lookup"><span data-stu-id="f6a5b-142">Type:</span></span> 
    - <span data-ttu-id="f6a5b-143">CNAMEAddress: autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="f6a5b-143">CNAMEAddress: autodiscover.outlook.com</span></span>
- <span data-ttu-id="f6a5b-144">Выберите **O** K.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-144">Select **O** K.</span></span>

<span data-ttu-id="f6a5b-145">Добавьте запись CNAME SIP.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-145">Add the SIP CNAME record.</span></span> 
- <span data-ttu-id="f6a5b-146">На странице Диспетчер DNS для домена перейдите к **действию** \> **CNAME (CNAME).**</span><span class="sxs-lookup"><span data-stu-id="f6a5b-146">On the DNS Manager page for the domain, go to **Action** \> **CNAME (CNAME)**.</span></span> 
- <span data-ttu-id="f6a5b-147">В **диалоговом окне Запись** новых ресурсов убедитесь, что поля задают следующие значения:</span><span class="sxs-lookup"><span data-stu-id="f6a5b-147">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    - <span data-ttu-id="f6a5b-148">Имя хозяина: sip</span><span class="sxs-lookup"><span data-stu-id="f6a5b-148">Host Name: sip</span></span>
    - <span data-ttu-id="f6a5b-149">Тип: CNAME</span><span class="sxs-lookup"><span data-stu-id="f6a5b-149">Type: CNAME</span></span>
    - <span data-ttu-id="f6a5b-150">Адрес: sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f6a5b-150">Address: sipdir.online.lync.com</span></span>
- <span data-ttu-id="f6a5b-151">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-151">Select **OK**.</span></span>

<span data-ttu-id="f6a5b-152">Добавьте запись автообнаружения CNAME для Skype для бизнеса online.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-152">Add the Skype for Business Online Autodiscover CNAME record.</span></span>  
- <span data-ttu-id="f6a5b-153">На странице Диспетчер DNS для домена перейдите к **действию** \> **CNAME (CNAME).**</span><span class="sxs-lookup"><span data-stu-id="f6a5b-153">On the DNS Manager page for the domain, go to **Action** \> **CNAME (CNAME)**.</span></span> <span data-ttu-id="f6a5b-154">В **диалоговом окне Запись** новых ресурсов убедитесь, что поля задают следующие значения:</span><span class="sxs-lookup"><span data-stu-id="f6a5b-154">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    - <span data-ttu-id="f6a5b-155">Имя хозяина: lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="f6a5b-155">Host Name: lyncdiscover</span></span>
    - <span data-ttu-id="f6a5b-156">Тип: CNAME</span><span class="sxs-lookup"><span data-stu-id="f6a5b-156">Type: CNAME</span></span>
    - <span data-ttu-id="f6a5b-157">Адрес: webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f6a5b-157">Address: webdir.online.lync.com</span></span>
- <span data-ttu-id="f6a5b-158">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-158">Select **OK**.</span></span>
   
### <a name="add-two-cname-records-for-mobile-device-management-mdm-for-microsoft"></a><span data-ttu-id="f6a5b-159">Добавление двух записей CNAME для управления мобильными устройствами (MDM) для Microsoft</span><span class="sxs-lookup"><span data-stu-id="f6a5b-159">Add two CNAME records for Mobile Device Management (MDM) for Microsoft</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f6a5b-160">Если у вас есть управление мобильными устройствами (MDM) для Microsoft, необходимо создать две дополнительные записи CNAME.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-160">If you have Mobile Device Management (MDM) for Microsoft, then you must create two additional CNAME records.</span></span> <span data-ttu-id="f6a5b-161">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-161">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> <span data-ttu-id="f6a5b-162">> (Если у вас нет MDM, вы можете пропустить этот шаг.)</span><span class="sxs-lookup"><span data-stu-id="f6a5b-162">>(If you do not have MDM, you can skip this step.)</span></span> 
  

<span data-ttu-id="f6a5b-163">Добавьте запись CNAME MDM Enterpriseregistration.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-163">Add the MDM Enterpriseregistration CNAME record.</span></span>  
- <span data-ttu-id="f6a5b-164">На странице Диспетчер DNS для домена перейдите к **действию** \> **CNAME (CNAME).**</span><span class="sxs-lookup"><span data-stu-id="f6a5b-164">On the DNS Manager page for the domain, go to **Action** \> **CNAME (CNAME)**.</span></span> 
- <span data-ttu-id="f6a5b-165">В **диалоговом окне Запись** новых ресурсов убедитесь, что поля задают следующие значения:</span><span class="sxs-lookup"><span data-stu-id="f6a5b-165">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
- <span data-ttu-id="f6a5b-166">Имя хозяина: корпоративная регистрация</span><span class="sxs-lookup"><span data-stu-id="f6a5b-166">Host Name: enterpriseregistration</span></span>
- <span data-ttu-id="f6a5b-167">Тип: CNAME</span><span class="sxs-lookup"><span data-stu-id="f6a5b-167">Type: CNAME</span></span>
- <span data-ttu-id="f6a5b-168">Адрес: enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="f6a5b-168">Address: enterpriseregistration.windows.net</span></span>
- <span data-ttu-id="f6a5b-169">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-169">Select **OK**.</span></span> 

<span data-ttu-id="f6a5b-170">Добавьте запись CNAME MDM Enterpriseenrollment.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-170">Add the MDM Enterpriseenrollment CNAME record.</span></span> 
-  <span data-ttu-id="f6a5b-171">На странице Диспетчер DNS для домена перейдите к **действию** \> **CNAME (CNAME).**</span><span class="sxs-lookup"><span data-stu-id="f6a5b-171">On the DNS Manager page for the domain, go to **Action** \> **CNAME (CNAME)**.</span></span> 
-  <span data-ttu-id="f6a5b-172">В **диалоговом окне Запись** новых ресурсов убедитесь, что поля задают следующие значения:</span><span class="sxs-lookup"><span data-stu-id="f6a5b-172">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    - <span data-ttu-id="f6a5b-173">Имя хозяина: enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="f6a5b-173">Host Name: enterpriseenrollment</span></span>
    - <span data-ttu-id="f6a5b-174">Тип: CNAME</span><span class="sxs-lookup"><span data-stu-id="f6a5b-174">Type: CNAME</span></span>
    - <span data-ttu-id="f6a5b-175">Адрес: enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="f6a5b-175">Address: enterpriseenrollment-s.manage.microsoft.com</span></span>
- <span data-ttu-id="f6a5b-176">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-176">Select **OK**.</span></span>
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="f6a5b-177">Добавление записи TXT для SPF, предотвращающей рассылку спама</span><span class="sxs-lookup"><span data-stu-id="f6a5b-177">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="f6a5b-178"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="f6a5b-178"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="f6a5b-179">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-179">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="f6a5b-180">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-180">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="f6a5b-181">Если вы уже указали запись SPF для домена, не создавайте еще одну для продуктов корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-181">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="f6a5b-182">Вместо этого добавьте необходимые значения Microsoft в текущую  запись, чтобы у вас была одна запись SPF, которая включает оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-182">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="f6a5b-183">Добавьте запись SPF TXT для домена, чтобы предотвратить получение нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-183">Add the SPF TXT record for your domain to help prevent email spam.</span></span>
  
- <span data-ttu-id="f6a5b-p111">Возможно, для этой записи сохранены другие строки в поле значения TXT (например, строки для маркетинговых рассылок)  это нормально. Не удаляйте их. Заключите добавляемую строку в двойные кавычки, чтобы отделить ее.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-p111">You might already have other strings in the TXT value for this record (such as strings for marketing email), which is fine. Leave those strings in place and add this one, placing double-quotes around each string to separate them.</span></span> 
- <span data-ttu-id="f6a5b-186">На странице Диспетчер DNS для домена перейдите в **текст** действия \> **(TXT).**</span><span class="sxs-lookup"><span data-stu-id="f6a5b-186">On the DNS Manager page for your domain, go to **Action** \> **Text (TXT)**.</span></span> 
-  <span data-ttu-id="f6a5b-187">В **диалоговом окне Запись** новых ресурсов убедитесь, что поля задают точно следующие значения.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-187">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values.</span></span> 
 > [!IMPORTANT]
> <span data-ttu-id="f6a5b-188">В некоторых версиях Windows DNS Manager домен может быть настроен таким образом, что при создании записи txt домашнее имя по умолчанию передается в родительский домен.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-188">In some versions of Windows DNS Manager, the domain may have been set up so that when you create a txt record, the home name defaults to the parent domain.</span></span> <span data-ttu-id="f6a5b-189">В этой ситуации при добавлении записи TXT установите имя хозяина пустым (без значения), а не настроив его на @ или доменное имя.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-189">In this situation, when adding a TXT record, set the host name to blank (no value) instead of setting it to @ or the domain name.</span></span> 

-  <span data-ttu-id="f6a5b-190">Тип хостов: @</span><span class="sxs-lookup"><span data-stu-id="f6a5b-190">Host type: @</span></span>
-  <span data-ttu-id="f6a5b-191">Тип записи: TXT</span><span class="sxs-lookup"><span data-stu-id="f6a5b-191">Record Type: TXT</span></span>
-  <span data-ttu-id="f6a5b-192">Адрес: v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="f6a5b-192">Address: v=spf1 include:spf.protection.outlook.com -all</span></span> 
         
-  <span data-ttu-id="f6a5b-193">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-193">Select **OK**.</span></span>
   
## <a name="add-srv-records"></a><span data-ttu-id="f6a5b-194">Добавление SRV-записей</span><span class="sxs-lookup"><span data-stu-id="f6a5b-194">Add SRV records</span></span>
<span data-ttu-id="f6a5b-195"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="f6a5b-195"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="f6a5b-196">Добавьте две записи SRV, необходимые для Корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-196">Add the two SRV records that are required for Microsoft.</span></span>

<span data-ttu-id="f6a5b-197">Добавьте запись SRV SIP для веб-конференций Skype для бизнеса online</span><span class="sxs-lookup"><span data-stu-id="f6a5b-197">Add the SIP SRV record for Skype for Business Online web conferencing.</span></span>  <br/> 
-  <span data-ttu-id="f6a5b-198">На странице Диспетчер DNS для домена перейдите в **Action** \> **Other New Records**.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-198">On the DNS Manager page for your domain, go to **Action** \> **Other New Records**.</span></span> 
-   <span data-ttu-id="f6a5b-199">В **окне Тип записи ресурсов** выберите **расположение службы (SRV)** и выберите **Создать запись.**</span><span class="sxs-lookup"><span data-stu-id="f6a5b-199">In the **Resource Record Type** window, select **Service Location (SRV)**, and then select **Create Record**.</span></span> 
-   <span data-ttu-id="f6a5b-200">В **диалоговом окне Запись** новых ресурсов убедитесь, что поля задают следующие значения:</span><span class="sxs-lookup"><span data-stu-id="f6a5b-200">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    -  <span data-ttu-id="f6a5b-201">Служба: _sip</span><span class="sxs-lookup"><span data-stu-id="f6a5b-201">Service: _sip</span></span>
    -  <span data-ttu-id="f6a5b-202">Протокол: _tls</span><span class="sxs-lookup"><span data-stu-id="f6a5b-202">Protocol: _tls</span></span>
    -  <span data-ttu-id="f6a5b-203">Приоритет: 100</span><span class="sxs-lookup"><span data-stu-id="f6a5b-203">Priority: 100</span></span>
    -  <span data-ttu-id="f6a5b-204">Вес: 1</span><span class="sxs-lookup"><span data-stu-id="f6a5b-204">Weight: 1</span></span>
    -  <span data-ttu-id="f6a5b-205">Порт: 443</span><span class="sxs-lookup"><span data-stu-id="f6a5b-205">Port: 443</span></span>
    -  <span data-ttu-id="f6a5b-206">Target (Hostname): sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f6a5b-206">Target (Hostname): sipdir.online.lync.com</span></span>
-  <span data-ttu-id="f6a5b-207">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-207">Select **OK**.</span></span> 


<span data-ttu-id="f6a5b-208">Добавьте запись SRV SIP для федерации Skype для бизнеса online.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-208">Add the SIP SRV record for Skype for Business Online federation.</span></span>  
-  <span data-ttu-id="f6a5b-209">На странице Диспетчер DNS для домена перейдите в **Action** \> **Other New Records**.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-209">On the DNS Manager page for your domain, go to **Action** \> **Other New Records**.</span></span>  
-  <span data-ttu-id="f6a5b-210">В **окне Тип записи ресурсов** выберите **расположение службы (SRV)** и выберите **Создать запись.**</span><span class="sxs-lookup"><span data-stu-id="f6a5b-210">In the **Resource Record Type** window, select **Service Location (SRV)**, and then select **Create Record**.</span></span> 
-   <span data-ttu-id="f6a5b-211">В **диалоговом окне Запись** новых ресурсов убедитесь, что поля задают следующие значения:</span><span class="sxs-lookup"><span data-stu-id="f6a5b-211">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    -  <span data-ttu-id="f6a5b-212">Служба: _sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="f6a5b-212">Service: _sipfederationtls</span></span>
    -  <span data-ttu-id="f6a5b-213">Протокол: _tcp</span><span class="sxs-lookup"><span data-stu-id="f6a5b-213">Protocol: _tcp</span></span>
    -  <span data-ttu-id="f6a5b-214">Приоритет: 100</span><span class="sxs-lookup"><span data-stu-id="f6a5b-214">Priority: 100</span></span>
    -  <span data-ttu-id="f6a5b-215">Вес: 1</span><span class="sxs-lookup"><span data-stu-id="f6a5b-215">Weight: 1</span></span>
    -  <span data-ttu-id="f6a5b-216">Порт: 5061</span><span class="sxs-lookup"><span data-stu-id="f6a5b-216">Port: 5061</span></span>
    -  <span data-ttu-id="f6a5b-217">Target (Hostname): sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f6a5b-217">Target (Hostname): sipfed.online.lync.com</span></span>
-  <span data-ttu-id="f6a5b-218">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-218">Select **OK**.</span></span> 
   
## <a name="add-a-record-to-verify-that-you-own-the-domain-if-you-havent-already"></a><span data-ttu-id="f6a5b-219">Добавление записи для подтверждения владения доменом, если это еще не сделано</span><span class="sxs-lookup"><span data-stu-id="f6a5b-219">Add a record to verify that you own the domain, if you haven't already</span></span>
<span data-ttu-id="f6a5b-220"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="f6a5b-220"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="f6a5b-221">Перед добавлением записей DNS для настройка служб Майкрософт Корпорация Майкрософт должна подтвердить, что у вас есть домен, который вы добавляете.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-221">Before you add the DNS records to set up your Microsoft services, Microsoft has to confirm that you own the domain you're adding.</span></span> <span data-ttu-id="f6a5b-222">Для этого добавьте запись, выполнив приведенные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-222">To do this, you add a record, following the steps below.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f6a5b-223">Эта запись используется только для проверки принадлежности домена. Она не используется для других целей.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-223">This record is used only to verify that you own your domain; it doesn't affect anything else.</span></span> 
  

1. <span data-ttu-id="f6a5b-224">Сбор сведений из Корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-224">Gather information from Microsoft.</span></span>  <br/> 
2. <span data-ttu-id="f6a5b-225">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="f6a5b-225">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span> 
3. <span data-ttu-id="f6a5b-226">На странице **Домены** в столбце **Действия** для проверяемой области выберите **настройку Начните.**</span><span class="sxs-lookup"><span data-stu-id="f6a5b-226">On the **Domains** page, in the **Actions** column for the domain that you are verifying, select **Start setup**.</span></span> 
4. <span data-ttu-id="f6a5b-227">На странице **Добавление домена в Microsoft** выберите **Начните шаг 1**.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-227">On the **Add a domain to Microsoft** page, select **Start step 1**.</span></span> 
5. <span data-ttu-id="f6a5b-228">На странице **Подтверждение того,** что у  вас есть страница домена, в инструкции см. инструкции по выполнению этого шага со списком drop-down выберите **Общие инструкции**.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-228">On the **Confirm that you own your domain** page, in the **See instructions for performing this step with** drop-down list, choose **General instructions**.</span></span> 
6. <span data-ttu-id="f6a5b-229">Из таблицы скопируйте значение Destination или Points to Address.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-229">From the table, copy the Destination or Points to Address value.</span></span> <span data-ttu-id="f6a5b-230">Он понадобится для следующего шага.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-230">You'll need it for the next step.</span></span> <span data-ttu-id="f6a5b-231">Рекомендуется скопировать и вклеить это значение, чтобы все интервалы оставались правильными.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-231">We recommend copying and pasting this value, so that all of the spacing stays correct.</span></span>

<span data-ttu-id="f6a5b-232">Добавьте запись TXT.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-232">Add a TXT record.</span></span> 
-  <span data-ttu-id="f6a5b-233">На странице Диспетчер DNS для домена перейдите в **текст** действия \> **(TXT).**</span><span class="sxs-lookup"><span data-stu-id="f6a5b-233">On the DNS Manager page for your domain, go to **Action** \> **Text (TXT)**.</span></span> 
-   <span data-ttu-id="f6a5b-234">В **диалоговом окне Запись новых** ресурсов выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-234">In the **New Resource Record** dialog box, select **Edit**.</span></span>  
-  <span data-ttu-id="f6a5b-235">В области **Настраиваемые имена** хостов в диалоговом окне **Запись** новых ресурсов убедитесь, что поля задают точно следующие значения.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-235">In the **Custom Host Names** area of the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values.</span></span> 

> [!IMPORTANT] 
> <span data-ttu-id="f6a5b-236">В некоторых версиях Windows DNS Manager домен может быть настроен таким образом, что при создании записи txt домашнее имя по умолчанию передается в родительский домен.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-236">In some versions of Windows DNS Manager, the domain may have been set up so that when you create a txt record, the home name defaults to the parent domain.</span></span> <span data-ttu-id="f6a5b-237">В этой ситуации при добавлении записи TXT установите имя хозяина пустым (без значения), а не настроив его на @ или доменное имя.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-237">In this situation, when adding a TXT record, set the host name to blank (no value) instead of setting it to @ or the domain name.</span></span> 

- <span data-ttu-id="f6a5b-238">Имя хозяина: @</span><span class="sxs-lookup"><span data-stu-id="f6a5b-238">Host Name: @</span></span>
- <span data-ttu-id="f6a5b-239">Тип: TXT</span><span class="sxs-lookup"><span data-stu-id="f6a5b-239">Type: TXT</span></span>
- <span data-ttu-id="f6a5b-240">Адрес: вклеить значение Destination или Points to Address, которое вы только что скопировали из Microsoft здесь.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-240">Address: Paste the Destination or Points to Address value that you just copied from Microsoft here.</span></span>  
- <span data-ttu-id="f6a5b-241">Выберите **ОК**  >  **Готово**.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-241">Select **OK** > **Done**.</span></span>

<span data-ttu-id="f6a5b-242">Проверка домена в Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-242">Verify your domain in Microsoft.</span></span>  
> [!IMPORTANT]
> <span data-ttu-id="f6a5b-243">Подождите около 15 минут, прежде чем сделать это, так что запись, созданная вами, может обновляться через Интернет.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-243">Wait about 15 minutes before you do this, so the record you just created can update across the Internet.</span></span>       

- <span data-ttu-id="f6a5b-244">Возвращайся в Microsoft и следуйте ниже шагам, чтобы запросить проверку проверки.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-244">Go back to Microsoft and follow the steps below to request a verification check.</span></span> <span data-ttu-id="f6a5b-245">В ходе проверки выполняется поиск TXT-записи, добавленной на предыдущем этапе.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-245">The check looks for the TXT record you added in the previous step.</span></span> <span data-ttu-id="f6a5b-246">Если обнаружена правильная TXT-запись, домен успешно проверен.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-246">When it finds the correct TXT record, the domain is verified.</span></span>  
1. <span data-ttu-id="f6a5b-247">В центре администрирования перейдите на страницу **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains.</a></span><span class="sxs-lookup"><span data-stu-id="f6a5b-247">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
2. <span data-ttu-id="f6a5b-248">На странице **Домены** в столбце **Действие** для проверяемой области выберите **Начните настройку.**</span><span class="sxs-lookup"><span data-stu-id="f6a5b-248">On the **Domains** page, in the **Action** column for the domain you are verifying, select **Start setup**.</span></span> 
3. <span data-ttu-id="f6a5b-249">На странице **Подтверждение того, что** у вас есть страница домена, выберите **сделано,** проверьте сейчас, а затем в диалоговом окне подтверждения выберите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-249">On the **Confirm that you own your domain** page, select **done, verify now**, and then in the confirmation dialog box, select **Finish**.</span></span> 
   
> [!NOTE]
>  <span data-ttu-id="f6a5b-p117">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="f6a5b-p117">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory"></a><span data-ttu-id="f6a5b-253">Использование адреса электронной почты, не поддерживающего маршрутизацию, в качестве имени участника-пользователя в локальной службе Active Directory</span><span class="sxs-lookup"><span data-stu-id="f6a5b-253">Non-routable email address used as a UPN in your on-prem Active Directory</span></span>
<span data-ttu-id="f6a5b-254"><a name="BKMK_ADNote"> </a></span><span class="sxs-lookup"><span data-stu-id="f6a5b-254"><a name="BKMK_ADNote"> </a></span></span>

<span data-ttu-id="f6a5b-255">Если вы планируете синхронизировать локальный active Directory с Microsoft, необходимо убедиться, что суффикс пользователя Active Directory — это допустимый суффикс домена, а не суффикс домена, неподкрепимый, например @contoso.local.</span><span class="sxs-lookup"><span data-stu-id="f6a5b-255">If you're planning to synchronize your on-premises Active Directory with Microsoft, you'll want to make sure that the Active Directory user principal name (UPN) suffix is a valid domain suffix, and not an unsupported domain suffix such as @contoso.local.</span></span> <span data-ttu-id="f6a5b-256">Если необходимо изменить суффикс upN, см. в приложении [How to prepare a non-routable domain for directory synchronization.](../../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="f6a5b-256">If you need to change your UPN suffix, see [How to prepare a non-routable domain for directory synchronization](../../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="f6a5b-p119">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="f6a5b-p119">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

## <a name="related-content"></a><span data-ttu-id="f6a5b-260">См. также:</span><span class="sxs-lookup"><span data-stu-id="f6a5b-260">Related content</span></span>

<span data-ttu-id="f6a5b-261">[Передача домена из Micrsoft 365 другому хосту](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/transfer-a-domain-from-microsoft-to-another-host) (статья)</span><span class="sxs-lookup"><span data-stu-id="f6a5b-261">[Transfer a domain from Micrsoft 365 to another host](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/transfer-a-domain-from-microsoft-to-another-host) (article)</span></span>

<span data-ttu-id="f6a5b-262">[Пилот Microsoft 365 из моего настраиваемого домена](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain) (статья)</span><span class="sxs-lookup"><span data-stu-id="f6a5b-262">[Pilot Microsoft 365 from my custom domain](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain) (article)</span></span>

<span data-ttu-id="f6a5b-263">[FaQ доменов](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) (статья)</span><span class="sxs-lookup"><span data-stu-id="f6a5b-263">[Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) (article)</span></span>