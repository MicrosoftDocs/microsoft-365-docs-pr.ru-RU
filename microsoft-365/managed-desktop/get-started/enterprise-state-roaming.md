---
title: Включение службы Enterprise State Roaming
description: ''
keywords: Компьютеры, управляемые Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 709a231f1c3f401ceeee2b3aaf99ff275f107e30
ms.sourcegitcommit: 8c698d1a0c41baf5f35d07b0d765b4a5ead593d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/13/2021
ms.locfileid: "53409120"
---
# <a name="enable-enterprise-state-roaming"></a><span data-ttu-id="2936a-103">Включение службы Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="2936a-103">Enable Enterprise State Roaming</span></span>

<span data-ttu-id="2936a-104">[Enterprise государственного роуминга](/azure/active-directory/devices/enterprise-state-roaming-overview) позволяет пользователям безопасно синхронизировать данные параметров пользователей и приложений в облаке.</span><span class="sxs-lookup"><span data-stu-id="2936a-104">[Enterprise State Roaming](/azure/active-directory/devices/enterprise-state-roaming-overview) lets users securely synchronize user and application settings data to the cloud.</span></span> <span data-ttu-id="2936a-105">Это означает, что они будут иметь одинаковый опыт независимо от того, Windows устройство они впишут.</span><span class="sxs-lookup"><span data-stu-id="2936a-105">This means they'll have the same experience no matter which Windows device they sign into.</span></span> <span data-ttu-id="2936a-106">Например, если заменить одно из компьютеры, управляемые Майкрософт на новое, оно будет выглядеть и вести себя точно так же, как и последнее.</span><span class="sxs-lookup"><span data-stu-id="2936a-106">For example, if you replace one of their Microsoft Managed Desktop devices with a new one, it will look and behave exactly the same as the last one.</span></span> <span data-ttu-id="2936a-107">Enterprise Государственный роуминг является необязательным элементом для службы компьютеры, управляемые Майкрософт, которую можно настроить для пользователей и которая не включена или не управляется в компьютеры, управляемые Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="2936a-107">Enterprise State Roaming is an optional feature for the Microsoft Managed Desktop service that you can configure for your users and isn't included or managed as part of Microsoft Managed Desktop.</span></span>

<span data-ttu-id="2936a-108">Чтобы включить Enterprise государственного роуминга, выполните действия в [Enterprise государственного роуминга в Azure Active Directory](/azure/active-directory/devices/enterprise-state-roaming-enable).</span><span class="sxs-lookup"><span data-stu-id="2936a-108">To enable Enterprise State Roaming, follow the steps in [Enable Enterprise State Roaming in Azure Active Directory](/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span>

>[!NOTE]
><span data-ttu-id="2936a-109">Если включить Enterprise государственного роуминга, в списке предпочтительных языков будет перезаписывать язык, выбранный во время установки устройства.</span><span class="sxs-lookup"><span data-stu-id="2936a-109">If you enable Enterprise State Roaming, your preferred language list will overwrite the language selected during device setup.</span></span> <span data-ttu-id="2936a-110">Несмотря на то, что пользователи могут легко это исправить, изначально это может привести к непоследовательной локализации.</span><span class="sxs-lookup"><span data-stu-id="2936a-110">Although users can fix this easily, it could cause an inconsistent localization experience initially.</span></span> <span data-ttu-id="2936a-111">Определите, Enterprise ли государственный роуминг является правильным для пользователей перед настройкой устройств.</span><span class="sxs-lookup"><span data-stu-id="2936a-111">Determine if Enterprise State Roaming is right for your users before setting up devices.</span></span>

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="2936a-112">Шаги для начала работы с компьютеры, управляемые Майкрософт</span><span class="sxs-lookup"><span data-stu-id="2936a-112">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="2936a-113">Добавление и проверка контактов администратора на портале администрирования</span><span class="sxs-lookup"><span data-stu-id="2936a-113">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="2936a-114">Настройка условного доступа</span><span class="sxs-lookup"><span data-stu-id="2936a-114">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="2936a-115">Назначение лицензий</span><span class="sxs-lookup"><span data-stu-id="2936a-115">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="2936a-116">Развертывание корпоративного портала Intune</span><span class="sxs-lookup"><span data-stu-id="2936a-116">Deploy Intune Company Portal</span></span>](company-portal.md)
5. <span data-ttu-id="2936a-117">Включить Enterprise государственного роуминга (этот раздел)</span><span class="sxs-lookup"><span data-stu-id="2936a-117">Enable Enterprise State Roaming (this topic)</span></span>
6. [<span data-ttu-id="2936a-118">Настройка устройств</span><span class="sxs-lookup"><span data-stu-id="2936a-118">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="2936a-119">Подготовка пользователей к работе с устройствами</span><span class="sxs-lookup"><span data-stu-id="2936a-119">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="2936a-120">Развертывание приложений</span><span class="sxs-lookup"><span data-stu-id="2936a-120">Deploy apps</span></span>](deploy-apps.md)
