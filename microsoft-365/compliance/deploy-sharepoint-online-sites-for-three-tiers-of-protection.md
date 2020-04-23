---
title: Развертывание сайтов SharePoint Online с тремя уровнями защиты
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/27/2019
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
ms.assetid: 1e8e3cfd-b878-4088-b941-9940363a5fae
description: Сводка. Сведения о создании и настройке сайтов группы в SharePoint Online для применения различных уровней защиты информации.
ms.openlocfilehash: 44aa7c126e3ac4b077868c055f35c0b99d678b58
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636137"
---
# <a name="deploy-sharepoint-online-sites-for-three-tiers-of-protection"></a><span data-ttu-id="41a19-103">Развертывание сайтов SharePoint Online с тремя уровнями защиты</span><span class="sxs-lookup"><span data-stu-id="41a19-103">Deploy SharePoint Online sites for three tiers of protection</span></span>

<span data-ttu-id="41a19-p101">В этой статье приводятся инструкции по разработке и развертыванию сайтов групп SharePoint Online с базовым, конфиденциальным и строго конфиденциальным уровнями защиты. Дополнительные сведения об этих трех уровнях защиты см. в статье [Secure SharePoint Online sites and files](../security/office-365-security/secure-sharepoint-online-sites-and-files.md) (Защита сайтов и файлов SharePoint Online).</span><span class="sxs-lookup"><span data-stu-id="41a19-p101">Use the steps in this article to design and deploy baseline, sensitive, and highly confidential SharePoint Online team sites. For more information about these three tiers of protection, see [Secure SharePoint Online sites and files](../security/office-365-security/secure-sharepoint-online-sites-and-files.md).</span></span>
  
## <a name="baseline-sharepoint-online-team-sites"></a><span data-ttu-id="41a19-106">Сайты групп SharePoint Online с базовым уровнем защиты</span><span class="sxs-lookup"><span data-stu-id="41a19-106">Baseline SharePoint Online team sites</span></span>

<span data-ttu-id="41a19-p102">Базовый уровень защиты распространяется на частные и общедоступные сайты групп. Обнаруживать общедоступные сайты групп и получать к ним доступ может любой пользователь в организации. Обнаруживать частные сайты и получать к ним доступ могут только участники группы Microsoft 365, связанной с сайтом группы. Оба этих типа сайтов групп позволяют участникам предоставлять доступ к сайту другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="41a19-p102">Baseline protection includes both public and private team sites. Public team sites can be discovered and accessed by anybody in the organization. Private sites can only be discovered and accessed by members of the Microsoft 365 group associated with the team site. Both of these types of team sites allow members to share the site with others.</span></span>
  
### <a name="public"></a><span data-ttu-id="41a19-111">Открытый</span><span class="sxs-lookup"><span data-stu-id="41a19-111">Public</span></span>

<span data-ttu-id="41a19-112">Чтобы создать сайт группы SharePoint Online с базовым уровнем защиты и общим доступом и разрешениями, выполните [эти инструкции](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).</span><span class="sxs-lookup"><span data-stu-id="41a19-112">To create a baseline SharePoint Online team site with public access and permissions, follow [these instructions](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).</span></span>

<span data-ttu-id="41a19-113">Ниже показана итоговая конфигурация.</span><span class="sxs-lookup"><span data-stu-id="41a19-113">Here is your resulting configuration.</span></span>
  
![Базовый уровень защиты для общедоступного сайта группы SharePoint Online.](../media/bcd46b8d-3f89-4398-80ce-4da17ee85e03.png)
  
### <a name="private"></a><span data-ttu-id="41a19-115">Личные сведения</span><span class="sxs-lookup"><span data-stu-id="41a19-115">Private</span></span>

<span data-ttu-id="41a19-116">Чтобы создать сайт группы SharePoint Online с базовым уровнем защиты, закрытым доступом и разрешениями, выполните [эти инструкции](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).</span><span class="sxs-lookup"><span data-stu-id="41a19-116">To create a baseline SharePoint Online team site with private access and permissions, follow [these instructions](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).</span></span>
  
