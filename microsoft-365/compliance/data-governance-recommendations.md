---
title: Как определяется содержимое для рекомендаций по управлению данными
ms.author: brendonb
author: laurawi
manager: laurawi
ms.date: 1/15/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Центр безопасности и соответствия требованиям Office 365 предоставляет рекомендации для управления данными на основе текущей настройки вашей организации и позволяет выполнить подготовку за пару щелчков. Некоторые из этих рекомендаций определяют конкретное содержимое в организации и указывают рекомендованные действия по управлению этим содержимым. Например, рекомендация может обнаружить элементы, содержащие важный деловой контент (например, связанные с адвокатской тайной сведения или соглашения о неразглашении) и затем позволяет автоматически присвоить метки хранения к этим элементам, чтобы обеспечить их конфиденциальность и правильное хранение. В этой статье перечислены рекомендации по управлению данными, которые вы можете встретить, и описано, какое содержимое обнаруживается для срабатывания каждой из них.
ms.openlocfilehash: 10752afb97fd0ae2993d88b4e3af9159d61de708
ms.sourcegitcommit: 1eecd7b127462585c35b0c96a179d37db45f6013
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "37342942"
---
# <a name="how-content-is-identified-for-data-governance-recommendations"></a><span data-ttu-id="6f660-106">Как определяется содержимое для рекомендаций по управлению данными</span><span class="sxs-lookup"><span data-stu-id="6f660-106">How content is identified for data-governance recommendations</span></span>

<span data-ttu-id="6f660-p102">Центр безопасности и соответствия требованиям Office 365 предоставляет рекомендации для управления данными на основе текущей настройки вашей организации и позволяет выполнить подготовку за пару щелчков. Некоторые из этих рекомендаций определяют конкретное содержимое в организации и указывают рекомендованные действия по управлению этим содержимым. Например, рекомендация может обнаружить элементы, содержащие важный деловой контент (например, связанные с адвокатской тайной сведения или соглашения о неразглашении) и затем позволяет автоматически присвоить метки хранения к этим элементам, чтобы обеспечить их конфиденциальность и правильное хранение.</span><span class="sxs-lookup"><span data-stu-id="6f660-p102">The Office 365 Security & Compliance Center provides recommendations for data governance based on your org's current setup and lets you set things up in a couple clicks. Some of these recommendations detect specific content in your organization and then provide recommended steps for managing that content. For example, a recommendation might detect items that contain business-critical content (such as attorney-client privilege or NDA info), and then let you automatically apply a retention label to those items to ensure that they’re classified and retained as needed.</span></span>

<span data-ttu-id="6f660-110">В этой статье перечислены рекомендации по управлению данными, которые вы можете встретить, и описано, какое содержимое обнаруживается для срабатывания каждой из них.</span><span class="sxs-lookup"><span data-stu-id="6f660-110">This topic lists the data-governance recommendations you might see and describes what content is detected to trigger each one.</span></span>

## <a name="clean-up-voicemail"></a><span data-ttu-id="6f660-111">Очистить голосовую почту</span><span class="sxs-lookup"><span data-stu-id="6f660-111">Clean up voicemail</span></span>

