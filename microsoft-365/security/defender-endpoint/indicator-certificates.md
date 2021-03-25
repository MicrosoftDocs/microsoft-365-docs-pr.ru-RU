---
title: Создание индикаторов на основе сертификатов
ms.reviewer: ''
description: Создание индикаторов на основе сертификатов, определяющих обнаружение, предотвращение и исключение сущностями.
keywords: ioc, сертификат, сертификаты, управление, разрешено, заблокировано, блок, чистый, вредоносный, файл, IP-адрес, URL-адрес, домен
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8cf611e38bc781c2302f70f6491bb827410235b0
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164685"
---
# <a name="create-indicators-based-on-certificates"></a><span data-ttu-id="8d845-104">Создание индикаторов на основе сертификатов</span><span class="sxs-lookup"><span data-stu-id="8d845-104">Create indicators based on certificates</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="8d845-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="8d845-105">**Applies to:**</span></span>
- [<span data-ttu-id="8d845-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="8d845-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8d845-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8d845-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="8d845-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="8d845-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8d845-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="8d845-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="8d845-110">Можно создавать индикаторы для сертификатов.</span><span class="sxs-lookup"><span data-stu-id="8d845-110">You can create indicators for certificates.</span></span> <span data-ttu-id="8d845-111">К числу распространенных случаев использования относятся следующие:</span><span class="sxs-lookup"><span data-stu-id="8d845-111">Some common use cases include:</span></span>

- <span data-ttu-id="8d845-112">Сценарии, когда необходимо развернуть технологии блокировки, такие [](controlled-folders.md) как правила уменьшения поверхности атаки и управляемый доступ к папкам, но необходимо разрешить поведение подписанных приложений, добавив сертификат в список допустимых. [](attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="8d845-112">Scenarios when you need to deploy blocking technologies, such as [attack surface reduction rules](attack-surface-reduction.md) and [controlled folder access](controlled-folders.md) but need to allow behaviors from signed applications by adding the certificate in the allow list.</span></span>
- <span data-ttu-id="8d845-113">Блокировка использования определенного подписанного приложения в организации.</span><span class="sxs-lookup"><span data-stu-id="8d845-113">Blocking the use of a specific signed application across your organization.</span></span> <span data-ttu-id="8d845-114">Создав индикатор для блокировки сертификата приложения, Защитник Windows av предотвратит выполнение файлов (блок и исправление), а автоматическое расследование и исправление ведут себя так же.</span><span class="sxs-lookup"><span data-stu-id="8d845-114">By creating an indicator to block the certificate of the application, Windows Defender AV will prevent file executions (block and remediate) and the Automated Investigation and Remediation behave the same.</span></span>


### <a name="before-you-begin"></a><span data-ttu-id="8d845-115">Перед началом работы</span><span class="sxs-lookup"><span data-stu-id="8d845-115">Before you begin</span></span>

<span data-ttu-id="8d845-116">Важно понимать следующие требования перед созданием индикаторов для сертификатов:</span><span class="sxs-lookup"><span data-stu-id="8d845-116">It's important to understand the following requirements prior to creating indicators for certificates:</span></span>

- <span data-ttu-id="8d845-117">Эта функция доступна, если в организации Защитник Windows включена антивирусная и облачная защита.</span><span class="sxs-lookup"><span data-stu-id="8d845-117">This feature is available if your organization uses Windows Defender Antivirus and Cloud-based protection is enabled.</span></span> <span data-ttu-id="8d845-118">Дополнительные сведения см. в [сведениях Управление облачной защитой.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="8d845-118">For more information, see [Manage cloud-based protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).</span></span>
- <span data-ttu-id="8d845-119">Клиентская версия antimalware должна быть 4.18.1901.x или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="8d845-119">The Antimalware client version must be  4.18.1901.x or later.</span></span>
- <span data-ttu-id="8d845-120">Поддерживается на компьютерах в Windows 10, версии 1703 или более поздней версии, Windows server 2016 и 2019.</span><span class="sxs-lookup"><span data-stu-id="8d845-120">Supported on machines on Windows 10, version 1703 or later, Windows server 2016 and 2019.</span></span>
- <span data-ttu-id="8d845-121">Определения защиты от вирусов и угроз должны быть в курсе.</span><span class="sxs-lookup"><span data-stu-id="8d845-121">The virus and threat protection definitions must be up to date.</span></span>
- <span data-ttu-id="8d845-122">Эта функция в настоящее время поддерживает ввод . CER или . Расширения файлов PEM.</span><span class="sxs-lookup"><span data-stu-id="8d845-122">This feature currently supports entering .CER or .PEM file extensions.</span></span>

>[!IMPORTANT]
> - <span data-ttu-id="8d845-123">Действительный сертификат листа — это сертификат подписи, который имеет допустимый путь сертификации и должен быть прикован к Службе корневого сертификата (CA), доверяемой Корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="8d845-123">A valid leaf certificate is a signing certificate that has a valid certification path and must be chained to the Root Certificate Authority (CA) trusted by Microsoft.</span></span>  <span data-ttu-id="8d845-124">Кроме того, пользовательский (самозаверяемый) сертификат можно использовать до тех пор, пока ему доверяет клиент (сертификат Root CA устанавливается в соответствии с локальным механизмом "Доверенные корневые органы сертификации").</span><span class="sxs-lookup"><span data-stu-id="8d845-124">Alternatively, a custom (self-signed) certificate can be used as long as it's trusted by the client (Root CA certificate is installed under the Local Machine 'Trusted Root Certification Authorities').</span></span>
>- <span data-ttu-id="8d845-125">Дети или родители IOCs разрешаемого или блокового сертификата не включаются в функцию allow/block IoC, поддерживаются только сертификаты листа.</span><span class="sxs-lookup"><span data-stu-id="8d845-125">The children or parent of the allow/block certificate IOCs are not included in the allow/block IoC functionality, only leaf certificates are supported.</span></span>
>- <span data-ttu-id="8d845-126">Сертификаты, подписанные Корпорацией Майкрософт, не могут быть заблокированы.</span><span class="sxs-lookup"><span data-stu-id="8d845-126">Microsoft signed certificates cannot be blocked.</span></span>

#### <a name="create-an-indicator-for-certificates-from-the-settings-page"></a><span data-ttu-id="8d845-127">Создание индикатора для сертификатов на странице параметры:</span><span class="sxs-lookup"><span data-stu-id="8d845-127">Create an indicator for certificates from the settings page:</span></span>

>[!IMPORTANT]
> <span data-ttu-id="8d845-128">Создание и удаление IoC сертификата может занять до 3 часов.</span><span class="sxs-lookup"><span data-stu-id="8d845-128">It can take up to 3 hours to create and remove a certificate IoC.</span></span>

1. <span data-ttu-id="8d845-129">В области навигации выберите **Параметры**  >  **Индикаторы**.</span><span class="sxs-lookup"><span data-stu-id="8d845-129">In the navigation pane, select **Settings** > **Indicators**.</span></span>  

2. <span data-ttu-id="8d845-130">Выберите **вкладку Сертификат.**</span><span class="sxs-lookup"><span data-stu-id="8d845-130">Select the **Certificate** tab.</span></span>

3. <span data-ttu-id="8d845-131">Выберите **индикатор Добавить**.</span><span class="sxs-lookup"><span data-stu-id="8d845-131">Select **Add indicator**.</span></span>

4. <span data-ttu-id="8d845-132">Укажите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="8d845-132">Specify the following details:</span></span>
   - <span data-ttu-id="8d845-133">Индикатор . Укажите сведения об объекте и определите срок действия индикатора.</span><span class="sxs-lookup"><span data-stu-id="8d845-133">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
   - <span data-ttu-id="8d845-134">Действие . Укажите действия, которые необходимо принять, и укажите описание.</span><span class="sxs-lookup"><span data-stu-id="8d845-134">Action - Specify the action to be taken and provide a description.</span></span>
   - <span data-ttu-id="8d845-135">Область — определите область действия группы машин.</span><span class="sxs-lookup"><span data-stu-id="8d845-135">Scope - Define the scope of the machine group.</span></span>

5. <span data-ttu-id="8d845-136">Просмотрите сведения в вкладке Сводка, а затем нажмите **кнопку Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="8d845-136">Review the details in the Summary tab, then click **Save**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8d845-137">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="8d845-137">Related topics</span></span>
- [<span data-ttu-id="8d845-138">Создание индикаторов</span><span class="sxs-lookup"><span data-stu-id="8d845-138">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="8d845-139">Создание индикаторов для файлов</span><span class="sxs-lookup"><span data-stu-id="8d845-139">Create indicators for files</span></span>](indicator-file.md)
- [<span data-ttu-id="8d845-140">Создание индикаторов для IPs и URL-адресов/доменов</span><span class="sxs-lookup"><span data-stu-id="8d845-140">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="8d845-141">Управление индикаторами</span><span class="sxs-lookup"><span data-stu-id="8d845-141">Manage indicators</span></span>](indicator-manage.md)