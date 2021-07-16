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
ms.openlocfilehash: 152f68e8fe0e7d7340d2e048bc73684bc079386f
ms.sourcegitcommit: 2fd60871975d61e60d4827b36cd689021fd2a4c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2021
ms.locfileid: "53438028"
---
# <a name="determine-your-app-compliance-posture"></a><span data-ttu-id="3221d-103">Определение соответствия вашего приложения требованиям</span><span class="sxs-lookup"><span data-stu-id="3221d-103">Determine your app compliance posture</span></span>

><span data-ttu-id="3221d-104">*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="3221d-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="3221d-105">Управление приложениями Майкрософт позволяет быстро оценить соответствие сторонних приложений требованиям, а также их доступ к данным в клиенте Microsoft 365 со страницы управления приложениями "Обзор" в [Центре соответствия требованиям Microsoft 365](https://aka.ms/appgovernance).</span><span class="sxs-lookup"><span data-stu-id="3221d-105">Microsoft app governance allows you to quickly assess the compliance posture of the third-party apps and their access to data in your Microsoft 365 tenant from the app governance Overview page in the [Microsoft 365 Compliance Center](https://aka.ms/appgovernance).</span></span>

![Страница обзора управления приложениями в Центре соответствия требованиям Microsoft 365](..\media\manage-app-protection-governance\mapg-cc-overview.png)

>[!Note]
> <span data-ttu-id="3221d-107">Ваша учетная запись входа в систему должна иметь одну из [этих ролей](app-governance-get-started.md#administrator-roles) для просмотра любых данных управления приложениями.</span><span class="sxs-lookup"><span data-stu-id="3221d-107">Your sign-in account must have one of [these roles](app-governance-get-started.md#administrator-roles) to view any app governance data.</span></span>
>

<span data-ttu-id="3221d-108">На этой странице можно увидеть следующее:</span><span class="sxs-lookup"><span data-stu-id="3221d-108">From this page, you can see:</span></span>

- <span data-ttu-id="3221d-109">Для приложений с поддержкой OAuth, которые используют API Microsoft Graph:</span><span class="sxs-lookup"><span data-stu-id="3221d-109">For OAuth-enabled apps that use the Microsoft Graph API:</span></span>

  - <span data-ttu-id="3221d-110">Количество приложений в клиенте</span><span class="sxs-lookup"><span data-stu-id="3221d-110">How many are in your tenant</span></span>
  - <span data-ttu-id="3221d-111">Возможное количество приложений с избыточными правами</span><span class="sxs-lookup"><span data-stu-id="3221d-111">How many might be overprivileged</span></span>
  - <span data-ttu-id="3221d-112">Количество приложений с высоким уровнем привилегий</span><span class="sxs-lookup"><span data-stu-id="3221d-112">How many are high privilege</span></span>

  <span data-ttu-id="3221d-113">Эти сведения помогут определить уровень риска для вашей организации от приложений с избыточными правами и высоким уровнем привилегий.</span><span class="sxs-lookup"><span data-stu-id="3221d-113">From this information, you can determine the level of risk to your organization by overprivileged and high privilege apps.</span></span>

- <span data-ttu-id="3221d-114">Для оповещений:</span><span class="sxs-lookup"><span data-stu-id="3221d-114">For alerts:</span></span>

  - <span data-ttu-id="3221d-115">Количество активных оповещений в клиенте</span><span class="sxs-lookup"><span data-stu-id="3221d-115">How many active alerts your tenant has</span></span>
  - <span data-ttu-id="3221d-116">Количество оповещений, основанных на обнаружениях управления приложениями (**Оповещения об угрозах**)</span><span class="sxs-lookup"><span data-stu-id="3221d-116">How many are based on app governance detections (**Threat alerts**)</span></span>
  - <span data-ttu-id="3221d-117">Количество оповещений, основанных на имеющихся политиках приложений (**Оповещения политики**)</span><span class="sxs-lookup"><span data-stu-id="3221d-117">How many are based on app policies you have in place (**Policy alerts**)</span></span>
  - <span data-ttu-id="3221d-118">10 последних оповещений</span><span class="sxs-lookup"><span data-stu-id="3221d-118">The 10 latest alerts</span></span>

  <span data-ttu-id="3221d-119">На основе этих сведений можно определить, как быстро создаются оповещения, а также относительное количество обнаруженных и основанных на политиках оповещений.</span><span class="sxs-lookup"><span data-stu-id="3221d-119">From this information, you can determine how quickly alerts are being generated and the relative number of detected and policy-based alerts.</span></span>

- <span data-ttu-id="3221d-120">Для доступа к данным и ресурсам:</span><span class="sxs-lookup"><span data-stu-id="3221d-120">For data and resources access:</span></span>

  - <span data-ttu-id="3221d-121">Общее количество данных, к которым приложения в клиенте обращались с помощью API Graph за текущий и предыдущие три календарных месяца.</span><span class="sxs-lookup"><span data-stu-id="3221d-121">Total data accessed by apps in the tenant through Graph API over the current and previous three calendar months.</span></span> <span data-ttu-id="3221d-122">(В настоящее время включает только почту и отправку файлов, а также использование скачивания)</span><span class="sxs-lookup"><span data-stu-id="3221d-122">(Currently only includes Mail and File upload and download usage)</span></span>
  - <span data-ttu-id="3221d-123">Использование данных за текущий и предыдущие три календарных месяца, разделенное по типу ресурсов.</span><span class="sxs-lookup"><span data-stu-id="3221d-123">Data usage over the current and previous three calendar months, broken down by resource type.</span></span> <span data-ttu-id="3221d-124">(В настоящее время включает только почту и отправку файлов, а также использование скачивания)</span><span class="sxs-lookup"><span data-stu-id="3221d-124">(Currently only includes Mail and File upload and download usage)</span></span>

  <span data-ttu-id="3221d-125">На основе этих сведений можно определить, существуют ли аномальные пики доступа к данным в клиенте Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3221d-125">From this information, you can determine if there are anomalous spikes in access to the data in your Microsoft 365 tenant.</span></span>
