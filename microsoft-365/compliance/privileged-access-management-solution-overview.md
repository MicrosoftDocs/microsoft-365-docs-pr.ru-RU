---
title: Управление привилегированным доступом в Microsoft 365
description: Узнайте, как настроить возможности риска для инсайдеров в Microsoft 365.
keywords: Microsoft 365, инсайдерский риск, соответствие требованиям
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
- m365solution-scenario
ms.openlocfilehash: a5cd9d62670b35f7093a3d38cf9e499df407de97
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423812"
---
# <a name="privileged-access-management-in-microsoft-365"></a><span data-ttu-id="a42d7-104">Управление привилегированным доступом в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a42d7-104">Privileged access management in Microsoft 365</span></span>

<span data-ttu-id="a42d7-105">Наличие постоянного доступа некоторых пользователей к конфиденциальной информации или критически важным настройкам конфигурации сети в Microsoft Exchange Online является потенциальным путем для взлома учетных записей или внутренних действий с угрозами.</span><span class="sxs-lookup"><span data-stu-id="a42d7-105">Having standing access by some users to sensitive information or critical network configuration settings in Microsoft Exchange Online is a potential pathway for compromised accounts or internal threat activities.</span></span> <span data-ttu-id="a42d7-106">Управление привилегированным доступом помогает защитить организацию от нарушений и помогает соответствовать лучшим практикам соответствия требованиям, ограничив постоянный доступ к конфиденциальным данным или доступу к критически важным настройкам конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a42d7-106">Privileged access management helps protect your organization from breaches and helps to meet compliance best practices by limiting standing access to sensitive data or access to critical configuration settings.</span></span> <span data-ttu-id="a42d7-107">Вместо администраторов, имеющих постоянный доступ, для задач, которые требуют повышенных разрешений, реализуются правила доступа к простому времени.</span><span class="sxs-lookup"><span data-stu-id="a42d7-107">Instead of administrators having constant access, just-in-time access rules are implemented for tasks that need elevated permissions.</span></span> <span data-ttu-id="a42d7-108">Включение управления привилегированным доступом для Exchange Online в Microsoft 365 позволяет вашей организации работать с нулевыми привилегиями и обеспечивать защиту от постоянных уязвимостей административного доступа.</span><span class="sxs-lookup"><span data-stu-id="a42d7-108">Enabling privileged access management for Exchange Online in Microsoft 365 allows your organization to operate with zero standing privileges and provide a layer of defense against standing administrative access vulnerabilities.</span></span>

## <a name="configure-privileged-access-management-for-microsoft-365"></a><span data-ttu-id="a42d7-109">Настройка управления привилегированным доступом для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a42d7-109">Configure privileged access management for Microsoft 365</span></span>

<span data-ttu-id="a42d7-110">Чтобы настроить управление привилегированным доступом для организации, используйте следующие действия:</span><span class="sxs-lookup"><span data-stu-id="a42d7-110">Use the following steps to configure privileged access management for your organization:</span></span>

![Действия по управлению привилегированным доступом для решения инсайдерской угрозы](../media/ir-solution-pam-steps.png)

1. <span data-ttu-id="a42d7-112">Узнайте об [управлении привилегированным доступом](privileged-access-management-overview.md) в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a42d7-112">Learn about [privileged access management](privileged-access-management-overview.md) in Microsoft 365</span></span>
2. <span data-ttu-id="a42d7-113">Создание [группы](privileged-access-management-configuration.md#step-1-create-an-approvers-group) утверждения</span><span class="sxs-lookup"><span data-stu-id="a42d7-113">Create an [approver's group](privileged-access-management-configuration.md#step-1-create-an-approvers-group)</span></span>
3. <span data-ttu-id="a42d7-114">Включить [управление привилегированным доступом](privileged-access-management-configuration.md#step-2-enable-privileged-access)</span><span class="sxs-lookup"><span data-stu-id="a42d7-114">Enable [privileged access management](privileged-access-management-configuration.md#step-2-enable-privileged-access)</span></span>
4. <span data-ttu-id="a42d7-115">Создание политики [доступа](privileged-access-management-configuration.md#step-3-create-an-access-policy)</span><span class="sxs-lookup"><span data-stu-id="a42d7-115">Create an [access policy](privileged-access-management-configuration.md#step-3-create-an-access-policy)</span></span>
5. <span data-ttu-id="a42d7-116">Отправка и утверждение [запросов на привилегированный доступ](privileged-access-management-configuration.md#step-4-submitapprove-privileged-access-requests)</span><span class="sxs-lookup"><span data-stu-id="a42d7-116">Submit/approve [privileged access requests](privileged-access-management-configuration.md#step-4-submitapprove-privileged-access-requests)</span></span>

## <a name="more-information-about-privileged-access-management"></a><span data-ttu-id="a42d7-117">Дополнительные сведения об управлении привилегированным доступом</span><span class="sxs-lookup"><span data-stu-id="a42d7-117">More information about privileged access management</span></span>

- [<span data-ttu-id="a42d7-118">Часто задамые вопросы об управлении привилегированным доступом</span><span class="sxs-lookup"><span data-stu-id="a42d7-118">Frequently asked questions about privileged access management</span></span>](privileged-access-management-overview.md#frequently-asked-questions)