---
title: Настройка функции управления правами на доступ к данным для использования локального сервера служб Active Directory Rights Management
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/13/2017
audience: End User
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 3ecde857-4b7c-451d-b4aa-9eeffc8a8c61
ms.collection:
- M365-security-compliance
description: Узнайте, как настроить управление правами на информацию (IRM) в Exchange Online использовать сервер службы управления правами active Directory (AD RMS).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5e430f9c6ad5d377b568d22e9de53ab79d19165a
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2021
ms.locfileid: "51876124"
---
# <a name="configure-irm-to-use-an-on-premises-ad-rms-server"></a><span data-ttu-id="b7695-103">Настройка функции управления правами на доступ к данным для использования локального сервера служб AD RMS</span><span class="sxs-lookup"><span data-stu-id="b7695-103">Configure IRM to use an on-premises AD RMS server</span></span>
  
<span data-ttu-id="b7695-104">Для использования в локальном развертывании управление правами на информацию в Exchange Online использует службы Active Directory Rights Management (AD RMS), технологию защиты информации в Windows Server 2008 и более поздней.</span><span class="sxs-lookup"><span data-stu-id="b7695-104">For use with on-premises deployments, Information Rights Management (IRM) in Exchange Online uses Active Directory Rights Management Services (AD RMS), an information protection technology in Windows Server 2008 and later.</span></span> <span data-ttu-id="b7695-105">К сообщению электронной почты применяется шаблон политики прав AD RMS.</span><span class="sxs-lookup"><span data-stu-id="b7695-105">IRM protection is applied to email by applying an AD RMS rights policy template to an email message.</span></span> <span data-ttu-id="b7695-106">Права прикрепляются к сообщению, поэтому защита обеспечивается как в сети, так и вне ее, за пределами брандмауэра организации и внутри него.</span><span class="sxs-lookup"><span data-stu-id="b7695-106">Rights are attached to the message itself so that protection occurs online and offline and inside and outside of your organization's firewall.</span></span>
  
<span data-ttu-id="b7695-107">В этом разделе показано, как настроить управление правами на доступ к данным для использования сервера службы управления правами Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b7695-107">This topic shows you how to configure IRM to use an AD RMS server.</span></span> <span data-ttu-id="b7695-108">Сведения об использовании новых возможностей для шифрование сообщений Office 365 с Azure Active Directory и Управление правами Azure см. в шифрование сообщений Office 365 [FAQ](./ome-faq.yml).</span><span class="sxs-lookup"><span data-stu-id="b7695-108">For information about using the new capabilities for Office 365 Message Encryption with Azure Active Directory and Azure Rights Management, see the [Office 365 Message Encryption FAQ](./ome-faq.yml).</span></span>
  
<span data-ttu-id="b7695-109">Дополнительные сведения об управлении правами на доступ к данным в Exchange Online см. в разделе [Управление правами на доступ к данным в Exchange Online](information-rights-management-in-exchange-online.md).</span><span class="sxs-lookup"><span data-stu-id="b7695-109">To learn more about IRM in Exchange Online, see [Information Rights Management in Exchange Online](information-rights-management-in-exchange-online.md).</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b7695-110">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="b7695-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b7695-111">Предполагаемое время выполнения задачи: 30 минут.</span><span class="sxs-lookup"><span data-stu-id="b7695-111">Estimated time to complete this task: 30 minutes</span></span>

- <span data-ttu-id="b7695-p103">Для выполнения этих процедур необходимы соответствующие разрешения. Сведения о необходимых разрешениях см. в статье "Управление правами на доступ к данным" в статье [Messaging policy and compliance permissions](/Exchange/permissions/feature-permissions/policy-and-compliance-permissions).</span><span class="sxs-lookup"><span data-stu-id="b7695-p103">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Information Rights Management" entry in the [Messaging policy and compliance permissions](/Exchange/permissions/feature-permissions/policy-and-compliance-permissions) topic.</span></span> 

