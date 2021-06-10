---
title: Локализация пользовательского интерфейса
description: Локализация устройств для пользователей
keywords: Компьютеры, управляемые Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 354f61284bbd95c1c7ca4cd50459a1644a89d090
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023265"
---
# <a name="localize-the-user-experience"></a><span data-ttu-id="19f0b-104">Локализация пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="19f0b-104">Localize the user experience</span></span>

<span data-ttu-id="19f0b-105">Пользователи компьютеры, управляемые Майкрософт устройств могут выбрать выбранный язык либо во время процесса установки ("вне полей"), либо после этого.</span><span class="sxs-lookup"><span data-stu-id="19f0b-105">Users of Microsoft Managed Desktop devices can select the language of their choice either during the setup process (the "out of box experience") or afterwards.</span></span>

## <a name="during-setup-the-out-of-box-experience"></a><span data-ttu-id="19f0b-106">Во время установки ("вне окна")</span><span class="sxs-lookup"><span data-stu-id="19f0b-106">During setup (the "out of box experience")</span></span>

<span data-ttu-id="19f0b-107">В процессе завершения настройки пользователи могут выбрать выбранный язык.</span><span class="sxs-lookup"><span data-stu-id="19f0b-107">During the process of completing setup, users can select the language of their choice.</span></span> <span data-ttu-id="19f0b-108">Этот выбор влияет на эти атрибуты:</span><span class="sxs-lookup"><span data-stu-id="19f0b-108">This selection affects these attributes:</span></span>

- <span data-ttu-id="19f0b-109">Windows 10 языковых функций:</span><span class="sxs-lookup"><span data-stu-id="19f0b-109">Windows 10 language features:</span></span>
    - <span data-ttu-id="19f0b-110">Отображение языка</span><span class="sxs-lookup"><span data-stu-id="19f0b-110">Display language</span></span>
    - <span data-ttu-id="19f0b-111">Язык клавиатуры</span><span class="sxs-lookup"><span data-stu-id="19f0b-111">Keyboard language</span></span>
    - <span data-ttu-id="19f0b-112">Языковые функции по запросу</span><span class="sxs-lookup"><span data-stu-id="19f0b-112">Language-related Features on Demand</span></span>

- <span data-ttu-id="19f0b-113">Приложения Microsoft 365 для Enterprise языковых функций:</span><span class="sxs-lookup"><span data-stu-id="19f0b-113">Microsoft 365 Apps for Enterprise language features:</span></span>
    - <span data-ttu-id="19f0b-114">Отображение языка</span><span class="sxs-lookup"><span data-stu-id="19f0b-114">Display language</span></span>
    - <span data-ttu-id="19f0b-115">Средства проверки и авторинга</span><span class="sxs-lookup"><span data-stu-id="19f0b-115">Proofing and authoring tools</span></span>

> [!NOTE]
> <span data-ttu-id="19f0b-116">Пользователи могут получить языковые функции по запросу, выбрав язык во время процесса настройки.</span><span class="sxs-lookup"><span data-stu-id="19f0b-116">Users can only get language-related Features On Demand by selecting the language during the setup process.</span></span>

## <a name="after-completing-setup"></a><span data-ttu-id="19f0b-117">После завершения установки</span><span class="sxs-lookup"><span data-stu-id="19f0b-117">After completing setup</span></span>

<span data-ttu-id="19f0b-118">Пользователи могут выбрать выбранный язык для Windows 10 и Приложения Microsoft 365 для Enterprise в любое время после завершения процесса настройки.</span><span class="sxs-lookup"><span data-stu-id="19f0b-118">Users can select the language of their choice for Windows 10 and Microsoft 365 Apps for Enterprise anytime after the setup process is complete.</span></span> <span data-ttu-id="19f0b-119">Это означает следующее:</span><span class="sxs-lookup"><span data-stu-id="19f0b-119">Specifically:</span></span>

- <span data-ttu-id="19f0b-120">Windows 10 языковых функций:</span><span class="sxs-lookup"><span data-stu-id="19f0b-120">Windows 10 language features:</span></span>
    - <span data-ttu-id="19f0b-121">Отображение языка</span><span class="sxs-lookup"><span data-stu-id="19f0b-121">Display language</span></span>
    - <span data-ttu-id="19f0b-122">Язык клавиатуры</span><span class="sxs-lookup"><span data-stu-id="19f0b-122">Keyboard language</span></span>

