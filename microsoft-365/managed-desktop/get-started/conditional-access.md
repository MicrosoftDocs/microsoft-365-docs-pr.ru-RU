---
title: Настройка условного доступа
description: Как исключить некоторые учетные записи Майкрософт
keywords: Настольные компьютеры, управляемые корпорацией Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 1bc5d937616cba60c5af43fe22a7c4dccf89a55e
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42085812"
---
# <a name="adjust-conditional-access"></a><span data-ttu-id="e95d8-104">Настройка условного доступа</span><span class="sxs-lookup"><span data-stu-id="e95d8-104">Adjust conditional access</span></span>

<span data-ttu-id="e95d8-105">Если вы используете политики [условного доступа](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) в Организации, необходимо настроить их для исключения определенных учетных записей, чтобы обеспечить правильную работу управляемого рабочего стола Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="e95d8-105">If you use [conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies in your organization, you'll have to set them to exclude certain accounts so that Microsoft Managed Desktop can work properly.</span></span>

<span data-ttu-id="e95d8-106">Для этого выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="e95d8-106">To do this, follow these steps:</span></span>

1. <span data-ttu-id="e95d8-107">Ознакомьтесь с разделом "откатить действия", [чтобы: планирование развертывания условного доступа в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access#rollback-steps).</span><span class="sxs-lookup"><span data-stu-id="e95d8-107">Refer to the "Rollback steps" section of [How To: Plan your Conditional Access deployment in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access#rollback-steps).</span></span>
2. <span data-ttu-id="e95d8-108">Выполните действия, чтобы исключить группу *служебных учетных записей современного рабочего места* для всех политик.</span><span class="sxs-lookup"><span data-stu-id="e95d8-108">Follow the steps there to exclude the *Modern Workplace Service Accounts* group for all policies.</span></span>


<span data-ttu-id="e95d8-109">Если у вас возникли сложности с использованием условного доступа, обратитесь в [службу поддержки](../working-with-managed-desktop/admin-support.md)администраторов.</span><span class="sxs-lookup"><span data-stu-id="e95d8-109">If you have any difficulty with conditional access, contact admin [support](../working-with-managed-desktop/admin-support.md).</span></span>

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="e95d8-110">Действия для начала работы с управляемым рабочим столом Майкрософт</span><span class="sxs-lookup"><span data-stu-id="e95d8-110">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="e95d8-111">Добавление и проверка контактов администратора на портале администрирования</span><span class="sxs-lookup"><span data-stu-id="e95d8-111">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. <span data-ttu-id="e95d8-112">Настройка условного доступа (этот раздел)</span><span class="sxs-lookup"><span data-stu-id="e95d8-112">Adjust conditional access (this topic)</span></span>
3. [<span data-ttu-id="e95d8-113">Назначение лицензий</span><span class="sxs-lookup"><span data-stu-id="e95d8-113">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="e95d8-114">Развертывание корпоративного портала Intune</span><span class="sxs-lookup"><span data-stu-id="e95d8-114">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="e95d8-115">Включение службы Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="e95d8-115">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="e95d8-116">Настройка устройств</span><span class="sxs-lookup"><span data-stu-id="e95d8-116">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="e95d8-117">Подготовка пользователей к работе с устройствами</span><span class="sxs-lookup"><span data-stu-id="e95d8-117">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="e95d8-118">Развертывание приложений</span><span class="sxs-lookup"><span data-stu-id="e95d8-118">Deploy apps</span></span>](deploy-apps.md)
