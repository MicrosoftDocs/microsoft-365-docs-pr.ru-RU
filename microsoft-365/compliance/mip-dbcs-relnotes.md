---
title: Поддержка соответствия требованиям Microsoft 365 для заметок к выпуску набора двухбайтовых символов (предварительная версия)
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Заметки к выпуску для поддержки наборов двухбайтовых символов.
ms.openlocfilehash: 1c2244c49a92aa2c00fad06caa8194cf7e32220e
ms.sourcegitcommit: 554755bc9ce40228ce6e34bde6fc6e226869b6a1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2020
ms.locfileid: "48681505"
---
# <a name="support-for-double-byte-character-set-release-notes-preview"></a><span data-ttu-id="b1f16-103">Поддержка для заметок к выпуску набора двухбайтовых символов (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="b1f16-103">Support for double byte character set release notes (preview)</span></span>

 <span data-ttu-id="b1f16-104">Служба защиты информации Microsoft 365 теперь в предварительный версии поддерживает языки с набором двухбайтовых символов:</span><span class="sxs-lookup"><span data-stu-id="b1f16-104">Microsoft 365 Information Protection now supports in preview double byte character set languages for:</span></span>

- <span data-ttu-id="b1f16-105">Китайский (упрощенное письмо)</span><span class="sxs-lookup"><span data-stu-id="b1f16-105">Chinese (simplified)</span></span>
- <span data-ttu-id="b1f16-106">Китайский (традиционное письмо)</span><span class="sxs-lookup"><span data-stu-id="b1f16-106">Chinese (traditional)</span></span>
- <span data-ttu-id="b1f16-107">Корейский</span><span class="sxs-lookup"><span data-stu-id="b1f16-107">Korean</span></span>
- <span data-ttu-id="b1f16-108">Японский</span><span class="sxs-lookup"><span data-stu-id="b1f16-108">Japanese</span></span>

<span data-ttu-id="b1f16-109">Эта поддержка доступна для типов конфиденциальной информации и словарей ключевых слов, и она будет отражаться в виде защиты от потери данных, обеспечения соответствия требованиям, Exchange Online, SharePoint Online, OneDrive для бизнеса и решений Teams.</span><span class="sxs-lookup"><span data-stu-id="b1f16-109">This support is available for sensitive information types and keyword dictionaries and will be reflected in data loss prevention, communications compliance, Exchange Online, SharePoint Online, OneDrive for Business, and Teams solutions.</span></span>

## <a name="known-issues"></a><span data-ttu-id="b1f16-110">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="b1f16-110">Known issues</span></span>

- <span data-ttu-id="b1f16-111">Если текстовый файл, вложенный в сообщение электронной почты, имеет формат UTF-8 без метки порядка байтов (BOM), то сообщение электронной почты не определяется политикой соответствия требованиям к обмену данными.</span><span class="sxs-lookup"><span data-stu-id="b1f16-111">When a text file attached to an email is in UTF-8 format without byte order mark (BOM), the email is not detected by the Communication Compliance policy.</span></span>

- <span data-ttu-id="b1f16-112">Политики соответствия требованиям к обмену данными не определяют значения, если предложение введено для условия политики: "Сообщение содержит любое из этих слов".</span><span class="sxs-lookup"><span data-stu-id="b1f16-112">Communication Compliance policies cannot detect values if a sentence is entered for the policy condition: “Message contains any of these words”.</span></span> <span data-ttu-id="b1f16-113">Если указанный в политике текст написан как слово, то он может быть обнаружен. Однако, если он написан в середине предложения, то он не будет обнаружен.</span><span class="sxs-lookup"><span data-stu-id="b1f16-113">If the text specified in the policy is written as a word, it can be detected; however, if it is written in the middle of a sentence, it will not be detected.</span></span>

- <span data-ttu-id="b1f16-114">Политики соответствия требованиям к обмену данными, которые определяют словари как информацию о типе, не определяют приватные чаты Teams и чаты в каналах.</span><span class="sxs-lookup"><span data-stu-id="b1f16-114">Communication Compliance policies that specify dictionaries as type information do not detect Teams private chats and channel chats.</span></span>

- <span data-ttu-id="b1f16-115">Указанные ниже условия не поддерживаются для обеспечения соответствия требованиям к обмену данными на этом этапе (мы планируем устранить эти проблемы в будущем).</span><span class="sxs-lookup"><span data-stu-id="b1f16-115">The following conditions are not supported for Communication Compliance at this stage (we plan to fix these issues in the future):</span></span> 
  - <span data-ttu-id="b1f16-116">“Сообщение содержит любое из этих слов”</span><span class="sxs-lookup"><span data-stu-id="b1f16-116">“Message contains any of these words”</span></span>
  - <span data-ttu-id="b1f16-117">“Сообщение не содержит ни одного из этих слов”</span><span class="sxs-lookup"><span data-stu-id="b1f16-117">“Message contains none of these words”</span></span>
  - <span data-ttu-id="b1f16-118">“Вложение содержит любое из этих слов”</span><span class="sxs-lookup"><span data-stu-id="b1f16-118">“Attachment contains any of these words”</span></span>
  - <span data-ttu-id="b1f16-119">“Вложение содержит любое из этих слов”</span><span class="sxs-lookup"><span data-stu-id="b1f16-119">“Attachment contains any of these words”</span></span>

<span data-ttu-id="b1f16-120">Вместо этого мы рекомендуем создать настраиваемый тип конфиденциальной информации (SIT) с помощью словаря ключевых слов, который будет определять шаблоны во всех сообщениях и вложениях, а также использовать этот SIT в качестве условия политики соответствия требованиям к обмену данными.</span><span class="sxs-lookup"><span data-stu-id="b1f16-120">Instead we recommend creating a custom Sensitive Information Type (SIT) with keyword dictionary which will detect patterns across messages and attachments, and using this custom SIT as a Communication Compliance policy condition.</span></span>