- <span data-ttu-id="19f0b-123">Приложения Microsoft 365 для Enterprise языковых функций:</span><span class="sxs-lookup"><span data-stu-id="19f0b-123">Microsoft 365 Apps for Enterprise language features:</span></span>
    - <span data-ttu-id="19f0b-124">Отображение языка</span><span class="sxs-lookup"><span data-stu-id="19f0b-124">Display language</span></span>
    - <span data-ttu-id="19f0b-125">Средства проверки и авторинга</span><span class="sxs-lookup"><span data-stu-id="19f0b-125">Proofing and authoring tools</span></span>

<span data-ttu-id="19f0b-126">Чтобы сделать [](#supported-languages) поддерживаемые языки Приложения Microsoft 365 для Enterprise пользователями для установки, добавьте пользователей в группу **Modern Workplace-Office-Language_Packs.**</span><span class="sxs-lookup"><span data-stu-id="19f0b-126">To make the [Supported languages](#supported-languages) for Microsoft 365 Apps for Enterprise available for your users to install, add the users to the **Modern Workplace-Office-Language_Packs** group.</span></span> <span data-ttu-id="19f0b-127">Языки будут доступны в Корпоративный портал Intune.</span><span class="sxs-lookup"><span data-stu-id="19f0b-127">The languages will be available in the Intune Company Portal.</span></span>


## <a name="supported-languages"></a><span data-ttu-id="19f0b-128">Поддерживаемые языки</span><span class="sxs-lookup"><span data-stu-id="19f0b-128">Supported languages</span></span>

<span data-ttu-id="19f0b-129">Для новых устройств производитель должен предоставить изображения устройств, включающее необходимые языки.</span><span class="sxs-lookup"><span data-stu-id="19f0b-129">For new devices, your manufacturer must provide device images that include the languages you require.</span></span> <span data-ttu-id="19f0b-130">Если изображение производителя включает языки, не включенные в поддерживаемый список языков, служба по-прежнему поддерживает его.</span><span class="sxs-lookup"><span data-stu-id="19f0b-130">If your manufacturer's image includes languages other than those provided in the supported languages list it is still supported by the service.</span></span>

<span data-ttu-id="19f0b-131">При повторном доступе к существующим устройствам может потребоваться работать с представителем учетной записи Майкрософт для получения соответствующих изображений.</span><span class="sxs-lookup"><span data-stu-id="19f0b-131">If you are reusing existing devices, you might need to work with your Microsoft account representative to obtain appropriate images.</span></span> <span data-ttu-id="19f0b-132">Дополнительные сведения см. в [иллюстрациях Device.](../service-description/device-images.md)</span><span class="sxs-lookup"><span data-stu-id="19f0b-132">For more information, see [Device images](../service-description/device-images.md).</span></span>

<span data-ttu-id="19f0b-133">Универсальное [изображение,](../service-description/device-images.md#universal-image) предоставленное компьютеры, управляемые Майкрософт, включает эти языки и Windows 10:</span><span class="sxs-lookup"><span data-stu-id="19f0b-133">The [universal image](../service-description/device-images.md#universal-image) provided by Microsoft Managed Desktop includes these languages and for Windows 10:</span></span>

- <span data-ttu-id="19f0b-134">Арабский</span><span class="sxs-lookup"><span data-stu-id="19f0b-134">Arabic</span></span>
- <span data-ttu-id="19f0b-135">болгарский;</span><span class="sxs-lookup"><span data-stu-id="19f0b-135">Bulgarian</span></span>
- <span data-ttu-id="19f0b-136">Китайский упрощенный</span><span class="sxs-lookup"><span data-stu-id="19f0b-136">Chinese Simplified</span></span>
- <span data-ttu-id="19f0b-137">Китайский традиционный</span><span class="sxs-lookup"><span data-stu-id="19f0b-137">Chinese Traditional</span></span>
- <span data-ttu-id="19f0b-138">хорватский;</span><span class="sxs-lookup"><span data-stu-id="19f0b-138">Croatian</span></span>
- <span data-ttu-id="19f0b-139">чешский;</span><span class="sxs-lookup"><span data-stu-id="19f0b-139">Czech</span></span>
- <span data-ttu-id="19f0b-140">датский;</span><span class="sxs-lookup"><span data-stu-id="19f0b-140">Danish</span></span>  
- <span data-ttu-id="19f0b-141">голландский;</span><span class="sxs-lookup"><span data-stu-id="19f0b-141">Dutch</span></span>  
- <span data-ttu-id="19f0b-142">Английский (US, GB, AU, CA, IN)</span><span class="sxs-lookup"><span data-stu-id="19f0b-142">English (US, GB, AU, CA, IN)</span></span>
- <span data-ttu-id="19f0b-143">эстонский;</span><span class="sxs-lookup"><span data-stu-id="19f0b-143">Estonian</span></span>
- <span data-ttu-id="19f0b-144">финский;</span><span class="sxs-lookup"><span data-stu-id="19f0b-144">Finnish</span></span> 
- <span data-ttu-id="19f0b-145">Французский (Франция, Канада)</span><span class="sxs-lookup"><span data-stu-id="19f0b-145">French (France, Canada)</span></span>
- <span data-ttu-id="19f0b-146">немецкий;</span><span class="sxs-lookup"><span data-stu-id="19f0b-146">German</span></span>
- <span data-ttu-id="19f0b-147">греческий;</span><span class="sxs-lookup"><span data-stu-id="19f0b-147">Greek</span></span>
- <span data-ttu-id="19f0b-148">иврит;</span><span class="sxs-lookup"><span data-stu-id="19f0b-148">Hebrew</span></span>
- <span data-ttu-id="19f0b-149">венгерский;</span><span class="sxs-lookup"><span data-stu-id="19f0b-149">Hungarian</span></span>
- <span data-ttu-id="19f0b-150">индонезийский;</span><span class="sxs-lookup"><span data-stu-id="19f0b-150">Indonesian</span></span>
- <span data-ttu-id="19f0b-151">итальянский;</span><span class="sxs-lookup"><span data-stu-id="19f0b-151">Italian</span></span>
- <span data-ttu-id="19f0b-152">японский;</span><span class="sxs-lookup"><span data-stu-id="19f0b-152">Japanese</span></span>
- <span data-ttu-id="19f0b-153">корейский;</span><span class="sxs-lookup"><span data-stu-id="19f0b-153">Korean</span></span>
- <span data-ttu-id="19f0b-154">латышский;</span><span class="sxs-lookup"><span data-stu-id="19f0b-154">Latvian</span></span>
- <span data-ttu-id="19f0b-155">литовский;</span><span class="sxs-lookup"><span data-stu-id="19f0b-155">Lithuanian</span></span>
- <span data-ttu-id="19f0b-156">норвежский (букмол);</span><span class="sxs-lookup"><span data-stu-id="19f0b-156">Norwegian (Bokmål)</span></span>
- <span data-ttu-id="19f0b-157">польский;</span><span class="sxs-lookup"><span data-stu-id="19f0b-157">Polish</span></span>
- <span data-ttu-id="19f0b-158">португальский (Бразилия);</span><span class="sxs-lookup"><span data-stu-id="19f0b-158">Portuguese (Brazil)</span></span>
- <span data-ttu-id="19f0b-159">португальский (Португалия);</span><span class="sxs-lookup"><span data-stu-id="19f0b-159">Portuguese (Portugal)</span></span>
- <span data-ttu-id="19f0b-160">румынский;</span><span class="sxs-lookup"><span data-stu-id="19f0b-160">Romanian</span></span>
- <span data-ttu-id="19f0b-161">русский;</span><span class="sxs-lookup"><span data-stu-id="19f0b-161">Russian</span></span> 
- <span data-ttu-id="19f0b-162">Сербский (латинский алфавит)</span><span class="sxs-lookup"><span data-stu-id="19f0b-162">Serbian (Latin alphabet)</span></span>
- <span data-ttu-id="19f0b-163">словацкий;</span><span class="sxs-lookup"><span data-stu-id="19f0b-163">Slovak</span></span>
- <span data-ttu-id="19f0b-164">словенский;</span><span class="sxs-lookup"><span data-stu-id="19f0b-164">Slovenian</span></span>
- <span data-ttu-id="19f0b-165">Испанский (Испания, Мексика)</span><span class="sxs-lookup"><span data-stu-id="19f0b-165">Spanish (Spain, Mexico)</span></span>
- <span data-ttu-id="19f0b-166">шведский;</span><span class="sxs-lookup"><span data-stu-id="19f0b-166">Swedish</span></span>
- <span data-ttu-id="19f0b-167">тайский;</span><span class="sxs-lookup"><span data-stu-id="19f0b-167">Thai</span></span>
- <span data-ttu-id="19f0b-168">турецкий;</span><span class="sxs-lookup"><span data-stu-id="19f0b-168">Turkish</span></span>
- <span data-ttu-id="19f0b-169">украинский;</span><span class="sxs-lookup"><span data-stu-id="19f0b-169">Ukrainian</span></span>
- <span data-ttu-id="19f0b-170">вьетнамский.</span><span class="sxs-lookup"><span data-stu-id="19f0b-170">Vietnamese</span></span>

<span data-ttu-id="19f0b-171">Приложения Microsoft 365 для Enterprise может поддерживать несколько другой список.</span><span class="sxs-lookup"><span data-stu-id="19f0b-171">Microsoft 365 Apps for Enterprise might support a slightly different list.</span></span>

<span data-ttu-id="19f0b-172">Если пользователям нужен язык, не указанный здесь, необходимо подать запрос на поддержку с помощью [портала Admin.](access-admin-portal.md) [](../working-with-managed-desktop/admin-support.md)</span><span class="sxs-lookup"><span data-stu-id="19f0b-172">If your users need a language other than the ones listed here, file a [support request](../working-with-managed-desktop/admin-support.md) by using the [Admin portal](access-admin-portal.md).</span></span>

## <a name="languages-for-support-and-operations"></a><span data-ttu-id="19f0b-173">Языки поддержки и операций</span><span class="sxs-lookup"><span data-stu-id="19f0b-173">Languages for support and operations</span></span>

### <a name="user-support"></a><span data-ttu-id="19f0b-174">Поддержка пользователей</span><span class="sxs-lookup"><span data-stu-id="19f0b-174">User support</span></span>
<span data-ttu-id="19f0b-175">компьютеры, управляемые Майкрософт поддерживается только на английском языке.</span><span class="sxs-lookup"><span data-stu-id="19f0b-175">Microsoft Managed Desktop provides support only in English.</span></span> <span data-ttu-id="19f0b-176">Если пользователи выбирают другой язык в приложении Техническая поддержка, они получат поддержку из общих каналов поддержки Майкрософт, а не непосредственно из компьютеры, управляемые Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="19f0b-176">If users choose another language in the Get Help app, they will get support from the general Microsoft support channels, rather than support directly from Microsoft Managed Desktop.</span></span> <span data-ttu-id="19f0b-177">Дополнительные сведения см. в [справке для пользователей](../working-with-managed-desktop/end-user-support.md).</span><span class="sxs-lookup"><span data-stu-id="19f0b-177">For more information, see [Getting help for users](../working-with-managed-desktop/end-user-support.md).</span></span>

<span data-ttu-id="19f0b-178">Если пользователям нужна поддержка на других языках, ее необходимо предоставить из источников поддержки, не в microsoft, или из вашей организации.</span><span class="sxs-lookup"><span data-stu-id="19f0b-178">If your users need support in other languages, you'll have to provide that through non-Microsoft support sources or from your own organization.</span></span>

### <a name="admin-support-and-operations"></a><span data-ttu-id="19f0b-179">Поддержка администратора и операции</span><span class="sxs-lookup"><span data-stu-id="19f0b-179">Admin support and operations</span></span>
<span data-ttu-id="19f0b-180">компьютеры, управляемые Майкрософт поддерживает администратора только на английском языке.</span><span class="sxs-lookup"><span data-stu-id="19f0b-180">Microsoft Managed Desktop provides admin support only in English.</span></span> <span data-ttu-id="19f0b-181">Это включает портал Admin и все сообщения с компьютеры, управляемые Майкрософт operations.</span><span class="sxs-lookup"><span data-stu-id="19f0b-181">This includes the Admin portal and all communications with Microsoft Managed Desktop Operations.</span></span> <span data-ttu-id="19f0b-182">Следует предположить, что все взаимодействия и интерфейсы, связанные с администрированием, будут на английском языке, если не указано иное.</span><span class="sxs-lookup"><span data-stu-id="19f0b-182">You should assume that all admin-related interactions and interfaces will be in English, unless specified otherwise.</span></span>


