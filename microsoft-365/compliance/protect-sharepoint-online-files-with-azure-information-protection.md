---
title: Защита файлов SharePoint Online с помощью Azure Information Protection
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/29/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
ms.custom:
- Ent_Solutions
ms.assetid: 5b9c8e41-25d2-436d-89bb-9aecb9ec2b80
description: Сводка. Защита файлов на строго конфиденциальном сайте группы SharePoint Online с помощью службы Azure Information Protection.
ms.openlocfilehash: f905f673efe050e07ad26728628bce05073a26b8
ms.sourcegitcommit: 1c90bcc5c56f24895f01c3e0423c3f6b73715c13
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "44214643"
---
# <a name="protect-sharepoint-online-files-with-azure-information-protection"></a><span data-ttu-id="4e734-103">Защита файлов SharePoint Online с помощью Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="4e734-103">Protect SharePoint Online files with Azure Information Protection</span></span>

>[!Note]
><span data-ttu-id="4e734-104">Текущее решение для файлов на строго конфиденциальном сайте группы SharePoint Online использует метки конфиденциальности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4e734-104">The current solution for files in a highly confidential SharePoint Online team site uses Microsoft 365 sensitivity labels.</span></span> <span data-ttu-id="4e734-105">Подробности представлены в [этой статье](protect-sharepoint-online-files-with-sensitivity-label.md).</span><span class="sxs-lookup"><span data-stu-id="4e734-105">Please see [this article](protect-sharepoint-online-files-with-sensitivity-label.md) for the details.</span></span>
>

<span data-ttu-id="4e734-p102">В этой статье показано, как настроить Azure Information Protection, чтобы обеспечить шифрование и применение разрешений для файлов. Эти файлы можно добавлять в библиотеку SharePoint, настроенную на строго конфиденциальный уровень защиты. Или можно открыть файл непосредственно на сайте и использовать клиент Azure Information Protection, чтобы добавить шифрование. Даже при скачивании с сайта файл будет по-прежнему защищен благодаря шифрованию и указанным разрешениям.</span><span class="sxs-lookup"><span data-stu-id="4e734-p102">Use the steps in this article to configure Azure Information Protection to provide encryption and permissions for files. These files can be added to a SharePoint library configured for highly confidential protection. Or, you can open a file directly from the site and use the Azure Information Protection client to add encryption. The encryption and permissions protection travels with a file even when it is downloaded from the site.</span></span> 