- <span data-ttu-id="b7695-p104">Сервер службы управления правами Active Directory должен работать под управлением ОС Windows Server 2008 или более поздней версии. Сведения о развертывании службы управления правами Active Directory см. в разделе [Установка кластера службы управления правами Active Directory](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc726041(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="b7695-p104">The AD RMS server must be running Windows Server 2008 or later. For details about how to deploy AD RMS, see [Installing an AD RMS Cluster](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc726041(v=ws.11)).</span></span>

- <span data-ttu-id="b7695-116">Сведения об установке и настройке Windows PowerShell и подключении к службе см. в разделе [Подключение к Exchange Online с помощью удаленной оболочки PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="b7695-116">For details about how to install and configure Windows PowerShell and connect to the service, see [Connect to Exchange Online Using Remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="b7695-117">Сведения о ярлыках клавиатуры, которые могут применяться к процедурам в этом разделе, см. в разделе [Клавишные](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)ярлыки для центра администрирования Exchange в Exchange Online .</span><span class="sxs-lookup"><span data-stu-id="b7695-117">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="b7695-p105">Возникли проблемы? Обратитесь за помощью к участникам форумов, посвященных Exchange. Посетите форумы по таким продуктам: [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612), [Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542) или [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span><span class="sxs-lookup"><span data-stu-id="b7695-p105">Having problems? Ask for help in the Exchange forums. Visit the forums at [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), or [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span></span> 
  
## <a name="how-do-you-do-this"></a><span data-ttu-id="b7695-121">Как это сделать</span><span class="sxs-lookup"><span data-stu-id="b7695-121">How do you do this?</span></span>
<span data-ttu-id="b7695-122"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="b7695-122"><a name="sectionSection1"> </a></span></span>

### <a name="step-1-use-the-ad-rms-console-to-export-a-trusted-publishing-domain-tpd-from-an-ad-rms-server"></a><span data-ttu-id="b7695-123">Действие 1. Использование консоли службы управления правами Active Directory для экспорта доверенного домена публикации (TPD) из сервера службы управления правами Active Directory</span><span class="sxs-lookup"><span data-stu-id="b7695-123">Step 1: Use the AD RMS console to export a trusted publishing domain (TPD) from an AD RMS server</span></span>

<span data-ttu-id="b7695-p106">Первый шаг — это экспорт доверенного домена публикации (TPD) с локального сервера AD RMS в XML-файл. Доверенный домен публикации (TPD) содержит следующие параметры, необходимые для использования функции службы управления правами:</span><span class="sxs-lookup"><span data-stu-id="b7695-p106">The first step is to export a trusted publishing domain (TPD) from the on-premises AD RMS server to an XML file. The TPD contains the following settings needed to use RMS features:</span></span>
  
- <span data-ttu-id="b7695-126">серверный сертификат лицензиара (SLC), который используется для подписания и шифрования сертификатов и лицензий;</span><span class="sxs-lookup"><span data-stu-id="b7695-126">The server licensor certificate (SLC) used for signing and encrypting certificates and licenses</span></span>

- <span data-ttu-id="b7695-127">URL-адреса, используемые для лицензирования и публикации;</span><span class="sxs-lookup"><span data-stu-id="b7695-127">The URLs used for licensing and publishing</span></span>

- <span data-ttu-id="b7695-128">шаблоны политики прав службы управления правами Active Directory, созданные с помощью конкретного серверного сертификата лицензиара (SLC) для данного доверенного домена публикации (TPD).</span><span class="sxs-lookup"><span data-stu-id="b7695-128">The AD RMS rights policy templates that were created with the specific SLC for that TPD</span></span>

<span data-ttu-id="b7695-129">При импорте доверенного домена публикации он сохраняется и защищается в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b7695-129">When you import the TPD, it's stored and protected in Exchange Online.</span></span>
  
1. <span data-ttu-id="b7695-130">Откройте консоль службы управления правами Active Directory и разверните кластер AD RMS.</span><span class="sxs-lookup"><span data-stu-id="b7695-130">Open the Active Directory Rights Management Services console, and then expand the AD RMS cluster.</span></span>

2. <span data-ttu-id="b7695-131">В дереве консоли раскройте узел **Политики доверия**, а затем выберите пункт **Доверенные домены публикации**.</span><span class="sxs-lookup"><span data-stu-id="b7695-131">In the console tree, expand **Trust Policies**, and then click **Trusted Publishing Domains**.</span></span>

3. <span data-ttu-id="b7695-132">В области результатов выберите сертификат домена, который необходимо экспортировать.</span><span class="sxs-lookup"><span data-stu-id="b7695-132">In the results pane, select the certificate for the domain you want to export.</span></span>

4. <span data-ttu-id="b7695-133">На панели **Действия** выберите команду **Экспортировать доверенный домен публикации**.</span><span class="sxs-lookup"><span data-stu-id="b7695-133">In the **Actions** pane, click **Export Trusted Publishing Domain**.</span></span>

5. <span data-ttu-id="b7695-p107">В окне **Файл домена публикации** нажмите кнопку **Сохранить как**, чтобы сохранить файл в известном расположении на локальном компьютере. Введите имя файла и обязательно укажите расширение имени файла  `.xml`, а затем нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b7695-p107">In the **Publishing domain file** box, click **Save As** to save the file to a specific location on the local computer. Type a file name, making sure to specify the  `.xml` file name extension, and then click **Save**.</span></span>

6. <span data-ttu-id="b7695-p108">В полях **Пароль** и **Подтверждение пароля** введите надежный пароль, используемый для шифрования файла доверенного домена публикации. Этот пароль потребуется указать при импорте доверенного домена публикации в облачную почтовую организацию.</span><span class="sxs-lookup"><span data-stu-id="b7695-p108">In the **Password** and **Confirm Password** boxes, type a strong password that will be used to encrypt the trusted publishing domain file. You will have to specify this password when you import the TPD to your cloud-based email organization.</span></span> 

### <a name="step-2-use-the-exchange-management-shell-to-import-the-tpd-to-exchange-online"></a><span data-ttu-id="b7695-138">Действие 2. Импортируйте TPD в службу Exchange Online с помощью командной консоли Exchange</span><span class="sxs-lookup"><span data-stu-id="b7695-138">Step 2: Use the Exchange Management Shell to import the TPD to Exchange Online</span></span>

<span data-ttu-id="b7695-p109">После экспорта TPD в XML-файл следует импортировать его в Exchange Online. При импорте TPD также импортируются шаблоны службы управления правами Active Directory вашей организации. При импорте первого TPD он становится TPD по умолчанию для вашей организации на основе облака. При импорте другого TPD можно использовать параметр **Default**, чтобы использовать его по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b7695-p109">After the TPD is exported to an XML file, you have to import it to Exchange Online. When a TPD is imported, your organization's AD RMS templates are also imported. When the first TPD is imported, it becomes the default TPD for your cloud-based organization. If you import another TPD, you can use the **Default** switch to make it the default TPD that is available to users.</span></span> 
  
<span data-ttu-id="b7695-143">Для импорта TPD выполните в среде Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b7695-143">To import the TPD, run the following command in Windows PowerShell:</span></span>
  
```powershell
Import-RMSTrustedPublishingDomain -FileData $([byte[]](Get-Content -Encoding byte -Path <path to exported TPD file> -ReadCount 0)) -Name "<name of TPD>" -ExtranetLicensingUrl <URL> -IntranetLicensingUrl <URL>
```

<span data-ttu-id="b7695-p110">Значения параметров  _ExtranetLicensingUrl_ и  _IntranetLicensingUrl_ можно получить в консоли службы управления правами Active Directory. В дереве консоли выберите кластер AD RMS. В области результатов отобразятся URL-адреса лицензирования. Эти URL-адреса используются почтовыми клиентами при необходимости расшифровки контента и в случае, если Exchange Online требуется определить используемый TPD.</span><span class="sxs-lookup"><span data-stu-id="b7695-p110">You can obtain the values for the  _ExtranetLicensingUrl_ and  _IntranetLicensingUrl_ parameters in the Active Directory Rights Management Services console. Select the AD RMS cluster in the console tree. The licensing URLs are displayed in the results pane. These URLs are used by email clients when content has to be decrypted and when Exchange Online needs to determine which TPD to use.</span></span>
  
<span data-ttu-id="b7695-p111">При запуске данной команды потребуется ввести пароль. Введите пароль, указанный при экспорте TPD с сервера AD RMS.</span><span class="sxs-lookup"><span data-stu-id="b7695-p111">When you run this command, you'll be prompted for a password. Enter the password that you specified when you exported the TPD from your AD RMS server.</span></span>
  
<span data-ttu-id="b7695-p112">Например, при выполнении следующей команды импортируется TPD с именем "Exported TPD" с помощью XML-файла, экспортированного с сервера службы управления правами Active Directory и сохраненного на рабочем столе учетной записи администратора. Параметр Name используется для указания имени TPD.</span><span class="sxs-lookup"><span data-stu-id="b7695-p112">For example, the following command imports the TPD named Exported TPD using the XML file that you exported from your AD RMS server and saved to the desktop of the Administrator account. The Name parameter is used to specify a name to the TPD.</span></span>
  
```powershell
Import-RMSTrustedPublishingDomain -FileData $([byte[]](Get-Content -Encoding byte -Path C:\Users\Administrator\Desktop\ExportTPD.xml -ReadCount 0)) -Name "Exported TPD" -ExtranetLicensingUrl https://corp.contoso.com/_wmcs/licensing -IntranetLicensingUrl https://rmsserver/_wmcs/licensing
```

<span data-ttu-id="b7695-152">Подробные сведения о синтаксисе и параметрах см. в разделе [Import-RMSTrustedPublishingDomain](/powershell/module/exchange/import-rmstrustedpublishingdomain).</span><span class="sxs-lookup"><span data-stu-id="b7695-152">For detailed syntax and parameter information, see [Import-RMSTrustedPublishingDomain](/powershell/module/exchange/import-rmstrustedpublishingdomain).</span></span>
  
#### <a name="how-do-you-know-this-step-worked"></a><span data-ttu-id="b7695-153">Как убедиться, что все получилось?</span><span class="sxs-lookup"><span data-stu-id="b7695-153">How do you know this step worked?</span></span>

<span data-ttu-id="b7695-p113">Чтобы убедиться, что вы успешно импортировали TPD, выполните командлет **Get-RMSTrustedPublishingDomain** для извлечения доверенных доменов публикации в вашей организации Exchange Online. Для получения дополнительных сведений см. примеры в разделе [Get-RMSTrustedPublishingDomain](/powershell/module/exchange/get-rmstrustedpublishingdomain).</span><span class="sxs-lookup"><span data-stu-id="b7695-p113">To verify that you have successfully imported the TPD, run the **Get-RMSTrustedPublishingDomain** cmdlet to retrieve TPDs in your Exchange Online organization. For details, see the examples in [Get-RMSTrustedPublishingDomain](/powershell/module/exchange/get-rmstrustedpublishingdomain).</span></span>
  
### <a name="step-3-use-the-exchange-management-shell-to-distribute-an-ad-rms-rights-policy-template"></a><span data-ttu-id="b7695-156">Действие 3. Распространите шаблон политики прав AD RMS с помощью командной консоли Exchange</span><span class="sxs-lookup"><span data-stu-id="b7695-156">Step 3: Use the Exchange Management Shell to distribute an AD RMS rights policy template</span></span>

<span data-ttu-id="b7695-157">После импорта TPD необходимо распространить шаблон политики прав службы управления правами Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b7695-157">After you import the TPD, you must make sure an AD RMS rights policy template is distributed.</span></span> <span data-ttu-id="b7695-158">Распределенный шаблон отображается для Outlook веб-пользователей (ранее известных как Outlook Web App), которые затем могут применять шаблоны к сообщению электронной почты.</span><span class="sxs-lookup"><span data-stu-id="b7695-158">A distributed template is visible to Outlook on the web (formerly known as Outlook Web App) users, who can then apply the templates to an email message.</span></span>
  
<span data-ttu-id="b7695-159">Чтобы получить список всех шаблонов в TPD по умолчанию, выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="b7695-159">To return a list of all templates contained in the default TPD, run the following command:</span></span>
  
```powershell
Get-RMSTemplate -Type All | fl
```

<span data-ttu-id="b7695-160">Если значение параметра  _Type_ равно  `Archived`, шаблон будет недоступен пользователям.</span><span class="sxs-lookup"><span data-stu-id="b7695-160">If the value of the  _Type_ parameter is  `Archived`, the template isn't visible to users.</span></span> <span data-ttu-id="b7695-161">Только распределенные шаблоны в TPD по умолчанию доступны в Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="b7695-161">Only distributed templates in the default TPD are available in Outlook on the web.</span></span>
  
<span data-ttu-id="b7695-162">Чтобы распространить шаблон, выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="b7695-162">To distribute a template, run the following command:</span></span>
  
```powershell
Set-RMSTemplate -Identity "<name of the template>" -Type Distributed
```

<span data-ttu-id="b7695-163">Например, при выполнении следующей команды импортируется шаблон "Company Confidential".</span><span class="sxs-lookup"><span data-stu-id="b7695-163">For example, the following command imports the Company Confidential template.</span></span>
  
```powershell
Set-RMSTemplate -Identity "Company Confidential" -Type Distributed
```

<span data-ttu-id="b7695-164">Дополнительные сведения о синтаксисе и параметрах см. в разделах [Get-RMSTemplate](/powershell/module/exchange/get-rmstemplate) и [Set-RMSTemplate](/powershell/module/exchange/set-rmstemplate).</span><span class="sxs-lookup"><span data-stu-id="b7695-164">For detailed syntax and parameter information, see [Get-RMSTemplate](/powershell/module/exchange/get-rmstemplate) and [Set-RMSTemplate](/powershell/module/exchange/set-rmstemplate).</span></span>
  
<span data-ttu-id="b7695-165">**Шаблон «"Не пересылать"»**</span><span class="sxs-lookup"><span data-stu-id="b7695-165">**The Do Not Forward template**</span></span>
  
<span data-ttu-id="b7695-p116">При импорте TPD по умолчанию из локальной организации в Exchange Online импортируется один шаблон политики прав службы управления правами Active Directory с именем **Не пересылать**. Этот шаблон автоматически распространяется при импорте TPD по умолчанию. Изменить шаблон **Не пересылать** с помощью командлета **Set-RMSTemplate** нельзя.</span><span class="sxs-lookup"><span data-stu-id="b7695-p116">When you import the default TPD from your on-premises organization into Exchange Online, one AD RMS rights policy template named **Do Not Forward** is imported. By default, this template is distributed when you import the default TPD. You can't use the **Set-RMSTemplate** cmdlet to modify the **Do Not Forward** template.</span></span> 
  
<span data-ttu-id="b7695-p117">Когда к сообщению применяется шаблон **Не пересылать**, прочитать это сообщение смогут только получатели, являющиеся его адресатами. Кроме того, получатели не смогут:</span><span class="sxs-lookup"><span data-stu-id="b7695-p117">When the **Do Not Forward** template is applied to a message, only the recipients addressed in the message can read the message. Additionally, recipients can't do the following:</span></span>
  
- <span data-ttu-id="b7695-171">пересылать сообщение другому пользователю;</span><span class="sxs-lookup"><span data-stu-id="b7695-171">Forward the message to another person.</span></span>

- <span data-ttu-id="b7695-172">копировать содержимое сообщения.</span><span class="sxs-lookup"><span data-stu-id="b7695-172">Copy content from the message.</span></span>

- <span data-ttu-id="b7695-173">и печатать его.</span><span class="sxs-lookup"><span data-stu-id="b7695-173">Print the message.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b7695-174">Шаблон **Не пересылать** не сможет защитить информацию из сообщения от копирования с помощью сторонних программ или камер, а также от простого переписывания.</span><span class="sxs-lookup"><span data-stu-id="b7695-174">The **Do Not Forward** template can't prevent information in a message from being copied with third-party screen capture programs, cameras, or users manually transcribing the information</span></span> 
  
<span data-ttu-id="b7695-p118">Можно также создать дополнительные шаблоны политики прав службы управления правами Active Directory на сервере службы управления правами Active Directory в локальной организации в соответствии с требованиями защиты IRM. При создании дополнительных шаблонов политики прав службы управления правами Active Directory следует снова экспортировать TPD с локального сервера службы управления правами Active Directory и обновить TPD в облачной почтовой организации.</span><span class="sxs-lookup"><span data-stu-id="b7695-p118">You can create additional AD RMS rights policy templates on the AD RMS server in your on-premises organization to meet your IRM protection requirements. If you create additional AD RMS rights policy templates, you have to export the TPD from the on-premises AD RMS server again and refresh the TPD in the cloud-based email organization.</span></span>
  
#### <a name="how-do-you-know-this-step-worked"></a><span data-ttu-id="b7695-177">Как убедиться, что все получилось?</span><span class="sxs-lookup"><span data-stu-id="b7695-177">How do you know this step worked?</span></span>

<span data-ttu-id="b7695-p119">Чтобы убедиться, что вы успешно распространили шаблон политики прав службы управления правами Active Directory, выполните командлет **Get-RMSTemplate** для проверки свойств шаблона. Для получения дополнительных сведений см. примеры в разделе [Get-RMSTemplate](/powershell/module/exchange/get-rmstemplate).</span><span class="sxs-lookup"><span data-stu-id="b7695-p119">To verify that you have successfully distributed and AD RMS rights policy template, run the **Get-RMSTemplate** cmdlet to check the template's properties. For details, see the examples in [Get-RMSTemplate](/powershell/module/exchange/get-rmstemplate).</span></span>
  
### <a name="step-4-use-the-exchange-management-shell-to-enable-irm"></a><span data-ttu-id="b7695-180">Действие 4. Включите управление правами на доступ к данным с помощью командной консоли Exchange</span><span class="sxs-lookup"><span data-stu-id="b7695-180">Step 4: Use the Exchange Management Shell to enable IRM</span></span>

<span data-ttu-id="b7695-181">После импорта TPD и распространения шаблона политики прав службы управления правами Active Directory выполните следующую команду, чтобы включить управление правами на доступ к данным для своей облачной почтовой организации.</span><span class="sxs-lookup"><span data-stu-id="b7695-181">After you import the TPD and distribute an AD RMS rights policy template, run the following command to enable IRM for your cloud-based email organization.</span></span>
  
```powershell
Set-IRMConfiguration -InternalLicensingEnabled $true
```

<span data-ttu-id="b7695-182">Подробные сведения о синтаксисе и параметрах см. в разделе [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration).</span><span class="sxs-lookup"><span data-stu-id="b7695-182">For detailed syntax and parameter information, see [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration).</span></span>
  
#### <a name="how-do-you-know-this-step-worked"></a><span data-ttu-id="b7695-183">Как убедиться, что все получилось?</span><span class="sxs-lookup"><span data-stu-id="b7695-183">How do you know this step worked?</span></span>

<span data-ttu-id="b7695-184">Чтобы убедиться, что вы успешно включили управление правами на доступ к данным (IRM), выполните командлет [Get-IRMConfiguration](/powershell/module/exchange/get-irmconfiguration) для проверки конфигурации IRM в организации Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b7695-184">To verify that you have successfully enabled IRM, run the [Get-IRMConfiguration](/powershell/module/exchange/get-irmconfiguration) cmdlet to check IRM configuration in the Exchange Online organization.</span></span>
  
## <a name="how-do-you-know-this-task-worked"></a><span data-ttu-id="b7695-185">Как убедиться, что это сработало?</span><span class="sxs-lookup"><span data-stu-id="b7695-185">How do you know this task worked?</span></span>
<span data-ttu-id="b7695-186"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="b7695-186"><a name="sectionSection2"> </a></span></span>

<span data-ttu-id="b7695-187">Чтобы убедиться, что вы успешно импортировали TPD и включили IRM, выполните приведенные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="b7695-187">To verify that you have successfully imported the TPD and enabled IRM, do the following:</span></span>
  
- <span data-ttu-id="b7695-p120">С помощью командлета **Test-IRMConfiguration** проверьте функциональные возможности IRM. Подробные сведения см. в примере 1 в разделе [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration).</span><span class="sxs-lookup"><span data-stu-id="b7695-p120">Use the **Test-IRMConfiguration** cmdlet to test IRM functionality. For details, see "Example 1" in [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration).</span></span>

- <span data-ttu-id="b7695-190">Соберите новое сообщение в Outlook веб-сайте и IRM-защита, выбрав параметр **Set permissions** из расширенного меню ![ (More Options ](../media/ITPro-EAC-MoreOptionsIcon.gif) Icon).</span><span class="sxs-lookup"><span data-stu-id="b7695-190">Compose a new message in Outlook on the web and IRM-protect it by selecting **Set permissions** option from the extended menu ( ![More Options Icon](../media/ITPro-EAC-MoreOptionsIcon.gif)).</span></span>