---
title: Создание записей DNS для Майкрософт с помощью DNS на основе Windows
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
description: Узнайте, как проверить свой домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб в службе DNS на основе Windows для Майкрософт.
ms.openlocfilehash: 8202ffe10b4a0ff9c94d863d92fc55c47ebb38d3
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656847"
---
# <a name="create-dns-records-for-microsoft-using-windows-based-dns"></a><span data-ttu-id="7ac81-103">Создание записей DNS для Майкрософт с помощью DNS на основе Windows</span><span class="sxs-lookup"><span data-stu-id="7ac81-103">Create DNS records for Microsoft using Windows-based DNS</span></span>

 <span data-ttu-id="7ac81-104">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="7ac81-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
   
<span data-ttu-id="7ac81-105">Если у вас есть записи DNS, созданные с помощью DNS на базе Windows, в этой статье приведены сведения о том, как настроить записи для электронной почты, Skype для бизнеса online и т. д.</span><span class="sxs-lookup"><span data-stu-id="7ac81-105">If you host your own DNS records using Windows-based DNS, follow the steps in this article to set up your records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="7ac81-106">Для начала необходимо найти записи DNS в DNS на основе [Windows,](#find-your-dns-records-in-windows-based-dns) чтобы их можно было обновить.</span><span class="sxs-lookup"><span data-stu-id="7ac81-106">To get started, you need to [find your DNS records in Windows-based DNS](#find-your-dns-records-in-windows-based-dns) so you can update them.</span></span> <span data-ttu-id="7ac81-107">Кроме того, если вы планируете синхронизировать свою локальность Active Directory с Корпорацией Майкрософт, см. нена маршрутизируемый адрес электронной почты, используемый в качестве upN в локальной [службе Active Directory.](#non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory)</span><span class="sxs-lookup"><span data-stu-id="7ac81-107">Also, if you're planning to synchronize your on-premises Active Directory with Microsoft, see [Non-routable email address used as a UPN in your on-prem Active Directory](#non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory).</span></span>
  
<span data-ttu-id="7ac81-108">Проблемы с потоком почты или другие проблемы после добавления записей DNS см. в подсети "Устранение неполадок после изменения имени домена или [записей DNS".](../get-help-with-domains/find-and-fix-issues.md)</span><span class="sxs-lookup"><span data-stu-id="7ac81-108">Trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="find-your-dns-records-in-windows-based-dns"></a><span data-ttu-id="7ac81-109">Поиск DNS-записей в службе DNS на основе Windows</span><span class="sxs-lookup"><span data-stu-id="7ac81-109">Find your DNS records in Windows-based DNS</span></span>
<span data-ttu-id="7ac81-110"><a name="BKMK_find_your_dns_1"></a> Перейдите на страницу с записями DNS для вашего домена.</span><span class="sxs-lookup"><span data-stu-id="7ac81-110"><a name="BKMK_find_your_dns_1"> </a> Go to the page that has the DNS records for your domain.</span></span> <span data-ttu-id="7ac81-111">Если вы работаете в Windows Server 2008, перейдите к **запуску.**  >  </span><span class="sxs-lookup"><span data-stu-id="7ac81-111">If you're working in Windows Server 2008, go to **Start** > **Run**.</span></span> <span data-ttu-id="7ac81-112">Если вы работаете в Windows Server 2012, нажмите клавишу Windows и **r**.</span><span class="sxs-lookup"><span data-stu-id="7ac81-112">If you're working in Windows Server 2012, press the Windows key and **r**.</span></span> <span data-ttu-id="7ac81-113">Введите **dnsmgmnt.msc** и выберите "ОК". </span><span class="sxs-lookup"><span data-stu-id="7ac81-113">Type **dnsmgmnt.msc**, and then select **OK**.</span></span> <span data-ttu-id="7ac81-114">В диспетчере DNS развягуте **\<DNS server name\> \> зоны "Вперед" подыском.**</span><span class="sxs-lookup"><span data-stu-id="7ac81-114">In DNS Manager, expand **\<DNS server name\>  \> Forward Lookup Zones**.</span></span> <span data-ttu-id="7ac81-115">Выберите домен.</span><span class="sxs-lookup"><span data-stu-id="7ac81-115">Select your domain.</span></span> <span data-ttu-id="7ac81-116">You're now ready to create the DNS records.</span><span class="sxs-lookup"><span data-stu-id="7ac81-116">You're now ready to create the DNS records.</span></span>
   
