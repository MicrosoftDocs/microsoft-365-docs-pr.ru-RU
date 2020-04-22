---
title: Шаг 5. Настройка защиты от потери данных
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Сведения о защите от потери данных в Microsoft 365 и о развертывании этой защиты.
ms.openlocfilehash: e3d18bf54ecdfe11f8233163e7f200a70606d81d
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636980"
---
# <a name="step-5-configure-data-loss-prevention"></a><span data-ttu-id="ec0a6-103">Шаг 5. Настройка защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="ec0a6-103">Step 5: Configure Data Loss Prevention</span></span>

<span data-ttu-id="ec0a6-104">*Этот этап не является обязательным. Он применяется к планам E3 и E5 Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="ec0a6-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Этап 6. Защита данных](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="ec0a6-106">Политики защиты от потери данных (DLP) в Центре безопасности и соответствия требованиям позволяют определять, отслеживать и автоматически защищать конфиденциальную информацию в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ec0a6-106">With data loss prevention (DLP) policies in the Security & Compliance center, you can identify, monitor, and automatically protect sensitive information across Microsoft 365.</span></span> <span data-ttu-id="ec0a6-107">С помощью политик защиты от потери данных вы можете:</span><span class="sxs-lookup"><span data-stu-id="ec0a6-107">With DLP policies, you can:</span></span>

- <span data-ttu-id="ec0a6-108">выявлять конфиденциальную информацию во множестве расположений, таких как Exchange Online, SharePoint Online, OneDrive для бизнеса и Microsoft Teams;</span><span class="sxs-lookup"><span data-stu-id="ec0a6-108">Identify sensitive information across many locations, such as Exchange Online, SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>
- <span data-ttu-id="ec0a6-109">предотвращать непреднамеренное разглашение конфиденциальной информации, блокируя доступ к документу или отправку содержащего его электронного сообщения;</span><span class="sxs-lookup"><span data-stu-id="ec0a6-109">Prevent the accidental sharing of sensitive information by blocking access to a document or blocking the email that contains it.</span></span>
- <span data-ttu-id="ec0a6-110">отслеживать и защищать конфиденциальную информацию в классических версиях Excel, PowerPoint и Word;</span><span class="sxs-lookup"><span data-stu-id="ec0a6-110">Monitor and protect sensitive information in the desktop versions of Excel, PowerPoint, and Word.</span></span>
- <span data-ttu-id="ec0a6-111">помогать пользователям соответствовать требованиям организации, не прерывая рабочий процесс уведомлениями электронной почты и подсказками политик;</span><span class="sxs-lookup"><span data-stu-id="ec0a6-111">Help users learn how to stay compliant without interrupting their workflow with email notifications and policy tips.</span></span> 
- <span data-ttu-id="ec0a6-112">просматривать отчеты DLP, в которых перечисляется содержимое, нарушающее политики защиты от потери данных вашей организации.</span><span class="sxs-lookup"><span data-stu-id="ec0a6-112">View DLP reports showing content that matches your organization's DLP policies.</span></span>

<span data-ttu-id="ec0a6-113">Политика защиты от потери данных указывает перечисленные ниже сведения.</span><span class="sxs-lookup"><span data-stu-id="ec0a6-113">A DLP policy specifies:</span></span>

- <span data-ttu-id="ec0a6-114">**Где:** такие расположения, как сайты Exchange Online, SharePoint Online и OneDrive для бизнеса, а также чаты и каналы Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ec0a6-114">**Where:** Locations such as Exchange Online, SharePoint Online, and OneDrive for Business sites, as well as Microsoft Teams chats and channels.</span></span>
- <span data-ttu-id="ec0a6-115">**Когда:** условия, которым должно отвечать содержимое в рамках определенного правила политики.</span><span class="sxs-lookup"><span data-stu-id="ec0a6-115">**When:** Conditions the content must match within a specific policy rule.</span></span>
- <span data-ttu-id="ec0a6-116">**Как:** действия этого правила политики, автоматически выполняемые для соответствующих условий.</span><span class="sxs-lookup"><span data-stu-id="ec0a6-116">**How:** Actions within that matching policy rule to take automatically for the matching conditions.</span></span>

<span data-ttu-id="ec0a6-117">Другими словами:</span><span class="sxs-lookup"><span data-stu-id="ec0a6-117">In other words:</span></span>

- <span data-ttu-id="ec0a6-118">для документа в этом расположении (где), если содержимое отвечает условиям правила (когда), автоматически выполняются действия, заданные в правиле (как).</span><span class="sxs-lookup"><span data-stu-id="ec0a6-118">For a document in this location (where), if the content matches the conditions of a rule (when), then automatically take the actions specified in the rule (how).</span></span>

<span data-ttu-id="ec0a6-119">Чтобы определить необходимый набор политик DLP, необходимо анализировать документы и содержащиеся в них типы данных, которые нуждаются в защите от потери данных.</span><span class="sxs-lookup"><span data-stu-id="ec0a6-119">To determine the set of DLP policies you need, you must analyze your documents and the types of data within them that need protection from data loss.</span></span> <span data-ttu-id="ec0a6-120">Например, если вы представляете финансовую организацию из Соединенных Штатов Америки, то вы можете создать политику защиты от потери данных, которая предотвращает передачу документов с номерами социального страхования за пределы организации и их отправку по электронной почте на сторонние адреса.</span><span class="sxs-lookup"><span data-stu-id="ec0a6-120">For example, if you are a financial organization in the United States of America, you would create a DLP policy that prevents documents with social security numbers from being shared outside the organization or sent in email to locations outside the organization.</span></span>

<span data-ttu-id="ec0a6-121">Затем вы настроите и испытаете политики с помощью тестовых расположений, чтобы обеспечить корректную работу защиту от потери данных и свести к минимуму количество ложных срабатываний.</span><span class="sxs-lookup"><span data-stu-id="ec0a6-121">Next, you configure and test the policies with test locations to ensure the correct DLP behavior and to minimize false positives.</span></span>

<span data-ttu-id="ec0a6-122">Напоследок вы развернете ее в своей организации, сообщив сотрудникам о новых политиках и расширив область расположений.</span><span class="sxs-lookup"><span data-stu-id="ec0a6-122">Finally, you roll it out to your organization by informing the employees of the new policies and their desired behavior and widening the scope of the locations.</span></span>

<span data-ttu-id="ec0a6-123">Дополнительные сведения см. в статье [Рекомендации по началу работы с политикой DLP](https://docs.microsoft.com/office365/securitycompliance/get-started-with-dlp-policy-recommendations).</span><span class="sxs-lookup"><span data-stu-id="ec0a6-123">For more information, see [Get started with DLP policy recommendations](https://docs.microsoft.com/office365/securitycompliance/get-started-with-dlp-policy-recommendations).</span></span>

<span data-ttu-id="ec0a6-124">Прежде чем перейти к следующему шагу, проверьте [условия](infoprotect-exit-criteria.md#crit-infoprotect-step5), при выполнении которых можно считать данный шаг завершенным.</span><span class="sxs-lookup"><span data-stu-id="ec0a6-124">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step5) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="ec0a6-125">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="ec0a6-125">Next step</span></span>

|||
|:-------|:-----|
|![Шаг 6](../media/stepnumbers/Step6.png)|[<span data-ttu-id="ec0a6-127">Настройка шифрования электронной почты</span><span class="sxs-lookup"><span data-stu-id="ec0a6-127">Configure email encryption</span></span>](infoprotect-email-encryption.md)|


