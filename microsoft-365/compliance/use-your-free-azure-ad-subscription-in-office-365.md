---
title: Использование бесплатной подписки на Azure Active Directory в Office 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: d104fb44-1c42-4541-89a6-1f67be22e4ad
description: Сведения о том, как получать доступ к Azure Active Directory в составе платной подписки организации на Office 365.
ms.openlocfilehash: fb1e2586c0b21c72084d7120b8735fccccd1a004
ms.sourcegitcommit: 01ead889086ecc7dcf5d10244bcf67c5a33c8114
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "42710498"
---
# <a name="use-your-free-azure-active-directory-subscription-in-office-365"></a><span data-ttu-id="2e92b-103">Использование бесплатной подписки на Azure Active Directory в Office 365</span><span class="sxs-lookup"><span data-stu-id="2e92b-103">Use your free Azure Active Directory subscription in Office 365</span></span>

<span data-ttu-id="2e92b-p101">Если у вашей организации есть платная подписка на Office 365, Microsoft Dynamics CRM Online, Enterprise Mobility + Security E3 или другие службы Майкрософт, у вас есть бесплатная подписка на Microsoft Azure Active Directory. Вы и другие администраторы можете использовать Azure AD для создания учетных записей групп и пользователей, а также для управления ими. Для работы с Azure AD нужно просто войти на портал Azure, используя учетную запись Office 365.</span><span class="sxs-lookup"><span data-stu-id="2e92b-p101">If your organization has a paid subscription to Office 365, Microsoft Dynamics CRM Online, Enterprise Mobility Suite, or other Microsoft services, you have a free subscription to Microsoft Azure Active Directory. You and other admins can use Azure AD to create and manage user and group accounts. To use Azure AD, just go to the Azure portal and sign in using your Office 365 account.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="2e92b-107">Перед началом работы</span><span class="sxs-lookup"><span data-stu-id="2e92b-107">Before you begin</span></span>

<span data-ttu-id="2e92b-p102">Используйте частный сеанс просмотра (не обычный сеанс) для доступа к порталу Azure (на шаге 1 ниже), поскольку это предотвращает передачу учетных данных, с которыми вы вошли в систему, в Azure. Чтобы открыть сеанс приватного просмотра:</span><span class="sxs-lookup"><span data-stu-id="2e92b-p102">Use a private browsing session (not a regular session) to access the Azure portal (in step 1 below) because this prevents the credentials that you're currently logged on with from being passed to Azure. To open an private browsing session:</span></span>

- <span data-ttu-id="2e92b-110">В Microsoft Edge (устаревшая версия), Internet Explorer или Mozilla FireFox нажмите клавиши `CTRL+SHIFT+P`.</span><span class="sxs-lookup"><span data-stu-id="2e92b-110">In Microsoft Edge (legacy version), Internet Explorer, or Mozilla FireFox, press `CTRL+SHIFT+P`.</span></span>

- <span data-ttu-id="2e92b-111">В Microsoft Edge (новая версия) или Google Chrome нажмите клавиши `CTRL+SHIFT+N`.</span><span class="sxs-lookup"><span data-stu-id="2e92b-111">In Microsoft Edge (newest version) or Google Chrome, press `CTRL+SHIFT+N`.</span></span>

## <a name="access-azure-active-directory"></a><span data-ttu-id="2e92b-112">Доступ к Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="2e92b-112">Access Azure Active Directory</span></span>

1. <span data-ttu-id="2e92b-113">Войдите на сайт [portal.azure.com](https://portal.azure.com), используя рабочую или учебную учетную запись Office 365.</span><span class="sxs-lookup"><span data-stu-id="2e92b-113">Go to [portal.azure.com](https://portal.azure.com) and sign in with your Office 365 work or student account.</span></span>

2. <span data-ttu-id="2e92b-114">На панели навигации портала Azure выберите **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="2e92b-114">In the left navigation pane in the Azure portal, click **Azure Active Directory**.</span></span>

    ![На панели навигации портала Azure, расположенной слева, выберите пункт "Azure Active Directory".](../media/97d2d72f-ac20-46ab-898c-851f6009b453.png)

    <span data-ttu-id="2e92b-116">Отобразится центр администрирования **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="2e92b-116">The **Azure Active Directory** admin center is displayed.</span></span>

## <a name="more-information"></a><span data-ttu-id="2e92b-117">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="2e92b-117">More information</span></span>

- <span data-ttu-id="2e92b-118">Бесплатная подписка на Azure Active Directory не включает отчет о действиях входа.</span><span class="sxs-lookup"><span data-stu-id="2e92b-118">A free Azure Active Directory subscription does not include the Sign-ins activity report.</span></span> <span data-ttu-id="2e92b-119">Чтобы записывать действия входа (это может быть полезно в случае нарушения безопасности данных), потребуется подписка на Azure Active Directory Premium.</span><span class="sxs-lookup"><span data-stu-id="2e92b-119">To record sign-in activity (which can be useful in the event of a data breach), you need an Azure Active Directory Premium subscription.</span></span> <span data-ttu-id="2e92b-120">Дополнительные сведения см. в статье [Как долго в Azure AD хранятся данные?](https://docs.microsoft.com/azure/active-directory/reports-monitoring/reference-reports-data-retention#how-long-does-azure-ad-store-the-data)</span><span class="sxs-lookup"><span data-stu-id="2e92b-120">For more information, see [How long does Azure AD store the data?](https://docs.microsoft.com/azure/active-directory/reports-monitoring/reference-reports-data-retention#how-long-does-azure-ad-store-the-data).</span></span>

- <span data-ttu-id="2e92b-121">Вы также можете открыть Центр администрирования **Azure Active Directory** из Центра администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2e92b-121">You can also access the **Azure Active Directory** admin center from the Microsoft 365 admin center.</span></span> <span data-ttu-id="2e92b-122">В левой области навигации Центра администрирования Microsoft 365 выберите **Центры администрирования** \> **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="2e92b-122">In the left navigation pane of the Microsoft 365 admin center, click **Admin centers** \> **Azure Active Directory**.</span></span>

- <span data-ttu-id="2e92b-123">Сведения об управлении пользователями и группами, а также о выполнении других задач по управлению каталогом см. в статье [Управление каталогом Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-administer).</span><span class="sxs-lookup"><span data-stu-id="2e92b-123">For information about managing users and groups and performing other directory management tasks, see [Manage your Azure AD directory](https://docs.microsoft.com/azure/active-directory/active-directory-administer).</span></span>