<span data-ttu-id="4e734-p103">Эти действия являются частью более крупного решения по настройке строго конфиденциальной защиты для сайтов SharePoint и файлов на этих сайтах. Дополнительные сведения см. в статье [Безопасность сайтов и файлов SharePoint Online](../security/office-365-security/secure-sharepoint-online-sites-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="4e734-p103">These steps are part of a larger solution for configuring highly confidential protection for SharePoint sites and the files within these sites. For more information, see [Secure SharePoint Online sites and files](../security/office-365-security/secure-sharepoint-online-sites-and-files.md).</span></span> 

<span data-ttu-id="4e734-112">Использование Azure Information Protection для файлов в SharePoint Online не рекомендуется для всех клиентов, но допустимо для клиентов, которым требуется этот уровень защиты для подмножества файлов.</span><span class="sxs-lookup"><span data-stu-id="4e734-112">Using Azure Information Protection for files in SharePoint Online is not recommended for all customers, but is an option for customers who need this level of protection for a subset of files.</span></span>

<span data-ttu-id="4e734-113">Некоторые важные замечания об этом решении:</span><span class="sxs-lookup"><span data-stu-id="4e734-113">Some important notes about this solution:</span></span>
- <span data-ttu-id="4e734-p104">Когда шифрование Azure Information Protection применяется к файлам в Office 365, служба не может обрабатывать содержимое этих файлов. Совместное редактирование, обнаружение электронных данных, поиск, Delve и другие функции совместной работы неактивны. Политики защиты от потери данных могут работать только с метаданными (включая метки Microsoft 365), но не с содержимым этих файлов (например, номерами кредитных карт в файлах).</span><span class="sxs-lookup"><span data-stu-id="4e734-p104">When Azure Information Protection encryption is applied to files stored in Office 365, the service cannot process the contents of these files. Co-authoring, eDiscovery, search, Delve, and other collaborative features do not work. Data Loss Prevention (DLP) policies can only work with the metadata (including Microsoft 365 labels) but not the contents of these files (such as credit card numbers within files).</span></span>

- <span data-ttu-id="4e734-p105">Для этого решения требуется, чтобы пользователь выбрал метку, которая применяет защиту от Azure Information Protection. Если вам требуется автоматическое шифрование, а также возможность индексировать и проверять файлы в SharePoint, рекомендуется использовать управление правами на доступ к данным (IRM) в SharePoint Online. При настройке библиотеки SharePoint для IRM, файлы автоматически шифруются, если они скачиваются для редактирования. Управление правами на доступ к данным SharePoint включает в себя ограничения, которые могут повлиять на ваше решение. Дополнительные сведения см. в статье [Настройка управления правами на доступ к данным (IRM) в центре администрирования SharePoint](https://docs.microsoft.com/microsoft-365/compliance/set-up-irm-in-sp-admin-center).</span><span class="sxs-lookup"><span data-stu-id="4e734-p105">This solution requires a user to select a label that applies the protection from Azure Information Protection. If you require automatic encryption and the ability for SharePoint to index and inspect the files, consider using Information Rights Management (IRM) in SharePoint Online. When you configure a SharePoint library for IRM, files are automatically encrypted when they are downloaded for editing.  SharePoint IRM includes limitations that might influence your decision. For more information, see [Set up Information Rights Management (IRM) in SharePoint admin center](https://docs.microsoft.com/microsoft-365/compliance/set-up-irm-in-sp-admin-center).</span></span>

## <a name="admin-setup"></a><span data-ttu-id="4e734-122">Настройка администратора</span><span class="sxs-lookup"><span data-stu-id="4e734-122">Admin setup</span></span>
<span data-ttu-id="4e734-123">Прежде всего, для настройки подписки на Microsoft 365 выполните действия, описанные в статье [Как активировать Azure RMS в Центре администрирования Microsoft 365](https://docs.microsoft.com/information-protection/deploy-use/activate-office365).</span><span class="sxs-lookup"><span data-stu-id="4e734-123">First, use the instructions in [Activate Azure RMS with the Microsoft 365 admin center](https://docs.microsoft.com/information-protection/deploy-use/activate-office365) for your Microsoft 365 subscription.</span></span>
  
<span data-ttu-id="4e734-124">Теперь настройте Azure Information Protection, добавив новую политику области и подчиненную метку для разрешений на доступ к строго конфиденциальному сайту группы SharePoint Online и его защиты.</span><span class="sxs-lookup"><span data-stu-id="4e734-124">Next, configure Azure Information Protection with a new scoped policy and sub-label for protection and permissions of your highly confidential SharePoint Online team site.</span></span>
  
1. <span data-ttu-id="4e734-125">Войдите в Центр администрирования, используя учетную запись с ролью администратора компании или администратора безопасности.</span><span class="sxs-lookup"><span data-stu-id="4e734-125">Sign in to the admin center with an account that has the Security Administrator or Company Administrator role.</span></span> <span data-ttu-id="4e734-126">Дополнительные сведения см. в статье [Вход в Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="4e734-126">For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="4e734-127">Перейдите на портал Azure ([https://portal.azure.com](https://portal.azure.com)), открыв отдельную вкладку браузера.</span><span class="sxs-lookup"><span data-stu-id="4e734-127">In a separate tab of your browser, go to the Azure portal ([https://portal.azure.com](https://portal.azure.com)).</span></span>
    
4. <span data-ttu-id="4e734-128">Введите в поле поиска запрос **information**, а затем выберите **Azure Information Protection**.</span><span class="sxs-lookup"><span data-stu-id="4e734-128">In the search box, type **information**, and then click **Azure Information Protection**.</span></span>

5. <span data-ttu-id="4e734-129">Выберите **Метки**.</span><span class="sxs-lookup"><span data-stu-id="4e734-129">Click **Labels**.</span></span>
    
6. <span data-ttu-id="4e734-130">Щелкните правой кнопкой мыши метку **Строго конфиденциально** и выберите элемент **Добавить подчин. метку**.</span><span class="sxs-lookup"><span data-stu-id="4e734-130">Right-click the **Highly Confidential** label, and then click **Add a sub-label**.</span></span>
    
7. <span data-ttu-id="4e734-131">Введите имя подчиненной метки в поле **Имя** и описание подчиненной метки в поле **Описание**.</span><span class="sxs-lookup"><span data-stu-id="4e734-131">Type a name for the sub-label in **Name** and a description of the sub-label in **Description**.</span></span>
    
8. <span data-ttu-id="4e734-132">В разделе **Задайте разрешения для документов и электронных писем, имеющих эту метку** нажмите кнопку **Защитить**.</span><span class="sxs-lookup"><span data-stu-id="4e734-132">In **Set permissions for documents and emails containing this label**, click **Protect**.</span></span>
    
9. <span data-ttu-id="4e734-133">В разделе **Защита** выберите элемент **Azure (облачный ключ)**.</span><span class="sxs-lookup"><span data-stu-id="4e734-133">In the **Protection** section, click **Azure (cloud key)**.</span></span>
    
10. <span data-ttu-id="4e734-134">В колонке **Защита** в разделе **Параметры защиты** нажмите кнопку **+ Добавить разрешения**.</span><span class="sxs-lookup"><span data-stu-id="4e734-134">On the **Protection** blade, under **Protection settings**, click **Add permissions**.</span></span>
    
11. <span data-ttu-id="4e734-135">Перейдите к колонке **Добавление разрешений** и выберите **Обзор каталога** в разделе **Укажите пользователей и группы**.</span><span class="sxs-lookup"><span data-stu-id="4e734-135">On the **Add permissions** blade, under **Specify users and groups**, click **Browse directory**.</span></span>
    
12. <span data-ttu-id="4e734-136">В области **Пользователи и группы AAD** выберите группу доступа для членов строго конфиденциального сайта группы SharePoint Online, а затем нажмите **Выбрать**.</span><span class="sxs-lookup"><span data-stu-id="4e734-136">On the **AAD Users and Groups** pane, select the site members access group for your highly sensitive SharePoint Online team site, and then click **Select**.</span></span>
    
13. <span data-ttu-id="4e734-137">В разделе **Выбрать из предустановленных разрешений или задать пользовательские** выберите вариант **Пользовательские**, а затем установите флажки **Просмотреть права**, **Изменить контент**, **Сохранить**, **Ответить** и **Ответить всем**.</span><span class="sxs-lookup"><span data-stu-id="4e734-137">Under **Choose permissions from the preset or set custom**, click **Custom**, and then click the **View Rights**, **Edit Content**, **Save**, **Reply**, and **Reply all** check boxes.</span></span>
    
14. <span data-ttu-id="4e734-138">Дважды нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="4e734-138">Click **OK** twice.</span></span>
    
15. <span data-ttu-id="4e734-139">В колонке **Подчиненная метка** нажмите кнопку **Сохранить**, а затем щелкните **ОК**.</span><span class="sxs-lookup"><span data-stu-id="4e734-139">On the **Sub-label** blade, click **Save**, and then click **OK**.</span></span>

16. <span data-ttu-id="4e734-140">В колонке **Azure Information Protection** щелкните элементы **Политики > + Добавить политику**.</span><span class="sxs-lookup"><span data-stu-id="4e734-140">On the **Azure Information protection** blade, click **Policies > + Add a new policy**.</span></span>
    
17. <span data-ttu-id="4e734-141">Введите имя новой политики в поле **Имя политики** и описание в поле **Описание**.</span><span class="sxs-lookup"><span data-stu-id="4e734-141">Type a name for the new policy in **Policy name** and a description in **Description**.</span></span>
    
18. <span data-ttu-id="4e734-142">Щелкните элементы **Выберите, к каким пользователям или группам будет применяться эта политика > Группы и пользователи**, а затем выберите группу доступа для участников строго конфиденциального сайта группы SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="4e734-142">Click **Select which users or groups get this policy > User/Groups**, and then select the site members access group for your highly sensitive SharePoint Online team site.</span></span>
    
19. <span data-ttu-id="4e734-143">Щелкните **Выбрать > ОК**.</span><span class="sxs-lookup"><span data-stu-id="4e734-143">Click **Select > OK**.</span></span>

20. <span data-ttu-id="4e734-p107">Выберите элемент **Добавить или удалить метки**. На панели **Политики: добавление и удаление меток** щелкните имя новой подчиненной метки и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="4e734-p107">Click **Add or remove labels**. In the **Policy: Add or remove labels** pane, click the name of your new sub-label, and then click **OK**.</span></span>   

21. <span data-ttu-id="4e734-146">Нажмите кнопку **Сохранить**, а затем — **ОК**.</span><span class="sxs-lookup"><span data-stu-id="4e734-146">Click **Save**, and then click **OK**.</span></span>
 
## <a name="client-setup"></a><span data-ttu-id="4e734-147">Настройка клиента</span><span class="sxs-lookup"><span data-stu-id="4e734-147">Client setup</span></span>
<span data-ttu-id="4e734-148">Теперь вы можете создавать документы и защищать их с помощью службы Azure Information Protection и новой метки.</span><span class="sxs-lookup"><span data-stu-id="4e734-148">You are now ready to begin creating documents and protecting them with Azure Information Protection and your new label.</span></span>
  
<span data-ttu-id="4e734-p108">Необходимо [установить клиент Azure Information Protection](https://docs.microsoft.com/information-protection/rms-client/install-client-app) на мобильном устройстве или компьютере под управлением Windows. Вы можете воспользоваться скриптом и автоматизировать установку. Кроме того, пользователи могут установить клиент вручную. Просмотрите указанные ниже ресурсы.</span><span class="sxs-lookup"><span data-stu-id="4e734-p108">You must [install the Azure Information Protection client](https://docs.microsoft.com/information-protection/rms-client/install-client-app) on your device or Windows-based computer. You can script and automate the installation, or users can install the client manually. See the following resources:</span></span>
  
- [<span data-ttu-id="4e734-152">Клиентская часть Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="4e734-152">The client side of Azure Information Protection</span></span>](https://docs.microsoft.com/information-protection/rms-client/use-client)
    
- [<span data-ttu-id="4e734-153">Установка клиента Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="4e734-153">Installing the Azure Information Protection client</span></span>](https://docs.microsoft.com/information-protection/rms-client/client-admin-guide)
    
- [<span data-ttu-id="4e734-154">Страница скачивания для установки вручную</span><span class="sxs-lookup"><span data-stu-id="4e734-154">Download page for manual installation</span></span>](https://www.microsoft.com/download/details.aspx?id=53018)
    
<span data-ttu-id="4e734-p109">После установки пользователи выполняют запуск и вход из приложения Office (например, Microsoft Word) с указанием своей учетной записи Microsoft 365. С помощью новой панели **Information Protection** пользователи могут выбрать новую метку. Убедитесь, что они знают, какую метку использовать для сайта группы SharePoint Online, чтобы защитить свои строго конфиденциальные файлы.</span><span class="sxs-lookup"><span data-stu-id="4e734-p109">Once installed, your users run and then sign-in from an Office application (such as Microsoft Word) with their Microsoft 365 account. A new **Information Protection** bar allows users to select the new label. Make sure that your users know the SharePoint Online team site and which label to use, to protect their highly confidential files.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4e734-158">Если у вас несколько строго конфиденциальных сайтов группы SharePoint Online, необходимо создать несколько политик области Azure Information Protection с подчиненными метками, используя указанные выше параметры. При этом нужно настроить разрешения для каждой подчиненной метки, заданные группе доступа для участников определенного сайта группы SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="4e734-158">If you have multiple highly sensitive SharePoint Online team sites, you should create multiple Azure Information Protection scoped policies with sub-labels with the above settings, with the permissions for each sub-label set to the site members access group of a specific SharePoint Online team site.</span></span> 
  
## <a name="adding-permissions-for-external-users"></a><span data-ttu-id="4e734-159">Добавление разрешений для внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="4e734-159">Adding permissions for external users</span></span>
<span data-ttu-id="4e734-p110">Предоставить внешним пользователям доступ к файлам, защищенным с помощью Azure Information Protection, можно двумя способами. В обоих случаях внешним пользователям необходима учетная запись Azure AD. Если внешние пользователи не состоят в организации, использующей Azure AD, они могут получить личную учетную запись Azure AD на странице регистрации: [https://aka.ms/aip-signup](https://aka.ms/aip-signup).</span><span class="sxs-lookup"><span data-stu-id="4e734-p110">There are two ways you can grant external users access to files protected with Azure Information Protection. In both cases, external users must have an Azure AD account. If external users aren't members of an organization that uses Azure AD, they can obtain an Azure AD account as an individual by using this signup page: [https://aka.ms/aip-signup](https://aka.ms/aip-signup).</span></span>

 - <span data-ttu-id="4e734-163">Добавление внешних пользователей в группу Azure AD, используемую для настройки защиты метки.</span><span class="sxs-lookup"><span data-stu-id="4e734-163">Add external users to an Azure AD group that is used to configure protection for a label.</span></span> <span data-ttu-id="4e734-164">Необходимо сначала добавить учетную запись в качестве B2B пользователя в каталог.</span><span class="sxs-lookup"><span data-stu-id="4e734-164">You'll need to first add the account as a B2B user in your directory.</span></span> <span data-ttu-id="4e734-165">[Кэширование членства в группах в Azure Rights Management](https://docs.microsoft.com/azure/information-protection/plan-design/prepare#group-membership-caching-by-azure-information-protection) может занять несколько часов.</span><span class="sxs-lookup"><span data-stu-id="4e734-165">It can take a couple of hours for [group membership caching by Azure Rights Management](https://docs.microsoft.com/azure/information-protection/plan-design/prepare#group-membership-caching-by-azure-information-protection).</span></span>  
 - <span data-ttu-id="4e734-p112">Непосредственное добавление внешних пользователей в защиту метки. Вы можете добавить всех пользователей из организации (например, Fabrikam.com), группу Azure AD (например, финансовый отдел в организации) или пользователя. Например, вы можете добавить внешнюю команду контролеров для защиты метки.</span><span class="sxs-lookup"><span data-stu-id="4e734-p112">Add external users directly to the label protection. You can add all users from an organization (e.g. Fabrikam.com), an Azure AD group (such as a finance group within an organization), or user. For example, you can add an external team of regulators to the protection for a label.</span></span>

## <a name="see-also"></a><span data-ttu-id="4e734-169">См. также</span><span class="sxs-lookup"><span data-stu-id="4e734-169">See Also</span></span>

[<span data-ttu-id="4e734-170">Руководство по безопасности (Майкрософт) для политических кампаний, некоммерческих и других динамических организаций</span><span class="sxs-lookup"><span data-stu-id="4e734-170">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](../security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[<span data-ttu-id="4e734-171">Освоение облака и гибридные решения</span><span class="sxs-lookup"><span data-stu-id="4e734-171">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