<span data-ttu-id="41a19-117">Ниже показана итоговая конфигурация.</span><span class="sxs-lookup"><span data-stu-id="41a19-117">Here is your resulting configuration.</span></span>
  
![Базовый уровень защиты для закрытого сайта группы SharePoint Online.](../media/91769026-37e3-4383-ac3c-dbf7aca98e41.png)
  
## <a name="sensitive-sharepoint-online-team-sites"></a><span data-ttu-id="41a19-119">Конфиденциальные сайты группы SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="41a19-119">Sensitive SharePoint Online team sites</span></span>

<span data-ttu-id="41a19-120">Создание конфиденциального сайта группы SharePoint Online начинается с закрытого сайта группы.</span><span class="sxs-lookup"><span data-stu-id="41a19-120">A sensitive SharePoint Online team site starts as a private team site.</span></span>
  
<span data-ttu-id="41a19-121">Сначала создайте закрытый сайт группы SharePoint Online, следуя [этим инструкциям](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).</span><span class="sxs-lookup"><span data-stu-id="41a19-121">First, create the private SharePoint Online team site with [these instructions](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).</span></span>

<span data-ttu-id="41a19-122">С помощью действий, приведенных ниже, настройте дополнительные параметры разрешений на новом сайте группы SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="41a19-122">Next, from the new SharePoint Online team site, configure additional permission settings with these steps.</span></span>

1.  <span data-ttu-id="41a19-123">На панели инструментов сайта группы SharePoint щелкните значок параметров и выберите вариант **Разрешения для сайта**.</span><span class="sxs-lookup"><span data-stu-id="41a19-123">In the tool bar of the SharePoint team site, click the settings icon, and then click **Site permissions**.</span></span>
2.  <span data-ttu-id="41a19-124">В области **Разрешения для сайта** в разделе **Параметры общего доступа** щелкните **Изменить параметры общего доступа**.</span><span class="sxs-lookup"><span data-stu-id="41a19-124">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
3.  <span data-ttu-id="41a19-125">В разделе **Разрешения на предоставление общего доступа** выберите **Только владельцы сайта могут делиться файлами, папками и сайтом** и щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="41a19-125">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**, and then click **Save**.</span></span>

<span data-ttu-id="41a19-126">Ознакомьтесь с результатами настройки разрешений.</span><span class="sxs-lookup"><span data-stu-id="41a19-126">The results of these permission settings are:</span></span>

- <span data-ttu-id="41a19-127">Для участников отключена возможность предоставления общего доступа другим участникам.</span><span class="sxs-lookup"><span data-stu-id="41a19-127">The ability for members to share with other members is disabled.</span></span>
- <span data-ttu-id="41a19-128">Для пользователей, не входящих в группу, включена возможность запроса доступа.</span><span class="sxs-lookup"><span data-stu-id="41a19-128">The ability for non-members to request access is enabled.</span></span>

<span data-ttu-id="41a19-129">Ниже показана полученная в итоге конфигурация.</span><span class="sxs-lookup"><span data-stu-id="41a19-129">Here is your resulting configuration.</span></span>
  
![Уровень защиты для конфиденциальных данных в случае изолированного сайта группы SharePoint Online.](../media/7a6ab9c6-560a-4674-ac39-8175644dbe6f.png)
  
<span data-ttu-id="41a19-131">Благодаря членству в одной из групп доступа участники сайта теперь могут безопасно работать с ресурсами сайта.</span><span class="sxs-lookup"><span data-stu-id="41a19-131">The members of the site, through group membership in one of the access groups, can now securely collaborate on the resources of the site.</span></span>
  
## <a name="highly-confidential-sharepoint-online-team-sites"></a><span data-ttu-id="41a19-132">Сайты групп SharePoint Online со строго конфиденциальным уровнем защиты</span><span class="sxs-lookup"><span data-stu-id="41a19-132">Highly confidential SharePoint Online team sites</span></span>