<span data-ttu-id="6f660-p103">Эта рекомендация отображается, если в почтовых ящиках пользователей обнаружен тип сообщений электронной почты, определенный как "голосовая почта". Узнайте больше о [свойствах сообщений в Exchange](https://docs.microsoft.com/en-us/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators?view=exchserver-2019#searchable-properties-in-exchange).</span><span class="sxs-lookup"><span data-stu-id="6f660-p103">This recommendation appears when email messages identified as the message type ‘voicemail’ are detected in users’ mailboxes. Learn more about [message properties in Exchange](https://docs.microsoft.com/en-us/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators?view=exchserver-2019#searchable-properties-in-exchange).</span></span>

## <a name="label-attorney-client-privilege-content"></a><span data-ttu-id="6f660-114">Пометить контент, содержащий адвокатскую тайну</span><span class="sxs-lookup"><span data-stu-id="6f660-114">Label attorney-client privilege content</span></span> 

<span data-ttu-id="6f660-115">Эта рекомендация отображается при выполнении любого из указанных ниже условий.</span><span class="sxs-lookup"><span data-stu-id="6f660-115">This recommendation appears when either of the following criteria are met.</span></span>

- <span data-ttu-id="6f660-116">В тексте сообщения электронной почты обнаружено любое сочетание этих ключевых слов:</span><span class="sxs-lookup"><span data-stu-id="6f660-116">Any of combination of these keywords is detected in the body of an email message:</span></span>
    - <span data-ttu-id="6f660-117">ACP</span><span class="sxs-lookup"><span data-stu-id="6f660-117">ACP</span></span>
    - <span data-ttu-id="6f660-118">Общение между адвокатом и клиентом с обеспечением конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="6f660-118">Attorney Client Privilege</span></span>
    - <span data-ttu-id="6f660-119">Адвокатская тайна</span><span class="sxs-lookup"><span data-stu-id="6f660-119">Attorney-Client Privilege</span></span>
    - <span data-ttu-id="6f660-120">Конфиденциальное общение с адвокатом</span><span class="sxs-lookup"><span data-stu-id="6f660-120">Attorney-Client Privileged</span></span>

- <span data-ttu-id="6f660-121">В файлах SharePoint или OneDrive обнаружено любое сочетание этих ключевых слов:</span><span class="sxs-lookup"><span data-stu-id="6f660-121">Any combination of these keywords are detected in SharePoint or OneDrive files:</span></span>
    - <span data-ttu-id="6f660-122">ACP</span><span class="sxs-lookup"><span data-stu-id="6f660-122">ACP</span></span>
    - <span data-ttu-id="6f660-123">Общение между адвокатом и клиентом с обеспечением конфиденциальности\*</span><span class="sxs-lookup"><span data-stu-id="6f660-123">Attorney Client Privilege\*</span></span>
    - <span data-ttu-id="6f660-124">Адвокатская тайна</span><span class="sxs-lookup"><span data-stu-id="6f660-124">AC Privilege</span></span>

## <a name="retain-audio-files"></a><span data-ttu-id="6f660-125">Сохранить звуковые файлы</span><span class="sxs-lookup"><span data-stu-id="6f660-125">Retain audio files</span></span>

<span data-ttu-id="6f660-126">Эта рекомендация отображается, если в SharePoint или OneDrive обнаружен любой из указанных ниже типов файлов.</span><span class="sxs-lookup"><span data-stu-id="6f660-126">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="6f660-127">MP3</span><span class="sxs-lookup"><span data-stu-id="6f660-127">.MP3</span></span>
- <span data-ttu-id="6f660-128">WMA</span><span class="sxs-lookup"><span data-stu-id="6f660-128">.WMA</span></span>
- <span data-ttu-id="6f660-129">WAV</span><span class="sxs-lookup"><span data-stu-id="6f660-129">.WAV</span></span>
- <span data-ttu-id="6f660-130">RA</span><span class="sxs-lookup"><span data-stu-id="6f660-130">.RA</span></span>
- <span data-ttu-id="6f660-131">RAM</span><span class="sxs-lookup"><span data-stu-id="6f660-131">.RAM</span></span>
- <span data-ttu-id="6f660-132">RM</span><span class="sxs-lookup"><span data-stu-id="6f660-132">.RM</span></span>
- <span data-ttu-id="6f660-133">MID</span><span class="sxs-lookup"><span data-stu-id="6f660-133">.MID</span></span>
- <span data-ttu-id="6f660-134">OGG</span><span class="sxs-lookup"><span data-stu-id="6f660-134">.OGG</span></span>
- <span data-ttu-id="6f660-135">AIFF</span><span class="sxs-lookup"><span data-stu-id="6f660-135">.AIFF</span></span>
- <span data-ttu-id="6f660-136">PCM</span><span class="sxs-lookup"><span data-stu-id="6f660-136">.PCM</span></span>
- <span data-ttu-id="6f660-137">AAC</span><span class="sxs-lookup"><span data-stu-id="6f660-137">.AAC</span></span>
- <span data-ttu-id="6f660-138">FLAC</span><span class="sxs-lookup"><span data-stu-id="6f660-138">.FLAC</span></span>
- <span data-ttu-id="6f660-139">ALAC</span><span class="sxs-lookup"><span data-stu-id="6f660-139">.ALAC</span></span>

## <a name="retain-cad-files"></a><span data-ttu-id="6f660-140">Сохранить файлы САПР</span><span class="sxs-lookup"><span data-stu-id="6f660-140">Retain CAD files</span></span>

<span data-ttu-id="6f660-141">Эта рекомендация отображается, если в SharePoint или OneDrive обнаружен любой из указанных ниже типов файлов.</span><span class="sxs-lookup"><span data-stu-id="6f660-141">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="6f660-142">3DXML</span><span class="sxs-lookup"><span data-stu-id="6f660-142">.3DXML</span></span>
- <span data-ttu-id="6f660-143">ACIS</span><span class="sxs-lookup"><span data-stu-id="6f660-143">.ACIS</span></span>
- <span data-ttu-id="6f660-144">ARC</span><span class="sxs-lookup"><span data-stu-id="6f660-144">.ARC</span></span>
- <span data-ttu-id="6f660-145">ASM</span><span class="sxs-lookup"><span data-stu-id="6f660-145">.ASM</span></span>
- <span data-ttu-id="6f660-146">CAT\*</span><span class="sxs-lookup"><span data-stu-id="6f660-146">.CAT\*</span></span>
- <span data-ttu-id="6f660-147">CGR</span><span class="sxs-lookup"><span data-stu-id="6f660-147">.CGR</span></span>
- <span data-ttu-id="6f660-148">DW\*</span><span class="sxs-lookup"><span data-stu-id="6f660-148">.DW\*</span></span>
- <span data-ttu-id="6f660-149">DX\*</span><span class="sxs-lookup"><span data-stu-id="6f660-149">.DX\*</span></span>
- <span data-ttu-id="6f660-150">EDRW</span><span class="sxs-lookup"><span data-stu-id="6f660-150">.EDRW</span></span>
- <span data-ttu-id="6f660-151">IAM</span><span class="sxs-lookup"><span data-stu-id="6f660-151">.IAM</span></span>
- <span data-ttu-id="6f660-152">IGES</span><span class="sxs-lookup"><span data-stu-id="6f660-152">.IGES</span></span>
- <span data-ttu-id="6f660-153">IGS</span><span class="sxs-lookup"><span data-stu-id="6f660-153">.IGS</span></span>
- <span data-ttu-id="6f660-154">IPT</span><span class="sxs-lookup"><span data-stu-id="6f660-154">.IPT</span></span>
- <span data-ttu-id="6f660-155">JT</span><span class="sxs-lookup"><span data-stu-id="6f660-155">.JT</span></span>
- <span data-ttu-id="6f660-156">MF1</span><span class="sxs-lookup"><span data-stu-id="6f660-156">.MF1</span></span>
- <span data-ttu-id="6f660-157">NEU</span><span class="sxs-lookup"><span data-stu-id="6f660-157">.NEU</span></span>
- <span data-ttu-id="6f660-158">PAR</span><span class="sxs-lookup"><span data-stu-id="6f660-158">.PAR</span></span>
- <span data-ttu-id="6f660-159">PKG</span><span class="sxs-lookup"><span data-stu-id="6f660-159">.PKG</span></span>
- <span data-ttu-id="6f660-160">PRC</span><span class="sxs-lookup"><span data-stu-id="6f660-160">.PRC</span></span>
- <span data-ttu-id="6f660-161">PRT</span><span class="sxs-lookup"><span data-stu-id="6f660-161">.PRT</span></span>
- <span data-ttu-id="6f660-162">PSM</span><span class="sxs-lookup"><span data-stu-id="6f660-162">.PSM</span></span>
- <span data-ttu-id="6f660-163">PWD</span><span class="sxs-lookup"><span data-stu-id="6f660-163">.PWD</span></span>
- <span data-ttu-id="6f660-164">SLD\*</span><span class="sxs-lookup"><span data-stu-id="6f660-164">.SLD\*</span></span>
- <span data-ttu-id="6f660-165">STEP</span><span class="sxs-lookup"><span data-stu-id="6f660-165">.STEP</span></span>
- <span data-ttu-id="6f660-166">STL</span><span class="sxs-lookup"><span data-stu-id="6f660-166">.STL</span></span>
- <span data-ttu-id="6f660-167">STP</span><span class="sxs-lookup"><span data-stu-id="6f660-167">.STP</span></span>
- <span data-ttu-id="6f660-168">U3D</span><span class="sxs-lookup"><span data-stu-id="6f660-168">.U3D</span></span>
- <span data-ttu-id="6f660-169">UNV</span><span class="sxs-lookup"><span data-stu-id="6f660-169">.UNV</span></span>
- <span data-ttu-id="6f660-170">VRML</span><span class="sxs-lookup"><span data-stu-id="6f660-170">.VRML</span></span>
- <span data-ttu-id="6f660-171">WRL</span><span class="sxs-lookup"><span data-stu-id="6f660-171">.WRL</span></span>
- <span data-ttu-id="6f660-172">X_\*</span><span class="sxs-lookup"><span data-stu-id="6f660-172">.X_\*</span></span>
- <span data-ttu-id="6f660-173">XAS</span><span class="sxs-lookup"><span data-stu-id="6f660-173">.XAS</span></span>
- <span data-ttu-id="6f660-174">XMT\*</span><span class="sxs-lookup"><span data-stu-id="6f660-174">.XMT\*</span></span>
- <span data-ttu-id="6f660-175">XPR</span><span class="sxs-lookup"><span data-stu-id="6f660-175">.XPR</span></span>

## <a name="retain-image-files"></a><span data-ttu-id="6f660-176">Сохранить файлы изображений</span><span class="sxs-lookup"><span data-stu-id="6f660-176">Retain image files</span></span>

<span data-ttu-id="6f660-177">Эта рекомендация отображается, если в SharePoint или OneDrive обнаружен любой из указанных ниже типов файлов.</span><span class="sxs-lookup"><span data-stu-id="6f660-177">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="6f660-178">JPEG</span><span class="sxs-lookup"><span data-stu-id="6f660-178">.JPEG</span></span>
- <span data-ttu-id="6f660-179">GIF</span><span class="sxs-lookup"><span data-stu-id="6f660-179">.GIF</span></span>
- <span data-ttu-id="6f660-180">TIF\*</span><span class="sxs-lookup"><span data-stu-id="6f660-180">.TIF\*</span></span>
- <span data-ttu-id="6f660-181">BMP</span><span class="sxs-lookup"><span data-stu-id="6f660-181">.BMP</span></span>
- <span data-ttu-id="6f660-182">PNG</span><span class="sxs-lookup"><span data-stu-id="6f660-182">.PNG</span></span>
- <span data-ttu-id="6f660-183">RAW</span><span class="sxs-lookup"><span data-stu-id="6f660-183">.RAW</span></span>
- <span data-ttu-id="6f660-184">PSD</span><span class="sxs-lookup"><span data-stu-id="6f660-184">.PSD</span></span>
- <span data-ttu-id="6f660-185">PSP</span><span class="sxs-lookup"><span data-stu-id="6f660-185">.PSP</span></span>
- <span data-ttu-id="6f660-186">JPG</span><span class="sxs-lookup"><span data-stu-id="6f660-186">.JPG</span></span>
- <span data-ttu-id="6f660-187">EXIF</span><span class="sxs-lookup"><span data-stu-id="6f660-187">.EXIF</span></span>
- <span data-ttu-id="6f660-188">PPM</span><span class="sxs-lookup"><span data-stu-id="6f660-188">.PPM</span></span>
- <span data-ttu-id="6f660-189">PGM</span><span class="sxs-lookup"><span data-stu-id="6f660-189">.PGM</span></span>
- <span data-ttu-id="6f660-190">PBM</span><span class="sxs-lookup"><span data-stu-id="6f660-190">.PBM</span></span>
- <span data-ttu-id="6f660-191">PNM</span><span class="sxs-lookup"><span data-stu-id="6f660-191">.PNM</span></span>
- <span data-ttu-id="6f660-192">WEBP</span><span class="sxs-lookup"><span data-stu-id="6f660-192">.WEBP</span></span>

## <a name="retain-nda-content"></a><span data-ttu-id="6f660-193">Сохранить содержимое о неразглашении</span><span class="sxs-lookup"><span data-stu-id="6f660-193">Retain NDA content</span></span> 

<span data-ttu-id="6f660-194">Эта рекомендация отображается при выполнении любого из указанных ниже условий.</span><span class="sxs-lookup"><span data-stu-id="6f660-194">This recommendation appears when either of the following criteria are met.</span></span>

- <span data-ttu-id="6f660-195">В тексте сообщения электронной почты обнаружено любое сочетание этих ключевых слов:</span><span class="sxs-lookup"><span data-stu-id="6f660-195">Any of combination of these keywords is detected in the body of an email message:</span></span>
    - <span data-ttu-id="6f660-196">NDA</span><span class="sxs-lookup"><span data-stu-id="6f660-196">NDA</span></span>
    - <span data-ttu-id="6f660-197">"Соглашение о нераспространении"</span><span class="sxs-lookup"><span data-stu-id="6f660-197">“Non-Disclosure Agreement”</span></span>
    - <span data-ttu-id="6f660-198">"Соглашение о неразглашении"</span><span class="sxs-lookup"><span data-stu-id="6f660-198">“Non Disclosure Agreement”</span></span>

- <span data-ttu-id="6f660-199">В файлах формата PDF или DOC в SharePoint или OneDrive обнаружено любое сочетание этих ключевых слов:</span><span class="sxs-lookup"><span data-stu-id="6f660-199">Any combination of these keywords are detected in .PDF or .DOC files in SharePoint or OneDrive:</span></span>
    - <span data-ttu-id="6f660-200">NDA</span><span class="sxs-lookup"><span data-stu-id="6f660-200">NDA</span></span>
    - <span data-ttu-id="6f660-201">Соглашение о неразглашении</span><span class="sxs-lookup"><span data-stu-id="6f660-201">Non Disclosure Agreement</span></span>

## <a name="retain-software-development-files"></a><span data-ttu-id="6f660-202">Сохранить файлы разработки программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="6f660-202">Retain software development files</span></span>

<span data-ttu-id="6f660-203">Эта рекомендация отображается, если в SharePoint или OneDrive обнаружен любой из указанных ниже типов файлов.</span><span class="sxs-lookup"><span data-stu-id="6f660-203">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="6f660-204">ASAX</span><span class="sxs-lookup"><span data-stu-id="6f660-204">.ASAX</span></span>
- <span data-ttu-id="6f660-205">ASM</span><span class="sxs-lookup"><span data-stu-id="6f660-205">.ASM</span></span>
- <span data-ttu-id="6f660-206">ASP\*</span><span class="sxs-lookup"><span data-stu-id="6f660-206">.ASP\*</span></span>
- <span data-ttu-id="6f660-207">BAT</span><span class="sxs-lookup"><span data-stu-id="6f660-207">.BAT</span></span>
- <span data-ttu-id="6f660-208">CONFIG</span><span class="sxs-lookup"><span data-stu-id="6f660-208">.CONFIG</span></span>
- <span data-ttu-id="6f660-209">CS</span><span class="sxs-lookup"><span data-stu-id="6f660-209">.CS</span></span>
- <span data-ttu-id="6f660-210">CSS</span><span class="sxs-lookup"><span data-stu-id="6f660-210">.CSS</span></span>
- <span data-ttu-id="6f660-211">DISCO</span><span class="sxs-lookup"><span data-stu-id="6f660-211">.DISCO</span></span>
- <span data-ttu-id="6f660-212">HTM\*</span><span class="sxs-lookup"><span data-stu-id="6f660-212">.HTM\*</span></span>
- <span data-ttu-id="6f660-213">INC</span><span class="sxs-lookup"><span data-stu-id="6f660-213">.INC</span></span>
- <span data-ttu-id="6f660-214">JAD</span><span class="sxs-lookup"><span data-stu-id="6f660-214">.JAD</span></span>
- <span data-ttu-id="6f660-215">JAVA</span><span class="sxs-lookup"><span data-stu-id="6f660-215">.JAVA</span></span>
- <span data-ttu-id="6f660-216">JS\*</span><span class="sxs-lookup"><span data-stu-id="6f660-216">.JS\*</span></span>
- <span data-ttu-id="6f660-217">LIB</span><span class="sxs-lookup"><span data-stu-id="6f660-217">.LIB</span></span>
- <span data-ttu-id="6f660-218">O</span><span class="sxs-lookup"><span data-stu-id="6f660-218">.O</span></span>
- <span data-ttu-id="6f660-219">PHP</span><span class="sxs-lookup"><span data-stu-id="6f660-219">.PHP</span></span>
- <span data-ttu-id="6f660-220">РК</span><span class="sxs-lookup"><span data-stu-id="6f660-220">.RC</span></span>
- <span data-ttu-id="6f660-221">RESX</span><span class="sxs-lookup"><span data-stu-id="6f660-221">.RESX</span></span>
- <span data-ttu-id="6f660-222">RPT</span><span class="sxs-lookup"><span data-stu-id="6f660-222">.RPT</span></span>
- <span data-ttu-id="6f660-223">RSS</span><span class="sxs-lookup"><span data-stu-id="6f660-223">.RSS</span></span>
- <span data-ttu-id="6f660-224">SCPT</span><span class="sxs-lookup"><span data-stu-id="6f660-224">.SCPT</span></span>
- <span data-ttu-id="6f660-225">SRC</span><span class="sxs-lookup"><span data-stu-id="6f660-225">.SRC</span></span>
- <span data-ttu-id="6f660-226">VB\*</span><span class="sxs-lookup"><span data-stu-id="6f660-226">.VB\*</span></span>
- <span data-ttu-id="6f660-227">WSF</span><span class="sxs-lookup"><span data-stu-id="6f660-227">.WSF</span></span>
- <span data-ttu-id="6f660-228">XCODEPROJ</span><span class="sxs-lookup"><span data-stu-id="6f660-228">.XCODEPROJ</span></span>
- <span data-ttu-id="6f660-229">XML</span><span class="sxs-lookup"><span data-stu-id="6f660-229">.XML</span></span>
- <span data-ttu-id="6f660-230">XSD</span><span class="sxs-lookup"><span data-stu-id="6f660-230">.XSD</span></span>
- <span data-ttu-id="6f660-231">XSL\*</span><span class="sxs-lookup"><span data-stu-id="6f660-231">.XSL\*</span></span>

## <a name="retain-video-files"></a><span data-ttu-id="6f660-232">Сохранить видеофайлы</span><span class="sxs-lookup"><span data-stu-id="6f660-232">Retain video files</span></span>

<span data-ttu-id="6f660-233">Эта рекомендация отображается, если в SharePoint или OneDrive обнаружен любой из указанных ниже типов файлов.</span><span class="sxs-lookup"><span data-stu-id="6f660-233">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="6f660-234">AVCHD</span><span class="sxs-lookup"><span data-stu-id="6f660-234">.AVCHD</span></span>
- <span data-ttu-id="6f660-235">AVI</span><span class="sxs-lookup"><span data-stu-id="6f660-235">.AVI</span></span>
- <span data-ttu-id="6f660-236">FLV</span><span class="sxs-lookup"><span data-stu-id="6f660-236">.FLV</span></span>
- <span data-ttu-id="6f660-237">MOV</span><span class="sxs-lookup"><span data-stu-id="6f660-237">.MOV</span></span>
- <span data-ttu-id="6f660-238">MP2V</span><span class="sxs-lookup"><span data-stu-id="6f660-238">.MP2V</span></span>
- <span data-ttu-id="6f660-239">MP4</span><span class="sxs-lookup"><span data-stu-id="6f660-239">.MP4</span></span>
- <span data-ttu-id="6f660-240">MP4V</span><span class="sxs-lookup"><span data-stu-id="6f660-240">.MP4V</span></span>
- <span data-ttu-id="6f660-241">MPE</span><span class="sxs-lookup"><span data-stu-id="6f660-241">.MPE</span></span>
- <span data-ttu-id="6f660-242">MPEG</span><span class="sxs-lookup"><span data-stu-id="6f660-242">.MPEG</span></span>
- <span data-ttu-id="6f660-243">MPEG1</span><span class="sxs-lookup"><span data-stu-id="6f660-243">.MPEG1</span></span>
- <span data-ttu-id="6f660-244">MPEG2</span><span class="sxs-lookup"><span data-stu-id="6f660-244">.MPEG2</span></span>
- <span data-ttu-id="6f660-245">MPEG4</span><span class="sxs-lookup"><span data-stu-id="6f660-245">.MPEG4</span></span>
- <span data-ttu-id="6f660-246">MPG</span><span class="sxs-lookup"><span data-stu-id="6f660-246">.MPG</span></span>
- <span data-ttu-id="6f660-247">MPG2</span><span class="sxs-lookup"><span data-stu-id="6f660-247">.MPG2</span></span>
- <span data-ttu-id="6f660-248">MPG4</span><span class="sxs-lookup"><span data-stu-id="6f660-248">.MPG4</span></span>
- <span data-ttu-id="6f660-249">WMV</span><span class="sxs-lookup"><span data-stu-id="6f660-249">.WMV</span></span>
- <span data-ttu-id="6f660-250">XMV</span><span class="sxs-lookup"><span data-stu-id="6f660-250">.XMV</span></span>
