---
title: Шаг 4. Настройка Windows Information Protection
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
ms.openlocfilehash: b624db45c4fe3bd75b2158f225176b7a78ba30f8
ms.sourcegitcommit: 63e35b846d964dde5919a08c2fe432e749e8eff6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2019
ms.locfileid: "37047272"
---
# <a name="step-4-configure-windows-information-protection"></a><span data-ttu-id="2e51f-103">Шаг 4. Настройка Windows Information Protection</span><span class="sxs-lookup"><span data-stu-id="2e51f-103">Step 4: Configure Windows Information Protection</span></span>

<span data-ttu-id="2e51f-104">*Этот шаг необязательный; он применяется к планам E3 и E5 Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="2e51f-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="2e51f-105">Чем больше персональных устройств используется для работы, тем выше становится риск утечки конфиденциальных данных организаций через приложения и устройства.</span><span class="sxs-lookup"><span data-stu-id="2e51f-105">With more personal devices being used for work, there’s increased risk for apps and devices to leak private organization data.</span></span> <span data-ttu-id="2e51f-106">Например, сотрудник может случайно отправить на сайт социальной сети рисунок с маркетинговым планом будущего продукта или сохранить в общедоступном облачном хранилище файл, содержащий совершенно секретную информацию.</span><span class="sxs-lookup"><span data-stu-id="2e51f-106">For example, an employee inadvertently sends a picture of a marketing plan for a future product to a social media site or saves a file containing highly confidential information to their public cloud storage.</span></span> 

<span data-ttu-id="2e51f-107">Windows Information Protection (WIP) обеспечивает защиту от утечки данных такого рода на устройствах с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="2e51f-107">Windows Information Protection (WIP) helps protect against these types of data leakage on Windows 10 devices.</span></span> <span data-ttu-id="2e51f-108">Дополнительные сведения см. в статье [Защита корпоративных данных с помощью WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip).</span><span class="sxs-lookup"><span data-stu-id="2e51f-108">For more information, see [Protect your enterprise data using WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip).</span></span>

<span data-ttu-id="2e51f-109">В Microsoft 365 корпоративный WIP представляет собой сочетание операционной системы Windows 10 Корпоративная и службы Microsoft Intune, которая входит в вашу подписку.</span><span class="sxs-lookup"><span data-stu-id="2e51f-109">In Microsoft 365 Enterprise, WIP is a combination of Windows 10 Enterprise and Microsoft Intune, which is included with Enterprise Mobility + Security (EMS) in your subscription.</span></span> 

<span data-ttu-id="2e51f-110">Для развертывания WIP в организации с использованием Microsoft 365 корпоративный выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="2e51f-110">To deploy WIP in your organization with Microsoft 365 Enterprise:</span></span>

1. <span data-ttu-id="2e51f-111">Зарегистрируйте свои устройства Windows в Intune.</span><span class="sxs-lookup"><span data-stu-id="2e51f-111">Enroll your Windows devices in Intune.</span></span> <span data-ttu-id="2e51f-112">Это уже должно быть сделано на [Шаге 5. Управление мобильными устройствами](mobility-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="2e51f-112">You should have done this in [Phase 5: Mobile Device Management](mobility-infrastructure.md).</span></span>
2. <span data-ttu-id="2e51f-113">Создайте [политику Intune для WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure).</span><span class="sxs-lookup"><span data-stu-id="2e51f-113">Create an [Intune policy for WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure).</span></span>
  - <span data-ttu-id="2e51f-114">Убедитесь, что список защищенных приложений заполнен.</span><span class="sxs-lookup"><span data-stu-id="2e51f-114">Ensure that you have filled out your Protected apps list.</span></span>
  - <span data-ttu-id="2e51f-115">Выберите уровень защиты WIP.</span><span class="sxs-lookup"><span data-stu-id="2e51f-115">Choose your WIP protection level.</span></span>

<span data-ttu-id="2e51f-116">Также можно использовать WIP с [System Center Configuration Manager](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/overview-create-wip-policy-sccm).</span><span class="sxs-lookup"><span data-stu-id="2e51f-116">You can also use WIP with [System Center Configuration Manager](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/overview-create-wip-policy-sccm).</span></span> 

<span data-ttu-id="2e51f-117">Дополнительную информацию см. в статье [Советы и рекомендации по WIP]( https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/guidance-and-best-practices-wip).</span><span class="sxs-lookup"><span data-stu-id="2e51f-117">See [WIP best practices]( https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/guidance-and-best-practices-wip) for more information.</span></span>

<span data-ttu-id="2e51f-118">Прежде чем перейти к следующему шагу, проверьте [условия](infoprotect-exit-criteria.md#crit-infoprotect-step4), при выполнении которых можно считать данный шаг завершенным.</span><span class="sxs-lookup"><span data-stu-id="2e51f-118">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step4) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="2e51f-119">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="2e51f-119">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)|[<span data-ttu-id="2e51f-120">Настройка защиты от потери данных Office 365</span><span class="sxs-lookup"><span data-stu-id="2e51f-120">Configure Office 365 Data Loss Prevention</span></span>](infoprotect-data-loss-prevention.md)|


