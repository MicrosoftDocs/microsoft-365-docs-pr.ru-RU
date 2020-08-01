---
title: Настройка условного доступа
description: Как исключить некоторые учетные записи Майкрософт
keywords: Компьютеры, управляемые Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 8844c50f5faba609b3f5f53adc5ab45ba1dbaa74
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529687"
---
# <a name="adjust-conditional-access"></a><span data-ttu-id="a9947-104">Настройка условного доступа</span><span class="sxs-lookup"><span data-stu-id="a9947-104">Adjust conditional access</span></span>

<span data-ttu-id="a9947-105">Если вы используете политики [условного доступа](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) в Организации, необходимо настроить их для исключения определенных учетных записей, чтобы обеспечить правильную работу управляемого рабочего стола Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a9947-105">If you use [conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies in your organization, you'll have to set them to exclude certain accounts so that Microsoft Managed Desktop can work properly.</span></span>

<span data-ttu-id="a9947-106">Для этого выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="a9947-106">To do this, follow these steps:</span></span>

1. <span data-ttu-id="a9947-107">Ознакомьтесь с разделом "откатить действия", [чтобы: планирование развертывания условного доступа в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access#rollback-steps).</span><span class="sxs-lookup"><span data-stu-id="a9947-107">Refer to the "Rollback steps" section of [How To: Plan your Conditional Access deployment in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access#rollback-steps).</span></span>
2. <span data-ttu-id="a9947-108">Выполните действия, чтобы исключить группу *служебных учетных записей современного рабочего места* для всех политик.</span><span class="sxs-lookup"><span data-stu-id="a9947-108">Follow the steps there to exclude the *Modern Workplace Service Accounts* group for all policies.</span></span>


<span data-ttu-id="a9947-109">Если у вас возникли сложности с использованием условного доступа, обратитесь в [службу поддержки](../working-with-managed-desktop/admin-support.md)администраторов.</span><span class="sxs-lookup"><span data-stu-id="a9947-109">If you have any difficulty with conditional access, contact admin [support](../working-with-managed-desktop/admin-support.md).</span></span>

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="a9947-110">Действия для начала работы с управляемым рабочим столом Майкрософт</span><span class="sxs-lookup"><span data-stu-id="a9947-110">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="a9947-111">Добавление и проверка контактов администратора на портале администрирования</span><span class="sxs-lookup"><span data-stu-id="a9947-111">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. <span data-ttu-id="a9947-112">Настройка условного доступа (этот раздел)</span><span class="sxs-lookup"><span data-stu-id="a9947-112">Adjust conditional access (this topic)</span></span>
3. [<span data-ttu-id="a9947-113">Назначение лицензий</span><span class="sxs-lookup"><span data-stu-id="a9947-113">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="a9947-114">Развертывание корпоративного портала Intune</span><span class="sxs-lookup"><span data-stu-id="a9947-114">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="a9947-115">Включение службы Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="a9947-115">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="a9947-116">Настройка устройств</span><span class="sxs-lookup"><span data-stu-id="a9947-116">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="a9947-117">Подготовка пользователей к работе с устройствами</span><span class="sxs-lookup"><span data-stu-id="a9947-117">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="a9947-118">Развертывание приложений</span><span class="sxs-lookup"><span data-stu-id="a9947-118">Deploy apps</span></span>](deploy-apps.md)
