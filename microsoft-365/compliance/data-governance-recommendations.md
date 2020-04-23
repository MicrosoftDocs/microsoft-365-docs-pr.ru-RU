---
title: Как определяется содержимое для рекомендаций по управлению данными
f1.keywords:
- NOCSH
ms.author: brendonb
author: cabailey
manager: laurawi
ms.date: 1/15/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Центр безопасности Microsoft 365 и Центр соответствия требованиям Microsoft 365 предоставляют рекомендации для управления данными на основе текущей настройки вашей организации и дают возможность быстро и удобно настроить необходимые параметры. Некоторые из рекомендаций определяют конкретное содержимое в организации и указывают рекомендованные действия для управления этим содержимым. Например, рекомендация может обнаруживать элементы, содержащие важный деловое содержимое (например, сведения, связанные с адвокатской тайной, или соглашения о неразглашении) и давать возможность автоматически присваивать метки хранения таким элементам, чтобы их классифицировать и хранить при необходимости. В этой статье перечислены рекомендации по управлению данными, которые вы можете встретить, и описано, какое содержимое обнаруживается для срабатывания каждой из них.
ms.openlocfilehash: 805919aa4cfceca5f3409b0f218a3b6018fc38cd
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637771"
---
# <a name="how-content-is-identified-for-data-governance-recommendations"></a><span data-ttu-id="f3448-106">Как определяется содержимое для рекомендаций по управлению данными</span><span class="sxs-lookup"><span data-stu-id="f3448-106">How content is identified for data-governance recommendations</span></span>

<span data-ttu-id="f3448-p102">Центр безопасности Microsoft 365 и Центр соответствия требованиям Microsoft 365 предоставляют рекомендации для управления данными на основе текущей настройки вашей организации и дают возможность быстро и удобно настроить необходимые параметры. Некоторые из рекомендаций определяют конкретное содержимое в организации и указывают рекомендованные действия для управления этим содержимым. Например, рекомендация может обнаруживать элементы, содержащие важный деловое содержимое (например, сведения, связанные с адвокатской тайной, или соглашения о неразглашении) и давать возможность автоматически присваивать метки хранения таким элементам, чтобы их классифицировать и хранить при необходимости.</span><span class="sxs-lookup"><span data-stu-id="f3448-p102">The Microsoft 365 security center and Microsoft 365 compliance center provide recommendations for data governance based on your org's current setup and lets you set things up in a couple clicks. Some of these recommendations detect specific content in your organization and then provide recommended steps for managing that content. For example, a recommendation might detect items that contain business-critical content (such as attorney-client privilege or NDA info), and then let you automatically apply a retention label to those items to ensure that they're classified and retained as needed.</span></span>

<span data-ttu-id="f3448-110">В этой статье перечислены рекомендации по управлению данными, которые вы можете встретить, и описано, какое содержимое обнаруживается для срабатывания каждой из них.</span><span class="sxs-lookup"><span data-stu-id="f3448-110">This topic lists the data-governance recommendations you might see and describes what content is detected to trigger each one.</span></span>

## <a name="clean-up-voicemail"></a><span data-ttu-id="f3448-111">Очистить голосовую почту</span><span class="sxs-lookup"><span data-stu-id="f3448-111">Clean up voicemail</span></span>

