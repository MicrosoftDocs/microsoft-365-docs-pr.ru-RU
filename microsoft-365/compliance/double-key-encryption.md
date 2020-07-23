---
title: Шифрование с двойным ключом (ДКЕ)
description: ДКЕ позволяет защищать строго конфиденциальные данные, обеспечивая полный контроль над ключом.
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 07/21/2020
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: d9ed155576d69889e53e4e4d1ce03e4233fd08ff
ms.sourcegitcommit: 4789b261eb029d7c965421a1260acc110e6385db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "45387446"
---
# <a name="double-key-encryption-dke"></a><span data-ttu-id="8ca4d-103">Шифрование с двойным ключом (ДКЕ)</span><span class="sxs-lookup"><span data-stu-id="8ca4d-103">Double Key Encryption (DKE)</span></span>

> <span data-ttu-id="8ca4d-104">*Применимо к: шифрование с двойным ключом для Microsoft 365 общедоступная Предварительная версия, [соответствие требованиям microsoft 365](https://www.microsoft.com/microsoft-365/business/compliance-management), [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*</span><span class="sxs-lookup"><span data-stu-id="8ca4d-104">*Applies to: Double Key Encryption for Microsoft 365 public preview, [Microsoft 365 Compliance](https://www.microsoft.com/microsoft-365/business/compliance-management), [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*</span></span>
>
> <span data-ttu-id="8ca4d-105">*Инструкции для: [клиент единой метки Azure Information Protection для Windows](https://docs.microsoft.com/azure/information-protection/faqs.md#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span><span class="sxs-lookup"><span data-stu-id="8ca4d-105">*Instructions for: [Azure Information Protection unified labeling client for Windows](https://docs.microsoft.com/azure/information-protection/faqs.md#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span></span>
>
> <span data-ttu-id="8ca4d-106">*Описание службы: [соответствие требованиям Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span><span class="sxs-lookup"><span data-stu-id="8ca4d-106">*Service description for: [Microsoft 365 Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span></span>

<span data-ttu-id="8ca4d-107">С помощью двойного шифрования (ДКЕ) для доступа к защищенному содержимому используются два ключа.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-107">Double Key Encryption (DKE) uses two keys together to access protected content.</span></span> <span data-ttu-id="8ca4d-108">Вы храните один ключ в Microsoft Azure, и вы держите другой ключ.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-108">You store one key in Microsoft Azure, and you hold the other key.</span></span> <span data-ttu-id="8ca4d-109">Клиент единой метки Azure Information Protection защищает строго конфиденциальный контент, пока вы сохраняете полный контроль над одним из ваших ключей.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-109">The Azure Information Protection unified labeling client protects highly sensitive content while you maintain full control of one of your keys.</span></span>

<span data-ttu-id="8ca4d-110">Двойное шифрование поддерживает развертывания как в облаке, так и в локальных развертываниях.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-110">Double Key Encryption supports both cloud and on-premises deployments.</span></span> <span data-ttu-id="8ca4d-111">Эти развертывания помогают убедиться, что зашифрованные данные остаются непрозрачными везде, где хранятся защищенные данные.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-111">These deployments help to ensure that encrypted data remains opaque wherever you store the protected data.</span></span>

<span data-ttu-id="8ca4d-112">Дополнительные сведения о корневых ключах облачных клиентов по умолчанию можно найти в статье [планирование и реализация ключа клиента Azure Information Protection](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key).</span><span class="sxs-lookup"><span data-stu-id="8ca4d-112">For more information about the default, cloud-based tenant root keys, see [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key).</span></span>

<span data-ttu-id="8ca4d-113">В следующем видеоролике показано, как работает двойное шифрование для защиты контента.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-113">The following video shows how Double Key Encryption works to secure your content.</span></span>

> [!VIDEO https://msit.microsoftstream.com/embed/video/f466a1ff-0400-a936-221c-f1eab45dc756]

<span data-ttu-id="8ca4d-114">Если у вашей организации есть какие – либо из следующих требований, вы можете использовать ДКЕ для защиты своего содержимого:</span><span class="sxs-lookup"><span data-stu-id="8ca4d-114">If your organizations have any of the following requirements, you can use DKE to help secure your content:</span></span>

- <span data-ttu-id="8ca4d-115">Вы хотите убедиться, что *только вы* можете расшифровывать защищенный контент при всех обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-115">You want to ensure that *only you* can ever decrypt protected content, under all circumstances.</span></span>
- <span data-ttu-id="8ca4d-116">Вы не хотите, чтобы у корпорации Майкрософт был доступ к защищенным данным самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-116">You don't want Microsoft to have access to protected data on its own.</span></span>
- <span data-ttu-id="8ca4d-117">Соблюдение нормативных требований для хранения ключей в пределах географической границы.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-117">You have regulatory requirements to hold keys within a geographical boundary.</span></span> <span data-ttu-id="8ca4d-118">Все ключи, которые вы удерживаете для шифрования и расшифровки данных, поддерживаются в центре обработки данных.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-118">All of the keys that you hold for data encryption and decryption are maintained in your data center.</span></span>

## <a name="system-and-licensing-requirements-for-dke"></a><span data-ttu-id="8ca4d-119">Требования к системе и лицензированию для ДКЕ</span><span class="sxs-lookup"><span data-stu-id="8ca4d-119">System and licensing requirements for DKE</span></span>

<span data-ttu-id="8ca4d-120">Двойное ключевое шифрование для Microsoft 365, часть Microsoft 365 об/в и Office 365</span><span class="sxs-lookup"><span data-stu-id="8ca4d-120">Double Key Encryption for Microsoft 365 part of Microsoft 365 E5 and Office 365 E5.</span></span> <span data-ttu-id="8ca4d-121">Если у вас нет лицензии на Microsoft 365, вы можете зарегистрироваться для получения [пробной версии](https://aka.ms/M365E5ComplianceTrial).</span><span class="sxs-lookup"><span data-stu-id="8ca4d-121">If you don’t have a Microsoft 365 E5 license, you can sign up for a [trial](https://aka.ms/M365E5ComplianceTrial).</span></span> <span data-ttu-id="8ca4d-122">Для получения дополнительных сведений об этих лицензиях обратитесь к разделу [руководство по лицензированию Microsoft 365 для обеспечения безопасности & соответствия требованиям](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="8ca4d-122">For more information about these licenses, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

<span data-ttu-id="8ca4d-123">**Предварительная сборка Office** Для использования общедоступной предварительной версии вы должны быть участником программы предварительной оценки Office.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-123">**Office Insider** To use the public preview, you must be a member of the Office Insider program.</span></span> <span data-ttu-id="8ca4d-124">Чтобы присоединиться к программе предварительной оценки Office, перейдите на страницу [https://insider.office.com](https://insider.office.com) .</span><span class="sxs-lookup"><span data-stu-id="8ca4d-124">To join Office Insider, go to [https://insider.office.com](https://insider.office.com).</span></span> <span data-ttu-id="8ca4d-125">Когда вы являетесь участником, подготовьте среду к развертыванию сборок для участников программы предварительной оценки Office, выбрав нужный метод развертывания для своей организации.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-125">Once you're a member, prepare your environment to deploy Office Insider builds by choosing the right deployment method for your organization.</span></span> <span data-ttu-id="8ca4d-126">Инструкции приведены в разделе [Начало работы по развертыванию сборок для участников программы предварительной оценки Office](https://insider.office.com/business/deploy).</span><span class="sxs-lookup"><span data-stu-id="8ca4d-126">For instructions, see [Getting started on deploying Office Insider builds](https://insider.office.com/business/deploy).</span></span>

<span data-ttu-id="8ca4d-127">**Azure Information Protection**.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-127">**Azure Information Protection**.</span></span> <span data-ttu-id="8ca4d-128">ДКЕ работает с метками конфиденциальности и требует использования Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-128">DKE works with sensitivity labels and requires Azure Information Protection.</span></span>

## <a name="supported-environments-for-storing-and-viewing-dke-protected-content"></a><span data-ttu-id="8ca4d-129">Поддерживаемые среды для хранения и просмотра защищенного ДКЕ контента</span><span class="sxs-lookup"><span data-stu-id="8ca4d-129">Supported environments for storing and viewing DKE-protected content</span></span>

<span data-ttu-id="8ca4d-130">**Поддерживаемые приложения**.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-130">**Supported applications**.</span></span> <span data-ttu-id="8ca4d-131">[Приложения Microsoft 365 для корпоративных](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) клиентов в Windows, в том числе Word, Excel и PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-131">[Microsoft 365 Apps for enterprise](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) clients on Windows, including Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="8ca4d-132">**Поддержка интерактивного содержимого**.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-132">**Online content support**.</span></span> <span data-ttu-id="8ca4d-133">Документы и файлы, хранящиеся в Интернете, поддерживаются как в Microsoft SharePoint, так и в OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-133">Documents and files stored online in both Microsoft SharePoint and OneDrive for Business are supported.</span></span> <span data-ttu-id="8ca4d-134">Вы можете предоставить доступ к зашифрованному содержимому по электронной почте, но вы не можете просматривать зашифрованные документы и файлы в Интернете.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-134">You can share encrypted content by email, but you can't view encrypted documents and files online.</span></span> <span data-ttu-id="8ca4d-135">Вместо этого необходимо просмотреть защищенный контент с помощью классических приложений на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-135">Instead, you must view protected content using the desktop apps on your local computer.</span></span>

## <a name="about-this-public-preview-article"></a><span data-ttu-id="8ca4d-136">Об этой общедоступной статье предварительной версии</span><span class="sxs-lookup"><span data-stu-id="8ca4d-136">About this public preview article</span></span>

<span data-ttu-id="8ca4d-137">Существует несколько способов выполнить некоторые действия по развертыванию двойного шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-137">There are several ways you can complete some of the steps to deploy Double Key Encryption.</span></span> <span data-ttu-id="8ca4d-138">В этой статье приводятся подробные инструкции, позволяющие менее опытным администраторам успешно развертывать службу.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-138">This article provides detailed instructions so that less experienced admins successfully deploy the service.</span></span> <span data-ttu-id="8ca4d-139">Если вы умеете, можете использовать собственные методы.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-139">If you're comfortable doing so, you can choose to use your own methods.</span></span>

<span data-ttu-id="8ca4d-140">В этой статье приведены пошаговые инструкции по развертыванию службы шифрования двойных ключей в Azure.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-140">This article includes step-by-step instructions on how to deploy the Double Key Encryption service to Azure.</span></span> <span data-ttu-id="8ca4d-141">Этот сценарий не является чем-то вероятным действием в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-141">This scenario isn't something you'd likely do in production.</span></span> <span data-ttu-id="8ca4d-142">Для общедоступной предварительной версии с помощью Azure можно быстро развернуть ДКЕ.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-142">For public preview, using Azure is a quick way to deploy DKE.</span></span> <span data-ttu-id="8ca4d-143">Развертывание в Azure позволяет начать использовать двойное шифрование ключа сразу.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-143">Deploying to Azure lets you get started using Double Key Encryption right away.</span></span>

<span data-ttu-id="8ca4d-144">Службу можно развернуть локально в сети или с помощью другого поставщика.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-144">You can deploy the service locally on your network or with another provider.</span></span> <span data-ttu-id="8ca4d-145">Необходимо опубликовать хранилище ключей с помощью методов, подходящих для этого расположения.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-145">You'll need to publish the key store using methods that are appropriate for that location.</span></span>

## <a name="deploy-double-key-encryption"></a><span data-ttu-id="8ca4d-146">Развертывание двойного шифрования ключей</span><span class="sxs-lookup"><span data-stu-id="8ca4d-146">Deploy Double Key Encryption</span></span>

<span data-ttu-id="8ca4d-147">В этой статье и видео о развертывании используется Azure в качестве места назначения развертывания для службы ДКЕ.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-147">This article and the deployment video use Azure as the deployment destination for the DKE service.</span></span> <span data-ttu-id="8ca4d-148">При развертывании в другом расположении необходимо указать собственные значения.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-148">If you're deploying to another location, you'll need to provide your own values.</span></span>

<span data-ttu-id="8ca4d-149">Просмотрите [видеоролик о развертывании двойных ключей](https://msit.microsoftstream.com/video/cfdda3ff-0400-a521-1579-f1eacc37fc7e) , чтобы просмотреть пошаговые инструкции по концепциям, представленным в этой статье.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-149">Watch the [Double Key Encryption deployment video](https://msit.microsoftstream.com/video/cfdda3ff-0400-a521-1579-f1eacc37fc7e) to see step-by-step overview of concepts in the article.</span></span> <span data-ttu-id="8ca4d-150">Для завершения видеоролика потребуется около 18 минут.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-150">The video takes about 18 minutes to complete.</span></span>

<span data-ttu-id="8ca4d-151">Ниже приведены общие действия по настройке шифрования с двойным ключом для Организации.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-151">You'll follow these general steps to set up Double Key Encryption for your organization.</span></span>

1. [<span data-ttu-id="8ca4d-152">Установка необходимого программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="8ca4d-152">Install software prerequisites</span></span>](#install-software-prerequisites)
1. [<span data-ttu-id="8ca4d-153">Клонировать репозиторий GitHub шифрования с двойным ключом</span><span class="sxs-lookup"><span data-stu-id="8ca4d-153">Clone the Double Key Encryption GitHub repository</span></span>](#clone-the-dke-github-repository)
1. [<span data-ttu-id="8ca4d-154">Изменение параметров приложения</span><span class="sxs-lookup"><span data-stu-id="8ca4d-154">Modify application settings</span></span>](#modify-application-settings)
1. [<span data-ttu-id="8ca4d-155">Создание тестовых ключей</span><span class="sxs-lookup"><span data-stu-id="8ca4d-155">Generate test keys</span></span>](#generate-test-keys)
1. [<span data-ttu-id="8ca4d-156">Построение проекта</span><span class="sxs-lookup"><span data-stu-id="8ca4d-156">Build the project</span></span>](#build-the-project)
1. [<span data-ttu-id="8ca4d-157">Публикация хранилища ключей</span><span class="sxs-lookup"><span data-stu-id="8ca4d-157">Publish the key store</span></span>](#publish-the-key-store)
1. [<span data-ttu-id="8ca4d-158">Проверка развертывания</span><span class="sxs-lookup"><span data-stu-id="8ca4d-158">Validate your deployment</span></span>](#validate-your-deployment)
1. [<span data-ttu-id="8ca4d-159">Регистрация своего хранилища ключей</span><span class="sxs-lookup"><span data-stu-id="8ca4d-159">Register your key store</span></span>](#register-your-key-store)
1. [<span data-ttu-id="8ca4d-160">Создание меток конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="8ca4d-160">Create sensitivity labels</span></span>](#create-labels-using-dke)

<span data-ttu-id="8ca4d-161">После этого вы сможете зашифровать документы и файлы с помощью ДКЕ.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-161">When you're done, you can encrypt documents and files using DKE.</span></span> <span data-ttu-id="8ca4d-162">Сведения о том, [как применить метки конфиденциальности к файлам и электронной почте в Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).</span><span class="sxs-lookup"><span data-stu-id="8ca4d-162">For information, see [Apply sensitivity labels to your files and email in Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).</span></span>

### <a name="install-software-prerequisites"></a><span data-ttu-id="8ca4d-163">Установка необходимого программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="8ca4d-163">Install software prerequisites</span></span>

<span data-ttu-id="8ca4d-164">Существует два типа требований к программному обеспечению для шифрования с двойным ключом.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-164">There are two types of software prerequisites for Double Key Encryption</span></span>

- [<span data-ttu-id="8ca4d-165">Необходимые условия для службы шифрования с двойным шифрованием</span><span class="sxs-lookup"><span data-stu-id="8ca4d-165">Double Key Encryption service prerequisites</span></span>](#double-key-encryption-service-prerequisites)
- [<span data-ttu-id="8ca4d-166">Необходимые условия для шифрования с двойным ключом для клиентских компьютеров</span><span class="sxs-lookup"><span data-stu-id="8ca4d-166">Double Key Encryption prerequisites for client computers</span></span>](#double-key-encryption-prerequisites-for-client-computers)

#### <a name="double-key-encryption-service-prerequisites"></a><span data-ttu-id="8ca4d-167">Необходимые условия для службы шифрования с двойным шифрованием</span><span class="sxs-lookup"><span data-stu-id="8ca4d-167">Double Key Encryption service prerequisites</span></span>

<span data-ttu-id="8ca4d-168">Установите эти компоненты на компьютер, на котором необходимо установить службу ДКЕ.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-168">Install these prerequisites on the computer where you want to install the DKE service.</span></span>

<span data-ttu-id="8ca4d-169">**Пакет SDK для .NET Core 3,1**.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-169">**.NET Core 3.1 SDK**.</span></span> <span data-ttu-id="8ca4d-170">Скачайте и установите пакет SDK из центра [загрузки .NET Core 3,1](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span><span class="sxs-lookup"><span data-stu-id="8ca4d-170">Download and install the SDK from [Download .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span></span>

<span data-ttu-id="8ca4d-171">**Visual Studio Code**.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-171">**Visual Studio Code**.</span></span> <span data-ttu-id="8ca4d-172">Скачайте Visual Studio Code FROM [https://code.visualstudio.com/](https://code.visualstudio.com) .</span><span class="sxs-lookup"><span data-stu-id="8ca4d-172">Download Visual Studio Code from [https://code.visualstudio.com/](https://code.visualstudio.com).</span></span> <span data-ttu-id="8ca4d-173">После установки запустите Visual Studio Code и выберите **View** \> **Extensions**.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-173">Once installed, run Visual Studio Code and select **View** \> **Extensions**.</span></span> <span data-ttu-id="8ca4d-174">Установите эти расширения.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-174">Install these extensions.</span></span>

- <span data-ttu-id="8ca4d-175">C# для Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="8ca4d-175">C# for Visual Studio Code</span></span>

- <span data-ttu-id="8ca4d-176">Диспетчер пакетов NuGet</span><span class="sxs-lookup"><span data-stu-id="8ca4d-176">NuGet Package Manager</span></span>

<span data-ttu-id="8ca4d-177">**Предварительная оценка Microsoft Office**.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-177">**Microsoft Office Insider**.</span></span> <span data-ttu-id="8ca4d-178">Настройте по крайней мере один [метод развертывания](https://insider.office.com/business/deploy).</span><span class="sxs-lookup"><span data-stu-id="8ca4d-178">Set up at least one [deployment method](https://insider.office.com/business/deploy).</span></span>

<span data-ttu-id="8ca4d-179">**Ресурсы Git**.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-179">**Git resources**.</span></span> <span data-ttu-id="8ca4d-180">Скачайте и установите один из следующих элементов.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-180">Download and install one of the following.</span></span>

- [<span data-ttu-id="8ca4d-181">Git</span><span class="sxs-lookup"><span data-stu-id="8ca4d-181">Git</span></span>](https://git-scm.com/downloads)

- [<span data-ttu-id="8ca4d-182">Классическое приложение GitHub</span><span class="sxs-lookup"><span data-stu-id="8ca4d-182">GitHub Desktop</span></span>](https://desktop.github.com/)

- [<span data-ttu-id="8ca4d-183">GitHub Enterprise</span><span class="sxs-lookup"><span data-stu-id="8ca4d-183">GitHub Enterprise</span></span>](https://github.com/enterprise)

<span data-ttu-id="8ca4d-184">**OpenSSL** Для [создания тестовых ключей](#generate-test-keys) после развертывания дке необходимо установить [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) .</span><span class="sxs-lookup"><span data-stu-id="8ca4d-184">**OpenSSL** You must have [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) installed to [generate test keys](#generate-test-keys) after you deploy DKE.</span></span> <span data-ttu-id="8ca4d-185">Убедитесь, что вы правильно вызываете его из пути переменных среды.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-185">Make sure you're invoking it correctly from your environment variables path.</span></span> <span data-ttu-id="8ca4d-186">Например, https://www.osradar.com/install-openssl-windows/ для получения дополнительных сведений обратитесь к разделу "Добавление каталога установки по пути".</span><span class="sxs-lookup"><span data-stu-id="8ca4d-186">For example, see "Add the installation directory to PATH" at https://www.osradar.com/install-openssl-windows/ for details.</span></span>

#### <a name="double-key-encryption-prerequisites-for-client-computers"></a><span data-ttu-id="8ca4d-187">Необходимые условия для шифрования с двойным ключом для клиентских компьютеров</span><span class="sxs-lookup"><span data-stu-id="8ca4d-187">Double Key Encryption prerequisites for client computers</span></span>

<span data-ttu-id="8ca4d-188">Установите эти компоненты на каждом клиентском компьютере, на котором требуется защитить и использовать защищенные документы.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-188">Install these prerequisites on each client computer where you want to protect and consume protected documents.</span></span>

<span data-ttu-id="8ca4d-189">**Microsoft Office** версии \*. 12711 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-189">**Microsoft Office** version \*.12711 or later.</span></span>

<span data-ttu-id="8ca4d-190">**Azure Information Protection единой метки версий клиентов** 2.7.93.0 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-190">**Azure Information Protection Unified Labeling Client** versions 2.7.93.0 or later.</span></span> <span data-ttu-id="8ca4d-191">Скачайте и установите клиент единой метки от [корпорации Майкрософт](https://www.microsoft.com/download/details.aspx?id=53018).</span><span class="sxs-lookup"><span data-stu-id="8ca4d-191">Download and install the Unified Labeling client from [Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

### <a name="clone-the-dke-github-repository"></a><span data-ttu-id="8ca4d-192">Клонирование репозитория ДКЕ GitHub</span><span class="sxs-lookup"><span data-stu-id="8ca4d-192">Clone the DKE GitHub repository</span></span>

<span data-ttu-id="8ca4d-193">Майкрософт предоставляет исходные файлы ДКЕ в репозитории GitHub.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-193">Microsoft supplies the DKE source files in a GitHub repository.</span></span> <span data-ttu-id="8ca4d-194">Необходимо клонировать репозиторий, чтобы создать проект локально для использования в Организации.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-194">You clone the repository to build the project locally for your organization's use.</span></span> <span data-ttu-id="8ca4d-195">Репозиторий GitHub ДКЕ находится по адресу [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) .</span><span class="sxs-lookup"><span data-stu-id="8ca4d-195">The DKE GitHub repository is located at [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).</span></span>

<span data-ttu-id="8ca4d-196">Следующие инструкции предназначены для неопытных пользователей Git или Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="8ca4d-196">The following instructions are intended for inexperienced git or Visual Studio Code users:</span></span>

1. <span data-ttu-id="8ca4d-197">В браузере перейдите по адресу:[https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService)</span><span class="sxs-lookup"><span data-stu-id="8ca4d-197">In your browser, go to: [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService)</span></span>

1. <span data-ttu-id="8ca4d-198">В правой части экрана выберите **код**.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-198">Towards the right side of the screen, select **Code**.</span></span> <span data-ttu-id="8ca4d-199">В вашей версии пользовательского интерфейса может отображаться кнопка " **Копировать" или "скачать** ".</span><span class="sxs-lookup"><span data-stu-id="8ca4d-199">Your version of the UI might show a **Clone or download** button.</span></span> <span data-ttu-id="8ca4d-200">Затем в появившемся раскрывающемся меню выберите значок Копировать, чтобы скопировать URL-адрес в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-200">Then, in the dropdown that appears, select the copy icon to copy the URL to your clipboard.</span></span>

    <span data-ttu-id="8ca4d-201">Пример:</span><span class="sxs-lookup"><span data-stu-id="8ca4d-201">For example:</span></span>

    :::image type="content" source="../media/dke-clone.png" alt-text="Клонирование базы данных двойных шифрования ключей из GitHub":::

3. <span data-ttu-id="8ca4d-203">В Visual Studio Code выберите пункт **Просмотреть** \> **палитру команд** и выберите **Git: Clone**.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-203">In Visual Studio Code, select **View** \> **Command Palette** and select **Git: Clone**.</span></span> <span data-ttu-id="8ca4d-204">Чтобы перейти к параметру в списке, начните ввод, `git: clone` чтобы отфильтровать записи, а затем выберите его в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-204">To jump to the option in the list, start typing `git: clone` to filter the entries and then select it from the drop-down.</span></span> <span data-ttu-id="8ca4d-205">Пример:</span><span class="sxs-lookup"><span data-stu-id="8ca4d-205">For example:</span></span>

    :::image type="content" source="../media/dke-vscode-clone.png" alt-text="Visual Studio Code GIT: параметр Clone":::

4. <span data-ttu-id="8ca4d-207">В текстовом поле вставьте URL-адрес, который вы скопировали из Git, и выберите **клон из GitHub**.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-207">In the text box, paste the URL that you copied from Git and select **Clone from GitHub**.</span></span>

5. <span data-ttu-id="8ca4d-208">В появившемся диалоговом окне **Выбор папки** найдите и выберите расположение для хранения репозитория.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-208">In the **Select Folder** dialog that appears, browse to and select a location to store the repository.</span></span> <span data-ttu-id="8ca4d-209">В командной строки нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-209">At the prompt, select **Open**.</span></span>

    <span data-ttu-id="8ca4d-210">Репозиторий открывается в Visual Studio Code и отображается в левом нижнем углу текущей ветви Git.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-210">The repository is opened in Visual Studio Code, and displays the current Git branch at the bottom left.</span></span> <span data-ttu-id="8ca4d-211">Ветвь должна быть **основной**.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-211">The branch should be **master**.</span></span>

    <span data-ttu-id="8ca4d-212">Пример:</span><span class="sxs-lookup"><span data-stu-id="8ca4d-212">For example:</span></span>

    :::image type="content" source="../media/dke-vscode-master.png" alt-text="Ветвь образца кода Visual Studio":::

6. <span data-ttu-id="8ca4d-214">Выберите образец Word **,** а затем в списке ветвей выберите пункт **public_preview** .</span><span class="sxs-lookup"><span data-stu-id="8ca4d-214">Select the word **master,** and then select **public_preview** from the list of branches.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="8ca4d-215">Выбор ветви public_preview позволяет убедиться, что у вас есть правильные файлы для построения проекта.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-215">Selecting the public_preview branch ensures that you have the correct files to build the project.</span></span> <span data-ttu-id="8ca4d-216">Если не выбрать подходящую ветвь, произойдет ошибка развертывания.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-216">If you do not choose the correct branch your deployment will fail.</span></span>

<span data-ttu-id="8ca4d-217">Теперь исходный репозиторий ДКЕ настроен локально.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-217">You now have your DKE source repository set up locally.</span></span> <span data-ttu-id="8ca4d-218">Затем [измените параметры приложения](#modify-application-settings) для своей организации.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-218">Next, [modify application settings](#modify-application-settings) for your organization.</span></span>

### <a name="modify-application-settings"></a><span data-ttu-id="8ca4d-219">Изменение параметров приложения</span><span class="sxs-lookup"><span data-stu-id="8ca4d-219">Modify application settings</span></span>

<span data-ttu-id="8ca4d-220">Чтобы развернуть службу ДКЕ, необходимо изменить следующие типы параметров приложений:</span><span class="sxs-lookup"><span data-stu-id="8ca4d-220">To deploy the DKE service, you must modify the following types of application settings:</span></span>

- [<span data-ttu-id="8ca4d-221">Параметры доступа к ключам</span><span class="sxs-lookup"><span data-stu-id="8ca4d-221">Key access settings</span></span>](#key-access-settings)
- [<span data-ttu-id="8ca4d-222">Параметры клиента и ключа</span><span class="sxs-lookup"><span data-stu-id="8ca4d-222">Tenant and key settings</span></span>](#tenant-and-key-settings)

<span data-ttu-id="8ca4d-223">Вы изменяете параметры приложения в appsettings.jsв файле.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-223">You modify application settings in the appsettings.json file.</span></span> <span data-ttu-id="8ca4d-224">Этот файл находится в репозитории Даублекэйенкриптионсервице, который вы клонированы локально в Даублекэйенкриптионсервице\срк\кустомер-Кэй-Сторе.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-224">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store.</span></span> <span data-ttu-id="8ca4d-225">Например, в Visual Studio Code можно перейти к файлу, как показано на рисунке ниже.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-225">For example, in Visual Studio Code, you can browse to the file as shown in the following picture.</span></span>

:::image type="content" source="../media/dke-appsettingsjson.png" alt-text="Поиск appsettings.jsв файле для ДКЕ.":::

#### <a name="key-access-settings"></a><span data-ttu-id="8ca4d-227">Параметры доступа к ключам</span><span class="sxs-lookup"><span data-stu-id="8ca4d-227">Key access settings</span></span>

<span data-ttu-id="8ca4d-228">Укажите, следует ли использовать авторизацию электронной почты или ролей.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-228">Choose whether to use email or role authorization.</span></span> <span data-ttu-id="8ca4d-229">ДКЕ поддерживает только один из этих методов проверки подлинности за раз.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-229">DKE supports only one of these authentication methods at a time.</span></span>

- <span data-ttu-id="8ca4d-230">**Авторизация электронной почты**.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-230">**Email authorization**.</span></span> <span data-ttu-id="8ca4d-231">Позволяет Организации авторизовать доступ к ключам только в соответствии с адресами электронной почты.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-231">Allows your organization to authorize access to keys based on email addresses only.</span></span>

- <span data-ttu-id="8ca4d-232">**Авторизация ролей**.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-232">**Role authorization**.</span></span> <span data-ttu-id="8ca4d-233">Позволяет Организации авторизовать доступ к ключам на основе групп Active Directory и требовать, чтобы веб-служба могла запрашивать LDAP.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-233">Allows your organization to authorize access to keys based on Active Directory groups, and requires that the web service can query LDAP.</span></span>

<span data-ttu-id="8ca4d-234">**Настройка параметров доступа к ключам для ДКЕ с помощью авторизации электронной почты**</span><span class="sxs-lookup"><span data-stu-id="8ca4d-234">**To set key access settings for DKE using email authorization**</span></span>

1. <span data-ttu-id="8ca4d-235">Откройте **appsettings.js** файла и выберите `AuthorizedEmailAddress` параметр.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-235">Open the **appsettings.json** file and locate the `AuthorizedEmailAddress` setting.</span></span>

2. <span data-ttu-id="8ca4d-236">Добавьте адрес электронной почты или адреса, которые вы хотите авторизовать.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-236">Add the email address or addresses that you want to authorize.</span></span> <span data-ttu-id="8ca4d-237">Разделяйте адреса электронной почты двойными кавычками и запятыми.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-237">Separate multiple email addresses with double quotes and commas.</span></span> <span data-ttu-id="8ca4d-238">Пример:</span><span class="sxs-lookup"><span data-stu-id="8ca4d-238">For example:</span></span>

   ```json
   "AuthorizedEmailAddress": ["email1@company.com", "email2@company.com ", "email3@company.com"]
   ```

3. <span data-ttu-id="8ca4d-239">Нахождение `LDAPPath` параметра и удаление текста `If role authorization is used then this is the LDAP path` между двойными кавычками.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-239">Locate the `LDAPPath` setting and remove the text `If role authorization is used then this is the LDAP path` between the double quotes.</span></span> <span data-ttu-id="8ca4d-240">Оставьте двойные кавычки на месте.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-240">Leave the double quotes in place.</span></span> <span data-ttu-id="8ca4d-241">По завершении этот параметр должен выглядеть так, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-241">When you're finished, the setting should look like this.</span></span>

   ```json
   "LDAPPath": ""
   ```

4. <span data-ttu-id="8ca4d-242">Нахождение `AuthorizedRoles` параметра и удаление всей строки.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-242">Locate the `AuthorizedRoles` setting and delete the entire line.</span></span>

<span data-ttu-id="8ca4d-243">На этом рисунке показано, как правильно отформатировать **appsettings.jsв** файле для авторизации электронной почты.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-243">This image shows the **appsettings.json** file correctly formatted for email authorization.</span></span>

   :::image type="content" source="../media/dke-email-accesssetting.png" alt-text="appsettings.jsдля файла с методом авторизации электронной почты":::

<span data-ttu-id="8ca4d-245">**Настройка параметров доступа к ключам для ДКЕ с помощью авторизации ролей**</span><span class="sxs-lookup"><span data-stu-id="8ca4d-245">**To set key access settings for DKE using role authorization**</span></span>

1. <span data-ttu-id="8ca4d-246">Откройте **appsettings.js** файла и выберите `AuthorizedRoles` параметр.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-246">Open the **appsettings.json** file and locate the `AuthorizedRoles` setting.</span></span>

2. <span data-ttu-id="8ca4d-247">Добавьте имена групп Active Directory, которые вы хотите авторизовать.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-247">Add the Active Directory group names you want to authorize.</span></span> <span data-ttu-id="8ca4d-248">Разделяйте имена групп двойными кавычками и запятыми.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-248">Separate multiple group names with double quotes and commas.</span></span> <span data-ttu-id="8ca4d-249">Пример:</span><span class="sxs-lookup"><span data-stu-id="8ca4d-249">For example:</span></span>

   ```json
   "AuthorizedRoles": ["group1", "group2", "group3"]
   ```

3. <span data-ttu-id="8ca4d-250">Нахождение `LDAPPath` параметра и добавление домена Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-250">Locate the `LDAPPath` setting and add the Active Directory domain.</span></span> <span data-ttu-id="8ca4d-251">Пример:</span><span class="sxs-lookup"><span data-stu-id="8ca4d-251">For example:</span></span>

   ```json
   "LDAPPath": "contoso.com"
   ```

4. <span data-ttu-id="8ca4d-252">Нахождение `AuthorizedEmailAddress` параметра и удаление всей строки.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-252">Locate the `AuthorizedEmailAddress` setting and delete the entire line.</span></span>

<span data-ttu-id="8ca4d-253">На этом рисунке показано, как правильно отформатировать **appsettings.jsв** файле для авторизации роли.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-253">This image shows the **appsettings.json** file correctly formatted for role authorization.</span></span>

   :::image type="content" source="../media/dke-role-accesssetting.png" alt-text="appsettings.jsдля файла с методом авторизации роли":::

#### <a name="tenant-and-key-settings"></a><span data-ttu-id="8ca4d-255">Параметры клиента и ключа</span><span class="sxs-lookup"><span data-stu-id="8ca4d-255">Tenant and key settings</span></span>

<span data-ttu-id="8ca4d-256">Параметры клиента и ключа ДКЕ находятся в **appsettings.js** в файле.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-256">DKE tenant and key settings are located in the **appsettings.json** file.</span></span>

<span data-ttu-id="8ca4d-257">**Настройка параметров клиента и ключа для ДКЕ**</span><span class="sxs-lookup"><span data-stu-id="8ca4d-257">**To configure tenant and key settings for DKE**</span></span>

1. <span data-ttu-id="8ca4d-258">Откройте **appsettings.jsв** файле.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-258">Open the **appsettings.json** file.</span></span>

2. <span data-ttu-id="8ca4d-259">Укажите `ValidIssuers` параметр и замените `<tenantid>` идентификатором клиента.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-259">Locate the `ValidIssuers` setting and replace `<tenantid>` with your tenant ID.</span></span> <span data-ttu-id="8ca4d-260">Вы можете определить идентификатор клиента, перейдя на портал Azure и просмотрев [Свойства клиента](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="8ca4d-260">You can locate your tenant ID by going to the Azure portal and viewing the [tenant properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> <span data-ttu-id="8ca4d-261">Пример:</span><span class="sxs-lookup"><span data-stu-id="8ca4d-261">For example:</span></span>

   ```json
   "ValidIssuers": [
     "https://sts.windows.net/9c99431e-b513-44be-a7d9-e7b500002d4b/"
   ]
   ```

<span data-ttu-id="8ca4d-262">Откройте файл `JwtAudience` .</span><span class="sxs-lookup"><span data-stu-id="8ca4d-262">Locate the `JwtAudience`.</span></span> <span data-ttu-id="8ca4d-263">Замените `<yourhostname>` на имя узла компьютера, на котором будет запускаться служба дке.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-263">Replace `<yourhostname>` with the hostname of the machine where the DKE service will run.</span></span> <span data-ttu-id="8ca4d-264">Пример:</span><span class="sxs-lookup"><span data-stu-id="8ca4d-264">For example:</span></span>



  > [!IMPORTANT]
  > <span data-ttu-id="8ca4d-265">Значение `JwtAudience` должно *точно*совпадать с именем узла.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-265">The value for `JwtAudience` must match the name of your host *exactly*.</span></span> <span data-ttu-id="8ca4d-266">При отладке вы можете использовать **localhost: 5001** .</span><span class="sxs-lookup"><span data-stu-id="8ca4d-266">You may use **localhost:5001** while debugging.</span></span> <span data-ttu-id="8ca4d-267">Однако после завершения отладки обязательно обновите это значение с помощью имени узла сервера.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-267">However, When you're done debugging, make sure to update this value to the server's hostname.</span></span>

- <span data-ttu-id="8ca4d-268">`TestKeys:Name`.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-268">`TestKeys:Name`.</span></span> <span data-ttu-id="8ca4d-269">Введите имя для ключа.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-269">Enter a name for your key.</span></span> <span data-ttu-id="8ca4d-270">Пример: `TestKey1`</span><span class="sxs-lookup"><span data-stu-id="8ca4d-270">For example: `TestKey1`</span></span>
- <span data-ttu-id="8ca4d-271">`TestKeys:Id`.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-271">`TestKeys:Id`.</span></span> <span data-ttu-id="8ca4d-272">Создайте GUID и введите его в качестве `TestKeys:ID` значения.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-272">Create a GUID and enter it as the `TestKeys:ID` value.</span></span> <span data-ttu-id="8ca4d-273">Например, `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-273">For example, `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`.</span></span> <span data-ttu-id="8ca4d-274">Для случайного создания GUID можно использовать сайт, например, [генератор GUID в Интернете](https://guidgenerator.com/) .</span><span class="sxs-lookup"><span data-stu-id="8ca4d-274">You can use a site like [Online GUID Generator](https://guidgenerator.com/) to randomly generate a GUID.</span></span>

<span data-ttu-id="8ca4d-275">На этом рисунке показан правильный формат параметров клиента и ключей в **appsettings.json**.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-275">This image shows the correct format for tenant and keys settings in **appsettings.json**.</span></span> <span data-ttu-id="8ca4d-276">`LDAPPath`настроена для авторизации роли.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-276">`LDAPPath` is configured for role authorization.</span></span>

:::image type="content" source="../media/dke-appsettingsjson-tenantkeysettings.png" alt-text="Показывает правильные параметры клиента и ключа для ДКЕ в appsettings.jsв файле.":::

### <a name="generate-test-keys"></a><span data-ttu-id="8ca4d-278">Создание тестовых ключей</span><span class="sxs-lookup"><span data-stu-id="8ca4d-278">Generate test keys</span></span>

<span data-ttu-id="8ca4d-279">После определения параметров приложения вы можете создать общедоступные и закрытые тестовые ключи.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-279">Once you have your application settings defined, you're ready to generate public and private test keys.</span></span>

<span data-ttu-id="8ca4d-280">Для создания ключей:</span><span class="sxs-lookup"><span data-stu-id="8ca4d-280">To generate keys:</span></span>

1. <span data-ttu-id="8ca4d-281">В меню Пуск Windows выполните командную строку OpenSSL.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-281">From the Windows Start menu, run the OpenSSL Command Prompt.</span></span>

1. <span data-ttu-id="8ca4d-282">Перейдите к папке, в которой вы хотите сохранить тестовые ключи.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-282">Change to the folder where you want to save the test keys.</span></span> <span data-ttu-id="8ca4d-283">Файлы, создаваемые при выполнении действий, описанных в этой задаче, хранятся в одной папке.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-283">The files you create by completing the steps in this task are stored in the same folder.</span></span>

1. <span data-ttu-id="8ca4d-284">Создайте новый тестовый ключ.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-284">Generate the new test key.</span></span>

   ```dos
   openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365
   ```

2. <span data-ttu-id="8ca4d-285">Создайте закрытый ключ.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-285">Generate the private key.</span></span>

   ```dos
   openssl rsa -in key.pem -out privkeynopass.pem
   ```

1. <span data-ttu-id="8ca4d-286">Создайте открытый ключ.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-286">Generate the public key.</span></span>

   ```dos
   openssl rsa -in key.pem -pubout > pubkeyonly.pem
   ```

1. <span data-ttu-id="8ca4d-287">В текстовом редакторе откройте **пубкэйонли. pem**.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-287">In a text editor, open **pubkeyonly.pem**.</span></span> <span data-ttu-id="8ca4d-288">Скопируйте весь контент из файла **пубкэйонли. pem** , за исключением первой и последней строки, в `PublicPem` раздел **appsettings.js** файла.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-288">Copy all of the content in the **pubkeyonly.pem** file, except the first and last lines, into the `PublicPem` section of the **appsettings.json** file.</span></span>

1. <span data-ttu-id="8ca4d-289">В текстовом редакторе откройте **привкэйнопасс. pem**.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-289">In a text editor, open **privkeynopass.pem**.</span></span> <span data-ttu-id="8ca4d-290">Скопируйте весь контент из файла **привкэйнопасс. pem** , за исключением первой и последней строки, в `PrivatePem` раздел **appsettings.js** файла.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-290">Copy all of the content in the **privkeynopass.pem** file, except the first and last lines, into the `PrivatePem` section of the **appsettings.json** file.</span></span>

1. <span data-ttu-id="8ca4d-291">Удалите все пробелы и символы новой строки в `PublicPem` разделах и и `PrivatePem` .</span><span class="sxs-lookup"><span data-stu-id="8ca4d-291">Remove all blank spaces and newlines in both the `PublicPem` and `PrivatePem` sections.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="8ca4d-292">При копировании этого контента не удаляйте какие бы то ни было данные PEM.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-292">When you copy this content, do not delete any of the PEM data.</span></span>

1. <span data-ttu-id="8ca4d-293">В Visual Studio Code перейдите к файлу **Startup.CS** .</span><span class="sxs-lookup"><span data-stu-id="8ca4d-293">In Visual Studio Code, browse to the **Startup.cs** file.</span></span> <span data-ttu-id="8ca4d-294">Этот файл находится в репозитории Даублекэйенкриптионсервице, который вы клонированы локально в Даублекэйенкриптионсервице\срк\кустомер-Кэй-сторе\.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-294">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store\.</span></span>

2. <span data-ttu-id="8ca4d-295">Откройте следующие строки:</span><span class="sxs-lookup"><span data-stu-id="8ca4d-295">Locate the following lines:</span></span>

   ```c#
        #if USE_TEST_KEYS
        #error !!!!!!!!!!!!!!!!!!!!!! Use of test keys is only supported for testing,
        DO NOT USE  FOR PRODUCTION !!!!!!!!!!!!!!!!!!!!!!!!!!!!!
        services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
        #endif
   ```

3. <span data-ttu-id="8ca4d-296">Замените эти строки следующим текстом:</span><span class="sxs-lookup"><span data-stu-id="8ca4d-296">Replace these lines with the following text:</span></span>

   ```csharp
   services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
   ```

   <span data-ttu-id="8ca4d-297">Конечный результат должен выглядеть примерно так, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-297">The end results should look similar to the following.</span></span>

   :::image type="content" source="../media/dke-startupcs-usetestkeys.png" alt-text="файл startup.cs для общедоступной предварительной версии":::

<span data-ttu-id="8ca4d-299">Теперь вы готовы к [созданию проекта дке](#build-the-project).</span><span class="sxs-lookup"><span data-stu-id="8ca4d-299">Now you're ready to [build your DKE project](#build-the-project).</span></span>

### <a name="build-the-project"></a><span data-ttu-id="8ca4d-300">Построение проекта</span><span class="sxs-lookup"><span data-stu-id="8ca4d-300">Build the project</span></span>

<span data-ttu-id="8ca4d-301">Используйте следующие инструкции для локального создания проекта ДКЕ:</span><span class="sxs-lookup"><span data-stu-id="8ca4d-301">Use the following instructions to build the DKE project locally:</span></span>

1. <span data-ttu-id="8ca4d-302">В Visual Studio Code в репозитории службы дке выберите пункт **Просмотреть** \> **палитру команд** и введите в командной строки команду **Build** .</span><span class="sxs-lookup"><span data-stu-id="8ca4d-302">In Visual Studio Code, in the DKE service repository, select **View** \> **Command Palette** and then type **build** at the prompt.</span></span>

1. <span data-ttu-id="8ca4d-303">В списке выберите **задачи: выполнение задачи сборки**.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-303">From the list, choose **Tasks: Run build task**.</span></span>

   <span data-ttu-id="8ca4d-304">Если задач сборки нет, выберите **настроить задачу построения** и создайте ее для .NET Core следующим образом.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-304">If there are no build tasks found, select **Configure Build Task** and create one for .NET core as follows.</span></span>

   :::image type="content" source="../media/dke-configurebuildtask.png" alt-text="Настройка отсутствующих задач сборки для .NET":::

   1. <span data-ttu-id="8ca4d-306">Выберите **создать tasks.jsна основе шаблона**.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-306">Choose **Create tasks.json from template**.</span></span>

   :::image type="content" source="../media/dke-createtasksjsonfromtemplate.png" alt-text="Создание tasks.jsдля файла из шаблона для ДКЕ":::

   2. <span data-ttu-id="8ca4d-308">В списке типов шаблонов выберите **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-308">From the list of template types, select **.NET Core**.</span></span>

   :::image type="content" source="../media/dke-tasksjsontemplate.png" alt-text="Создание tasks.jsдля файла из шаблона для ДКЕ":::

   3. <span data-ttu-id="8ca4d-310">В разделе Build (построение) выберите путь к файлу **кустомеркэйсторе. csproj** .</span><span class="sxs-lookup"><span data-stu-id="8ca4d-310">In the build section, locate the path to the **customerkeystore.csproj** file.</span></span> <span data-ttu-id="8ca4d-311">Если это не так, добавьте следующую строку:</span><span class="sxs-lookup"><span data-stu-id="8ca4d-311">If it's not there, add the following line:</span></span>

      ```json
      "${workspaceFolder}/src/customer-key-store/customerkeystore.csproj",
      ```

  4. <span data-ttu-id="8ca4d-312">Снова запустите построение.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-312">Run the build again.</span></span>

1. <span data-ttu-id="8ca4d-313">Убедитесь, что в окне вывода нет красных ошибок.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-313">Verify that there are no red errors in the output window.</span></span>

   <span data-ttu-id="8ca4d-314">При наличии красных ошибок проверьте вывод консоли.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-314">If there are red errors, check the console output.</span></span> <span data-ttu-id="8ca4d-315">Убедитесь, что все предыдущие действия выполнены правильно, и в них имеются правильные версии сборки.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-315">Ensure that you completed all the previous steps correctly and the correct build versions are present.</span></span>

2. <span data-ttu-id="8ca4d-316">Чтобы отладить процесс, нажмите кнопку **выполнить** \> **Запуск отладки** .</span><span class="sxs-lookup"><span data-stu-id="8ca4d-316">Select **Run** \> **Start Debugging** to debug the process.</span></span> <span data-ttu-id="8ca4d-317">Если вам будет предложено выбрать среду, выберите пункт **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-317">If you're prompted to select an environment, select **.NET core**.</span></span>

<span data-ttu-id="8ca4d-318">Основной отладчик .NET, как правило, запускается в ' ' https://localhost:5001 `. To view your test key, go to ` https://localhost:5001 ' и добавляет косую черту (/) и имя ключа.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-318">The .NET core debugger typically launches to \`\`https://localhost:5001`. To view your test key, go to `https://localhost:5001\` and append a forward slash (/) and the name of your key.</span></span> <span data-ttu-id="8ca4d-319">Пример:</span><span class="sxs-lookup"><span data-stu-id="8ca4d-319">For example:</span></span>

```https
https://localhost:5001/TestKey1
```

<span data-ttu-id="8ca4d-320">Ключ должен отображаться в формате JSON.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-320">The key should display in JSON format.</span></span>

<span data-ttu-id="8ca4d-321">Теперь настройка завершена.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-321">Your setup is now complete.</span></span> <span data-ttu-id="8ca4d-322">Перед публикацией хранилища ключей в appsettings.jsдля параметра Жвтаудиенце убедитесь, что значение Hostname точно соответствует имени узла службы приложений.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-322">Before you publish the keystore, in appsettings.json, for the JwtAudience setting, ensure the value for hostname exactly matches your App Service host name.</span></span> <span data-ttu-id="8ca4d-323">Возможно, вы изменили его на localhost, чтобы устранить неполадки с построением.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-323">You may have changed it to localhost to troubleshoot the build.</span></span>

### <a name="publish-the-key-store"></a><span data-ttu-id="8ca4d-324">Публикация хранилища ключей</span><span class="sxs-lookup"><span data-stu-id="8ca4d-324">Publish the key store</span></span>

<span data-ttu-id="8ca4d-325">Чтобы опубликовать хранилище ключей, вы создадите экземпляр службы приложений Azure для размещения вашего развертывания ДКЕ.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-325">To publish the key store, you'll create an Azure App Service instance to host your DKE deployment.</span></span> <span data-ttu-id="8ca4d-326">Теперь вы публикуете созданные ключи в Azure.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-326">Next, you'll publish your generated keys to Azure.</span></span>

<span data-ttu-id="8ca4d-327">**Создание экземпляра веб-приложения Azure для размещения развертывания ДКЕ**</span><span class="sxs-lookup"><span data-stu-id="8ca4d-327">**To create an Azure Web App instance to host your DKE deployment**</span></span>

1. <span data-ttu-id="8ca4d-328">В браузере Войдите на [портал Microsoft Azure](https://ms.portal.azure.com)и перейдите к разделу Добавление **служб приложений**  >  **Add**.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-328">In your browser, sign in to the [Microsoft Azure portal](https://ms.portal.azure.com), and go to **App Services** > **Add**.</span></span>

1. <span data-ttu-id="8ca4d-329">Выберите свою подписку и группу ресурсов и определите сведения об экземпляре.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-329">Select your subscription and resource group and define your instance details.</span></span>

    - <span data-ttu-id="8ca4d-330">Введите имя узла компьютера, на котором необходимо установить службу ДКЕ.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-330">Enter the hostname of the computer where you want to install the DKE service.</span></span> <span data-ttu-id="8ca4d-331">Убедитесь, что это то же имя, которое задано для параметра Жвтаудиенце в [**appsettings.js**](#tenant-and-key-settings) файла.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-331">Make sure it's the same name as the one defined for the JwtAudience setting in the [**appsettings.json**](#tenant-and-key-settings) file.</span></span> <span data-ttu-id="8ca4d-332">Значение, которое вы задаете для имени, также равно Вебаппинстанценаме.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-332">The value you provide for the name is also the WebAppInstanceName.</span></span>

    - <span data-ttu-id="8ca4d-333">Для **публикации**выберите **код**и для **стека времени выполнения**выберите **.NET Core 3,1**.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-333">For **Publish**, select **code**, and for **Runtime stack**, select **.NET Core 3.1**.</span></span>

    <span data-ttu-id="8ca4d-334">Пример:</span><span class="sxs-lookup"><span data-stu-id="8ca4d-334">For example:</span></span>

    :::image type="content" source="../media/dke-azure-add-app-service.png" alt-text="Добавление службы приложений":::

1. <span data-ttu-id="8ca4d-336">В нижней части страницы выберите пункт Просмотр и **Создание**, а затем нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-336">At the bottom of the page, select **Review + create**, and then select **Add**.</span></span>

1. <span data-ttu-id="8ca4d-337">Выполните одно из следующих действий, чтобы опубликовать созданные ключи в Azure:</span><span class="sxs-lookup"><span data-stu-id="8ca4d-337">Do one of the following to publish your generated keys to Azure:</span></span>

    - [<span data-ttu-id="8ca4d-338">Публикация с помощью Зипдеплойуи</span><span class="sxs-lookup"><span data-stu-id="8ca4d-338">Publish via ZipDeployUI</span></span>](#publish-via-zipdeployui)
    - [<span data-ttu-id="8ca4d-339">Опубликовать через FTP</span><span class="sxs-lookup"><span data-stu-id="8ca4d-339">Publish via FTP</span></span>](#publish-via-ftp)
    - [<span data-ttu-id="8ca4d-340">Публикация с помощью Visual Studio 2019 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="8ca4d-340">Publish via Visual Studio 2019 or later</span></span>](https://docs.microsoft.com/aspnet/core/tutorials/)
    - [<span data-ttu-id="8ca4d-341">Публикация в локальной системе</span><span class="sxs-lookup"><span data-stu-id="8ca4d-341">Publish to an on-premises system</span></span>](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli)

    > [!NOTE]
    > <span data-ttu-id="8ca4d-342">Вы можете предпочесть другие методы для развертывания ключей.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-342">You may prefer other methods to deploy your keys.</span></span> <span data-ttu-id="8ca4d-343">Выберите метод, который лучше всего подходит для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-343">Select the method that works best for your organization.</span></span>

    > [!TIP]
    > <span data-ttu-id="8ca4d-344">[Публикация с помощью Visual Studio](https://docs.microsoft.com/aspnet/core/tutorials/) и [локальной системы](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli) описана в [документации по ASP .NET](https://docs.microsoft.com/aspnet/core/).</span><span class="sxs-lookup"><span data-stu-id="8ca4d-344">[Publishing via Visual Studio](https://docs.microsoft.com/aspnet/core/tutorials/) and to an [on-premises system](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli) is described in the [ASP .NET documentation](https://docs.microsoft.com/aspnet/core/).</span></span> <span data-ttu-id="8ca4d-345">Если вы используете один из этих методов, откройте инструкции на отдельной вкладке, чтобы вы могли вернуться к ней, когда все будет готово.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-345">If you use one of these methods, open the instructions in a separate tab so that you can return here easily when you're done.</span></span>

#### <a name="publish-via-zipdeployui"></a><span data-ttu-id="8ca4d-346">Публикация с помощью Зипдеплойуи</span><span class="sxs-lookup"><span data-stu-id="8ca4d-346">Publish via ZipDeployUI</span></span>

1. <span data-ttu-id="8ca4d-347">Перейдите на сайт `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-347">Go to `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.</span></span>

    <span data-ttu-id="8ca4d-348">Пример: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="8ca4d-348">For example: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span></span>

1. <span data-ttu-id="8ca4d-349">В базе кода для хранилища ключей перейдите в папку **Кустомер-Кэй-сторе\срк\кустомер-Кэй-Сторе** и убедитесь, что эта папка содержит файл **кустомеркэйсторе. csproj** .</span><span class="sxs-lookup"><span data-stu-id="8ca4d-349">In the codebase for the key store, go to the **customer-key-store\src\customer-key-store** folder, and verify that this folder contains the **customerkeystore.csproj** file.</span></span>

1. <span data-ttu-id="8ca4d-350">Выполнить: **Публикация DotNet**</span><span class="sxs-lookup"><span data-stu-id="8ca4d-350">Run: **dotnet publish**</span></span>

     <span data-ttu-id="8ca4d-351">В окне вывода отображается каталог, в котором была развернута публикация.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-351">The output window displays the directory where the publish was deployed.</span></span>

    <span data-ttu-id="8ca4d-352">Пример: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="8ca4d-352">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

1. <span data-ttu-id="8ca4d-353">Отправьте все файлы в каталоге публикации в ZIP-файл.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-353">Send all files in the publish directory to a .zip file.</span></span> <span data-ttu-id="8ca4d-354">При создании ZIP-файла убедитесь, что все файлы в каталоге находятся на корневом уровне ZIP-файла.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-354">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

1. <span data-ttu-id="8ca4d-355">Перетащите созданный ZIP-файл на сайт Зипдеплойуи, который вы открыли ранее.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-355">Drag and drop the .zip file you create to the ZipDeployUI site you opened above.</span></span> <span data-ttu-id="8ca4d-356">Пример: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="8ca4d-356">For example: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span></span>

<span data-ttu-id="8ca4d-357">ДКЕ развернута, и вы можете перейти к созданным тестовым ключам.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-357">DKE is deployed and you can browse to the test keys you've created.</span></span> <span data-ttu-id="8ca4d-358">Продолжите [проверку развертывания](#validate-your-deployment) ниже.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-358">Continue to [Validate your deployment](#validate-your-deployment) below.</span></span>

#### <a name="publish-via-ftp"></a><span data-ttu-id="8ca4d-359">Опубликовать через FTP</span><span class="sxs-lookup"><span data-stu-id="8ca4d-359">Publish via FTP</span></span>

1. <span data-ttu-id="8ca4d-360">Подключитесь к службе приложений, созданной [ранее](#publish-the-key-store).</span><span class="sxs-lookup"><span data-stu-id="8ca4d-360">Connect to the App Service you created [above](#publish-the-key-store).</span></span>

    <span data-ttu-id="8ca4d-361">В браузере перейдите по адресу: **Azure portal**  >  центр развертывания**службы приложений**портала Azure  >  **Deployment Center**  >  **развертывание**  >  **FTP**  >  **панели мониторинга**FTP.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-361">In your browser, go to: **Azure portal** > **App Service** > **Deployment Center** > **Manual Deployment** > **FTP** > **Dashboard**.</span></span>

1. <span data-ttu-id="8ca4d-362">Скопируйте строки подключения, отображаемые в локальный файл.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-362">Copy the connection strings displayed to a local file.</span></span> <span data-ttu-id="8ca4d-363">Эти строки будут использоваться для подключения к службе веб-приложений и отправки файлов через FTP.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-363">You'll use these strings to connect to the Web App Service and upload files via FTP.</span></span>

    <span data-ttu-id="8ca4d-364">Пример:</span><span class="sxs-lookup"><span data-stu-id="8ca4d-364">For example:</span></span>

    :::image type="content" source="../media/dke-ftp-dashboard.png" alt-text="Копирование строк подключения из панели мониторинга FTP":::

1. <span data-ttu-id="8ca4d-366">В базе кода для хранилища ключей перейдите в **Каталог Кустомер-Кэй-сторе\срк\кустомер-Кэй-Сторе**.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-366">In the codebase for the key storage, go to the **customer-key-store\src\customer-key-store directory**.</span></span>

1. <span data-ttu-id="8ca4d-367">Убедитесь, что этот каталог содержит файл **кустомеркэйсторе. csproj** .</span><span class="sxs-lookup"><span data-stu-id="8ca4d-367">Verify that this directory contains the **customerkeystore.csproj** file.</span></span>

1. <span data-ttu-id="8ca4d-368">Выполнить: **Публикация DotNet**</span><span class="sxs-lookup"><span data-stu-id="8ca4d-368">Run: **dotnet publish**</span></span>

    <span data-ttu-id="8ca4d-369">Выходные данные содержат каталог, в котором развернута публикация.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-369">The output contains the directory where the publish was deployed.</span></span>

    <span data-ttu-id="8ca4d-370">Пример: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="8ca4d-370">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

1. <span data-ttu-id="8ca4d-371">Отправьте все файлы в каталоге публикации в ZIP-файл.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-371">Send all files in the publish directory to a zip file.</span></span> <span data-ttu-id="8ca4d-372">При создании ZIP-файла убедитесь, что все файлы в каталоге находятся на корневом уровне ZIP-файла.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-372">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

1. <span data-ttu-id="8ca4d-373">В клиенте FTP используйте сведения о подключении, скопированные для подключения к службе приложений.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-373">From your FTP client, use the connection information you copied to connect to your App Service.</span></span> <span data-ttu-id="8ca4d-374">Отправьте ZIP-файл, созданный на предыдущем шаге, в корневой каталог веб-приложения.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-374">Upload the .zip file you created in the previous step to the root directory of your Web App.</span></span>

<span data-ttu-id="8ca4d-375">ДКЕ развернута, и вы можете перейти к созданным тестовым ключам.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-375">DKE is deployed and you can browse to the test keys you'd created.</span></span> <span data-ttu-id="8ca4d-376">Затем [Подтвердите развертывание](#validate-your-deployment).</span><span class="sxs-lookup"><span data-stu-id="8ca4d-376">Next, [Validate your deployment](#validate-your-deployment).</span></span>

### <a name="validate-your-deployment"></a><span data-ttu-id="8ca4d-377">Проверка развертывания</span><span class="sxs-lookup"><span data-stu-id="8ca4d-377">Validate your deployment</span></span>

<span data-ttu-id="8ca4d-378">После развертывания ДКЕ с помощью одного из методов, описанных выше, проверяйте развертывание и параметры хранилища ключей.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-378">After deploying DKE using one of the methods described above, validate the deployment and the key store settings.</span></span>

<span data-ttu-id="8ca4d-379">Выполняем</span><span class="sxs-lookup"><span data-stu-id="8ca4d-379">Run:</span></span>

<span data-ttu-id="8ca4d-380">src\customer-key-store\scripts\key_store_tester.ps1 микэйстореурл/микэй</span><span class="sxs-lookup"><span data-stu-id="8ca4d-380">src\customer-key-store\scripts\key_store_tester.ps1 mykeystoreurl/mykey</span></span>

<span data-ttu-id="8ca4d-381">Пример:</span><span class="sxs-lookup"><span data-stu-id="8ca4d-381">For example:</span></span>

<span data-ttu-id="8ca4d-382">key_store_tester.ps1https://mycustomerkeystore.com/mykey</span><span class="sxs-lookup"><span data-stu-id="8ca4d-382">key_store_tester.ps1 https://mycustomerkeystore.com/mykey</span></span>

<span data-ttu-id="8ca4d-383">Убедитесь, что в выходных данных не отображаются ошибки.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-383">Ensure that no errors appear in the output.</span></span> <span data-ttu-id="8ca4d-384">Когда вы будете готовы, [Зарегистрируйте свое хранилище ключей](#register-your-key-store).</span><span class="sxs-lookup"><span data-stu-id="8ca4d-384">When you're ready, [register your key store](#register-your-key-store).</span></span>

## <a name="register-your-key-store"></a><span data-ttu-id="8ca4d-385">Регистрация своего хранилища ключей</span><span class="sxs-lookup"><span data-stu-id="8ca4d-385">Register your key store</span></span>

<span data-ttu-id="8ca4d-386">Следующие действия позволяют зарегистрировать свое хранилище ключей.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-386">The following steps enable you to register your key store.</span></span> <span data-ttu-id="8ca4d-387">Регистрация основного хранилища — это последний шаг в развертывании ДКЕ, прежде чем вы сможете создавать метки.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-387">Registering your key store is the last step in deploying DKE before you can start creating labels.</span></span>

<span data-ttu-id="8ca4d-388">Чтобы зарегистрировать свое хранилище ключей:</span><span class="sxs-lookup"><span data-stu-id="8ca4d-388">To register your key store:</span></span>

1. <span data-ttu-id="8ca4d-389">В браузере откройте [портал Microsoft Azure](https://ms.portal.azure.com/)и перейдите ко **всем** \> **Identity** \> **регистрациям приложений**удостоверений для служб.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-389">In your browser, open the [Microsoft Azure portal](https://ms.portal.azure.com/), and go to **All Services** \> **Identity** \> **App Registrations**.</span></span>

2. <span data-ttu-id="8ca4d-390">Нажмите кнопку **создать регистрацию**и введите понятное имя.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-390">Select **New registration**, and enter a meaningful name.</span></span>

3. <span data-ttu-id="8ca4d-391">Выберите тип учетной записи в отображаемых параметрах.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-391">Select an account type from the options displayed.</span></span>

    <span data-ttu-id="8ca4d-392">Если вы используете Microsoft Azure с нестандартным доменом, например **onmicrosoft.com**, выберите **учетные записи только в данном организационном каталоге (только Microsoft — один клиент).**</span><span class="sxs-lookup"><span data-stu-id="8ca4d-392">If you're using Microsoft Azure with a non-custom domain, such as **onmicrosoft.com**, select **Accounts in this organizational directory only (Microsoft only - Single tenant).**</span></span>

    <span data-ttu-id="8ca4d-393">Пример:</span><span class="sxs-lookup"><span data-stu-id="8ca4d-393">For example:</span></span>

    :::image type="content" source="../media/dke-app-registration.png" alt-text="Регистрация нового приложения":::

4. <span data-ttu-id="8ca4d-395">В нижней части страницы выберите пункт **Регистрация** , чтобы создать новую регистрацию приложения.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-395">At the bottom of the page, select **Register** to create the new App Registration.</span></span>

5. <span data-ttu-id="8ca4d-396">В разделе Управление новой регистрацией приложения в разделе **Управление**выберите **Проверка подлинности**.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-396">In your new App Registration, in the left pane, under **Manage**, select **Authentication**.</span></span>

6. <span data-ttu-id="8ca4d-397">Выберите **элемент добавить платформу**.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-397">Select **Add a platform**.</span></span>
 
7. <span data-ttu-id="8ca4d-398">В меню **Настройка платформы** выберите пункт **веб**.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-398">On the **Configure platforms** popup, select **Web**.</span></span>
 
8. <span data-ttu-id="8ca4d-399">В разделе **URI перенаправления**введите универсальный код ресурса (URI) для службы шифрования двойных ключей.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-399">Under **Redirect URIs**, enter the URI of your double key encryption service.</span></span> <span data-ttu-id="8ca4d-400">Введите URL-адрес службы приложений, включая имя узла и домен.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-400">Enter the App Service URL, including both the hostname and domain.</span></span>

    <span data-ttu-id="8ca4d-401">Пример: https://mycustomerkeystoretest.com</span><span class="sxs-lookup"><span data-stu-id="8ca4d-401">For example: https://mycustomerkeystoretest.com</span></span>

    - <span data-ttu-id="8ca4d-402">Введенный URL-адрес должен быть соответствующим имени узла, на котором развернуто ваше хранилище ключей.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-402">The URL you enter must match the hostname where your key store is deployed.</span></span>
    - <span data-ttu-id="8ca4d-403">Если вы тестируете локально с помощью Visual Studio, используйте **https://localhost:5001** .</span><span class="sxs-lookup"><span data-stu-id="8ca4d-403">If you're testing locally with Visual Studio, use **https://localhost:5001**.</span></span>
    - <span data-ttu-id="8ca4d-404">Во всех случаях схема должна иметь значение **HTTPS**.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-404">In all cases, the scheme must be **https**.</span></span>

    <span data-ttu-id="8ca4d-405">Убедитесь, что имя узла совпадает с именем узла службы приложений.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-405">Ensure the hostname exactly matches your App Service host name.</span></span> <span data-ttu-id="8ca4d-406">Возможно, вы изменили его на `localhost` "Устранение неполадок сборки".</span><span class="sxs-lookup"><span data-stu-id="8ca4d-406">You may have changed it to `localhost` to troubleshoot the build.</span></span> <span data-ttu-id="8ca4d-407">В **appsettings.json**это имя узла, для которого задано значение `JwtAudience` .</span><span class="sxs-lookup"><span data-stu-id="8ca4d-407">In **appsettings.json**, this value is the hostname you set for `JwtAudience`.</span></span>

6. <span data-ttu-id="8ca4d-408">В разделе **неявное предоставление разрешений**установите флажок **маркеры ID** .</span><span class="sxs-lookup"><span data-stu-id="8ca4d-408">Under **Implicit grant**, select the **ID tokens** checkbox.</span></span>

1. <span data-ttu-id="8ca4d-409">Нажмите кнопку **Сохранить**, чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-409">Select **Save** to save your changes.</span></span>

7. <span data-ttu-id="8ca4d-410">В левой области выберите **Показать API**, а затем рядом с URI идентификатора приложения выберите **Set (установить**).</span><span class="sxs-lookup"><span data-stu-id="8ca4d-410">On the left pane, select **Expose an API**, then next to Application ID URI, select **Set**.</span></span>

9. <span data-ttu-id="8ca4d-411">По-прежнему откройте страницу **API** , в области **области, определяемые этой** областью API выберите **Добавить область**.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-411">Still on the **Expose an API** page, in the **Scopes defined by this API** area, select **Add a scope**.</span></span> <span data-ttu-id="8ca4d-412">В новой области:</span><span class="sxs-lookup"><span data-stu-id="8ca4d-412">In the new scope:</span></span>

    1. <span data-ttu-id="8ca4d-413">Определите имя области как **user_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-413">Define the scope name as **user_impersonation**.</span></span>

    2. <span data-ttu-id="8ca4d-414">Выберите администраторов и пользователей, которым разрешено согласие.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-414">Select the administrators and users who can consent.</span></span>

    3. <span data-ttu-id="8ca4d-415">Определите все остальные необходимые значения.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-415">Define any remaining values required.</span></span>

    4. <span data-ttu-id="8ca4d-416">Выберите **Добавить область.**</span><span class="sxs-lookup"><span data-stu-id="8ca4d-416">Select **Add scope.**</span></span>

    <span data-ttu-id="8ca4d-417">В верхней части нажмите кнопку **сохранить** , чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-417">Select **Save** at the top to save your changes.</span></span>

10. <span data-ttu-id="8ca4d-418">По-прежнему на странице " **предоставление доступа к API** " в области **Авторизованные клиентские приложения** выберите **добавить клиентское приложение**.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-418">Still on the **Expose an API** page, in the **Authorized client applications** area, select **Add a client application**.</span></span>

    <span data-ttu-id="8ca4d-419">В новом клиентском приложении:</span><span class="sxs-lookup"><span data-stu-id="8ca4d-419">In the new client application:</span></span>

    1. <span data-ttu-id="8ca4d-420">Определите идентификатор клиента как **d3590ed6-52b3-4102-aeff-aad2292ab01c**.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-420">Define the Client ID as **d3590ed6-52b3-4102-aeff-aad2292ab01c**.</span></span> <span data-ttu-id="8ca4d-421">Это значение является ИДЕНТИФИКАТОРом клиента Microsoft Office и позволяет Office получить маркер доступа для вашего хранилища ключей.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-421">This value is the Microsoft Office client ID, and enables Office to obtain an access token for your key store.</span></span>

    2. <span data-ttu-id="8ca4d-422">В разделе **Разрешенные области**выберите область **user_impersonation** .</span><span class="sxs-lookup"><span data-stu-id="8ca4d-422">Under **Authorized scopes**, select the **user_impersonation** scope.</span></span>

    3. <span data-ttu-id="8ca4d-423">Нажмите кнопку **Добавить приложение**.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-423">Select **Add application**.</span></span>

    4. <span data-ttu-id="8ca4d-424">В верхней части нажмите кнопку **сохранить** , чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-424">Select **Save** at the top to save your changes.</span></span>

<span data-ttu-id="8ca4d-425">Теперь ваше хранилище ключей ДКЕ зарегистрировано.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-425">Your DKE key store is now registered.</span></span> <span data-ttu-id="8ca4d-426">Продолжите [Создание меток с помощью дке](#create-labels-using-dke).</span><span class="sxs-lookup"><span data-stu-id="8ca4d-426">Continue by [creating labels using DKE](#create-labels-using-dke).</span></span>

## <a name="create-labels-using-dke"></a><span data-ttu-id="8ca4d-427">Создание меток с помощью ДКЕ</span><span class="sxs-lookup"><span data-stu-id="8ca4d-427">Create labels using DKE</span></span>

<span data-ttu-id="8ca4d-428">В центре соответствия требованиям Microsoft 365 создайте новую метку чувствительности и примените шифрование, как в противном случае.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-428">In the Microsoft 365 compliance center, create a new sensitivity label and apply encryption as you would otherwise.</span></span> <span data-ttu-id="8ca4d-429">Выберите **использовать шифрование с двойным ключом** и введите URL-адрес конечной точки для своего ключа.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-429">Select **Use Double Key Encryption** and enter the endpoint URL for your key.</span></span>

<span data-ttu-id="8ca4d-430">Пример:</span><span class="sxs-lookup"><span data-stu-id="8ca4d-430">For example:</span></span>

:::image type="content" source="../media/dke-use-dke.png" alt-text="Выберите использовать шифрование с двойным ключом в центре соответствия требованиям Microsoft 365":::

<span data-ttu-id="8ca4d-432">Все добавляемые метки ДКЕ будут отображаться для пользователей в последних версиях приложений Microsoft 365 для предприятий.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-432">Any DKE labels you add will start appearing for users in the latest versions of Microsoft 365 Apps for enterprise.</span></span>

> [!NOTE]
> <span data-ttu-id="8ca4d-433">Для обновления клиентов с новыми метками может потребоваться до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-433">It may take up to 24 hours for the clients to refresh with the new labels.</span></span>

### <a name="enable-dke-in-your-client"></a><span data-ttu-id="8ca4d-434">Включение ДКЕ в клиенте</span><span class="sxs-lookup"><span data-stu-id="8ca4d-434">Enable DKE in your client</span></span>

<span data-ttu-id="8ca4d-435">Если метки ДКЕ не отображаются на ленте чувствительность в Microsoft Office, возможно, у клиента ДКЕ не включена.</span><span class="sxs-lookup"><span data-stu-id="8ca4d-435">If your DKE labels don't appear under the Sensitivity ribbon in Microsoft Office, your client may not have DKE enabled.</span></span>

<span data-ttu-id="8ca4d-436">Включите ДКЕ для клиента, добавив следующие разделы реестра:</span><span class="sxs-lookup"><span data-stu-id="8ca4d-436">Enable DKE for your client by adding the following registry keys:</span></span>

```ini
    [HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001

    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001
```
