---
title: Шаг 4. Настройка Windows Information Protection
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Изучение и развертывание Windows Information Protection в Microsoft 365.
ms.openlocfilehash: c7b76ef28d41810d6e9e45e98adb7a94cf8ae2f4
ms.sourcegitcommit: 634abe8a237e27dfe82376e6ef32280aab5d4a27
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "45005726"
---
# <a name="step-4-configure-windows-information-protection"></a><span data-ttu-id="836f2-103">Шаг 4. Настройка Windows Information Protection</span><span class="sxs-lookup"><span data-stu-id="836f2-103">Step 4: Configure Windows Information Protection</span></span>

<span data-ttu-id="836f2-104">*Этот этап не является обязательным. Он применяется к планам E3 и E5 Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="836f2-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Этап 6. Защита данных](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="836f2-106">Чем больше персональных устройств используется для работы, тем выше становится риск утечки конфиденциальных данных организаций через приложения и устройства.</span><span class="sxs-lookup"><span data-stu-id="836f2-106">With more personal devices being used for work, there’s increased risk for apps and devices to leak private organization data.</span></span> <span data-ttu-id="836f2-107">Например, сотрудник может случайно отправить на сайт социальной сети рисунок с маркетинговым планом будущего продукта или сохранить в общедоступном облачном хранилище файл, содержащий совершенно секретную информацию.</span><span class="sxs-lookup"><span data-stu-id="836f2-107">For example, an employee inadvertently sends a picture of a marketing plan for a future product to a social media site or saves a file containing highly confidential information to their public cloud storage.</span></span> 

<span data-ttu-id="836f2-108">Windows Information Protection (WIP) обеспечивает защиту от утечки данных такого рода на устройствах с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="836f2-108">Windows Information Protection (WIP) helps protect against these types of data leakage on Windows 10 devices.</span></span> <span data-ttu-id="836f2-109">Дополнительные сведения см. в статье [Защита корпоративных данных с помощью WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip).</span><span class="sxs-lookup"><span data-stu-id="836f2-109">For more information, see [Protect your enterprise data using WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip).</span></span>

<span data-ttu-id="836f2-110">В Microsoft 365 корпоративный WIP представляет собой сочетание операционной системы Windows 10 Корпоративная и службы Microsoft Intune, которая входит в вашу подписку.</span><span class="sxs-lookup"><span data-stu-id="836f2-110">In Microsoft 365 Enterprise, WIP is a combination of Windows 10 Enterprise and Microsoft Intune, which is included with your subscription.</span></span> 

<span data-ttu-id="836f2-111">Для развертывания WIP в организации с использованием Microsoft 365 корпоративный выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="836f2-111">To deploy WIP in your organization with Microsoft 365 Enterprise:</span></span>

1. <span data-ttu-id="836f2-112">Зарегистрируйте свои устройства Windows в Intune.</span><span class="sxs-lookup"><span data-stu-id="836f2-112">Enroll your Windows devices in Intune.</span></span> <span data-ttu-id="836f2-113">Это уже должно быть сделано на [Этапе 5. Управление мобильными устройствами](mobility-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="836f2-113">You should have done this in [Phase 5: Mobile Device Management](mobility-infrastructure.md).</span></span>

2. <span data-ttu-id="836f2-114">Создайте [политику Intune для WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure).</span><span class="sxs-lookup"><span data-stu-id="836f2-114">Create an [Intune policy for WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure).</span></span>

   -    <span data-ttu-id="836f2-115">Убедитесь, что список защищенных приложений заполнен.</span><span class="sxs-lookup"><span data-stu-id="836f2-115">Ensure that you have filled out your Protected apps list.</span></span>
  
   - <span data-ttu-id="836f2-116">Выберите уровень защиты WIP.</span><span class="sxs-lookup"><span data-stu-id="836f2-116">Choose your WIP protection level.</span></span>

<span data-ttu-id="836f2-117">Также можно использовать WIP с [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-configmgr).</span><span class="sxs-lookup"><span data-stu-id="836f2-117">You can also use WIP with [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-configmgr).</span></span> 

<span data-ttu-id="836f2-118">Дополнительную информацию см. в статье [Советы и рекомендации по WIP]( https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/guidance-and-best-practices-wip).</span><span class="sxs-lookup"><span data-stu-id="836f2-118">See [WIP best practices]( https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/guidance-and-best-practices-wip) for more information.</span></span>

<span data-ttu-id="836f2-119">Прежде чем перейти к следующему шагу, проверьте [условия](infoprotect-exit-criteria.md#crit-infoprotect-step4), при выполнении которых можно считать данный шаг завершенным.</span><span class="sxs-lookup"><span data-stu-id="836f2-119">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step4) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="836f2-120">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="836f2-120">Next step</span></span>

|||
|:-------|:-----|
|![Шаг 5](../media/stepnumbers/Step5.png)|[<span data-ttu-id="836f2-122">Настройка защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="836f2-122">Configure Data Loss Prevention</span></span>](infoprotect-data-loss-prevention.md)|


