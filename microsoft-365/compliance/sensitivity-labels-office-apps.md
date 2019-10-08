---
title: Как метки конфиденциальности действуют в приложениях Office
ms.author: greglin
author: greg-lindsay
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: С помощью меток конфиденциальности вы можете классифицировать и защищать конфиденциальное содержимое, не мешая совместной работе и производительности пользователей. Метки конфиденциальности можно использовать для применения параметров защиты, например шифрования или подложек для содержимого с метками.
ms.openlocfilehash: f702423f0b1074b5619ef1c321cc5e9f1daef1d7
ms.sourcegitcommit: 15173ab87325b7d79bab683702b35d77a355cd6b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/08/2019
ms.locfileid: "37417568"
---
# <a name="how-sensitivity-labels-work-in-office-apps"></a><span data-ttu-id="2c1a3-104">Как метки конфиденциальности действуют в приложениях Office</span><span class="sxs-lookup"><span data-stu-id="2c1a3-104">How sensitivity labels work in Office apps</span></span>

## <a name="what-prerequisites-are-there-to-use-sensitivity-labels-in-office-applications"></a><span data-ttu-id="2c1a3-105">Какие предварительные требования существуют для использования меток конфиденциальности в приложениях Office?</span><span class="sxs-lookup"><span data-stu-id="2c1a3-105">What prerequisites are there to use sensitivity labels in Office applications?</span></span>

### <a name="common-requirements"></a><span data-ttu-id="2c1a3-106">Общие требования</span><span class="sxs-lookup"><span data-stu-id="2c1a3-106">Common requirements</span></span> 