<span data-ttu-id="41a19-133">Сайт группы SharePoint Online со строго конфиденциальным уровнем защиты — это закрытый сайт группы с дополнительными параметрами разрешений.</span><span class="sxs-lookup"><span data-stu-id="41a19-133">A highly confidential SharePoint Online team site is a private team site with additional permissions settings.</span></span>

<span data-ttu-id="41a19-134">Сначала создайте закрытый сайт группы SharePoint Online, следуя [этим инструкциям](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).</span><span class="sxs-lookup"><span data-stu-id="41a19-134">First, create the private SharePoint Online team site with [these instructions](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).</span></span>

<span data-ttu-id="41a19-135">С помощью действий, приведенных ниже, настройте дополнительные параметры разрешений на новом сайте группы SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="41a19-135">Next, from the new SharePoint Online team site, configure additional permission settings with these steps.</span></span>

1.  <span data-ttu-id="41a19-136">На панели инструментов сайта группы SharePoint щелкните значок параметров и выберите вариант **Разрешения для сайта**.</span><span class="sxs-lookup"><span data-stu-id="41a19-136">In the tool bar of the SharePoint team site, click the settings icon, and then click **Site permissions**.</span></span>
2.  <span data-ttu-id="41a19-137">В области **Разрешения для сайта** в разделе **Параметры общего доступа** щелкните **Изменить параметры общего доступа**.</span><span class="sxs-lookup"><span data-stu-id="41a19-137">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
3.  <span data-ttu-id="41a19-138">В разделе **Разрешения на предоставление общего доступа** установите флажок **Только владельцы сайта могут делиться файлами, папками и сайтом**.</span><span class="sxs-lookup"><span data-stu-id="41a19-138">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>
4. <span data-ttu-id="41a19-139">Отключите параметр **Разрешить запросы на доступ** и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="41a19-139">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="41a19-140">Ознакомьтесь с результатами настройки разрешений.</span><span class="sxs-lookup"><span data-stu-id="41a19-140">The results of these permission settings are:</span></span>

- <span data-ttu-id="41a19-141">Для участников отключена возможность предоставления общего доступа другим участникам.</span><span class="sxs-lookup"><span data-stu-id="41a19-141">The ability for members to share with other members is disabled.</span></span>
- <span data-ttu-id="41a19-142">Для пользователей, не являющихся участниками, отключена возможность запроса доступа.</span><span class="sxs-lookup"><span data-stu-id="41a19-142">The ability for non-members to request access is disabled.</span></span>

<span data-ttu-id="41a19-143">Ниже показана полученная в итоге конфигурация.</span><span class="sxs-lookup"><span data-stu-id="41a19-143">Here is your resulting configuration.</span></span>
  
![Уровень защиты строго конфиденциальных данных для изолированного сайта группы SharePoint Online.](../media/196359ab-d7ed-4fcf-97b4-61820a74aca4.png)
  
<span data-ttu-id="41a19-145">Благодаря членству в одной из групп доступа участники сайта теперь могут безопасно работать с ресурсами сайта.</span><span class="sxs-lookup"><span data-stu-id="41a19-145">The members of the site, through group membership in one of the access groups, can now securely collaborate on the resources of the site.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="41a19-146">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="41a19-146">Next step</span></span>

[<span data-ttu-id="41a19-147">Защита файлов SharePoint Online с помощью меток и DLP</span><span class="sxs-lookup"><span data-stu-id="41a19-147">Protect SharePoint Online files with labels and DLP</span></span>](protect-sharepoint-online-files-with-office-365-labels-and-dlp.md)

## <a name="see-also"></a><span data-ttu-id="41a19-148">См. также</span><span class="sxs-lookup"><span data-stu-id="41a19-148">See also</span></span>

[<span data-ttu-id="41a19-149">Руководство по безопасности (Майкрософт) для политических кампаний, некоммерческих и других динамических организаций</span><span class="sxs-lookup"><span data-stu-id="41a19-149">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](../security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[<span data-ttu-id="41a19-150">Освоение облака и гибридные решения</span><span class="sxs-lookup"><span data-stu-id="41a19-150">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
