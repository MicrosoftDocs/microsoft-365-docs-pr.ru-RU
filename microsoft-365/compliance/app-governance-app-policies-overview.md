---
title: Сведения о политиках приложения
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
description: Сведения о политиках приложения.
ms.openlocfilehash: 6d4ff23ca0e09f5e410d32d6ced144afc0c4bb15
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420359"
---
# <a name="learn-about-app-policies"></a><span data-ttu-id="789d7-103">Сведения о политиках приложения</span><span class="sxs-lookup"><span data-stu-id="789d7-103">Learn about app policies</span></span>

><span data-ttu-id="789d7-104">*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="789d7-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="789d7-105">Система управления приложениями Майкрософт обнаруживает аномальное поведение приложений в клиенте Microsoft 365 и создает оповещения, которые можно просмотреть, исследовать и устранить.</span><span class="sxs-lookup"><span data-stu-id="789d7-105">Microsoft app governance detects anomalous app behavior in your Microsoft 365 tenant and generates alerts that you can see, investigate, and resolve.</span></span> <span data-ttu-id="789d7-106">Помимо этой встроенной возможности обнаружения можно использовать набор стандартных шаблонов для создания собственных политик приложения, генерирующих другие оповещения.</span><span class="sxs-lookup"><span data-stu-id="789d7-106">Beyond this built-in detection capability, you can use a set of default templates to create your own app policies that generate other alerts.</span></span>

<span data-ttu-id="789d7-107">Эти политики для шаблонов и поведения приложений и пользователей могут защитить ваших пользователей от использования несоответствующих требованиям или вредоносных приложений и ограничить доступ подозрительных приложений к данным вашего клиента.</span><span class="sxs-lookup"><span data-stu-id="789d7-107">These policies for app and user patterns and behaviors can protect your users from using non-compliant or malicious apps and limit the access of risky apps to your tenant data.</span></span>

<span data-ttu-id="789d7-108">Вот краткий обзор необходимых ролей администратора для управления политикой приложения.</span><span class="sxs-lookup"><span data-stu-id="789d7-108">Here's a quick review of required administrator roles for app policy management.</span></span>

| <span data-ttu-id="789d7-109">Роль</span><span class="sxs-lookup"><span data-stu-id="789d7-109">Role</span></span> | <span data-ttu-id="789d7-110">Политики чтения</span><span class="sxs-lookup"><span data-stu-id="789d7-110">Read policies</span></span> | <span data-ttu-id="789d7-111">Создание, обновление и удаление политик</span><span class="sxs-lookup"><span data-stu-id="789d7-111">Create, update, or delete policies</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="789d7-112">Администратор соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="789d7-112">Compliance Administrator</span></span> | ![Флажок](..\media\checkmark.png) | ![Флажок](..\media\checkmark.png) |
| <span data-ttu-id="789d7-115">Средство чтения соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="789d7-115">Compliance Reader</span></span> | ![Флажок](..\media\checkmark.png) |  |
| <span data-ttu-id="789d7-117">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="789d7-117">Global Administrator</span></span> | ![Флажок](..\media\checkmark.png) | ![Флажок](..\media\checkmark.png) |
| <span data-ttu-id="789d7-120">Глобальный читатель</span><span class="sxs-lookup"><span data-stu-id="789d7-120">Global Reader</span></span>  | ![Флажок](..\media\checkmark.png) |  |
| <span data-ttu-id="789d7-122">Администратор безопасности</span><span class="sxs-lookup"><span data-stu-id="789d7-122">Security Administrator</span></span> | ![Флажок](..\media\checkmark.png) | ![Флажок](..\media\checkmark.png) |
| <span data-ttu-id="789d7-125">Читатель сведений о безопасности</span><span class="sxs-lookup"><span data-stu-id="789d7-125">Security Reader</span></span>  | ![Флажок](..\media\checkmark.png) |  |
| <span data-ttu-id="789d7-127">Оператор безопасности</span><span class="sxs-lookup"><span data-stu-id="789d7-127">Security Operator</span></span> | ![Флажок](..\media\checkmark.png) | ![Флажок](..\media\checkmark.png) |
||||

<!--
How app policies are the method by which MAPG detects app anomolies resulting in detection (alerts) and remediation (manual or automatic) 


CFA #2 Scenario 1: As an admin, I can quickly set up policies to govern M365 apps in my tenant using MAPG out-of-the-box templates
CFA #2 Scenario 2: As an admin, I can create customized policies to govern M365 apps in my tenant to meet my organizations requirements.
CFA #2 Scenario 3: As an admin or policy reviewer, I can view all policies created in my environment and quickly see which policies have associated alerts. 
CFA #2 Scenario 4: As an admin, I can adjust policies efficiently to meet changing needs.

App policy templates

- Basic info
- Policy settings and conditions
- Actions
- Status

--> 

## <a name="next-step"></a><span data-ttu-id="789d7-130">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="789d7-130">Next step</span></span>

[<span data-ttu-id="789d7-131">Начало работы с политиками приложения.</span><span class="sxs-lookup"><span data-stu-id="789d7-131">Get started with app policies.</span></span>](app-governance-app-policies-get-started.md)