## <a name="add-mx-record"></a><span data-ttu-id="7ac81-117">Добавление MX-записи</span><span class="sxs-lookup"><span data-stu-id="7ac81-117">Add MX record</span></span>
<span data-ttu-id="7ac81-118"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="7ac81-118"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="7ac81-119">Добавьте запись MX, чтобы электронная почта для вашего домена была отправлена в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7ac81-119">Add an MX record so email for your domain will come to Microsoft.</span></span>
- <span data-ttu-id="7ac81-120">Добавляемая запись MX содержит значение (значение "Указывает на адрес"), которое выглядит так: .mail.protection.outlook.com, где это значение, например  \<MX token\> \<MX token\> MSxxxxxxxxx.</span><span class="sxs-lookup"><span data-stu-id="7ac81-120">The MX record you'll add includes a value (the **Points to address** value) that looks something like this: \<MX token\>.mail.protection.outlook.com, where \<MX token\> is a value like MSxxxxxxx.</span></span> 
- <span data-ttu-id="7ac81-121">В строке MX в разделе Exchange Online на странице "Добавление записей DNS" в Корпорации Майкрософт скопируйте значение, перечисленное в разделе "Указывает на адрес".</span><span class="sxs-lookup"><span data-stu-id="7ac81-121">From the MX row in the Exchange Online section of the Add DNS records page in Microsoft, copy the value listed under Points to address.</span></span> <span data-ttu-id="7ac81-122">Вы будете использовать это значение в записи, которую вы создаете в этой задаче.</span><span class="sxs-lookup"><span data-stu-id="7ac81-122">You'll use this value in the record you're creating in this task.</span></span> 
- <span data-ttu-id="7ac81-123">On the DNS Manager page for the domain, go to **Action**  >  **Mail Exchanger (MX)**.</span><span class="sxs-lookup"><span data-stu-id="7ac81-123">On the DNS Manager page for the domain, go to **Action** > **Mail Exchanger (MX)**.</span></span> <span data-ttu-id="7ac81-124">Чтобы найти эту страницу для домена, см. поиск [записей DNS в DNS на основе Windows.](#find-your-dns-records-in-windows-based-dns)</span><span class="sxs-lookup"><span data-stu-id="7ac81-124">To find this page for the domain, see [Find your DNS records in Windows-based DNS](#find-your-dns-records-in-windows-based-dns).</span></span>  
- <span data-ttu-id="7ac81-125">В **диалоговом окне** "Новая запись ресурса" убедитесь, что для полей установлены именно следующие значения:</span><span class="sxs-lookup"><span data-stu-id="7ac81-125">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span> 
    - <span data-ttu-id="7ac81-126">Host Name (Имя узла): </span><span class="sxs-lookup"><span data-stu-id="7ac81-126">Host Name:</span></span> 
    - <span data-ttu-id="7ac81-127">@Address. В этом пункте в paste the Points to address value that you just copied from Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7ac81-127">@Address: Paste the Points to address  value that you just copied from Microsoft here.</span></span>  
    - <span data-ttu-id="7ac81-128">Pref:</span><span class="sxs-lookup"><span data-stu-id="7ac81-128">Pref:</span></span> 
- <span data-ttu-id="7ac81-129">Выберите **"Сохранить изменения"**.</span><span class="sxs-lookup"><span data-stu-id="7ac81-129">Select **Save Changes**.</span></span>
- <span data-ttu-id="7ac81-130">Удалите устаревшие записи MX.</span><span class="sxs-lookup"><span data-stu-id="7ac81-130">Remove any obsolete MX records.</span></span> <span data-ttu-id="7ac81-131">Если у вас есть какие-либо старые записи MX для этого домена, которые маршрутят электронную почту в другое место, выберите этот список рядом с каждой старой записью, а затем выберите **"Удалить**  >  **ОК".**</span><span class="sxs-lookup"><span data-stu-id="7ac81-131">If you have any old MX records for this domain that route email somewhere else, select the check box next to each old record, and then select **Delete** > **OK**.</span></span> 
   
## <a name="add-cname-records"></a><span data-ttu-id="7ac81-132">Добавление записей CNAME</span><span class="sxs-lookup"><span data-stu-id="7ac81-132">Add CNAME records</span></span>
<span data-ttu-id="7ac81-133"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="7ac81-133"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="7ac81-134">Добавьте записи CNAME, необходимые для Корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7ac81-134">Add the CNAME records that are required for Microsoft.</span></span> <span data-ttu-id="7ac81-135">Если в Корпорации Майкрософт перечислены дополнительные записи CNAME, добавьте их, выполнив те же общие действия, что и здесь.</span><span class="sxs-lookup"><span data-stu-id="7ac81-135">If additional CNAME records are listed in Microsoft, add those following the same general steps shown here.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7ac81-136">Если у вас есть служба управления мобильными устройствами (MDM) для Майкрософт, необходимо создать две дополнительные записи CNAME.</span><span class="sxs-lookup"><span data-stu-id="7ac81-136">If you have Mobile Device Management (MDM) for Microsoft, then you must create two additional CNAME records.</span></span> <span data-ttu-id="7ac81-137">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="7ac81-137">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> <span data-ttu-id="7ac81-138">(Если у вас нет MDM, вы можете пропустить этот шаг.)</span><span class="sxs-lookup"><span data-stu-id="7ac81-138">(If you do not have MDM, you can skip this step.)</span></span> 

- <span data-ttu-id="7ac81-139">На странице "Диспетчер DNS" для домена перейдите к **действию**  >  **CNAME (CNAME).**</span><span class="sxs-lookup"><span data-stu-id="7ac81-139">On the DNS Manager page for the domain, go to **Action** > **CNAME (CNAME)**.</span></span>
- <span data-ttu-id="7ac81-140">В **диалоговом окне** "Новая запись ресурса" убедитесь, что для полей установлены именно следующие значения:</span><span class="sxs-lookup"><span data-stu-id="7ac81-140">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    - <span data-ttu-id="7ac81-141">Имя хоста: autodiscover</span><span class="sxs-lookup"><span data-stu-id="7ac81-141">Host Name: autodiscover</span></span>
    - <span data-ttu-id="7ac81-142">Тип:</span><span class="sxs-lookup"><span data-stu-id="7ac81-142">Type:</span></span> 
    - <span data-ttu-id="7ac81-143">CNAMEAddress: autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="7ac81-143">CNAMEAddress: autodiscover.outlook.com</span></span>
- <span data-ttu-id="7ac81-144">Выберите **"O** K".</span><span class="sxs-lookup"><span data-stu-id="7ac81-144">Select **O** K.</span></span>

<span data-ttu-id="7ac81-145">Добавьте запись CNAME SIP.</span><span class="sxs-lookup"><span data-stu-id="7ac81-145">Add the SIP CNAME record.</span></span> 
- <span data-ttu-id="7ac81-146">На странице "Диспетчер DNS" для домена перейдите к **действию** \> **CNAME (CNAME).**</span><span class="sxs-lookup"><span data-stu-id="7ac81-146">On the DNS Manager page for the domain, go to **Action** \> **CNAME (CNAME)**.</span></span> 
- <span data-ttu-id="7ac81-147">В **диалоговом окне** "Новая запись ресурса" убедитесь, что для полей установлены именно следующие значения:</span><span class="sxs-lookup"><span data-stu-id="7ac81-147">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    - <span data-ttu-id="7ac81-148">Имя хоста: sip</span><span class="sxs-lookup"><span data-stu-id="7ac81-148">Host Name: sip</span></span>
    - <span data-ttu-id="7ac81-149">Тип: CNAME</span><span class="sxs-lookup"><span data-stu-id="7ac81-149">Type: CNAME</span></span>
    - <span data-ttu-id="7ac81-150">Адрес: sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="7ac81-150">Address: sipdir.online.lync.com</span></span>
- <span data-ttu-id="7ac81-151">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7ac81-151">Select **OK**.</span></span>

<span data-ttu-id="7ac81-152">Добавьте запись автообнаружения CNAME для Skype для бизнеса online.</span><span class="sxs-lookup"><span data-stu-id="7ac81-152">Add the Skype for Business Online Autodiscover CNAME record.</span></span>  
- <span data-ttu-id="7ac81-153">На странице "Диспетчер DNS" для домена перейдите к **действию** \> **CNAME (CNAME).**</span><span class="sxs-lookup"><span data-stu-id="7ac81-153">On the DNS Manager page for the domain, go to **Action** \> **CNAME (CNAME)**.</span></span> <span data-ttu-id="7ac81-154">В **диалоговом окне** "Новая запись ресурса" убедитесь, что для полей установлены именно следующие значения:</span><span class="sxs-lookup"><span data-stu-id="7ac81-154">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    - <span data-ttu-id="7ac81-155">Имя хоста: lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="7ac81-155">Host Name: lyncdiscover</span></span>
    - <span data-ttu-id="7ac81-156">Тип: CNAME</span><span class="sxs-lookup"><span data-stu-id="7ac81-156">Type: CNAME</span></span>
    - <span data-ttu-id="7ac81-157">Адрес: webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="7ac81-157">Address: webdir.online.lync.com</span></span>
- <span data-ttu-id="7ac81-158">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7ac81-158">Select **OK**.</span></span>
   
### <a name="add-two-cname-records-for-mobile-device-management-mdm-for-microsoft"></a><span data-ttu-id="7ac81-159">Добавление двух записей CNAME для управления мобильными устройствами (MDM) для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="7ac81-159">Add two CNAME records for Mobile Device Management (MDM) for Microsoft</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7ac81-160">Если у вас есть служба управления мобильными устройствами (MDM) для Майкрософт, необходимо создать две дополнительные записи CNAME.</span><span class="sxs-lookup"><span data-stu-id="7ac81-160">If you have Mobile Device Management (MDM) for Microsoft, then you must create two additional CNAME records.</span></span> <span data-ttu-id="7ac81-161">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="7ac81-161">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> <span data-ttu-id="7ac81-162">>(Если у вас нет MDM, вы можете пропустить этот шаг.)</span><span class="sxs-lookup"><span data-stu-id="7ac81-162">>(If you do not have MDM, you can skip this step.)</span></span> 
  

<span data-ttu-id="7ac81-163">Добавьте запись CNAME MDM Enterpriseregistration.</span><span class="sxs-lookup"><span data-stu-id="7ac81-163">Add the MDM Enterpriseregistration CNAME record.</span></span>  
- <span data-ttu-id="7ac81-164">На странице "Диспетчер DNS" для домена перейдите к **действию** \> **CNAME (CNAME).**</span><span class="sxs-lookup"><span data-stu-id="7ac81-164">On the DNS Manager page for the domain, go to **Action** \> **CNAME (CNAME)**.</span></span> 
- <span data-ttu-id="7ac81-165">В **диалоговом окне** "Новая запись ресурса" убедитесь, что для полей установлены именно следующие значения:</span><span class="sxs-lookup"><span data-stu-id="7ac81-165">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
- <span data-ttu-id="7ac81-166">Имя хоста: enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="7ac81-166">Host Name: enterpriseregistration</span></span>
- <span data-ttu-id="7ac81-167">Тип: CNAME</span><span class="sxs-lookup"><span data-stu-id="7ac81-167">Type: CNAME</span></span>
- <span data-ttu-id="7ac81-168">Адрес: enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="7ac81-168">Address: enterpriseregistration.windows.net</span></span>
- <span data-ttu-id="7ac81-169">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7ac81-169">Select **OK**.</span></span> 

<span data-ttu-id="7ac81-170">Добавьте запись CNAME MDM Enterpriseenrollment.</span><span class="sxs-lookup"><span data-stu-id="7ac81-170">Add the MDM Enterpriseenrollment CNAME record.</span></span> 
-  <span data-ttu-id="7ac81-171">На странице "Диспетчер DNS" для домена перейдите к **действию** \> **CNAME (CNAME).**</span><span class="sxs-lookup"><span data-stu-id="7ac81-171">On the DNS Manager page for the domain, go to **Action** \> **CNAME (CNAME)**.</span></span> 
-  <span data-ttu-id="7ac81-172">В **диалоговом окне** "Новая запись ресурса" убедитесь, что для полей установлены именно следующие значения:</span><span class="sxs-lookup"><span data-stu-id="7ac81-172">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    - <span data-ttu-id="7ac81-173">Имя хоста: enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="7ac81-173">Host Name: enterpriseenrollment</span></span>
    - <span data-ttu-id="7ac81-174">Тип: CNAME</span><span class="sxs-lookup"><span data-stu-id="7ac81-174">Type: CNAME</span></span>
    - <span data-ttu-id="7ac81-175">Адрес: enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="7ac81-175">Address: enterpriseenrollment-s.manage.microsoft.com</span></span>
- <span data-ttu-id="7ac81-176">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7ac81-176">Select **OK**.</span></span>
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="7ac81-177">Добавление записи TXT для SPF, предотвращающей рассылку спама</span><span class="sxs-lookup"><span data-stu-id="7ac81-177">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="7ac81-178"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="7ac81-178"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="7ac81-179">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="7ac81-179">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="7ac81-180">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="7ac81-180">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="7ac81-181">Если вы уже указали запись SPF для домена, не создавайте еще одну для продуктов корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7ac81-181">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="7ac81-182">Вместо этого добавьте необходимые значения Майкрософт в текущую  запись, чтобы иметь одну запись SPF, которая включает оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="7ac81-182">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="7ac81-183">Добавьте запись SPF TXT для домена, чтобы предотвратить получение нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="7ac81-183">Add the SPF TXT record for your domain to help prevent email spam.</span></span>
  
- <span data-ttu-id="7ac81-p111">Возможно, для этой записи сохранены другие строки в поле значения TXT (например, строки для маркетинговых рассылок)  это нормально. Не удаляйте их. Заключите добавляемую строку в двойные кавычки, чтобы отделить ее.</span><span class="sxs-lookup"><span data-stu-id="7ac81-p111">You might already have other strings in the TXT value for this record (such as strings for marketing email), which is fine. Leave those strings in place and add this one, placing double-quotes around each string to separate them.</span></span> 
- <span data-ttu-id="7ac81-186">На странице "Диспетчер DNS" для вашего домена перейдите к **тексту** действия \> **(TXT).**</span><span class="sxs-lookup"><span data-stu-id="7ac81-186">On the DNS Manager page for your domain, go to **Action** \> **Text (TXT)**.</span></span> 
-  <span data-ttu-id="7ac81-187">В **диалоговом окне** "Новая запись ресурса" убедитесь, что для полей установлены именно следующие значения.</span><span class="sxs-lookup"><span data-stu-id="7ac81-187">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values.</span></span> 
 > [!IMPORTANT]
> <span data-ttu-id="7ac81-188">В некоторых версиях диспетчера DNS Windows домен может быть настроен таким образом, что при создании TXT-записи домашнее имя по умолчанию будет иметь родительский домен.</span><span class="sxs-lookup"><span data-stu-id="7ac81-188">In some versions of Windows DNS Manager, the domain may have been set up so that when you create a txt record, the home name defaults to the parent domain.</span></span> <span data-ttu-id="7ac81-189">В этой ситуации при добавлении записи TXT запишите пустое имя хоста (без значения), а не настроив для него значение @или доменное имя.</span><span class="sxs-lookup"><span data-stu-id="7ac81-189">In this situation, when adding a TXT record, set the host name to blank (no value) instead of setting it to @ or the domain name.</span></span> 

-  <span data-ttu-id="7ac81-190">Тип хоста: @</span><span class="sxs-lookup"><span data-stu-id="7ac81-190">Host type: @</span></span>
-  <span data-ttu-id="7ac81-191">Тип записи: TXT</span><span class="sxs-lookup"><span data-stu-id="7ac81-191">Record Type: TXT</span></span>
-  <span data-ttu-id="7ac81-192">Адрес: v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="7ac81-192">Address: v=spf1 include:spf.protection.outlook.com -all</span></span> 
         
-  <span data-ttu-id="7ac81-193">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7ac81-193">Select **OK**.</span></span>
   
## <a name="add-srv-records"></a><span data-ttu-id="7ac81-194">Добавление SRV-записей</span><span class="sxs-lookup"><span data-stu-id="7ac81-194">Add SRV records</span></span>
<span data-ttu-id="7ac81-195"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="7ac81-195"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="7ac81-196">Добавьте две записи SRV, необходимые для Корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7ac81-196">Add the two SRV records that are required for Microsoft.</span></span>

<span data-ttu-id="7ac81-197">Добавьте запись SRV SIP для веб-конференций Skype для бизнеса online</span><span class="sxs-lookup"><span data-stu-id="7ac81-197">Add the SIP SRV record for Skype for Business Online web conferencing.</span></span>  <br/> 
-  <span data-ttu-id="7ac81-198">On the DNS Manager page for your domain, go to **Action** \> **Other New Records**.</span><span class="sxs-lookup"><span data-stu-id="7ac81-198">On the DNS Manager page for your domain, go to **Action** \> **Other New Records**.</span></span> 
-   <span data-ttu-id="7ac81-199">В **окне "Тип записи ресурса"** выберите **расположение службы (SRV)** и выберите **"Создать запись".**</span><span class="sxs-lookup"><span data-stu-id="7ac81-199">In the **Resource Record Type** window, select **Service Location (SRV)**, and then select **Create Record**.</span></span> 
-   <span data-ttu-id="7ac81-200">В **диалоговом окне** "Новая запись ресурса" убедитесь, что для полей установлены именно следующие значения:</span><span class="sxs-lookup"><span data-stu-id="7ac81-200">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    -  <span data-ttu-id="7ac81-201">Служба: _sip</span><span class="sxs-lookup"><span data-stu-id="7ac81-201">Service: _sip</span></span>
    -  <span data-ttu-id="7ac81-202">Протокол: _tls</span><span class="sxs-lookup"><span data-stu-id="7ac81-202">Protocol: _tls</span></span>
    -  <span data-ttu-id="7ac81-203">Приоритет: 100</span><span class="sxs-lookup"><span data-stu-id="7ac81-203">Priority: 100</span></span>
    -  <span data-ttu-id="7ac81-204">Вес: 1</span><span class="sxs-lookup"><span data-stu-id="7ac81-204">Weight: 1</span></span>
    -  <span data-ttu-id="7ac81-205">Порт: 443</span><span class="sxs-lookup"><span data-stu-id="7ac81-205">Port: 443</span></span>
    -  <span data-ttu-id="7ac81-206">Target (Hostname): sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="7ac81-206">Target (Hostname): sipdir.online.lync.com</span></span>
-  <span data-ttu-id="7ac81-207">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7ac81-207">Select **OK**.</span></span> 


<span data-ttu-id="7ac81-208">Добавьте запись SRV SIP для федерации Skype для бизнеса online.</span><span class="sxs-lookup"><span data-stu-id="7ac81-208">Add the SIP SRV record for Skype for Business Online federation.</span></span>  
-  <span data-ttu-id="7ac81-209">On the DNS Manager page for your domain, go to **Action** \> **Other New Records**.</span><span class="sxs-lookup"><span data-stu-id="7ac81-209">On the DNS Manager page for your domain, go to **Action** \> **Other New Records**.</span></span>  
-  <span data-ttu-id="7ac81-210">В **окне "Тип записи ресурса"** выберите **расположение службы (SRV)** и выберите **"Создать запись".**</span><span class="sxs-lookup"><span data-stu-id="7ac81-210">In the **Resource Record Type** window, select **Service Location (SRV)**, and then select **Create Record**.</span></span> 
-   <span data-ttu-id="7ac81-211">В **диалоговом окне** "Новая запись ресурса" убедитесь, что для полей установлены именно следующие значения:</span><span class="sxs-lookup"><span data-stu-id="7ac81-211">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    -  <span data-ttu-id="7ac81-212">Служба: _sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="7ac81-212">Service: _sipfederationtls</span></span>
    -  <span data-ttu-id="7ac81-213">Протокол: _tcp</span><span class="sxs-lookup"><span data-stu-id="7ac81-213">Protocol: _tcp</span></span>
    -  <span data-ttu-id="7ac81-214">Приоритет: 100</span><span class="sxs-lookup"><span data-stu-id="7ac81-214">Priority: 100</span></span>
    -  <span data-ttu-id="7ac81-215">Вес: 1</span><span class="sxs-lookup"><span data-stu-id="7ac81-215">Weight: 1</span></span>
    -  <span data-ttu-id="7ac81-216">Порт: 5061</span><span class="sxs-lookup"><span data-stu-id="7ac81-216">Port: 5061</span></span>
    -  <span data-ttu-id="7ac81-217">Target (Hostname): sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="7ac81-217">Target (Hostname): sipfed.online.lync.com</span></span>
-  <span data-ttu-id="7ac81-218">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7ac81-218">Select **OK**.</span></span> 
   
## <a name="add-a-record-to-verify-that-you-own-the-domain-if-you-havent-already"></a><span data-ttu-id="7ac81-219">Добавление записи для подтверждения владения доменом, если это еще не сделано</span><span class="sxs-lookup"><span data-stu-id="7ac81-219">Add a record to verify that you own the domain, if you haven't already</span></span>
<span data-ttu-id="7ac81-220"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="7ac81-220"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="7ac81-221">Перед добавлением записей DNS для настроить службы Майкрософт необходимо подтвердить, что вы владеете добавляемом доменом.</span><span class="sxs-lookup"><span data-stu-id="7ac81-221">Before you add the DNS records to set up your Microsoft services, Microsoft has to confirm that you own the domain you're adding.</span></span> <span data-ttu-id="7ac81-222">Для этого добавьте запись, выполнив приведенные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="7ac81-222">To do this, you add a record, following the steps below.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7ac81-223">Эта запись используется только для проверки принадлежности домена. Она не используется для других целей.</span><span class="sxs-lookup"><span data-stu-id="7ac81-223">This record is used only to verify that you own your domain; it doesn't affect anything else.</span></span> 
  

1. <span data-ttu-id="7ac81-224">Сбор сведений от Корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7ac81-224">Gather information from Microsoft.</span></span>  <br/> 
2. <span data-ttu-id="7ac81-225">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="7ac81-225">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span> 
3. <span data-ttu-id="7ac81-226">На странице **"Домены"** в столбце **"Действия"** для проверяемго домена выберите **"Начать установку".**</span><span class="sxs-lookup"><span data-stu-id="7ac81-226">On the **Domains** page, in the **Actions** column for the domain that you are verifying, select **Start setup**.</span></span> 
4. <span data-ttu-id="7ac81-227">На странице **"Добавление домена в Майкрософт"** выберите **"Начните с шага 1".**</span><span class="sxs-lookup"><span data-stu-id="7ac81-227">On the **Add a domain to Microsoft** page, select **Start step 1**.</span></span> 
5. <span data-ttu-id="7ac81-228">На странице **"Подтверждение** владения доменом"  в списке "См. инструкции по выполнению этого шага с помощью выпадающих списков" выберите **"Общие инструкции".**</span><span class="sxs-lookup"><span data-stu-id="7ac81-228">On the **Confirm that you own your domain** page, in the **See instructions for performing this step with** drop-down list, choose **General instructions**.</span></span> 
6. <span data-ttu-id="7ac81-229">В таблице скопируйте значение "Назначение" или "Указывает на адрес".</span><span class="sxs-lookup"><span data-stu-id="7ac81-229">From the table, copy the Destination or Points to Address value.</span></span> <span data-ttu-id="7ac81-230">Он понадобится вам на следующем этапе.</span><span class="sxs-lookup"><span data-stu-id="7ac81-230">You'll need it for the next step.</span></span> <span data-ttu-id="7ac81-231">Рекомендуется скопировать и в pasting это значение, чтобы все интервалы оставались правильными.</span><span class="sxs-lookup"><span data-stu-id="7ac81-231">We recommend copying and pasting this value, so that all of the spacing stays correct.</span></span>

<span data-ttu-id="7ac81-232">Добавьте запись TXT.</span><span class="sxs-lookup"><span data-stu-id="7ac81-232">Add a TXT record.</span></span> 
-  <span data-ttu-id="7ac81-233">На странице "Диспетчер DNS" для вашего домена перейдите к **тексту** действия \> **(TXT).**</span><span class="sxs-lookup"><span data-stu-id="7ac81-233">On the DNS Manager page for your domain, go to **Action** \> **Text (TXT)**.</span></span> 
-   <span data-ttu-id="7ac81-234">В **диалоговом окне** "Новая запись ресурса" выберите **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="7ac81-234">In the **New Resource Record** dialog box, select **Edit**.</span></span>  
-  <span data-ttu-id="7ac81-235">В области **"Пользовательские**  имена хостов" диалоговых окна "Новая запись ресурса" убедитесь, что для полей установлены именно следующие значения.</span><span class="sxs-lookup"><span data-stu-id="7ac81-235">In the **Custom Host Names** area of the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values.</span></span> 

> [!IMPORTANT] 
> <span data-ttu-id="7ac81-236">В некоторых версиях диспетчера DNS Windows домен может быть настроен таким образом, что при создании TXT-записи домашнее имя по умолчанию будет иметь родительский домен.</span><span class="sxs-lookup"><span data-stu-id="7ac81-236">In some versions of Windows DNS Manager, the domain may have been set up so that when you create a txt record, the home name defaults to the parent domain.</span></span> <span data-ttu-id="7ac81-237">В этой ситуации при добавлении записи TXT запишите пустое имя хоста (без значения), а не настроив для него значение @или доменное имя.</span><span class="sxs-lookup"><span data-stu-id="7ac81-237">In this situation, when adding a TXT record, set the host name to blank (no value) instead of setting it to @ or the domain name.</span></span> 

- <span data-ttu-id="7ac81-238">Имя хоста: @</span><span class="sxs-lookup"><span data-stu-id="7ac81-238">Host Name: @</span></span>
- <span data-ttu-id="7ac81-239">Тип: TXT</span><span class="sxs-lookup"><span data-stu-id="7ac81-239">Type: TXT</span></span>
- <span data-ttu-id="7ac81-240">Адрес: в paste the Destination or Points to Address value that you just copied from Microsoft here.</span><span class="sxs-lookup"><span data-stu-id="7ac81-240">Address: Paste the Destination or Points to Address value that you just copied from Microsoft here.</span></span>  
- <span data-ttu-id="7ac81-241">Выберите **"Готово"**  >  .</span><span class="sxs-lookup"><span data-stu-id="7ac81-241">Select **OK** > **Done**.</span></span>

<span data-ttu-id="7ac81-242">Проверьте свой домен в Корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7ac81-242">Verify your domain in Microsoft.</span></span>  
> [!IMPORTANT]
> <span data-ttu-id="7ac81-243">Подождите около 15 минут, чтобы созданную запись можно было обновить в Интернете.</span><span class="sxs-lookup"><span data-stu-id="7ac81-243">Wait about 15 minutes before you do this, so the record you just created can update across the Internet.</span></span>       

- <span data-ttu-id="7ac81-244">Снова в корпорацию Майкрософт и выполните следующие действия, чтобы запросить проверку.</span><span class="sxs-lookup"><span data-stu-id="7ac81-244">Go back to Microsoft and follow the steps below to request a verification check.</span></span> <span data-ttu-id="7ac81-245">В ходе проверки выполняется поиск TXT-записи, добавленной на предыдущем этапе.</span><span class="sxs-lookup"><span data-stu-id="7ac81-245">The check looks for the TXT record you added in the previous step.</span></span> <span data-ttu-id="7ac81-246">Если обнаружена правильная TXT-запись, домен успешно проверен.</span><span class="sxs-lookup"><span data-stu-id="7ac81-246">When it finds the correct TXT record, the domain is verified.</span></span>  
1. <span data-ttu-id="7ac81-247">В Центре администрирования перейдите на страницу **"Настройка** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">доменов".</a></span><span class="sxs-lookup"><span data-stu-id="7ac81-247">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
2. <span data-ttu-id="7ac81-248">На странице **"Домены"** в столбце **"Действие"** для проверяемго домена выберите **"Начать установку".**</span><span class="sxs-lookup"><span data-stu-id="7ac81-248">On the **Domains** page, in the **Action** column for the domain you are verifying, select **Start setup**.</span></span> 
3. <span data-ttu-id="7ac81-249">On the **Confirm that you own your domain** page, select **done, verify now**, and then in the confirmation dialog box, select **Finish**.</span><span class="sxs-lookup"><span data-stu-id="7ac81-249">On the **Confirm that you own your domain** page, select **done, verify now**, and then in the confirmation dialog box, select **Finish**.</span></span> 
   
> [!NOTE]
>  <span data-ttu-id="7ac81-p117">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7ac81-p117">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory"></a><span data-ttu-id="7ac81-253">Использование адреса электронной почты, не поддерживающего маршрутизацию, в качестве имени участника-пользователя в локальной службе Active Directory</span><span class="sxs-lookup"><span data-stu-id="7ac81-253">Non-routable email address used as a UPN in your on-prem Active Directory</span></span>
<span data-ttu-id="7ac81-254"><a name="BKMK_ADNote"> </a></span><span class="sxs-lookup"><span data-stu-id="7ac81-254"><a name="BKMK_ADNote"> </a></span></span>

<span data-ttu-id="7ac81-255">Если вы планируете синхронизировать локовую службу Active Directory с Корпорацией Майкрософт, убедитесь, что суффикс имени пользователя Active Directory является допустимым суффиксом домена, а не не суффиксом неподкрепимого домена, например @contoso.local.</span><span class="sxs-lookup"><span data-stu-id="7ac81-255">If you're planning to synchronize your on-premises Active Directory with Microsoft, you'll want to make sure that the Active Directory user principal name (UPN) suffix is a valid domain suffix, and not an unsupported domain suffix such as @contoso.local.</span></span> <span data-ttu-id="7ac81-256">Если вам нужно изменить суффикс имени upN, см. узнайте, как подготовить не маршрутизируемый домен для синхронизации [каталогов.](https://docs.microsoft.com/microsoft-365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization)</span><span class="sxs-lookup"><span data-stu-id="7ac81-256">If you need to change your UPN suffix, see [How to prepare a non-routable domain for directory synchronization](https://docs.microsoft.com/microsoft-365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="7ac81-p119">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7ac81-p119">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
