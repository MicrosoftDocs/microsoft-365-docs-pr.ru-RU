---
title: Перенаправление пользователей из центра Office 365 безопасности и соответствия требованиям в центр Microsoft 365 соответствия требованиям
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.service: O365-seccomp
audience: ITPro
ms.topic: article
localization_priority: Normal
description: Узнайте об автоматической перенаправлении Office 365 пользователей центра безопасности и соответствия требованиям в центр Microsoft 365 соответствия требованиям..
ms.collection: M365-security-compliance
ms.openlocfilehash: b51b2e225c833ac499379bbee119f8cb6f4216e9
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782841"
---
# <a name="redirect-users-from-the-office-365-security-and-compliance-center-to-the-microsoft-365-compliance-center"></a><span data-ttu-id="cfc0d-103">Перенаправление пользователей из центра Office 365 безопасности и соответствия требованиям в центр Microsoft 365 соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="cfc0d-103">Redirect users from the Office 365 Security and Compliance center to the Microsoft 365 compliance center</span></span>

<span data-ttu-id="cfc0d-104">В этой статье рассказывается, как работает автоматическая перенаправление для пользователей, которые могут получать доступ к решениям по обеспечению соответствия требованиям из центра Office 365 безопасности и соответствия требованиям (protection.office.com) в центр Microsoft 365 соответствия требованиям (compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="cfc0d-104">This article explains how automatic redirection works for users accessing compliance solutions from the Office 365 Security and Compliance Center (protection.office.com) to the Microsoft 365 compliance center (compliance.microsoft.com).</span></span>

## <a name="what-to-expect"></a><span data-ttu-id="cfc0d-105">Чего ожидать</span><span class="sxs-lookup"><span data-stu-id="cfc0d-105">What to expect</span></span>

<span data-ttu-id="cfc0d-106">Автоматическое перенаправление включено по умолчанию для всех пользователей, которые имеют доступ к следующим решениям, связанным с соблюдением требований, Office 365 безопасности и соответствия требованиям (protection.office.com):</span><span class="sxs-lookup"><span data-stu-id="cfc0d-106">Automatic redirection is enabled by default for all users accessing the following compliance-related solutions in Office 365 Security and Compliance (protection.office.com):</span></span>

- <span data-ttu-id="cfc0d-107">Защита от потери данных (DLP)</span><span class="sxs-lookup"><span data-stu-id="cfc0d-107">Data loss prevention (DLP)</span></span>
- <span data-ttu-id="cfc0d-108">Классификация</span><span class="sxs-lookup"><span data-stu-id="cfc0d-108">Classification</span></span>
- <span data-ttu-id="cfc0d-109">Управление информацией</span><span class="sxs-lookup"><span data-stu-id="cfc0d-109">Information governance</span></span>
- <span data-ttu-id="cfc0d-110">Управление записями</span><span class="sxs-lookup"><span data-stu-id="cfc0d-110">Records management</span></span>
- <span data-ttu-id="cfc0d-111">Соответствие требованиям связи (ранее 'Supervision')</span><span class="sxs-lookup"><span data-stu-id="cfc0d-111">Communication compliance (formerly 'Supervision')</span></span>

<span data-ttu-id="cfc0d-112">Пользователи автоматически перенаписыются в те же решения по обеспечению соответствия требованиям в центре Microsoft 365 соответствия требованиям (compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="cfc0d-112">Users are automatically routed to the same compliance solutions in the Microsoft 365 compliance center (compliance.microsoft.com).</span></span>

>[!NOTE]
><span data-ttu-id="cfc0d-113">Для других решений по обеспечению соответствия требованиям, включенных в центр Office 365 безопасности и соответствия требованиям, пользователи будут продолжать управлять этими решениями в центре Microsoft 365 или центре Office 365 безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="cfc0d-113">For other compliance solutions included in the Office 365 Security and Compliance Center, users will continue to manage these solutions in either the Microsoft 365 compliance center or the Office 365 Security and Compliance Center.</span></span> <span data-ttu-id="cfc0d-114">Автоматическое перенаправление для этих решений соответствия требованиям будет доступно в ближайшее время.\*</span><span class="sxs-lookup"><span data-stu-id="cfc0d-114">The automatic redirection for these compliance solutions will be available soon.\*</span></span>

<span data-ttu-id="cfc0d-115">Эта функция и связанные элементы управления не позволяют автоматически перенаправлять функции безопасности для Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="cfc0d-115">This feature and associated controls does not enable the automatic redirection of Security features for Microsoft Defender for Office 365.</span></span> <span data-ttu-id="cfc0d-116">Сведения о перенаправлении функций безопасности [см.](/microsoft-365/security/defender/microsoft-365-security-mdo-redirection) в материале Перенаправление учетных записей из Microsoft Defender для Office 365 в центр безопасности Microsoft 365 безопасности.</span><span class="sxs-lookup"><span data-stu-id="cfc0d-116">To enable the redirection for security features, see [Redirecting accounts from Microsoft Defender for Office 365 to the Microsoft 365 security center](/microsoft-365/security/defender/microsoft-365-security-mdo-redirection) for details.</span></span>

## <a name="can-i-go-back-to-using-the-former-portal"></a><span data-ttu-id="cfc0d-117">Можно ли вернуться к использованию бывшего портала?</span><span class="sxs-lookup"><span data-stu-id="cfc0d-117">Can I go back to using the former portal?</span></span>

<span data-ttu-id="cfc0d-118">Если что-то не работает для вас или вы не можете выполнить что-либо через портал центра Microsoft 365 соответствия требованиям, вы можете временно отключить автоматическое перенаправление для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="cfc0d-118">If something isn't working for you or if there's anything you're unable to complete through the Microsoft 365 compliance center portal, you can temporarily disable the automatic redirection for all users.</span></span>

>[!IMPORTANT]
><span data-ttu-id="cfc0d-119">Центр Microsoft 365 является порталом управления заменой решений соответствия требованиям, управляемым в настоящее время в центре Office 365 безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="cfc0d-119">The Microsoft 365 compliance center is the replacement management portal for compliance solutions currently managed in the Office 365 Security and Compliance center.</span></span> <span data-ttu-id="cfc0d-120">Все Microsoft 365 соответствия требованиям будут управляться исключительно в центре Microsoft 365 соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="cfc0d-120">All Microsoft 365 compliance solutions will be managed solely in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="cfc0d-121">Отключение перенаправления в центр Microsoft 365 соответствия требованиям должно быть краткосрочным решением.\*</span><span class="sxs-lookup"><span data-stu-id="cfc0d-121">Disabling redirection to the Microsoft 365 compliance center should be a short-term solution.\*</span></span>

<span data-ttu-id="cfc0d-122">Чтобы вернуться к центру Office 365 безопасности и соответствия требованиям (protection.microsoft.com) для всех пользователей, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="cfc0d-122">To switch back to the Office 365 Security and Compliance center (protection.microsoft.com) for all users, complete the following steps:</span></span>

1. <span data-ttu-id="cfc0d-123">Ворегистрируйся [в центр Microsoft 365](https://compliance.microsoft.com) в качестве глобального администратора или используя любую учетную запись с разрешениями администратора соответствия требованиям в каталоге Azure Active.</span><span class="sxs-lookup"><span data-stu-id="cfc0d-123">Sign in to the [Microsoft 365 compliance center](https://compliance.microsoft.com) as a global administrator or using any account with compliance administrator permissions in Azure Active directory.</span></span>
2. <span data-ttu-id="cfc0d-124">Перейдите **Параметры**  >  **перенаправление центра соответствия** требованиям.</span><span class="sxs-lookup"><span data-stu-id="cfc0d-124">Navigate to **Settings** > **Compliance center redirection**.</span></span>
3. <span data-ttu-id="cfc0d-125">Переключение параметра Автоматическое перенаправление в **Off**.</span><span class="sxs-lookup"><span data-stu-id="cfc0d-125">Toggle the Automatic redirection setting to **Off**.</span></span>
4. <span data-ttu-id="cfc0d-126">Выберите **Отключение** и совместное отзывов при запросе.</span><span class="sxs-lookup"><span data-stu-id="cfc0d-126">Select **Turn off** and share feedback when prompted.</span></span>

<span data-ttu-id="cfc0d-127">После отключения пользователи больше не будут compliance.microsoft.com и они будут направлены в центр Office 365 безопасности и соответствия требованиям (protection.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="cfc0d-127">Once disabled, users will no longer be routed to compliance.microsoft.com and they will be directed to the Office 365 Security and Compliance center (protection.microsoft.com).</span></span> <span data-ttu-id="cfc0d-128">Этот параметр может быть включен снова в любое время администраторами Global или Compliance.</span><span class="sxs-lookup"><span data-stu-id="cfc0d-128">This setting can be enabled again at any time by Global or Compliance admins.</span></span>

## <a name="related-information"></a><span data-ttu-id="cfc0d-129">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="cfc0d-129">Related information</span></span>

- [<span data-ttu-id="cfc0d-130">Microsoft 365 центра соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="cfc0d-130">Microsoft 365 compliance center overview</span></span>](/microsoft-365/compliance/microsoft-365-compliance-center)