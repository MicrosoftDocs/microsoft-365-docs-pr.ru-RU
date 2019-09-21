---
title: GDPR для локальных общих папок
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
description: Узнайте, как обеспечивать соблюдение требований GDPR в локальных общих папках Windows Server.
ms.openlocfilehash: b5d5023ec8a052dc51575fa01f9cb77c4bf001c4
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37089494"
---
# <a name="gdpr-for-on-premises-windows-server-file-shares"></a><span data-ttu-id="fe715-103">GDPR для локальных общих папок Windows Server</span><span class="sxs-lookup"><span data-stu-id="fe715-103">GDPR for on-premises Windows Server file shares</span></span>

<span data-ttu-id="fe715-104">Основной рекомендуемый подход для общих папок:</span><span class="sxs-lookup"><span data-stu-id="fe715-104">The basic recommended approach for file shares is:</span></span>

-   <span data-ttu-id="fe715-105">Используйте Azure Information Protection для пометки конфиденциальных данных.</span><span class="sxs-lookup"><span data-stu-id="fe715-105">Use Azure Information Protection to label sensitive data.</span></span>

-   <span data-ttu-id="fe715-106">Используйте сканер Azure Information Protection для поиска данных.</span><span class="sxs-lookup"><span data-stu-id="fe715-106">Use Azure Information Protection scanner to find data.</span></span>

<span data-ttu-id="fe715-107">Рекомендуемый подход для общих папок включает следующие действия:</span><span class="sxs-lookup"><span data-stu-id="fe715-107">The recommended approach for files shares includes these steps:</span></span>

1.  <span data-ttu-id="fe715-108">**Установите и настройте сканер Azure Information Protection.**</span><span class="sxs-lookup"><span data-stu-id="fe715-108">**Install and configure Azure Information Protection scanner.**</span></span>

    -   <span data-ttu-id="fe715-109">Выберите необходимые типы конфиденциальных данных.</span><span class="sxs-lookup"><span data-stu-id="fe715-109">Decide which sensitive data types to use.</span></span>

    -   <span data-ttu-id="fe715-110">Укажите необходимые локальные и сетевые папки.</span><span class="sxs-lookup"><span data-stu-id="fe715-110">Specify local folders and network shares to use.</span></span>

2.  <span data-ttu-id="fe715-111">**Выполните цикл обнаружения.**</span><span class="sxs-lookup"><span data-stu-id="fe715-111">**Complete a discovery cycle.**</span></span>

    -   <span data-ttu-id="fe715-112">Запустите сканер в режиме обнаружения и проверьте обнаруженные данные.</span><span class="sxs-lookup"><span data-stu-id="fe715-112">Run the scanner in discovery mode and validate the findings.</span></span>

    -   <span data-ttu-id="fe715-113">При необходимости оптимизируйте условия и типы конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="fe715-113">If needed, optimize the conditions and sensitive information types.</span></span>

    -   <span data-ttu-id="fe715-114">Оцените ожидаемое воздействие автоматического применения меток.</span><span class="sxs-lookup"><span data-stu-id="fe715-114">Assess the expected impact of automatically applying labels.</span></span>

3.  <span data-ttu-id="fe715-115">**Запустите сканер Azure Information Protection для применения меток к соответствующим документам**.</span><span class="sxs-lookup"><span data-stu-id="fe715-115">**Run the Azure Information Protection scanner to apply labels to qualifying documents**.</span></span>

4.  <span data-ttu-id="fe715-116">**Для защиты:**</span><span class="sxs-lookup"><span data-stu-id="fe715-116">**For protection:**</span></span>

    -   <span data-ttu-id="fe715-117">Настройте правила защиты от потери данных в Exchange, чтобы защитить документы с нужной меткой.</span><span class="sxs-lookup"><span data-stu-id="fe715-117">Configure Exchange data loss prevention rules to protect documents with the desired label.</span></span>

    -   <span data-ttu-id="fe715-118">Обязательно используйте разрешения, чтобы ограничить доступ к файлам.</span><span class="sxs-lookup"><span data-stu-id="fe715-118">Be sure to use permissions to limit who can access files.</span></span>

5.  <span data-ttu-id="fe715-119">**Интегрируйте журналы Windows Server со средством SIEM для мониторинга.**</span><span class="sxs-lookup"><span data-stu-id="fe715-119">**For monitoring, integrate Windows Server logs with a SIEM tool.**</span></span>

    -   <span data-ttu-id="fe715-p101">Чтобы находить персональные данные для запросов субъектов данных, используйте сканер Azure Information Protection. Вы также можете включить обход общих папок в настройках поиска SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="fe715-p101">To find personal data for data subject requests, use Azure Information Protection scanner. You can also configure SharePoint Server search to crawl file shares.</span></span>

<span data-ttu-id="fe715-122">Дополнительные сведения об использовании сканера Azure Information Protection для поиска и пометки персональных данных см. в наборе средств для обнаружения данных GDPR (Майкрософт) на странице [http://aka.ms/gdprpartners](<http://aka.ms/gdprpartners>).</span><span class="sxs-lookup"><span data-stu-id="fe715-122">For more information on using Azure Information Protection scanner to find and label personal data, see the Microsoft GDPR Data Discovery Toolkit at [http://aka.ms/gdprpartners](<http://aka.ms/gdprpartners>).</span></span>

<span data-ttu-id="fe715-p102">Сведения о настройке сканера в соответствии с условиями и использовании типов конфиденциальной информации для защиты от потери данных (DLP) в Office 365 см. в статье [Как настроить условия для автоматической и рекомендуемой классификации с помощью Azure Information Protection](https://docs.microsoft.com/ru-RU/information-protection/deploy-use/configure-policy-classification). Обратите внимание, что новые типы конфиденциальной информации Office 365 не сразу станут доступны для использования в сканере. Кроме того, в нем невозможно использовать пользовательские типы конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="fe715-p102">For information on configuring the scanner for conditions and using the Office 365 data loss prevention (DLP) sensitive information types, see [How to configure conditions for automatic and recommended classification for Azure Information Protection](https://docs.microsoft.com/ru-RU/information-protection/deploy-use/configure-policy-classification). Note that new Office 365 sensitive information types will not be immediately available to use with the scanner and custom sensitive information types cannot be used with the scanner.</span></span>