- <span data-ttu-id="2c1a3-107">Унифицированные метки конфиденциальности должны быть [настроены и опубликованы в Центре безопасности и соответствия требованиям](https://aka.ms/managemip).</span><span class="sxs-lookup"><span data-stu-id="2c1a3-107">Unified sensitivity labels must be [configured and published in the Security and Compliance Center](https://aka.ms/managemip)</span></span>
- <span data-ttu-id="2c1a3-108">Пользователи должны выполнить вход в Office с помощью рабочей учетной записи.</span><span class="sxs-lookup"><span data-stu-id="2c1a3-108">Users must be signed in to Office with their work account.</span></span>
- <span data-ttu-id="2c1a3-109">Пользователям должны быть назначены лицензии Office 365 E3 или выше.</span><span class="sxs-lookup"><span data-stu-id="2c1a3-109">Users must have an Office 365 E3 or above license assigned.</span></span>

### <a name="additional-requirements-for-office-for-windows"></a><span data-ttu-id="2c1a3-110">Дополнительные требования к Office для Windows</span><span class="sxs-lookup"><span data-stu-id="2c1a3-110">Additional requirements for Office for Windows</span></span> 

- <span data-ttu-id="2c1a3-111">Клиент Azure Information Protection не должен быть запущен в Office.</span><span class="sxs-lookup"><span data-stu-id="2c1a3-111">The Azure Information Protection client must not be running in Office.</span></span> <span data-ttu-id="2c1a3-112">См. также: [Могут ли метки конфиденциальности одновременно использоваться в клиенте Azure Information Protection в Office для Windows?](#can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows).</span><span class="sxs-lookup"><span data-stu-id="2c1a3-112">See also: [Can sensitivity labels run alongside the Azure Information Protection client in Office for Windows?](#can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows).</span></span>

### <a name="additional-requirements-for-outlook-on-all-platforms"></a><span data-ttu-id="2c1a3-113">Дополнительные требования для Outlook на всех платформах</span><span class="sxs-lookup"><span data-stu-id="2c1a3-113">Additional requirements for Outlook on all platforms</span></span> 

- <span data-ttu-id="2c1a3-114">Если при настройке меток отключена маркировка содержимого, требуется использовать Exchange Online, чтобы маркировка содержимого была добавлена при переносе.</span><span class="sxs-lookup"><span data-stu-id="2c1a3-114">In your label configuration, if you turn on content marking, you must be using Exchange Online for that content marking to be inserted in transit.</span></span>

## <a name="what-sensitivity-label-capabilities-are-supported-in-office-today"></a><span data-ttu-id="2c1a3-115">Какие возможности меток конфиденциальности в настоящее время поддерживаются в Office?</span><span class="sxs-lookup"><span data-stu-id="2c1a3-115">What sensitivity label capabilities are supported in Office today?</span></span> 

<table border="1" cellspacing="0" cellpadding="0">
<th><span data-ttu-id="2c1a3-116"><font size="-1">Возможность</span><span class="sxs-lookup"><span data-stu-id="2c1a3-116"><font size="-1">Capability</span></span><th><span data-ttu-id="2c1a3-117"><font size="-1">Windows</span><span class="sxs-lookup"><span data-stu-id="2c1a3-117"><font size="-1">Windows</span></span><th><span data-ttu-id="2c1a3-118"><font size="-1">Mac<th colspan="2"><font size="-1">iOS<th colspan="2"><font size="-1">Android<th colspan="2"><font size="-1">Интернет</span><span class="sxs-lookup"><span data-stu-id="2c1a3-118"><font size="-1">Mac<th colspan="2"><font size="-1">iOS<th colspan="2"><font size="-1">Android<th colspan="2"><font size="-1">Web</span></span></tr>
<tr><td>

<td><span data-ttu-id="2c1a3-119"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="2c1a3-119"><font size="-1"> Word</span></span><br>
<span data-ttu-id="2c1a3-120">Excel</span><span class="sxs-lookup"><span data-stu-id="2c1a3-120">Excel</span></span><br>
<span data-ttu-id="2c1a3-121">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="2c1a3-121">PowerPoint</span></span><br>
<span data-ttu-id="2c1a3-122">Outlook</span><span class="sxs-lookup"><span data-stu-id="2c1a3-122">Outlook</span></span>


<td><span data-ttu-id="2c1a3-123"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="2c1a3-123"><font size="-1"> Word</span></span><br>
<span data-ttu-id="2c1a3-124">Excel</span><span class="sxs-lookup"><span data-stu-id="2c1a3-124">Excel</span></span><br>
<span data-ttu-id="2c1a3-125">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="2c1a3-125">PowerPoint</span></span><br>
<span data-ttu-id="2c1a3-126">Outlook</span><span class="sxs-lookup"><span data-stu-id="2c1a3-126">Outlook</span></span>

<td><span data-ttu-id="2c1a3-127"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="2c1a3-127"><font size="-1"> Word</span></span><br>
<span data-ttu-id="2c1a3-128">Excel</span><span class="sxs-lookup"><span data-stu-id="2c1a3-128">Excel</span></span><br>
<span data-ttu-id="2c1a3-129">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="2c1a3-129">PowerPoint</span></span>
<td><span data-ttu-id="2c1a3-130"><font size="-1"> Outlook</span><span class="sxs-lookup"><span data-stu-id="2c1a3-130"><font size="-1"> Outlook</span></span>

<td><span data-ttu-id="2c1a3-131"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="2c1a3-131"><font size="-1"> Word</span></span><br>
<span data-ttu-id="2c1a3-132">Excel</span><span class="sxs-lookup"><span data-stu-id="2c1a3-132">Excel</span></span><br>
<span data-ttu-id="2c1a3-133">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="2c1a3-133">PowerPoint</span></span>
<td><span data-ttu-id="2c1a3-134"><font size="-1"> Outlook</span><span class="sxs-lookup"><span data-stu-id="2c1a3-134"><font size="-1"> Outlook</span></span>

<td><span data-ttu-id="2c1a3-135"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="2c1a3-135"><font size="-1"> Word</span></span><br>
<span data-ttu-id="2c1a3-136">Excel</span><span class="sxs-lookup"><span data-stu-id="2c1a3-136">Excel</span></span><br>
<span data-ttu-id="2c1a3-137">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="2c1a3-137">PowerPoint</span></span>
<td><span data-ttu-id="2c1a3-138"><font size="-1"> Outlook </b>
</span><span class="sxs-lookup"><span data-stu-id="2c1a3-138"><font size="-1"> Outlook </b>
</span></span></tr>

<tr>
<td><span data-ttu-id="2c1a3-139"><font size="-1">Применение, изменение или удаление метки вручную</span><span class="sxs-lookup"><span data-stu-id="2c1a3-139"><font size="-1">Manually apply, change, or remove label</span></span><td><span data-ttu-id="2c1a3-140"><font size="-1"><b>Да</b></span><span class="sxs-lookup"><span data-stu-id="2c1a3-140"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="2c1a3-141"><font size="-1">1910 и выше</font>

</span><span class="sxs-lookup"><span data-stu-id="2c1a3-141"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="2c1a3-142"><font size="-1"><b>Да</b></span><span class="sxs-lookup"><span data-stu-id="2c1a3-142"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="2c1a3-143"><font size="-1">16.21.0 и выше</font>

</span><span class="sxs-lookup"><span data-stu-id="2c1a3-143"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="2c1a3-144"><font size="-1"><b>Да</b></span><span class="sxs-lookup"><span data-stu-id="2c1a3-144"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="2c1a3-145"><font size="-1">2.21 и выше</font>
</span><span class="sxs-lookup"><span data-stu-id="2c1a3-145"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="2c1a3-146"><font size="-1">Ожидается в ближайшее время<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2c1a3-146"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2c1a3-147"><font size="-1"><b>Да</b></span><span class="sxs-lookup"><span data-stu-id="2c1a3-147"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="2c1a3-148"><font size="-1">16.0.11231 и выше</font>
</span><span class="sxs-lookup"><span data-stu-id="2c1a3-148"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="2c1a3-149"><font size="-1">Ожидается в ближайшее время<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2c1a3-149"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2c1a3-150"><font size="-1">Ожидается в ближайшее время<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="2c1a3-150"><font size="-1">Coming soon<sup>3</sup></span></span><td><span data-ttu-id="2c1a3-151"><font size="-1">Ожидается в ближайшее время<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="2c1a3-151"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr>
<td><span data-ttu-id="2c1a3-152"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Применение стандартной метки</a>
</span><span class="sxs-lookup"><span data-stu-id="2c1a3-152"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Apply a default label</a>
</span></span><td><span data-ttu-id="2c1a3-153"><font size="-1"><b>Да</b></span><span class="sxs-lookup"><span data-stu-id="2c1a3-153"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="2c1a3-154"><font size="-1">1910 и выше</font>

</span><span class="sxs-lookup"><span data-stu-id="2c1a3-154"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="2c1a3-155"><font size="-1"><b>Да</b></span><span class="sxs-lookup"><span data-stu-id="2c1a3-155"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="2c1a3-156"><font size="-1">16.21.0 и выше</font>

</span><span class="sxs-lookup"><span data-stu-id="2c1a3-156"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="2c1a3-157"><font size="-1"><b>Да</b></span><span class="sxs-lookup"><span data-stu-id="2c1a3-157"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="2c1a3-158"><font size="-1">2.21 и выше</font>
</span><span class="sxs-lookup"><span data-stu-id="2c1a3-158"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="2c1a3-159"><font size="-1">Ожидается в ближайшее время<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2c1a3-159"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2c1a3-160"><font size="-1"><b>Да</b></span><span class="sxs-lookup"><span data-stu-id="2c1a3-160"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="2c1a3-161"><font size="-1">16.0.11231 и выше</font>
</span><span class="sxs-lookup"><span data-stu-id="2c1a3-161"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="2c1a3-162"><font size="-1">Ожидается в ближайшее время<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2c1a3-162"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2c1a3-163"><font size="-1">Ожидается в ближайшее время<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2c1a3-163"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2c1a3-164"><font size="-1">Ожидается в ближайшее время<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="2c1a3-164"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="2c1a3-165"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Требование обоснования для изменения метки</a><sup>1</sup>
</span><span class="sxs-lookup"><span data-stu-id="2c1a3-165"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Require a justification for changing a label</a><sup>1</sup>
</span></span><td><span data-ttu-id="2c1a3-166"><font size="-1"><b>Да</b></span><span class="sxs-lookup"><span data-stu-id="2c1a3-166"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="2c1a3-167"><font size="-1">1910 и выше</font>

</span><span class="sxs-lookup"><span data-stu-id="2c1a3-167"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="2c1a3-168"><font size="-1"><b>Да</b></span><span class="sxs-lookup"><span data-stu-id="2c1a3-168"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="2c1a3-169"><font size="-1">16.21.0 и выше</font>

</span><span class="sxs-lookup"><span data-stu-id="2c1a3-169"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="2c1a3-170"><font size="-1"><b>Да</b></span><span class="sxs-lookup"><span data-stu-id="2c1a3-170"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="2c1a3-171"><font size="-1">2.21 и выше</font>
</span><span class="sxs-lookup"><span data-stu-id="2c1a3-171"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="2c1a3-172"><font size="-1">Ожидается в ближайшее время<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2c1a3-172"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2c1a3-173"><font size="-1"><b>Да</b></span><span class="sxs-lookup"><span data-stu-id="2c1a3-173"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="2c1a3-174"><font size="-1">16.0.11231 и выше</font>
</span><span class="sxs-lookup"><span data-stu-id="2c1a3-174"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="2c1a3-175"><font size="-1">Ожидается в ближайшее время<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2c1a3-175"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2c1a3-176"><font size="-1">Ожидается в ближайшее время<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2c1a3-176"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2c1a3-177"><font size="-1">Ожидается в ближайшее время<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="2c1a3-177"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="2c1a3-178"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Предоставление ссылки на страницу настраиваемой справки</a>
</span><span class="sxs-lookup"><span data-stu-id="2c1a3-178"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Provide help link to a custom help page</a>
</span></span><td><span data-ttu-id="2c1a3-179"><font size="-1"><b>Да</b></span><span class="sxs-lookup"><span data-stu-id="2c1a3-179"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="2c1a3-180"><font size="-1">1910 и выше</font>

</span><span class="sxs-lookup"><span data-stu-id="2c1a3-180"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="2c1a3-181"><font size="-1"><b>Да</b></span><span class="sxs-lookup"><span data-stu-id="2c1a3-181"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="2c1a3-182"><font size="-1">16.21.0 и выше</font>

</span><span class="sxs-lookup"><span data-stu-id="2c1a3-182"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="2c1a3-183"><font size="-1"><b>Да</b></span><span class="sxs-lookup"><span data-stu-id="2c1a3-183"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="2c1a3-184"><font size="-1">2.21 и выше</font>
</span><span class="sxs-lookup"><span data-stu-id="2c1a3-184"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="2c1a3-185"><font size="-1">Ожидается в ближайшее время<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2c1a3-185"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2c1a3-186"><font size="-1"><b>Да</b></span><span class="sxs-lookup"><span data-stu-id="2c1a3-186"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="2c1a3-187"><font size="-1">16.0.11231 и выше</font>
</span><span class="sxs-lookup"><span data-stu-id="2c1a3-187"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="2c1a3-188"><font size="-1">Ожидается в ближайшее время<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2c1a3-188"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2c1a3-189"><font size="-1">Ожидается в ближайшее время<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2c1a3-189"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2c1a3-190"><font size="-1">Ожидается в ближайшее время<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="2c1a3-190"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="2c1a3-191"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-sensitivity-labels-can-do">Маркировка содержимого</a>
</span><span class="sxs-lookup"><span data-stu-id="2c1a3-191"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-sensitivity-labels-can-do">Mark the content</a>
</span></span><td><span data-ttu-id="2c1a3-192"><font size="-1"><b>Да</b></span><span class="sxs-lookup"><span data-stu-id="2c1a3-192"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="2c1a3-193"><font size="-1">1910 и выше</font>

</span><span class="sxs-lookup"><span data-stu-id="2c1a3-193"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="2c1a3-194"><font size="-1"><b>Да</b></span><span class="sxs-lookup"><span data-stu-id="2c1a3-194"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="2c1a3-195"><font size="-1">16.21.0 и выше</font>

</span><span class="sxs-lookup"><span data-stu-id="2c1a3-195"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="2c1a3-196"><font size="-1"><b>Да</b></span><span class="sxs-lookup"><span data-stu-id="2c1a3-196"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="2c1a3-197"><font size="-1">2.21 и выше</font>
</span><span class="sxs-lookup"><span data-stu-id="2c1a3-197"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="2c1a3-198"><font size="-1">Ожидается в ближайшее время<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2c1a3-198"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2c1a3-199"><font size="-1"><b>Да</b></span><span class="sxs-lookup"><span data-stu-id="2c1a3-199"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="2c1a3-200"><font size="-1">16.0.11231 и выше</font
</span><span class="sxs-lookup"><span data-stu-id="2c1a3-200"><font size="-1">16.0.11231+</font
</span></span>><td><span data-ttu-id="2c1a3-201"><font size="-1">Ожидается в ближайшее время<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2c1a3-201"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2c1a3-202"><font size="-1">Ожидается в ближайшее время<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2c1a3-202"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2c1a3-203"><font size="-1">Ожидается в ближайшее время<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="2c1a3-203"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="2c1a3-204"><font size="-1">
  <a href="https://docs.microsoft.com/en-us/microsoft-365/compliance/encryption-sensitivity-labels#assign-permissions-now">Назначение предопределенных разрешений</a>
</span><span class="sxs-lookup"><span data-stu-id="2c1a3-204"><font size="-1">Assign pre-defined permissions</span></span><td><span data-ttu-id="2c1a3-205"><font size="-1"><b>Да</b></span><span class="sxs-lookup"><span data-stu-id="2c1a3-205"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="2c1a3-206"><font size="-1">1910 и выше</font>

</span><span class="sxs-lookup"><span data-stu-id="2c1a3-206"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="2c1a3-207"><font size="-1"><b>Да</b></span><span class="sxs-lookup"><span data-stu-id="2c1a3-207"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="2c1a3-208"><font size="-1">16.21.0 и выше</font>

</span><span class="sxs-lookup"><span data-stu-id="2c1a3-208"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="2c1a3-209"><font size="-1"><b>Да</b></span><span class="sxs-lookup"><span data-stu-id="2c1a3-209"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="2c1a3-210"><font size="-1">2.21 и выше</font>
</span><span class="sxs-lookup"><span data-stu-id="2c1a3-210"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="2c1a3-211"><font size="-1">Ожидается в ближайшее время<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2c1a3-211"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2c1a3-212"><font size="-1"><b>Да</b></span><span class="sxs-lookup"><span data-stu-id="2c1a3-212"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="2c1a3-213"><font size="-1">16.0.11231 и выше</font>
</span><span class="sxs-lookup"><span data-stu-id="2c1a3-213"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="2c1a3-214"><font size="-1">Ожидается в ближайшее время<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2c1a3-214"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2c1a3-215"><font size="-1">Ожидается в ближайшее время<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2c1a3-215"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2c1a3-216"><font size="-1">Ожидается в ближайшее время<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="2c1a3-216"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="2c1a3-217"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels#let-users-assign-permissions">Предоставление пользователям возможности назначать разрешения</a>
</span><span class="sxs-lookup"><span data-stu-id="2c1a3-217"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels#let-users-assign-permissions">Let users assign permissions</a>
</span></span><td><span data-ttu-id="2c1a3-218"><font size="-1"><b>Да</b><sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="2c1a3-218"><font size="-1"><b>Yes</b><sup>2</sup></span></span><br><span data-ttu-id="2c1a3-219"><font size="-1">1910 и выше</font>

</span><span class="sxs-lookup"><span data-stu-id="2c1a3-219"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="2c1a3-220"><font size="-1"><b>Да</b><sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="2c1a3-220"><font size="-1"><b>Yes</b><sup>2</sup></span></span><br><span data-ttu-id="2c1a3-221"><font size="-1">16.21.0 и выше</font></span><span class="sxs-lookup"><span data-stu-id="2c1a3-221"><font size="-1">16.21.0+</font></span></span>

<td><span data-ttu-id="2c1a3-222"><font size="-1">Подлежит уточнению</span><span class="sxs-lookup"><span data-stu-id="2c1a3-222"><font size="-1">TBD</span></span>
<td><span data-ttu-id="2c1a3-223"><font size="-1">Ожидается в ближайшее время<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2c1a3-223"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2c1a3-224"><font size="-1">Подлежит уточнению</span><span class="sxs-lookup"><span data-stu-id="2c1a3-224"><font size="-1">TBD</span></span><td
><span data-ttu-id="2c1a3-225"><font size="-1">Ожидается в ближайшее время<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2c1a3-225"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2c1a3-226"><font size="-1">Подлежит уточнению</span><span class="sxs-lookup"><span data-stu-id="2c1a3-226"><font size="-1">TBD</span></span>
<td><span data-ttu-id="2c1a3-227"><font size="-1">Ожидается в ближайшее время<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="2c1a3-227"><font size="-1">Coming soon<sup>3</sup></span></span>

<tr><td><span data-ttu-id="2c1a3-228"><font size="-1">Отправка данных <a href="https://docs.microsoft.com/microsoft-365/compliance/label-analytics">аналитики меток</a> для администраторов</span><span class="sxs-lookup"><span data-stu-id="2c1a3-228"><font size="-1">Send <a href="https://docs.microsoft.com/microsoft-365/compliance/label-analytics">label analytics</a> data for administrators</span></span>
<td><span data-ttu-id="2c1a3-229"><font size="-1">Подлежит уточнению</span><span class="sxs-lookup"><span data-stu-id="2c1a3-229"><font size="-1">TBD</span></span>

<td><span data-ttu-id="2c1a3-230"><font size="-1">Подлежит уточнению</span><span class="sxs-lookup"><span data-stu-id="2c1a3-230"><font size="-1">TBD</span></span>

<td><span data-ttu-id="2c1a3-231"><font size="-1">Подлежит уточнению</span><span class="sxs-lookup"><span data-stu-id="2c1a3-231"><font size="-1">TBD</span></span>
<td><span data-ttu-id="2c1a3-232"><font size="-1">Подлежит уточнению</span><span class="sxs-lookup"><span data-stu-id="2c1a3-232"><font size="-1">TBD</span></span>
<td><span data-ttu-id="2c1a3-233"><font size="-1">Подлежит уточнению</span><span class="sxs-lookup"><span data-stu-id="2c1a3-233"><font size="-1">TBD</span></span>
<td><span data-ttu-id="2c1a3-234"><font size="-1">Подлежит уточнению</span><span class="sxs-lookup"><span data-stu-id="2c1a3-234"><font size="-1">TBD</span></span>
<td><span data-ttu-id="2c1a3-235"><font size="-1">Подлежит уточнению</span><span class="sxs-lookup"><span data-stu-id="2c1a3-235"><font size="-1">TBD</span></span>
<td><span data-ttu-id="2c1a3-236"><font size="-1">Подлежит уточнению</span><span class="sxs-lookup"><span data-stu-id="2c1a3-236"><font size="-1">TBD</span></span>

<tr><td><span data-ttu-id="2c1a3-237"><font size="-1">
  <a href="https://docs.microsoft.com/en-us/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Требование применения пользователями метки к электронной почте и документам</a>
</span><span class="sxs-lookup"><span data-stu-id="2c1a3-237"><font size="-1">Require users to apply a label to their email and documents</span></span><td><span data-ttu-id="2c1a3-238"><font size="-1">Подлежит уточнению</span><span class="sxs-lookup"><span data-stu-id="2c1a3-238"><font size="-1">TBD</span></span>

<td><span data-ttu-id="2c1a3-239"><font size="-1">Подлежит уточнению</span><span class="sxs-lookup"><span data-stu-id="2c1a3-239"><font size="-1">TBD</span></span>

<td><span data-ttu-id="2c1a3-240"><font size="-1">Подлежит уточнению</span><span class="sxs-lookup"><span data-stu-id="2c1a3-240"><font size="-1">TBD</span></span>
<td><span data-ttu-id="2c1a3-241"><font size="-1">Подлежит уточнению</span><span class="sxs-lookup"><span data-stu-id="2c1a3-241"><font size="-1">TBD</span></span>
<td><span data-ttu-id="2c1a3-242"><font size="-1">Подлежит уточнению</span><span class="sxs-lookup"><span data-stu-id="2c1a3-242"><font size="-1">TBD</span></span>
<td><span data-ttu-id="2c1a3-243"><font size="-1">Подлежит уточнению</span><span class="sxs-lookup"><span data-stu-id="2c1a3-243"><font size="-1">TBD</span></span>
<td><span data-ttu-id="2c1a3-244"><font size="-1">Подлежит уточнению</span><span class="sxs-lookup"><span data-stu-id="2c1a3-244"><font size="-1">TBD</span></span>
<td><span data-ttu-id="2c1a3-245"><font size="-1">Подлежит уточнению</span><span class="sxs-lookup"><span data-stu-id="2c1a3-245"><font size="-1">TBD</span></span>

<tr><td><span data-ttu-id="2c1a3-246"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically">Автоматическое применение метки конфиденциальности к содержимому</a>
</span><span class="sxs-lookup"><span data-stu-id="2c1a3-246"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically">Apply a sensitivity label to content automatically</a>
</span></span><td><span data-ttu-id="2c1a3-247"><font size="-1">Подлежит уточнению</span><span class="sxs-lookup"><span data-stu-id="2c1a3-247"><font size="-1">TBD</span></span>

<td><span data-ttu-id="2c1a3-248"><font size="-1">Подлежит уточнению</span><span class="sxs-lookup"><span data-stu-id="2c1a3-248"><font size="-1">TBD</span></span>

<td><span data-ttu-id="2c1a3-249"><font size="-1">Подлежит уточнению</span><span class="sxs-lookup"><span data-stu-id="2c1a3-249"><font size="-1">TBD</span></span>
<td><span data-ttu-id="2c1a3-250"><font size="-1">Подлежит уточнению</span><span class="sxs-lookup"><span data-stu-id="2c1a3-250"><font size="-1">TBD</span></span>
<td><span data-ttu-id="2c1a3-251"><font size="-1">Подлежит уточнению</span><span class="sxs-lookup"><span data-stu-id="2c1a3-251"><font size="-1">TBD</span></span>
<td><span data-ttu-id="2c1a3-252"><font size="-1">Подлежит уточнению</span><span class="sxs-lookup"><span data-stu-id="2c1a3-252"><font size="-1">TBD</span></span>
<td><span data-ttu-id="2c1a3-253"><font size="-1">Подлежит уточнению</span><span class="sxs-lookup"><span data-stu-id="2c1a3-253"><font size="-1">TBD</span></span>
<td><span data-ttu-id="2c1a3-254"><font size="-1">Подлежит уточнению</span><span class="sxs-lookup"><span data-stu-id="2c1a3-254"><font size="-1">TBD</span></span>
</table>

<br><span data-ttu-id="2c1a3-255"><sup>1</sup>Если настроено, пользователям потребуется обосновать понижение уровня метки.</span><span class="sxs-lookup"><span data-stu-id="2c1a3-255"><sup>1</sup>If configured, users are prompted to justify label downgrades.</span></span> <span data-ttu-id="2c1a3-256">Однако данные обоснования пока недоступны администраторам.</span><span class="sxs-lookup"><span data-stu-id="2c1a3-256">However, the justification data is not made available for administrators yet.</span></span> <span data-ttu-id="2c1a3-257">Они станут доступны, когда будет поддерживаться функция "Отправка данных аналитики меток для администраторов".</span><span class="sxs-lookup"><span data-stu-id="2c1a3-257">It will become available when the “send label analytics data for administrators” capability is supported.</span></span>
<br><span data-ttu-id="2c1a3-258"><sup>2</sup>Возможность назначения разрешений пользователями в настоящее время доступна только в Outlook для Windows и Mac.</span><span class="sxs-lookup"><span data-stu-id="2c1a3-258"><sup>2</sup>Let users assign permissions is currently only available in Outlook for Windows and Mac.</span></span> <span data-ttu-id="2c1a3-259">Доступность для Word, Excel и PowerPoint подлежит уточнению.</span><span class="sxs-lookup"><span data-stu-id="2c1a3-259">Availability for Word, Excel, and PowerPoint is TBD.</span></span>
<br><span data-ttu-id="2c1a3-260"><sup>3</sup>Ожидается в 4 квартале 2019 г.</span><span class="sxs-lookup"><span data-stu-id="2c1a3-260"><sup>3</sup>Expected Q4 of calendar year 2019.</span></span>

## <a name="when-do-content-marks-or-encryption-get-applied-after-content-is-given-a-sensitivity-label"></a><span data-ttu-id="2c1a3-261">Когда к содержимому применяется маркировка или шифрование после присвоения метки конфиденциальности?</span><span class="sxs-lookup"><span data-stu-id="2c1a3-261">When do content marks or encryption get applied after content is given a sensitivity label?</span></span>

| <span data-ttu-id="2c1a3-262">Приложение</span><span class="sxs-lookup"><span data-stu-id="2c1a3-262">Application</span></span> | <span data-ttu-id="2c1a3-263">Маркировка содержимого</span><span class="sxs-lookup"><span data-stu-id="2c1a3-263">Content marking</span></span> | <span data-ttu-id="2c1a3-264">Шифрование</span><span class="sxs-lookup"><span data-stu-id="2c1a3-264">Encryption</span></span>
| --- | --- | --- |
| <span data-ttu-id="2c1a3-265">Word, Excel, PowerPoint на всех платформах</span><span class="sxs-lookup"><span data-stu-id="2c1a3-265">Word, Excel, PowerPoint on all platforms</span></span> | <span data-ttu-id="2c1a3-266">Сразу</span><span class="sxs-lookup"><span data-stu-id="2c1a3-266">Immediately</span></span> | <span data-ttu-id="2c1a3-267">Сразу</span><span class="sxs-lookup"><span data-stu-id="2c1a3-267">Immediately</span></span> |
| <span data-ttu-id="2c1a3-268">Outlook для ПК и Mac</span><span class="sxs-lookup"><span data-stu-id="2c1a3-268">Outlook for PC and Mac</span></span> | <span data-ttu-id="2c1a3-269">После отправки сообщения электронной почты службой Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2c1a3-269">After the email is sent by Exchange Online</span></span> | <span data-ttu-id="2c1a3-270">Сразу</span><span class="sxs-lookup"><span data-stu-id="2c1a3-270">Immediately</span></span> |
| <span data-ttu-id="2c1a3-271">Outlook в Интернете, для iOS и Android</span><span class="sxs-lookup"><span data-stu-id="2c1a3-271">Outlook on the web, iOS, and Android</span></span> | <span data-ttu-id="2c1a3-272">После отправки сообщения электронной почты службой Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2c1a3-272">After the email is sent by Exchange Online</span></span> | <span data-ttu-id="2c1a3-273">После отправки сообщения электронной почты службой Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2c1a3-273">After the email is sent by Exchange Online</span></span> |

## <a name="can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows"></a><span data-ttu-id="2c1a3-274">Могут ли метки конфиденциальности одновременно использоваться в клиенте Azure Information Protection в Office для Windows?</span><span class="sxs-lookup"><span data-stu-id="2c1a3-274">Can sensitivity labels run alongside the Azure Information Protection client in Office for Windows?</span></span>

<span data-ttu-id="2c1a3-275">Нет.</span><span class="sxs-lookup"><span data-stu-id="2c1a3-275">No.</span></span> <span data-ttu-id="2c1a3-276">Метки конфиденциальности отключены, если клиент Azure Information Protection загружен в Office для Windows.</span><span class="sxs-lookup"><span data-stu-id="2c1a3-276">Sensitivity labels are turned off if the Azure Information Protection client is loaded in Office for Windows.</span></span>

<span data-ttu-id="2c1a3-277">Если у вас установлен клиент Azure Information Protection, но вы хотите вместо него использовать метки конфиденциальности, можно выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="2c1a3-277">If you have the Azure Information Protection client installed, but you want to use sensitivity labels instead, you can:</span></span>

1. <span data-ttu-id="2c1a3-278">Настройте параметр групповой политики  **Использование функции "Конфиденциальность" в Office для применения и просмотра меток конфиденциальности**, находящийся в разделе **Конфигурация пользователя/Административные шаблоны/Microsoft Office 2016/Параметры безопасности**.</span><span class="sxs-lookup"><span data-stu-id="2c1a3-278">Configure the **Use the Sensitivity feature in Office to apply and view sensitivity labels** Group Policy setting, which can be found under **User Configuration/Administrative Templates/Microsoft Office 2016/Security Settings**.</span></span>

  ><span data-ttu-id="2c1a3-279">Примечание. Этот параметр можно развернуть с помощью традиционных механизмов развертывания групповой политики или с помощью [службы политики облака Office](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service).</span><span class="sxs-lookup"><span data-stu-id="2c1a3-279">Note: this setting can be deployed via traditional group policy deployment mechanisms, or by the [Office cloud policy service](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service).</span></span> 
 
  <span data-ttu-id="2c1a3-280">Кроме того, вы можете удалить или  [отключить](https://support.office.com/article/view-manage-and-install-add-ins-in-office-programs-16278816-1948-4028-91e5-76dca5380f8d) клиент Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="2c1a3-280">Alternatively, you can uninstall or [disable](https://support.office.com/article/view-manage-and-install-add-ins-in-office-programs-16278816-1948-4028-91e5-76dca5380f8d) the Azure Information Protection client.</span></span> 

2. <span data-ttu-id="2c1a3-281">Перезапустите все приложения Office.</span><span class="sxs-lookup"><span data-stu-id="2c1a3-281">Restart all Office applications.</span></span>

## <a name="will-sensitivity-labels-be-supported-in-non-subscription-versions-of-office-like-office-2016-or-office-2019"></a><span data-ttu-id="2c1a3-282">Поддерживаются ли метки конфиденциальности в версиях Office без подписки, таких как Office 2016 и Office 2019?</span><span class="sxs-lookup"><span data-stu-id="2c1a3-282">Will sensitivity labels be supported in non-subscription versions of Office like Office 2016 or Office 2019?</span></span>

<span data-ttu-id="2c1a3-283">Нет.</span><span class="sxs-lookup"><span data-stu-id="2c1a3-283">No.</span></span> <span data-ttu-id="2c1a3-284">Метки конфиденциальности поддерживаются только в версии Office 365 с подпиской и не поддерживаются в версиях без подписки.</span><span class="sxs-lookup"><span data-stu-id="2c1a3-284">Sensitivity labels will only be supported in the Office 365 subscription and will not be supported in any non-subscription version.</span></span> <span data-ttu-id="2c1a3-285">Однако в версиях Office без подписки можно использовать клиент унифицированных меток Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="2c1a3-285">However, the Azure Information Protection unified labeling client may be used in non-subscription versions of Office.</span></span> 

## <a name="i-previously-deployed-protection-templates-before-setting-up-sensitivity-labels-where-did-they-go"></a><span data-ttu-id="2c1a3-286">Перед настройкой меток конфиденциальности я развернул шаблоны защиты.</span><span class="sxs-lookup"><span data-stu-id="2c1a3-286">I previously deployed protection templates before setting up sensitivity labels.</span></span> <span data-ttu-id="2c1a3-287">Куда они делись?</span><span class="sxs-lookup"><span data-stu-id="2c1a3-287">Where did they go?</span></span>

<span data-ttu-id="2c1a3-288">Определяемые администратором [шаблоны защиты](https://docs.microsoft.com/azure/information-protection/configure-policy-templates) скрываются из пользовательского интерфейса Office, когда включаются метки конфиденциальности, так как они являются избыточными при применении меток конфиденциальности, в которых включено шифрование.</span><span class="sxs-lookup"><span data-stu-id="2c1a3-288">Administrator-defined [protection templates](https://docs.microsoft.com/azure/information-protection/configure-policy-templates) are hidden from the Office user experience when sensitivity labels are enabled because they are redundant with sensitivity labels that have encryption enabled.</span></span> 

## <a name="can-a-file-or-email-have-more-than-one-classification"></a><span data-ttu-id="2c1a3-289">Может ли файл или сообщение электронной почты иметь несколько классификаций?</span><span class="sxs-lookup"><span data-stu-id="2c1a3-289">Can a file or email have more than one classification?</span></span>

<span data-ttu-id="2c1a3-290">Нет.</span><span class="sxs-lookup"><span data-stu-id="2c1a3-290">No.</span></span> <span data-ttu-id="2c1a3-291">Пользователи могут одновременно выбрать только одну метку для каждого документа или сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="2c1a3-291">Users can select just one label at a time for each document or email, which often results in just one classification.</span></span>

## <a name="when-an-email-is-labeled-do-any-attachments-automatically-get-the-same-labeling"></a><span data-ttu-id="2c1a3-292">Когда метка присваивается сообщению электронной почты, получают ли все вложения такую же метку автоматически?</span><span class="sxs-lookup"><span data-stu-id="2c1a3-292">When an email is labeled, do any attachments automatically get the same labeling?</span></span>

<span data-ttu-id="2c1a3-293">Нет.</span><span class="sxs-lookup"><span data-stu-id="2c1a3-293">No.</span></span> <span data-ttu-id="2c1a3-294">Если метка присваивается сообщению электронной почты с вложениями, эти вложения не наследуют такую же метку.</span><span class="sxs-lookup"><span data-stu-id="2c1a3-294">When you label an email message that has attachments, those attachments do not inherit the same label.</span></span> <span data-ttu-id="2c1a3-295">Вложения остаются без метки или сохраняют отдельно присвоенную метку.</span><span class="sxs-lookup"><span data-stu-id="2c1a3-295">The attachments remain either without a label or retain a separately applied label.</span></span> <span data-ttu-id="2c1a3-296">Однако если метка для сообщения электронной почты обеспечивает применение защиты, эта защита применяется к вложениям Office.</span><span class="sxs-lookup"><span data-stu-id="2c1a3-296">However, if the label for the email applies protection, that protection is applied to Office attachments.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2c1a3-297">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="2c1a3-297">Additional resources</span></span>

[<span data-ttu-id="2c1a3-298">Вопросы и ответы о классификации и присвоении меток в Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="2c1a3-298">Frequently asked questions about classification and labeling in Azure Information Protection</span></span>](https://docs.microsoft.com/azure/information-protection/faqs-infoprotect)<br>
[<span data-ttu-id="2c1a3-299">Применение меток конфиденциальности к документам и сообщениям электронной почты в Office</span><span class="sxs-lookup"><span data-stu-id="2c1a3-299">Apply sensitivity labels to your documents and email within Office</span></span>](https://support.office.com/article/apply-sensitivity-labels-to-your-documents-and-email-within-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
