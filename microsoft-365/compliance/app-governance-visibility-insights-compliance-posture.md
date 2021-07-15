---
title: Определение соответствия вашего приложения требованиям
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Определите, насколько ваше приложение соответствует требованиям.
ms.openlocfilehash: 3d7cac319c31bac40a3aad2f6b9a4c16303f6a20
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420253"
---
# <a name="determine-your-app-compliance-posture"></a><span data-ttu-id="51dc4-103">Определение соответствия вашего приложения требованиям</span><span class="sxs-lookup"><span data-stu-id="51dc4-103">Determine your app compliance posture</span></span>

><span data-ttu-id="51dc4-104">*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="51dc4-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="51dc4-105">Управление приложениями Майкрософт позволяет быстро оценить соответствие сторонних приложений требованиям, а также их доступ к данным в клиенте Microsoft 365 со страницы управления приложениями "Обзор" в [Центре соответствия требованиям Microsoft 365](https://compliance.microsoft.com/appgovernance).</span><span class="sxs-lookup"><span data-stu-id="51dc4-105">Microsoft app governance allows you to quickly assess the compliance posture of the third-party apps and their access to data in your Microsoft 365 tenant from the app governance Overview page in the [Microsoft 365 Compliance Center](https://compliance.microsoft.com/appgovernance).</span></span>

![Страница обзора управления приложениями в Центре соответствия требованиям Microsoft 365](..\media\manage-app-protection-governance\mapg-cc-overview.png)

>[!Note]
> <span data-ttu-id="51dc4-107">Ваша учетная запись входа в систему должна иметь одну из [этих ролей](app-governance-get-started.md#administrator-roles) для просмотра любых данных управления приложениями.</span><span class="sxs-lookup"><span data-stu-id="51dc4-107">Your sign-in account must have one of [these roles](app-governance-get-started.md#administrator-roles) to view any app governance data.</span></span>
>

<span data-ttu-id="51dc4-108">На этой странице можно увидеть следующее:</span><span class="sxs-lookup"><span data-stu-id="51dc4-108">From this page, you can see:</span></span>

- <span data-ttu-id="51dc4-109">Для приложений с поддержкой OAuth, которые используют API Microsoft Graph:</span><span class="sxs-lookup"><span data-stu-id="51dc4-109">For OAuth-enabled apps that use the Microsoft Graph API:</span></span>

  - <span data-ttu-id="51dc4-110">Количество приложений в клиенте</span><span class="sxs-lookup"><span data-stu-id="51dc4-110">How many are in your tenant</span></span>
  - <span data-ttu-id="51dc4-111">Возможное количество приложений с избыточными правами</span><span class="sxs-lookup"><span data-stu-id="51dc4-111">How many might be overprivileged</span></span>
  - <span data-ttu-id="51dc4-112">Количество приложений с высоким уровнем привилегий</span><span class="sxs-lookup"><span data-stu-id="51dc4-112">How many are high privilege</span></span>

  <span data-ttu-id="51dc4-113">Эти сведения помогут определить уровень риска для вашей организации от приложений с избыточными правами и высоким уровнем привилегий.</span><span class="sxs-lookup"><span data-stu-id="51dc4-113">From this information, you can determine the level of risk to your organization by overprivileged and high privilege apps.</span></span>

- <span data-ttu-id="51dc4-114">Для оповещений:</span><span class="sxs-lookup"><span data-stu-id="51dc4-114">For alerts:</span></span>

  - <span data-ttu-id="51dc4-115">Количество активных оповещений в клиенте</span><span class="sxs-lookup"><span data-stu-id="51dc4-115">How many active alerts your tenant has</span></span>
  - <span data-ttu-id="51dc4-116">Количество оповещений, основанных на обнаружениях управления приложениями (**Оповещения об угрозах**)</span><span class="sxs-lookup"><span data-stu-id="51dc4-116">How many are based on app governance detections (**Threat alerts**)</span></span>
  - <span data-ttu-id="51dc4-117">Количество оповещений, основанных на имеющихся политиках приложений (**Оповещения политики**)</span><span class="sxs-lookup"><span data-stu-id="51dc4-117">How many are based on app policies you have in place (**Policy alerts**)</span></span>
  - <span data-ttu-id="51dc4-118">10 последних оповещений</span><span class="sxs-lookup"><span data-stu-id="51dc4-118">The 10 latest alerts</span></span>

  <span data-ttu-id="51dc4-119">На основе этих сведений можно определить, как быстро создаются оповещения, а также относительное количество обнаруженных и основанных на политиках оповещений.</span><span class="sxs-lookup"><span data-stu-id="51dc4-119">From this information, you can determine how quickly alerts are being generated and the relative number of detected and policy-based alerts.</span></span>

- <span data-ttu-id="51dc4-120">Для доступа к данным и ресурсам:</span><span class="sxs-lookup"><span data-stu-id="51dc4-120">For data and resources access:</span></span>

  - <span data-ttu-id="51dc4-121">Доступ к данным API приложения за последние 90 дней</span><span class="sxs-lookup"><span data-stu-id="51dc4-121">The application API data access in the last 90 days</span></span>
  - <span data-ttu-id="51dc4-122">Использование основных ресурсов за последние 90 дней</span><span class="sxs-lookup"><span data-stu-id="51dc4-122">The usage of the top resources in the last 90 days</span></span>

  <span data-ttu-id="51dc4-123">На основе этих сведений можно определить, существуют ли аномальные пики доступа к данным в клиенте Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="51dc4-123">From this information, you can determine if there are anomalous spikes in access to the data in your Microsoft 365 tenant.</span></span>