<span data-ttu-id="f3448-p103">Эта рекомендация отображается, если в почтовых ящиках пользователей обнаружен тип сообщений электронной почты, определенный как "голосовая почта". Узнайте больше о [свойствах сообщений в Exchange](https://docs.microsoft.com/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators?view=exchserver-2019#searchable-properties-in-exchange).</span><span class="sxs-lookup"><span data-stu-id="f3448-p103">This recommendation appears when email messages identified as the message type 'voicemail' are detected in users' mailboxes. Learn more about [message properties in Exchange](https://docs.microsoft.com/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators?view=exchserver-2019#searchable-properties-in-exchange).</span></span>

## <a name="label-attorney-client-privilege-content"></a><span data-ttu-id="f3448-114">Пометить контент, содержащий адвокатскую тайну</span><span class="sxs-lookup"><span data-stu-id="f3448-114">Label attorney-client privilege content</span></span> 

<span data-ttu-id="f3448-115">Эта рекомендация отображается при выполнении любого из указанных ниже условий.</span><span class="sxs-lookup"><span data-stu-id="f3448-115">This recommendation appears when either of the following criteria are met.</span></span>

- <span data-ttu-id="f3448-116">В тексте сообщения электронной почты обнаружено любое сочетание этих ключевых слов:</span><span class="sxs-lookup"><span data-stu-id="f3448-116">Any of combination of these keywords is detected in the body of an email message:</span></span>
    - <span data-ttu-id="f3448-117">ACP</span><span class="sxs-lookup"><span data-stu-id="f3448-117">ACP</span></span>
    - <span data-ttu-id="f3448-118">Общение между адвокатом и клиентом с обеспечением конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="f3448-118">Attorney Client Privilege</span></span>
    - <span data-ttu-id="f3448-119">Адвокатская тайна</span><span class="sxs-lookup"><span data-stu-id="f3448-119">Attorney-Client Privilege</span></span>
    - <span data-ttu-id="f3448-120">Конфиденциальное общение с адвокатом</span><span class="sxs-lookup"><span data-stu-id="f3448-120">Attorney-Client Privileged</span></span>

- <span data-ttu-id="f3448-121">В файлах SharePoint или OneDrive обнаружено любое сочетание этих ключевых слов:</span><span class="sxs-lookup"><span data-stu-id="f3448-121">Any combination of these keywords are detected in SharePoint or OneDrive files:</span></span>
    - <span data-ttu-id="f3448-122">ACP</span><span class="sxs-lookup"><span data-stu-id="f3448-122">ACP</span></span>
    - <span data-ttu-id="f3448-123">Общение между адвокатом и клиентом с обеспечением конфиденциальности\*</span><span class="sxs-lookup"><span data-stu-id="f3448-123">Attorney Client Privilege\*</span></span>
    - <span data-ttu-id="f3448-124">Адвокатская тайна</span><span class="sxs-lookup"><span data-stu-id="f3448-124">AC Privilege</span></span>

## <a name="retain-audio-files"></a><span data-ttu-id="f3448-125">Сохранить звуковые файлы</span><span class="sxs-lookup"><span data-stu-id="f3448-125">Retain audio files</span></span>

<span data-ttu-id="f3448-126">Эта рекомендация отображается, если в SharePoint или OneDrive обнаружен любой из указанных ниже типов файлов.</span><span class="sxs-lookup"><span data-stu-id="f3448-126">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="f3448-127">MP3</span><span class="sxs-lookup"><span data-stu-id="f3448-127">.MP3</span></span>
- <span data-ttu-id="f3448-128">WMA</span><span class="sxs-lookup"><span data-stu-id="f3448-128">.WMA</span></span>
- <span data-ttu-id="f3448-129">WAV</span><span class="sxs-lookup"><span data-stu-id="f3448-129">.WAV</span></span>
- <span data-ttu-id="f3448-130">RA</span><span class="sxs-lookup"><span data-stu-id="f3448-130">.RA</span></span>
- <span data-ttu-id="f3448-131">RAM</span><span class="sxs-lookup"><span data-stu-id="f3448-131">.RAM</span></span>
- <span data-ttu-id="f3448-132">RM</span><span class="sxs-lookup"><span data-stu-id="f3448-132">.RM</span></span>
- <span data-ttu-id="f3448-133">MID</span><span class="sxs-lookup"><span data-stu-id="f3448-133">.MID</span></span>
- <span data-ttu-id="f3448-134">OGG</span><span class="sxs-lookup"><span data-stu-id="f3448-134">.OGG</span></span>
- <span data-ttu-id="f3448-135">AIFF</span><span class="sxs-lookup"><span data-stu-id="f3448-135">.AIFF</span></span>
- <span data-ttu-id="f3448-136">PCM</span><span class="sxs-lookup"><span data-stu-id="f3448-136">.PCM</span></span>
- <span data-ttu-id="f3448-137">AAC</span><span class="sxs-lookup"><span data-stu-id="f3448-137">.AAC</span></span>
- <span data-ttu-id="f3448-138">FLAC</span><span class="sxs-lookup"><span data-stu-id="f3448-138">.FLAC</span></span>
- <span data-ttu-id="f3448-139">ALAC</span><span class="sxs-lookup"><span data-stu-id="f3448-139">.ALAC</span></span>

## <a name="retain-cad-files"></a><span data-ttu-id="f3448-140">Сохранить файлы САПР</span><span class="sxs-lookup"><span data-stu-id="f3448-140">Retain CAD files</span></span>

<span data-ttu-id="f3448-141">Эта рекомендация отображается, если в SharePoint или OneDrive обнаружен любой из указанных ниже типов файлов.</span><span class="sxs-lookup"><span data-stu-id="f3448-141">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="f3448-142">3DXML</span><span class="sxs-lookup"><span data-stu-id="f3448-142">.3DXML</span></span>
- <span data-ttu-id="f3448-143">ACIS</span><span class="sxs-lookup"><span data-stu-id="f3448-143">.ACIS</span></span>
- <span data-ttu-id="f3448-144">ARC</span><span class="sxs-lookup"><span data-stu-id="f3448-144">.ARC</span></span>
- <span data-ttu-id="f3448-145">ASM</span><span class="sxs-lookup"><span data-stu-id="f3448-145">.ASM</span></span>
- <span data-ttu-id="f3448-146">CAT\*</span><span class="sxs-lookup"><span data-stu-id="f3448-146">.CAT\*</span></span>
- <span data-ttu-id="f3448-147">CGR</span><span class="sxs-lookup"><span data-stu-id="f3448-147">.CGR</span></span>
- <span data-ttu-id="f3448-148">DW\*</span><span class="sxs-lookup"><span data-stu-id="f3448-148">.DW\*</span></span>
- <span data-ttu-id="f3448-149">DX\*</span><span class="sxs-lookup"><span data-stu-id="f3448-149">.DX\*</span></span>
- <span data-ttu-id="f3448-150">EDRW</span><span class="sxs-lookup"><span data-stu-id="f3448-150">.EDRW</span></span>
- <span data-ttu-id="f3448-151">IAM</span><span class="sxs-lookup"><span data-stu-id="f3448-151">.IAM</span></span>
- <span data-ttu-id="f3448-152">IGES</span><span class="sxs-lookup"><span data-stu-id="f3448-152">.IGES</span></span>
- <span data-ttu-id="f3448-153">IGS</span><span class="sxs-lookup"><span data-stu-id="f3448-153">.IGS</span></span>
- <span data-ttu-id="f3448-154">IPT</span><span class="sxs-lookup"><span data-stu-id="f3448-154">.IPT</span></span>
- <span data-ttu-id="f3448-155">JT</span><span class="sxs-lookup"><span data-stu-id="f3448-155">.JT</span></span>
- <span data-ttu-id="f3448-156">MF1</span><span class="sxs-lookup"><span data-stu-id="f3448-156">.MF1</span></span>
- <span data-ttu-id="f3448-157">NEU</span><span class="sxs-lookup"><span data-stu-id="f3448-157">.NEU</span></span>
- <span data-ttu-id="f3448-158">PAR</span><span class="sxs-lookup"><span data-stu-id="f3448-158">.PAR</span></span>
- <span data-ttu-id="f3448-159">PKG</span><span class="sxs-lookup"><span data-stu-id="f3448-159">.PKG</span></span>
- <span data-ttu-id="f3448-160">PRC</span><span class="sxs-lookup"><span data-stu-id="f3448-160">.PRC</span></span>
- <span data-ttu-id="f3448-161">PRT</span><span class="sxs-lookup"><span data-stu-id="f3448-161">.PRT</span></span>
- <span data-ttu-id="f3448-162">PSM</span><span class="sxs-lookup"><span data-stu-id="f3448-162">.PSM</span></span>
- <span data-ttu-id="f3448-163">PWD</span><span class="sxs-lookup"><span data-stu-id="f3448-163">.PWD</span></span>
- <span data-ttu-id="f3448-164">SLD\*</span><span class="sxs-lookup"><span data-stu-id="f3448-164">.SLD\*</span></span>
- <span data-ttu-id="f3448-165">STEP</span><span class="sxs-lookup"><span data-stu-id="f3448-165">.STEP</span></span>
- <span data-ttu-id="f3448-166">STL</span><span class="sxs-lookup"><span data-stu-id="f3448-166">.STL</span></span>
- <span data-ttu-id="f3448-167">STP</span><span class="sxs-lookup"><span data-stu-id="f3448-167">.STP</span></span>
- <span data-ttu-id="f3448-168">U3D</span><span class="sxs-lookup"><span data-stu-id="f3448-168">.U3D</span></span>
- <span data-ttu-id="f3448-169">UNV</span><span class="sxs-lookup"><span data-stu-id="f3448-169">.UNV</span></span>
- <span data-ttu-id="f3448-170">VRML</span><span class="sxs-lookup"><span data-stu-id="f3448-170">.VRML</span></span>
- <span data-ttu-id="f3448-171">WRL</span><span class="sxs-lookup"><span data-stu-id="f3448-171">.WRL</span></span>
- <span data-ttu-id="f3448-172">X_\*</span><span class="sxs-lookup"><span data-stu-id="f3448-172">.X_\*</span></span>
- <span data-ttu-id="f3448-173">XAS</span><span class="sxs-lookup"><span data-stu-id="f3448-173">.XAS</span></span>
- <span data-ttu-id="f3448-174">XMT\*</span><span class="sxs-lookup"><span data-stu-id="f3448-174">.XMT\*</span></span>
- <span data-ttu-id="f3448-175">XPR</span><span class="sxs-lookup"><span data-stu-id="f3448-175">.XPR</span></span>

## <a name="retain-image-files"></a><span data-ttu-id="f3448-176">Сохранить файлы изображений</span><span class="sxs-lookup"><span data-stu-id="f3448-176">Retain image files</span></span>

<span data-ttu-id="f3448-177">Эта рекомендация отображается, если в SharePoint или OneDrive обнаружен любой из указанных ниже типов файлов.</span><span class="sxs-lookup"><span data-stu-id="f3448-177">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="f3448-178">JPEG</span><span class="sxs-lookup"><span data-stu-id="f3448-178">.JPEG</span></span>
- <span data-ttu-id="f3448-179">GIF</span><span class="sxs-lookup"><span data-stu-id="f3448-179">.GIF</span></span>
- <span data-ttu-id="f3448-180">TIF\*</span><span class="sxs-lookup"><span data-stu-id="f3448-180">.TIF\*</span></span>
- <span data-ttu-id="f3448-181">BMP</span><span class="sxs-lookup"><span data-stu-id="f3448-181">.BMP</span></span>
- <span data-ttu-id="f3448-182">PNG</span><span class="sxs-lookup"><span data-stu-id="f3448-182">.PNG</span></span>
- <span data-ttu-id="f3448-183">RAW</span><span class="sxs-lookup"><span data-stu-id="f3448-183">.RAW</span></span>
- <span data-ttu-id="f3448-184">PSD</span><span class="sxs-lookup"><span data-stu-id="f3448-184">.PSD</span></span>
- <span data-ttu-id="f3448-185">PSP</span><span class="sxs-lookup"><span data-stu-id="f3448-185">.PSP</span></span>
- <span data-ttu-id="f3448-186">JPG</span><span class="sxs-lookup"><span data-stu-id="f3448-186">.JPG</span></span>
- <span data-ttu-id="f3448-187">EXIF</span><span class="sxs-lookup"><span data-stu-id="f3448-187">.EXIF</span></span>
- <span data-ttu-id="f3448-188">PPM</span><span class="sxs-lookup"><span data-stu-id="f3448-188">.PPM</span></span>
- <span data-ttu-id="f3448-189">PGM</span><span class="sxs-lookup"><span data-stu-id="f3448-189">.PGM</span></span>
- <span data-ttu-id="f3448-190">PBM</span><span class="sxs-lookup"><span data-stu-id="f3448-190">.PBM</span></span>
- <span data-ttu-id="f3448-191">PNM</span><span class="sxs-lookup"><span data-stu-id="f3448-191">.PNM</span></span>
- <span data-ttu-id="f3448-192">WEBP</span><span class="sxs-lookup"><span data-stu-id="f3448-192">.WEBP</span></span>

## <a name="retain-nda-content"></a><span data-ttu-id="f3448-193">Сохранить содержимое о неразглашении</span><span class="sxs-lookup"><span data-stu-id="f3448-193">Retain NDA content</span></span> 

<span data-ttu-id="f3448-194">Эта рекомендация отображается при выполнении любого из указанных ниже условий.</span><span class="sxs-lookup"><span data-stu-id="f3448-194">This recommendation appears when either of the following criteria are met.</span></span>

- <span data-ttu-id="f3448-195">В тексте сообщения электронной почты обнаружено любое сочетание этих ключевых слов:</span><span class="sxs-lookup"><span data-stu-id="f3448-195">Any of combination of these keywords is detected in the body of an email message:</span></span>
    - <span data-ttu-id="f3448-196">NDA</span><span class="sxs-lookup"><span data-stu-id="f3448-196">NDA</span></span>
    - <span data-ttu-id="f3448-197">"Соглашение о неразглашении"</span><span class="sxs-lookup"><span data-stu-id="f3448-197">"Non-Disclosure Agreement"</span></span>
    - <span data-ttu-id="f3448-198">"Соглашение о неразглашении"</span><span class="sxs-lookup"><span data-stu-id="f3448-198">"Non Disclosure Agreement"</span></span>

- <span data-ttu-id="f3448-199">В файлах формата PDF или DOC в SharePoint или OneDrive обнаружено любое сочетание этих ключевых слов:</span><span class="sxs-lookup"><span data-stu-id="f3448-199">Any combination of these keywords are detected in .PDF or .DOC files in SharePoint or OneDrive:</span></span>
    - <span data-ttu-id="f3448-200">NDA</span><span class="sxs-lookup"><span data-stu-id="f3448-200">NDA</span></span>
    - <span data-ttu-id="f3448-201">Соглашение о неразглашении</span><span class="sxs-lookup"><span data-stu-id="f3448-201">Non Disclosure Agreement</span></span>

## <a name="retain-software-development-files"></a><span data-ttu-id="f3448-202">Сохранить файлы разработки программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="f3448-202">Retain software development files</span></span>

<span data-ttu-id="f3448-203">Эта рекомендация отображается, если в SharePoint или OneDrive обнаружен любой из указанных ниже типов файлов.</span><span class="sxs-lookup"><span data-stu-id="f3448-203">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="f3448-204">ASAX</span><span class="sxs-lookup"><span data-stu-id="f3448-204">.ASAX</span></span>
- <span data-ttu-id="f3448-205">ASM</span><span class="sxs-lookup"><span data-stu-id="f3448-205">.ASM</span></span>
- <span data-ttu-id="f3448-206">ASP\*</span><span class="sxs-lookup"><span data-stu-id="f3448-206">.ASP\*</span></span>
- <span data-ttu-id="f3448-207">BAT</span><span class="sxs-lookup"><span data-stu-id="f3448-207">.BAT</span></span>
- <span data-ttu-id="f3448-208">CONFIG</span><span class="sxs-lookup"><span data-stu-id="f3448-208">.CONFIG</span></span>
- <span data-ttu-id="f3448-209">CS</span><span class="sxs-lookup"><span data-stu-id="f3448-209">.CS</span></span>
- <span data-ttu-id="f3448-210">CSS</span><span class="sxs-lookup"><span data-stu-id="f3448-210">.CSS</span></span>
- <span data-ttu-id="f3448-211">DISCO</span><span class="sxs-lookup"><span data-stu-id="f3448-211">.DISCO</span></span>
- <span data-ttu-id="f3448-212">HTM\*</span><span class="sxs-lookup"><span data-stu-id="f3448-212">.HTM\*</span></span>
- <span data-ttu-id="f3448-213">INC</span><span class="sxs-lookup"><span data-stu-id="f3448-213">.INC</span></span>
- <span data-ttu-id="f3448-214">JAD</span><span class="sxs-lookup"><span data-stu-id="f3448-214">.JAD</span></span>
- <span data-ttu-id="f3448-215">JAVA</span><span class="sxs-lookup"><span data-stu-id="f3448-215">.JAVA</span></span>
- <span data-ttu-id="f3448-216">JS\*</span><span class="sxs-lookup"><span data-stu-id="f3448-216">.JS\*</span></span>
- <span data-ttu-id="f3448-217">LIB</span><span class="sxs-lookup"><span data-stu-id="f3448-217">.LIB</span></span>
- <span data-ttu-id="f3448-218">O</span><span class="sxs-lookup"><span data-stu-id="f3448-218">.O</span></span>
- <span data-ttu-id="f3448-219">PHP</span><span class="sxs-lookup"><span data-stu-id="f3448-219">.PHP</span></span>
- <span data-ttu-id="f3448-220">РК</span><span class="sxs-lookup"><span data-stu-id="f3448-220">.RC</span></span>
- <span data-ttu-id="f3448-221">RESX</span><span class="sxs-lookup"><span data-stu-id="f3448-221">.RESX</span></span>
- <span data-ttu-id="f3448-222">RPT</span><span class="sxs-lookup"><span data-stu-id="f3448-222">.RPT</span></span>
- <span data-ttu-id="f3448-223">RSS</span><span class="sxs-lookup"><span data-stu-id="f3448-223">.RSS</span></span>
- <span data-ttu-id="f3448-224">SCPT</span><span class="sxs-lookup"><span data-stu-id="f3448-224">.SCPT</span></span>
- <span data-ttu-id="f3448-225">SRC</span><span class="sxs-lookup"><span data-stu-id="f3448-225">.SRC</span></span>
- <span data-ttu-id="f3448-226">VB\*</span><span class="sxs-lookup"><span data-stu-id="f3448-226">.VB\*</span></span>
- <span data-ttu-id="f3448-227">WSF</span><span class="sxs-lookup"><span data-stu-id="f3448-227">.WSF</span></span>
- <span data-ttu-id="f3448-228">XCODEPROJ</span><span class="sxs-lookup"><span data-stu-id="f3448-228">.XCODEPROJ</span></span>
- <span data-ttu-id="f3448-229">XML</span><span class="sxs-lookup"><span data-stu-id="f3448-229">.XML</span></span>
- <span data-ttu-id="f3448-230">XSD</span><span class="sxs-lookup"><span data-stu-id="f3448-230">.XSD</span></span>
- <span data-ttu-id="f3448-231">XSL\*</span><span class="sxs-lookup"><span data-stu-id="f3448-231">.XSL\*</span></span>

## <a name="retain-video-files"></a><span data-ttu-id="f3448-232">Сохранить видеофайлы</span><span class="sxs-lookup"><span data-stu-id="f3448-232">Retain video files</span></span>

<span data-ttu-id="f3448-233">Эта рекомендация отображается, если в SharePoint или OneDrive обнаружен любой из указанных ниже типов файлов.</span><span class="sxs-lookup"><span data-stu-id="f3448-233">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="f3448-234">AVCHD</span><span class="sxs-lookup"><span data-stu-id="f3448-234">.AVCHD</span></span>
- <span data-ttu-id="f3448-235">AVI</span><span class="sxs-lookup"><span data-stu-id="f3448-235">.AVI</span></span>
- <span data-ttu-id="f3448-236">FLV</span><span class="sxs-lookup"><span data-stu-id="f3448-236">.FLV</span></span>
- <span data-ttu-id="f3448-237">MOV</span><span class="sxs-lookup"><span data-stu-id="f3448-237">.MOV</span></span>
- <span data-ttu-id="f3448-238">MP2V</span><span class="sxs-lookup"><span data-stu-id="f3448-238">.MP2V</span></span>
- <span data-ttu-id="f3448-239">MP4</span><span class="sxs-lookup"><span data-stu-id="f3448-239">.MP4</span></span>
- <span data-ttu-id="f3448-240">MP4V</span><span class="sxs-lookup"><span data-stu-id="f3448-240">.MP4V</span></span>
- <span data-ttu-id="f3448-241">MPE</span><span class="sxs-lookup"><span data-stu-id="f3448-241">.MPE</span></span>
- <span data-ttu-id="f3448-242">MPEG</span><span class="sxs-lookup"><span data-stu-id="f3448-242">.MPEG</span></span>
- <span data-ttu-id="f3448-243">MPEG1</span><span class="sxs-lookup"><span data-stu-id="f3448-243">.MPEG1</span></span>
- <span data-ttu-id="f3448-244">MPEG2</span><span class="sxs-lookup"><span data-stu-id="f3448-244">.MPEG2</span></span>
- <span data-ttu-id="f3448-245">MPEG4</span><span class="sxs-lookup"><span data-stu-id="f3448-245">.MPEG4</span></span>
- <span data-ttu-id="f3448-246">MPG</span><span class="sxs-lookup"><span data-stu-id="f3448-246">.MPG</span></span>
- <span data-ttu-id="f3448-247">MPG2</span><span class="sxs-lookup"><span data-stu-id="f3448-247">.MPG2</span></span>
- <span data-ttu-id="f3448-248">MPG4</span><span class="sxs-lookup"><span data-stu-id="f3448-248">.MPG4</span></span>
- <span data-ttu-id="f3448-249">WMV</span><span class="sxs-lookup"><span data-stu-id="f3448-249">.WMV</span></span>
- <span data-ttu-id="f3448-250">XMV</span><span class="sxs-lookup"><span data-stu-id="f3448-250">.XMV</span></span>
