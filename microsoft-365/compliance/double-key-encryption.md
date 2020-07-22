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
ms.openlocfilehash: 47fc4bc47831970ef7a7f2087cf6c86b6fefb8c2
ms.sourcegitcommit: fe20f5ed07f38786c63df0f73659ca472e69e478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/21/2020
ms.locfileid: "45201777"
---
# <a name="double-key-encryption-dke"></a><span data-ttu-id="4baea-103">Шифрование с двойным ключом (ДКЕ)</span><span class="sxs-lookup"><span data-stu-id="4baea-103">Double Key Encryption (DKE)</span></span>

> <span data-ttu-id="4baea-104">*Применимо к: [соответствие требованиям Microsoft 365](https://www.microsoft.com/microsoft-365/business/compliance-management), [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*</span><span class="sxs-lookup"><span data-stu-id="4baea-104">*Applies to: [Microsoft 365 Compliance](https://www.microsoft.com/microsoft-365/business/compliance-management), [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*</span></span>
>
> <span data-ttu-id="4baea-105">*Инструкции для: [клиент единой метки Azure Information Protection для Windows](https://docs.microsoft.com/azure/information-protection/faqs.md#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span><span class="sxs-lookup"><span data-stu-id="4baea-105">*Instructions for: [Azure Information Protection unified labeling client for Windows](https://docs.microsoft.com/azure/information-protection/faqs.md#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span></span>
>
> <span data-ttu-id="4baea-106">*Описание службы: [соответствие требованиям Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span><span class="sxs-lookup"><span data-stu-id="4baea-106">*Service description for: [Microsoft 365 Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span></span>

<span data-ttu-id="4baea-107">Эта общедоступная Предварительная версия шифрования с двойным ключом (ДКЕ) позволяет использовать клиент единой метки Azure Information Protection для защиты строго конфиденциального содержимого, сохраняя полный контроль над ключом.</span><span class="sxs-lookup"><span data-stu-id="4baea-107">This public preview version of Double Key Encryption (DKE) enables you to use the Azure Information Protection Unified Labeling Client to protect highly sensitive content while maintaining full control of your key.</span></span>

<span data-ttu-id="4baea-108">Для доступа к защищенному содержимому с помощью двойного шифрования необходимо использовать два ключа (совместно).</span><span class="sxs-lookup"><span data-stu-id="4baea-108">Double Key Encryption requires two keys, used together, to access protected content.</span></span> <span data-ttu-id="4baea-109">Вы храните один ключ в Microsoft Azure, и вы держите другой ключ.</span><span class="sxs-lookup"><span data-stu-id="4baea-109">You store one key in Microsoft Azure, and you hold the other key.</span></span>

<span data-ttu-id="4baea-110">Двойное шифрование поддерживает развертывания как в облаке, так и в локальных развертываниях.</span><span class="sxs-lookup"><span data-stu-id="4baea-110">Double Key Encryption supports both cloud and on-premises deployments.</span></span> <span data-ttu-id="4baea-111">Эти развертывания помогают убедиться, что зашифрованные данные остаются непрозрачными везде, где хранятся защищенные данные.</span><span class="sxs-lookup"><span data-stu-id="4baea-111">These deployments help to ensure that encrypted data remains opaque wherever you store the protected data.</span></span>

<span data-ttu-id="4baea-112">Дополнительные сведения о корневых ключах облачных клиентов по умолчанию можно найти в статье [планирование и реализация ключа клиента Azure Information Protection](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key).</span><span class="sxs-lookup"><span data-stu-id="4baea-112">For more information about the default, cloud-based tenant root keys, see [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key).</span></span>

<span data-ttu-id="4baea-113">Двойное Ключическое шифрование аналогично полю безопасности, для которого требуется получить доступ к банковскому ключу и ключу клиента.</span><span class="sxs-lookup"><span data-stu-id="4baea-113">Double Key Encryption is similar to a safety deposit box that requires both a bank key and a customer key to gain access.</span></span> <span data-ttu-id="4baea-114">Для расшифровки защищенного контента необходимо использовать управляемый ключ Майкрософт и ключ, удерживаемый клиентом.</span><span class="sxs-lookup"><span data-stu-id="4baea-114">To decrypt protected content, you must use both the Microsoft managed key and the customer-held key.</span></span>

<span data-ttu-id="4baea-115">В следующем видеоролике показано, как работает двойное шифрование для защиты контента.</span><span class="sxs-lookup"><span data-stu-id="4baea-115">The following video shows how Double Key Encryption works to secure your content.</span></span>

<span data-ttu-id="4baea-116">Если у вашей организации есть какие – либо из следующих требований, вы можете использовать ДКЕ для защиты своего содержимого:</span><span class="sxs-lookup"><span data-stu-id="4baea-116">If your organizations have any of the following requirements, you can use DKE to help secure your content:</span></span>

- <span data-ttu-id="4baea-117">Вы хотите убедиться, что *только вы* можете расшифровывать защищенный контент при всех обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="4baea-117">You want to ensure that *only you* can ever decrypt protected content, under all circumstances.</span></span>
- <span data-ttu-id="4baea-118">Вы не хотите, чтобы у корпорации Майкрософт был доступ к защищенным данным самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="4baea-118">You don't want Microsoft to have access to protected data on its own.</span></span>
- <span data-ttu-id="4baea-119">Соблюдение нормативных требований для хранения ключей в пределах географической границы.</span><span class="sxs-lookup"><span data-stu-id="4baea-119">You have regulatory requirements to hold keys within a geographical boundary.</span></span> <span data-ttu-id="4baea-120">Все ключи, удерживаемые клиентом для шифрования и расшифровки данных, поддерживаются в центре обработки данных.</span><span class="sxs-lookup"><span data-stu-id="4baea-120">All customer-held keys for data encryption and decryption are maintained in your data center.</span></span>

> [!VIDEO https://msit.microsoftstream.com/embed/video/f466a1ff-0400-a936-221c-f1eab45dc756]

## <a name="system-and-licensing-requirements-for-dke"></a><span data-ttu-id="4baea-121">Требования к системе и лицензированию для ДКЕ</span><span class="sxs-lookup"><span data-stu-id="4baea-121">System and licensing requirements for DKE</span></span>

<span data-ttu-id="4baea-122">Этот общедоступный ознакомительный выпуск с двойным ключом шифрования для Microsoft 365 доступен в составе Microsoft 365 а и Office 365.</span><span class="sxs-lookup"><span data-stu-id="4baea-122">This public preview release of Double Key Encryption for Microsoft 365 is available as part of Microsoft 365 E5 and Office 365 E5.</span></span> <span data-ttu-id="4baea-123">Если у вас нет лицензии на Microsoft 365, вы можете зарегистрироваться для получения [пробной версии](https://aka.ms/M365E5ComplianceTrial).</span><span class="sxs-lookup"><span data-stu-id="4baea-123">If you don’t have a Microsoft 365 E5 license, you can sign up for a [trial](https://aka.ms/M365E5ComplianceTrial).</span></span> <span data-ttu-id="4baea-124">Для получения дополнительных сведений об этих лицензиях обратитесь к разделу [руководство по лицензированию Microsoft 365 для обеспечения безопасности & соответствия требованиям](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="4baea-124">For more information about these licenses, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

<span data-ttu-id="4baea-125">**Предварительная сборка Office** Для использования общедоступной предварительной версии вы должны быть участником программы предварительной оценки Office.</span><span class="sxs-lookup"><span data-stu-id="4baea-125">**Office Insider** To use the public preview, you must be a member of the Office Insider program.</span></span> <span data-ttu-id="4baea-126">Чтобы присоединиться к программе предварительной оценки Office, перейдите на страницу [https://insider.office.com](https://insider.office.com) .</span><span class="sxs-lookup"><span data-stu-id="4baea-126">To join Office Insider, go to [https://insider.office.com](https://insider.office.com).</span></span> <span data-ttu-id="4baea-127">Когда вы являетесь участником, подготовьте среду к развертыванию сборок для участников программы предварительной оценки Office, выбрав нужный метод развертывания для своей организации.</span><span class="sxs-lookup"><span data-stu-id="4baea-127">Once you're a member, prepare your environment to deploy Office Insider builds by choosing the right deployment method for your organization.</span></span> <span data-ttu-id="4baea-128">Инструкции приведены в разделе [Начало работы по развертыванию сборок для участников программы предварительной оценки Office](https://insider.office.com/business/deploy).</span><span class="sxs-lookup"><span data-stu-id="4baea-128">For instructions, see [Getting started on deploying Office Insider builds](https://insider.office.com/business/deploy).</span></span>

<span data-ttu-id="4baea-129">**Azure Information Protection**.</span><span class="sxs-lookup"><span data-stu-id="4baea-129">**Azure Information Protection**.</span></span> <span data-ttu-id="4baea-130">ДКЕ работает с метками конфиденциальности и требует использования Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="4baea-130">DKE works with sensitivity labels and requires Azure Information Protection.</span></span>

## <a name="supported-environments-for-storing-and-viewing-dke-protected-content"></a><span data-ttu-id="4baea-131">Поддерживаемые среды для хранения и просмотра защищенного ДКЕ контента</span><span class="sxs-lookup"><span data-stu-id="4baea-131">Supported environments for storing and viewing DKE-protected content</span></span>

<span data-ttu-id="4baea-132">**Поддерживаемые приложения**.</span><span class="sxs-lookup"><span data-stu-id="4baea-132">**Supported applications**.</span></span> <span data-ttu-id="4baea-133">[Приложения Microsoft 365 для корпоративных](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) клиентов в Windows, в том числе Word, Excel и PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="4baea-133">[Microsoft 365 Apps for enterprise](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) clients on Windows, including Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="4baea-134">**Поддержка интерактивного содержимого**.</span><span class="sxs-lookup"><span data-stu-id="4baea-134">**Online content support**.</span></span> <span data-ttu-id="4baea-135">Документы и файлы, хранящиеся в Интернете, поддерживаются как в Microsoft SharePoint, так и в OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="4baea-135">Documents and files stored online in both Microsoft SharePoint and OneDrive for Business are supported.</span></span> <span data-ttu-id="4baea-136">Вы можете предоставить доступ к зашифрованному содержимому по электронной почте, но вы не можете просматривать зашифрованные документы и файлы в Интернете.</span><span class="sxs-lookup"><span data-stu-id="4baea-136">You can share encrypted content by email, but you can't view encrypted documents and files online.</span></span> <span data-ttu-id="4baea-137">Вместо этого необходимо просмотреть защищенный контент с помощью классических приложений на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="4baea-137">Instead, you must view protected content using the desktop apps on your local computer.</span></span>

## <a name="about-this-public-preview-article"></a><span data-ttu-id="4baea-138">Об этой общедоступной статье предварительной версии</span><span class="sxs-lookup"><span data-stu-id="4baea-138">About this public preview article</span></span>

<span data-ttu-id="4baea-139">Существует несколько способов выполнить некоторые действия по развертыванию двойного шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="4baea-139">There are several ways you can complete some of the steps to deploy Double Key Encryption.</span></span> <span data-ttu-id="4baea-140">В этой статье приводятся подробные инструкции, позволяющие менее опытным администраторам успешно развертывать службу.</span><span class="sxs-lookup"><span data-stu-id="4baea-140">This article provides detailed instructions so that less experienced admins successfully deploy the service.</span></span> <span data-ttu-id="4baea-141">Если у вас возникли общие технологии, например Git, совместно используемые методами развертывания, описанными в этой статье, вы можете использовать собственные методы.</span><span class="sxs-lookup"><span data-stu-id="4baea-141">If you're experienced with the common technologies, such as git, shared by the deployment methods described in this article, you can choose to use your own methods.</span></span>

<span data-ttu-id="4baea-142">Для общедоступной предварительной версии мы включили пошаговые инструкции по развертыванию службы шифрования двойных ключей в Azure.</span><span class="sxs-lookup"><span data-stu-id="4baea-142">For public preview, we've included step-by-step instructions on how to deploy the Double Key Encryption service to Azure.</span></span> <span data-ttu-id="4baea-143">Этот сценарий не является чем-то вероятным действием в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="4baea-143">This scenario isn't something you'd likely do in production.</span></span> <span data-ttu-id="4baea-144">Для общедоступной предварительной версии с помощью Azure можно быстро приступить к работе с двойным ключом шифрования сразу.</span><span class="sxs-lookup"><span data-stu-id="4baea-144">For public preview using Azure is a quick way to deploy that lets you get started using Double Key Encryption right away.</span></span>

<span data-ttu-id="4baea-145">Службу можно развернуть везде, где угодно, независимо от того, находится ли она локально в вашей сети или с другим поставщиком.</span><span class="sxs-lookup"><span data-stu-id="4baea-145">You can choose to deploy the service wherever you want, whether it's locally on your network or with another provider.</span></span> <span data-ttu-id="4baea-146">Необходимо опубликовать хранилище ключей с помощью методов, соответствующих этому расположению.</span><span class="sxs-lookup"><span data-stu-id="4baea-146">You'll need to publish the key store using methods appropriate for that location.</span></span>

## <a name="deploy-double-key-encryption"></a><span data-ttu-id="4baea-147">Развертывание двойного шифрования ключей</span><span class="sxs-lookup"><span data-stu-id="4baea-147">Deploy Double Key Encryption</span></span>

<span data-ttu-id="4baea-148">Ниже приведены общие действия по настройке шифрования с двойным ключом для Организации.</span><span class="sxs-lookup"><span data-stu-id="4baea-148">You'll follow these general steps to set up Double Key Encryption for your organization.</span></span> <span data-ttu-id="4baea-149">В примере, приведенном в этой статье, используется Azure в качестве места назначения развертывания для службы ДКЕ.</span><span class="sxs-lookup"><span data-stu-id="4baea-149">The example in this article uses Azure as the deployment destination for the DKE service.</span></span> <span data-ttu-id="4baea-150">При развертывании в другом расположении необходимо указать собственные значения.</span><span class="sxs-lookup"><span data-stu-id="4baea-150">If you're deploying to another location, you'll need to provide your own values.</span></span>

1. [<span data-ttu-id="4baea-151">Установка необходимого программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="4baea-151">Install software prerequisites</span></span>](#install-software-prerequisites)
1. [<span data-ttu-id="4baea-152">Клонировать репозиторий GitHub шифрования с двойным ключом</span><span class="sxs-lookup"><span data-stu-id="4baea-152">Clone the Double Key Encryption GitHub repository</span></span>](#clone-the-dke-github-repository)
1. [<span data-ttu-id="4baea-153">Изменение параметров приложения</span><span class="sxs-lookup"><span data-stu-id="4baea-153">Modify application settings</span></span>](#modify-application-settings)
1. [<span data-ttu-id="4baea-154">Создание тестовых ключей</span><span class="sxs-lookup"><span data-stu-id="4baea-154">Generate test keys</span></span>](#generate-test-keys)
1. [<span data-ttu-id="4baea-155">Построение проекта</span><span class="sxs-lookup"><span data-stu-id="4baea-155">Build the project</span></span>](#build-the-project)
1. [<span data-ttu-id="4baea-156">Публикация хранилища ключей</span><span class="sxs-lookup"><span data-stu-id="4baea-156">Publish the key store</span></span>](#publish-the-key-store)
1. [<span data-ttu-id="4baea-157">Проверка развертывания</span><span class="sxs-lookup"><span data-stu-id="4baea-157">Validate your deployment</span></span>](#validate-your-deployment)
1. [<span data-ttu-id="4baea-158">Регистрация своего хранилища ключей</span><span class="sxs-lookup"><span data-stu-id="4baea-158">Register your key store</span></span>](#register-your-key-store)
1. [<span data-ttu-id="4baea-159">Создание меток конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="4baea-159">Create sensitivity labels</span></span>](#create-labels-using-dke)

<span data-ttu-id="4baea-160">После этого вы сможете зашифровать документы и файлы с помощью ДКЕ.</span><span class="sxs-lookup"><span data-stu-id="4baea-160">When you're done, you can encrypt documents and files using DKE.</span></span> <span data-ttu-id="4baea-161">Сведения о том, [как применить метки конфиденциальности к файлам и электронной почте в Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).</span><span class="sxs-lookup"><span data-stu-id="4baea-161">For information, see [Apply sensitivity labels to your files and email in Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).</span></span>

### <a name="install-software-prerequisites"></a><span data-ttu-id="4baea-162">Установка необходимого программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="4baea-162">Install software prerequisites</span></span>

<span data-ttu-id="4baea-163">Существует два типа требований к программному обеспечению для шифрования с двойным ключом.</span><span class="sxs-lookup"><span data-stu-id="4baea-163">There are two types of software prerequisites for Double Key Encryption</span></span>

- [<span data-ttu-id="4baea-164">Необходимые условия для службы шифрования с двойным шифрованием</span><span class="sxs-lookup"><span data-stu-id="4baea-164">Double Key Encryption service prerequisites</span></span>](#double-key-encryption-service-prerequisites)
- [<span data-ttu-id="4baea-165">Необходимые условия для шифрования с двойным ключом для клиентских компьютеров</span><span class="sxs-lookup"><span data-stu-id="4baea-165">Double Key Encryption prerequisites for client computers</span></span>](#double-key-encryption-prerequisites-for-client-computers)

#### <a name="double-key-encryption-service-prerequisites"></a><span data-ttu-id="4baea-166">Необходимые условия для службы шифрования с двойным шифрованием</span><span class="sxs-lookup"><span data-stu-id="4baea-166">Double Key Encryption service prerequisites</span></span>

<span data-ttu-id="4baea-167">Установите эти компоненты на компьютер, на котором необходимо установить службу ДКЕ.</span><span class="sxs-lookup"><span data-stu-id="4baea-167">Install these prerequisites on the computer where you want to install the DKE service.</span></span>

<span data-ttu-id="4baea-168">**Пакет SDK для .NET Core 3,1**.</span><span class="sxs-lookup"><span data-stu-id="4baea-168">**.NET Core 3.1 SDK**.</span></span> <span data-ttu-id="4baea-169">Скачайте и установите пакет SDK из центра [загрузки .NET Core 3,1](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span><span class="sxs-lookup"><span data-stu-id="4baea-169">Download and install the SDK from [Download .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span></span>

<span data-ttu-id="4baea-170">**Visual Studio Code**.</span><span class="sxs-lookup"><span data-stu-id="4baea-170">**Visual Studio Code**.</span></span> <span data-ttu-id="4baea-171">Скачайте Visual Studio Code FROM [https://code.visualstudio.com/](https://code.visualstudio.com) .</span><span class="sxs-lookup"><span data-stu-id="4baea-171">Download Visual Studio Code from [https://code.visualstudio.com/](https://code.visualstudio.com).</span></span> <span data-ttu-id="4baea-172">После установки запустите Visual Studio Code и выберите **View** \> **Extensions**.</span><span class="sxs-lookup"><span data-stu-id="4baea-172">Once installed, run Visual Studio Code and select **View** \> **Extensions**.</span></span> <span data-ttu-id="4baea-173">Установите эти расширения.</span><span class="sxs-lookup"><span data-stu-id="4baea-173">Install these extensions.</span></span>

- <span data-ttu-id="4baea-174">C# для Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="4baea-174">C# for Visual Studio Code</span></span>

- <span data-ttu-id="4baea-175">Диспетчер пакетов NuGet</span><span class="sxs-lookup"><span data-stu-id="4baea-175">NuGet Package Manager</span></span>

<span data-ttu-id="4baea-176">**Предварительная оценка Microsoft Office**.</span><span class="sxs-lookup"><span data-stu-id="4baea-176">**Microsoft Office Insider**.</span></span> <span data-ttu-id="4baea-177">Настройте по крайней мере один [метод развертывания](https://insider.office.com/business/deploy).</span><span class="sxs-lookup"><span data-stu-id="4baea-177">Set up at least one [deployment method](https://insider.office.com/business/deploy).</span></span>

<span data-ttu-id="4baea-178">**Ресурсы Git**.</span><span class="sxs-lookup"><span data-stu-id="4baea-178">**Git resources**.</span></span> <span data-ttu-id="4baea-179">Скачайте и установите один из следующих элементов.</span><span class="sxs-lookup"><span data-stu-id="4baea-179">Download and install one of the following.</span></span>

- [<span data-ttu-id="4baea-180">Git</span><span class="sxs-lookup"><span data-stu-id="4baea-180">Git</span></span>](https://git-scm.com/downloads)

- [<span data-ttu-id="4baea-181">Классическое приложение GitHub</span><span class="sxs-lookup"><span data-stu-id="4baea-181">GitHub Desktop</span></span>](https://desktop.github.com/)

- [<span data-ttu-id="4baea-182">GitHub Enterprise</span><span class="sxs-lookup"><span data-stu-id="4baea-182">GitHub Enterprise</span></span>](https://github.com/enterprise)

<span data-ttu-id="4baea-183">**OpenSSL** Для [создания тестовых ключей](#generate-test-keys) после развертывания дке необходимо установить [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) .</span><span class="sxs-lookup"><span data-stu-id="4baea-183">**OpenSSL** You must have [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) installed to [generate test keys](#generate-test-keys) after you deploy DKE.</span></span> <span data-ttu-id="4baea-184">Убедитесь, что вы правильно вызываете его из пути переменных среды.</span><span class="sxs-lookup"><span data-stu-id="4baea-184">Make sure you're invoking it correctly from your environment variables path.</span></span> <span data-ttu-id="4baea-185">Например, https://www.osradar.com/install-openssl-windows/ для получения дополнительных сведений обратитесь к разделу "Добавление каталога установки по пути".</span><span class="sxs-lookup"><span data-stu-id="4baea-185">For example, see "Add the installation directory to PATH" at https://www.osradar.com/install-openssl-windows/ for details.</span></span>

#### <a name="double-key-encryption-prerequisites-for-client-computers"></a><span data-ttu-id="4baea-186">Необходимые условия для шифрования с двойным ключом для клиентских компьютеров</span><span class="sxs-lookup"><span data-stu-id="4baea-186">Double Key Encryption prerequisites for client computers</span></span>

<span data-ttu-id="4baea-187">Установите эти компоненты на каждом клиентском компьютере, на котором требуется защитить и использовать защищенные документы.</span><span class="sxs-lookup"><span data-stu-id="4baea-187">Install these prerequisites on each client computer where you want to protect and consume protected documents.</span></span>

<span data-ttu-id="4baea-188">**Microsoft Office** версии \*. 12711 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="4baea-188">**Microsoft Office** version \*.12711 or later.</span></span>

<span data-ttu-id="4baea-189">**Azure Information Protection единой метки версий клиентов** 2.7.93.0 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="4baea-189">**Azure Information Protection Unified Labeling Client** versions 2.7.93.0 or later.</span></span> <span data-ttu-id="4baea-190">Скачайте и установите клиент единой метки от [корпорации Майкрософт](https://www.microsoft.com/download/details.aspx?id=53018).</span><span class="sxs-lookup"><span data-stu-id="4baea-190">Download and install the Unified Labeling client from [Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

### <a name="clone-the-dke-github-repository"></a><span data-ttu-id="4baea-191">Клонирование репозитория ДКЕ GitHub</span><span class="sxs-lookup"><span data-stu-id="4baea-191">Clone the DKE GitHub repository</span></span>

<span data-ttu-id="4baea-192">Майкрософт предоставляет исходные файлы ДКЕ в репозитории GitHub.</span><span class="sxs-lookup"><span data-stu-id="4baea-192">Microsoft supplies the DKE source files in a GitHub repository.</span></span> <span data-ttu-id="4baea-193">Необходимо клонировать репозиторий, чтобы создать проект локально для использования в Организации.</span><span class="sxs-lookup"><span data-stu-id="4baea-193">You clone the repository to build the project locally for your organization's use.</span></span> <span data-ttu-id="4baea-194">Репозиторий GitHub ДКЕ находится по адресу [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) .</span><span class="sxs-lookup"><span data-stu-id="4baea-194">The DKE GitHub repository is located at [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).</span></span>

<span data-ttu-id="4baea-195">Следующие инструкции предназначены для неопытных пользователей Git или Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="4baea-195">The following instructions are intended for inexperienced git or Visual Studio Code users:</span></span>

1. <span data-ttu-id="4baea-196">В браузере перейдите по адресу:[https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService)</span><span class="sxs-lookup"><span data-stu-id="4baea-196">In your browser, go to: [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService)</span></span>

1. <span data-ttu-id="4baea-197">В правой части экрана выберите **код**.</span><span class="sxs-lookup"><span data-stu-id="4baea-197">Towards the right side of the screen, select **Code**.</span></span> <span data-ttu-id="4baea-198">В вашей версии пользовательского интерфейса может отображаться кнопка " **Копировать" или "скачать** ".</span><span class="sxs-lookup"><span data-stu-id="4baea-198">Your version of the UI might show a **Clone or download** button.</span></span> <span data-ttu-id="4baea-199">Затем в появившемся раскрывающемся меню выберите значок Копировать, чтобы скопировать URL-адрес в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="4baea-199">Then, in the dropdown that appears, select the copy icon to copy the URL to your clipboard.</span></span>

    <span data-ttu-id="4baea-200">Пример:</span><span class="sxs-lookup"><span data-stu-id="4baea-200">For example:</span></span>

    :::image type="content" source="../media/dke-clone.png" alt-text="Клонирование базы данных двойных шифрования ключей из GitHub":::

3. <span data-ttu-id="4baea-202">В Visual Studio Code выберите пункт **Просмотреть** \> **палитру команд** и выберите **Git: Clone**.</span><span class="sxs-lookup"><span data-stu-id="4baea-202">In Visual Studio Code, select **View** \> **Command Palette** and select **Git: Clone**.</span></span> <span data-ttu-id="4baea-203">Чтобы перейти к параметру в списке, начните ввод, `git: clone` чтобы отфильтровать записи, а затем выберите его в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="4baea-203">To jump to the option in the list, start typing `git: clone` to filter the entries and then select it from the drop-down.</span></span> <span data-ttu-id="4baea-204">Пример:</span><span class="sxs-lookup"><span data-stu-id="4baea-204">For example:</span></span>

    :::image type="content" source="../media/dke-vscode-clone.png" alt-text="Visual Studio Code GIT: параметр Clone":::

4. <span data-ttu-id="4baea-206">В текстовом поле вставьте URL-адрес, который вы скопировали из Git, и выберите **клон из GitHub**.</span><span class="sxs-lookup"><span data-stu-id="4baea-206">In the text box, paste the URL that you copied from Git and select **Clone from GitHub**.</span></span>

5. <span data-ttu-id="4baea-207">В появившемся диалоговом окне **Выбор папки** найдите и выберите расположение для хранения репозитория.</span><span class="sxs-lookup"><span data-stu-id="4baea-207">In the **Select Folder** dialog that appears, browse to and select a location to store the repository.</span></span> <span data-ttu-id="4baea-208">В командной строки нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="4baea-208">At the prompt, select **Open**.</span></span>

    <span data-ttu-id="4baea-209">Репозиторий открывается в Visual Studio Code и отображается в левом нижнем углу текущей ветви Git.</span><span class="sxs-lookup"><span data-stu-id="4baea-209">The repository is opened in Visual Studio Code, and displays the current Git branch at the bottom left.</span></span> <span data-ttu-id="4baea-210">Текущая ветвь должна быть **основной**.</span><span class="sxs-lookup"><span data-stu-id="4baea-210">Your current branch should be **master**.</span></span>

    <span data-ttu-id="4baea-211">Пример:</span><span class="sxs-lookup"><span data-stu-id="4baea-211">For example:</span></span>

    :::image type="content" source="../media/dke-vscode-master.png" alt-text="Ветвь образца кода Visual Studio":::

6. <span data-ttu-id="4baea-213">Выберите образец Word **,** а затем в списке ветвей выберите пункт **public_preview** .</span><span class="sxs-lookup"><span data-stu-id="4baea-213">Select the word **master,** and then select **public_preview** from the list of branches.</span></span> 

   > [!IMPORTANT]
   > <span data-ttu-id="4baea-214">Выбор ветви public_preview позволяет убедиться, что у вас есть правильные файлы для построения проекта.</span><span class="sxs-lookup"><span data-stu-id="4baea-214">Selecting the public_preview branch ensures that you have the correct files to build the project.</span></span> <span data-ttu-id="4baea-215">Если не выбрать подходящую ветвь, произойдет ошибка развертывания.</span><span class="sxs-lookup"><span data-stu-id="4baea-215">If you do not choose the correct branch your deployment will fail.</span></span>

<span data-ttu-id="4baea-216">Теперь исходный репозиторий ДКЕ настроен локально.</span><span class="sxs-lookup"><span data-stu-id="4baea-216">You now have your DKE source repository set up locally.</span></span> <span data-ttu-id="4baea-217">Затем [измените параметры приложения](#modify-application-settings) для своей организации.</span><span class="sxs-lookup"><span data-stu-id="4baea-217">Next, [modify application settings](#modify-application-settings) for your organization.</span></span>

### <a name="modify-application-settings"></a><span data-ttu-id="4baea-218">Изменение параметров приложения</span><span class="sxs-lookup"><span data-stu-id="4baea-218">Modify application settings</span></span>

<span data-ttu-id="4baea-219">Чтобы развернуть службу ДКЕ, необходимо изменить следующие типы параметров приложений:</span><span class="sxs-lookup"><span data-stu-id="4baea-219">To deploy the DKE service, you must modify the following types of application settings:</span></span>

- [<span data-ttu-id="4baea-220">Параметры доступа к ключам</span><span class="sxs-lookup"><span data-stu-id="4baea-220">Key access settings</span></span>](#key-access-settings)
- [<span data-ttu-id="4baea-221">Параметры клиента и ключа</span><span class="sxs-lookup"><span data-stu-id="4baea-221">Tenant and key settings</span></span>](#tenant-and-key-settings)

<span data-ttu-id="4baea-222">Вы изменяете параметры приложения в appsettings.jsв файле.</span><span class="sxs-lookup"><span data-stu-id="4baea-222">You modify application settings in the appsettings.json file.</span></span> <span data-ttu-id="4baea-223">Этот файл находится в репозитории Даублекэйенкриптионсервице, который вы клонированы локально в Даублекэйенкриптионсервице\срк\кустомер-Кэй-Сторе.</span><span class="sxs-lookup"><span data-stu-id="4baea-223">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store.</span></span> <span data-ttu-id="4baea-224">Например, в Visual Studio Code можно перейти к файлу, как показано на рисунке ниже.</span><span class="sxs-lookup"><span data-stu-id="4baea-224">For example, in Visual Studio Code, you can browse to the file as shown in the following picture.</span></span>

:::image type="content" source="../media/dke-appsettingsjson.png" alt-text="Поиск appsettings.jsв файле для ДКЕ.":::

#### <a name="key-access-settings"></a><span data-ttu-id="4baea-226">Параметры доступа к ключам</span><span class="sxs-lookup"><span data-stu-id="4baea-226">Key access settings</span></span>

<span data-ttu-id="4baea-227">Укажите, следует ли использовать авторизацию электронной почты или ролей.</span><span class="sxs-lookup"><span data-stu-id="4baea-227">Choose whether to use email or role authorization.</span></span> <span data-ttu-id="4baea-228">ДКЕ поддерживает только один из этих методов проверки подлинности за раз.</span><span class="sxs-lookup"><span data-stu-id="4baea-228">DKE supports only one of these authentication methods at a time.</span></span>

- <span data-ttu-id="4baea-229">**Авторизация электронной почты**.</span><span class="sxs-lookup"><span data-stu-id="4baea-229">**Email authorization**.</span></span> <span data-ttu-id="4baea-230">Позволяет Организации авторизовать доступ к ключам только в соответствии с адресами электронной почты.</span><span class="sxs-lookup"><span data-stu-id="4baea-230">Allows your organization to authorize access to keys based on email addresses only.</span></span>

- <span data-ttu-id="4baea-231">**Авторизация ролей**.</span><span class="sxs-lookup"><span data-stu-id="4baea-231">**Role authorization**.</span></span> <span data-ttu-id="4baea-232">Позволяет Организации авторизовать доступ к ключам на основе групп Active Directory и требовать, чтобы веб-служба могла запрашивать LDAP.</span><span class="sxs-lookup"><span data-stu-id="4baea-232">Allows your organization to authorize access to keys based on Active Directory groups, and requires that the web service can query LDAP.</span></span>

<span data-ttu-id="4baea-233">Чтобы настроить параметры доступа к ключам для ДКЕ, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="4baea-233">To set key access settings for DKE:</span></span>

1. <span data-ttu-id="4baea-234">В **appsettings.js** "файл" определите только один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="4baea-234">In the **appsettings.json** file, define only one of these settings:</span></span>

   - <span data-ttu-id="4baea-235">Для проверки подлинности электронной почты выберите параметр **аусоризедемаиладдрессес** .</span><span class="sxs-lookup"><span data-stu-id="4baea-235">For email authorization, locate the **AuthorizedEmailAddresses** setting.</span></span> <span data-ttu-id="4baea-236">Добавьте адрес электронной почты, который нужно авторизовать.</span><span class="sxs-lookup"><span data-stu-id="4baea-236">Add the email address that you want to authorize.</span></span> <span data-ttu-id="4baea-237">Разделяйте адреса электронной почты двойными кавычками и запятыми.</span><span class="sxs-lookup"><span data-stu-id="4baea-237">Separate multiple email addresses with double quotes and commas.</span></span> <span data-ttu-id="4baea-238">Пример: **"' аусоризедемаиладдрессес '": ["email1@company.com", "email2@company.com", email3@company.com]**</span><span class="sxs-lookup"><span data-stu-id="4baea-238">For example: **" ‘AuthorizedEmailAddresses’ ": ["email1@company.com", "email2@company.com ", email3@company.com]**</span></span>

   :::image type="content" source="../media/dke-email-accesssetting.png" alt-text="appsettings.jsв файле с методом авторизации электронной почты":::

   - <span data-ttu-id="4baea-240">В разделе Авторизация роли выберите параметр **аусоризедролес** .</span><span class="sxs-lookup"><span data-stu-id="4baea-240">For role authorization, locate the **AuthorizedRoles** setting.</span></span> <span data-ttu-id="4baea-241">Определите имена групп ActiveDirectory, которые вы хотите авторизовать.</span><span class="sxs-lookup"><span data-stu-id="4baea-241">Define with the ActiveDirectory group names you want to authorize.</span></span> <span data-ttu-id="4baea-242">Пример: **"аусоризедролес": ["Group1", "group2", "group3"]**</span><span class="sxs-lookup"><span data-stu-id="4baea-242">For example: **"AuthorizedRoles": ["group1", "group2", "group3"]**</span></span>

   :::image type="content" source="../media/dke-role-accesssetting.png" alt-text="appsettings.jsдля файла с методом авторизации роли":::

2. <span data-ttu-id="4baea-244">Удалите параметр, не относящийся к выбранному способу проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="4baea-244">Remove the setting that isn't relevant for your chosen authorization method.</span></span>

#### <a name="tenant-and-key-settings"></a><span data-ttu-id="4baea-245">Параметры клиента и ключа</span><span class="sxs-lookup"><span data-stu-id="4baea-245">Tenant and key settings</span></span>

<span data-ttu-id="4baea-246">Параметры клиента и ключа ДКЕ размещаются в **appsettings.js** файла и **Startup.CS** .</span><span class="sxs-lookup"><span data-stu-id="4baea-246">DKE tenant and key settings are located in the **appsettings.json** file and the **startup.cs** file.</span></span>

<span data-ttu-id="4baea-247">В **appsettings.js** файла измените следующие значения:</span><span class="sxs-lookup"><span data-stu-id="4baea-247">In the **appsettings.json** file, modify the following values:</span></span>

- <span data-ttu-id="4baea-248">**Валидиссуерс**.</span><span class="sxs-lookup"><span data-stu-id="4baea-248">**ValidIssuers**.</span></span> <span data-ttu-id="4baea-249">Замените `<tenantid>` идентификатором GUID клиента.</span><span class="sxs-lookup"><span data-stu-id="4baea-249">Replace `<tenantid>` with your tenant GUID.</span></span>
- <span data-ttu-id="4baea-250">**Жвтаудиенце**.</span><span class="sxs-lookup"><span data-stu-id="4baea-250">**JwtAudience**.</span></span> <span data-ttu-id="4baea-251">Замените `<yourhostname>` на имя узла компьютера, на котором будет запускаться служба дке.</span><span class="sxs-lookup"><span data-stu-id="4baea-251">Replace `<yourhostname>` with the hostname of the machine where the DKE service will run.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="4baea-252">Значение для Жвтаудиенце должно *точно*совпадать с именем узла.</span><span class="sxs-lookup"><span data-stu-id="4baea-252">The value for JwtAudience must match the name of your host *exactly*.</span></span> <span data-ttu-id="4baea-253">В процессе отладки можно использовать **localhost: 5000** .</span><span class="sxs-lookup"><span data-stu-id="4baea-253">You may use **localhost:5000** while debugging.</span></span> <span data-ttu-id="4baea-254">Однако после завершения отладки обязательно обновите это значение с помощью имени узла сервера.</span><span class="sxs-lookup"><span data-stu-id="4baea-254">However, When you're done debugging, make sure to update this value to the server's hostname.</span></span>

- <span data-ttu-id="4baea-255">**Лдаппас**.</span><span class="sxs-lookup"><span data-stu-id="4baea-255">**LDAPPath**.</span></span> <span data-ttu-id="4baea-256">Задайте значение следующим образом:</span><span class="sxs-lookup"><span data-stu-id="4baea-256">Set the value as follows:</span></span>

  - <span data-ttu-id="4baea-257">Если вы используете авторизацию ролей, введите домен LDAP.</span><span class="sxs-lookup"><span data-stu-id="4baea-257">If you're using role authorization, enter the LDAP domain.</span></span>
  - <span data-ttu-id="4baea-258">Если вы используете авторизацию электронной почты, оставьте это значение пустым.</span><span class="sxs-lookup"><span data-stu-id="4baea-258">If you're using email authorization, leave this value empty.</span></span>

   <span data-ttu-id="4baea-259">Дополнительные сведения см. в разделе [параметры доступа к ключам](#key-access-settings).</span><span class="sxs-lookup"><span data-stu-id="4baea-259">For more information, see [Key access settings](#key-access-settings).</span></span>

- <span data-ttu-id="4baea-260">**Тесткэйс: имя**.</span><span class="sxs-lookup"><span data-stu-id="4baea-260">**TestKeys:Name**.</span></span> <span data-ttu-id="4baea-261">Введите имя для ключа.</span><span class="sxs-lookup"><span data-stu-id="4baea-261">Enter a name for your key.</span></span> <span data-ttu-id="4baea-262">Пример: **TestKey1**</span><span class="sxs-lookup"><span data-stu-id="4baea-262">Example: **TestKey1**</span></span>
- <span data-ttu-id="4baea-263">**Тесткэйс: ID**. Создайте GUID и введите его в качестве значения **тесткэйс: ID** .</span><span class="sxs-lookup"><span data-stu-id="4baea-263">**TestKeys:Id**. Create a GUID and enter it as the **TestKeys:ID** value.</span></span> <span data-ttu-id="4baea-264">Например, **DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE**.</span><span class="sxs-lookup"><span data-stu-id="4baea-264">For example, **DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE**.</span></span> <span data-ttu-id="4baea-265">Для случайного создания GUID можно использовать сайт, например, [генератор GUID в Интернете](https://guidgenerator.com/) .</span><span class="sxs-lookup"><span data-stu-id="4baea-265">You can use a site like [Online GUID Generator](https://guidgenerator.com/) to randomly generate a GUID.</span></span>

### <a name="generate-test-keys"></a><span data-ttu-id="4baea-266">Создание тестовых ключей</span><span class="sxs-lookup"><span data-stu-id="4baea-266">Generate test keys</span></span>

<span data-ttu-id="4baea-267">После определения параметров приложения вы можете создать общедоступные и закрытые тестовые ключи.</span><span class="sxs-lookup"><span data-stu-id="4baea-267">Once you have your application settings defined, you're ready to generate public and private test keys.</span></span>

<span data-ttu-id="4baea-268">Для создания ключей:</span><span class="sxs-lookup"><span data-stu-id="4baea-268">To generate keys:</span></span>

1. <span data-ttu-id="4baea-269">В меню Пуск Windows выполните командную строку OpenSSL.</span><span class="sxs-lookup"><span data-stu-id="4baea-269">From the Windows Start menu, run the OpenSSL Command Prompt.</span></span>

1. <span data-ttu-id="4baea-270">Перейдите к папке, в которой вы хотите сохранить тестовые ключи.</span><span class="sxs-lookup"><span data-stu-id="4baea-270">Change to the folder where you want to save the test keys.</span></span> <span data-ttu-id="4baea-271">Файлы, создаваемые при выполнении действий, описанных в этой задаче, хранятся в одной папке.</span><span class="sxs-lookup"><span data-stu-id="4baea-271">The files you create by completing the steps in this task are stored in the same folder.</span></span>

1. <span data-ttu-id="4baea-272">Создайте новый тестовый ключ.</span><span class="sxs-lookup"><span data-stu-id="4baea-272">Generate the new test key.</span></span>

   ```dos
   openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365
   ```

2. <span data-ttu-id="4baea-273">Создайте закрытый ключ.</span><span class="sxs-lookup"><span data-stu-id="4baea-273">Generate the private key.</span></span>

   ```dos
   openssl rsa -in key.pem -out privkeynopass.pem
   ```

1. <span data-ttu-id="4baea-274">Создайте открытый ключ.</span><span class="sxs-lookup"><span data-stu-id="4baea-274">Generate the public key.</span></span>

   ```dos
   openssl rsa -in key.pem -pubout > pubkeyonly.pem
   ```

1. <span data-ttu-id="4baea-275">В текстовом редакторе откройте **пубкэйонли. pem**.</span><span class="sxs-lookup"><span data-stu-id="4baea-275">In a text editor, open **pubkeyonly.pem**.</span></span> <span data-ttu-id="4baea-276">Скопируйте весь контент из файла **пубкэйонли. pem** , за исключением первой и последней строки, в раздел **публикпем** **appsettings.js** файла.</span><span class="sxs-lookup"><span data-stu-id="4baea-276">Copy all of the content in the **pubkeyonly.pem** file, except the first and last lines, into the **PublicPem** section of the **appsettings.json** file.</span></span>

1. <span data-ttu-id="4baea-277">В текстовом редакторе откройте **привкэйнопасс. pem**.</span><span class="sxs-lookup"><span data-stu-id="4baea-277">In a text editor, open **privkeynopass.pem**.</span></span> <span data-ttu-id="4baea-278">Скопируйте весь контент из файла **привкэйнопасс. pem** , за исключением первой и последней строки, в раздел **приватепем** **appsettings.js** файла.</span><span class="sxs-lookup"><span data-stu-id="4baea-278">Copy all of the content in the **privkeynopass.pem** file, except the first and last lines, into the **PrivatePem** section of the **appsettings.json** file.</span></span>

1. <span data-ttu-id="4baea-279">Удалите все пробелы и символы новой строки в разделах **публикпем** и **приватепем** .</span><span class="sxs-lookup"><span data-stu-id="4baea-279">Remove all blank spaces and newlines in both the **PublicPem** and **PrivatePem** sections.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="4baea-280">При копировании этого контента не удаляйте какие бы то ни было данные PEM.</span><span class="sxs-lookup"><span data-stu-id="4baea-280">When you copy this content, do not delete any of the PEM data.</span></span>

1. <span data-ttu-id="4baea-281">Откройте файл **Startup.CS** и перейдите к следующим строкам:</span><span class="sxs-lookup"><span data-stu-id="4baea-281">Open the **Startup.cs** file, and locate the following lines:</span></span>

   ```c#
        #if USE_TEST_KEYS
        #error !!!!!!!!!!!!!!!!!!!!!! Use of test keys is only supported for testing,
        DO NOT USE  FOR PRODUCTION !!!!!!!!!!!!!!!!!!!!!!!!!!!!!
        services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
        #endif
   ```

1. <span data-ttu-id="4baea-282">Замените эти строки следующим текстом:</span><span class="sxs-lookup"><span data-stu-id="4baea-282">Replace these lines with the following text:</span></span>

   ```csharp
   services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
   ```

   <span data-ttu-id="4baea-283">Конечный результат должен выглядеть примерно так, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="4baea-283">The end results should look similar to the following picture.</span></span>

   :::image type="content" source="../media/dke-startupcs-usetestkeys.png" alt-text="файл startup.cs для общедоступной предварительной версии":::

<span data-ttu-id="4baea-285">Теперь вы готовы к [созданию проекта дке](#build-the-project).</span><span class="sxs-lookup"><span data-stu-id="4baea-285">Now you're ready to [build your DKE project](#build-the-project).</span></span>

### <a name="build-the-project"></a><span data-ttu-id="4baea-286">Построение проекта</span><span class="sxs-lookup"><span data-stu-id="4baea-286">Build the project</span></span>

<span data-ttu-id="4baea-287">Используйте следующие инструкции для локального создания проекта ДКЕ:</span><span class="sxs-lookup"><span data-stu-id="4baea-287">Use the following instructions to build the DKE project locally:</span></span>

1. <span data-ttu-id="4baea-288">В Visual Studio Code в репозитории службы дке выберите пункт **Просмотреть** \> **палитру команд** и введите в командной строки команду **Build** .</span><span class="sxs-lookup"><span data-stu-id="4baea-288">In Visual Studio Code, in the DKE service repository, select **View** \> **Command Palette** and then type **build** at the prompt.</span></span>

1. <span data-ttu-id="4baea-289">В списке выберите **задачи: выполнение задачи сборки**.</span><span class="sxs-lookup"><span data-stu-id="4baea-289">From the list, choose **Tasks: Run build task**.</span></span>

   <span data-ttu-id="4baea-290">Если задач сборки нет, выберите **настроить задачу построения** и создайте ее для .NET Core следующим образом.</span><span class="sxs-lookup"><span data-stu-id="4baea-290">If there are no build tasks found, select **Configure Build Task** and create one for .NET core as follows.</span></span>

   :::image type="content" source="../media/dke-configurebuildtask.png" alt-text="Настройка отсутствующих задач сборки для .NET":::

   1. <span data-ttu-id="4baea-292">Выберите **создать tasks.jsна основе шаблона**.</span><span class="sxs-lookup"><span data-stu-id="4baea-292">Choose **Create tasks.json from template**.</span></span>

   :::image type="content" source="../media/dke-createtasksjsonfromtemplate.png" alt-text="Создание tasks.jsдля файла из шаблона для ДКЕ":::

   2. <span data-ttu-id="4baea-294">В списке типов шаблонов выберите **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="4baea-294">From the list of template types, select **.NET Core**.</span></span>

   :::image type="content" source="../media/dke-tasksjsontemplate.png" alt-text="Создание tasks.jsдля файла из шаблона для ДКЕ":::

   3. <span data-ttu-id="4baea-296">В разделе Build (построение) выберите путь к файлу **кустомеркэйсторе. csproj** .</span><span class="sxs-lookup"><span data-stu-id="4baea-296">In the build section, locate the path to the **customerkeystore.csproj** file.</span></span> <span data-ttu-id="4baea-297">Если это не так, добавьте следующую строку:</span><span class="sxs-lookup"><span data-stu-id="4baea-297">If it's not there, add the following line:</span></span>

      ```json
      "${workspaceFolder}/src/customer-key-store/customerkeystore.csproj",
      ```

  4. <span data-ttu-id="4baea-298">Снова запустите построение.</span><span class="sxs-lookup"><span data-stu-id="4baea-298">Run the build again.</span></span>

1. <span data-ttu-id="4baea-299">Убедитесь, что в окне вывода нет красных ошибок.</span><span class="sxs-lookup"><span data-stu-id="4baea-299">Verify that there are no red errors in the output window.</span></span>

   <span data-ttu-id="4baea-300">При наличии красных ошибок проверьте вывод консоли.</span><span class="sxs-lookup"><span data-stu-id="4baea-300">If there are red errors, check the console output.</span></span> <span data-ttu-id="4baea-301">Убедитесь, что все предыдущие действия выполнены правильно, и в них имеются правильные версии сборки.</span><span class="sxs-lookup"><span data-stu-id="4baea-301">Ensure that you completed all the previous steps correctly and the correct build versions are present.</span></span>

1. <span data-ttu-id="4baea-302">**Запуск** \> **Начните отладку** , чтобы выполнить отладку процесса.</span><span class="sxs-lookup"><span data-stu-id="4baea-302">**Run** \> **Start Debugging** to debug the process.</span></span> <span data-ttu-id="4baea-303">Если вам будет предложено выбрать среду, выберите пункт **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="4baea-303">If you're prompted to select an environment, select **.NET core**.</span></span>

<span data-ttu-id="4baea-304">Основной отладчик .NET обычно запускается в **https://localhost:5001** .</span><span class="sxs-lookup"><span data-stu-id="4baea-304">The .NET core debugger typically launches to **https://localhost:5001**.</span></span> <span data-ttu-id="4baea-305">Чтобы просмотреть тестовый ключ, перейдите к разделу **https://localhost:5001** и добавьте косую черту (/) и имя ключа.</span><span class="sxs-lookup"><span data-stu-id="4baea-305">To view your test key, go to **https://localhost:5001**, and append a forward slash (/) and the name of your key.</span></span>

<span data-ttu-id="4baea-306">Например:**https://localhost:5001/TestKey1**</span><span class="sxs-lookup"><span data-stu-id="4baea-306">For example: **https://localhost:5001/TestKey1**</span></span>

<span data-ttu-id="4baea-307">Ключ должен отображаться в формате JSON.</span><span class="sxs-lookup"><span data-stu-id="4baea-307">The key should display in JSON format.</span></span>

<span data-ttu-id="4baea-308">Теперь настройка завершена.</span><span class="sxs-lookup"><span data-stu-id="4baea-308">Your setup is now complete.</span></span> <span data-ttu-id="4baea-309">Перед публикацией хранилища ключей в appsettings.jsдля параметра Жвтаудиенце убедитесь, что значение Hostname точно соответствует имени узла службы приложений.</span><span class="sxs-lookup"><span data-stu-id="4baea-309">Before you publish the keystore, in appsettings.json, for the JwtAudience setting, ensure the value for hostname exactly matches your App Service host name.</span></span> <span data-ttu-id="4baea-310">Возможно, вы изменили его на localhost, чтобы устранить неполадки с построением.</span><span class="sxs-lookup"><span data-stu-id="4baea-310">You may have changed it to localhost to troubleshoot the build.</span></span>

### <a name="publish-the-key-store"></a><span data-ttu-id="4baea-311">Публикация хранилища ключей</span><span class="sxs-lookup"><span data-stu-id="4baea-311">Publish the key store</span></span>

<span data-ttu-id="4baea-312">Ниже описано, как создать экземпляр службы приложений Azure для размещения вашего развертывания ДКЕ, а также как опубликовать созданные ключи в Azure.</span><span class="sxs-lookup"><span data-stu-id="4baea-312">The following steps describe how to create an Azure App Service instance to host your DKE deployment, and how to publish your generated keys to Azure.</span></span>

<span data-ttu-id="4baea-313">Чтобы создать экземпляр веб-приложения Azure для размещения развертывания ДКЕ, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="4baea-313">To create an Azure Web App instance to host your DKE deployment:</span></span>

1. <span data-ttu-id="4baea-314">В браузере Войдите на [портал Microsoft Azure](https://ms.portal.azure.com)и перейдите к разделу Добавление **служб приложений**  >  **Add**.</span><span class="sxs-lookup"><span data-stu-id="4baea-314">In your browser, sign in to the [Microsoft Azure portal](https://ms.portal.azure.com), and go to **App Services** > **Add**.</span></span>

1. <span data-ttu-id="4baea-315">Выберите свою подписку и группу ресурсов и определите сведения об экземпляре.</span><span class="sxs-lookup"><span data-stu-id="4baea-315">Select your subscription and resource group and define your instance details.</span></span>

    - <span data-ttu-id="4baea-316">Введите имя узла компьютера, на котором необходимо установить службу ДКЕ.</span><span class="sxs-lookup"><span data-stu-id="4baea-316">Enter the hostname of the computer where you want to install the DKE service.</span></span> <span data-ttu-id="4baea-317">Убедитесь, что это то же имя, которое задано для параметра Жвтаудиенце в [**appsettings.js**](#tenant-and-key-settings) файла.</span><span class="sxs-lookup"><span data-stu-id="4baea-317">Make sure it's the same name as the one defined for the JwtAudience setting in the [**appsettings.json**](#tenant-and-key-settings) file.</span></span> <span data-ttu-id="4baea-318">Значение, которое вы задаете для имени, также равно Вебаппинстанценаме.</span><span class="sxs-lookup"><span data-stu-id="4baea-318">The value you provide for the name is also the WebAppInstanceName.</span></span>

    - <span data-ttu-id="4baea-319">Для **публикации**выберите **код**и для **стека времени выполнения**выберите **.NET Core 3,1**.</span><span class="sxs-lookup"><span data-stu-id="4baea-319">For **Publish**, select **code**, and for **Runtime stack**, select **.NET Core 3.1**.</span></span>

    <span data-ttu-id="4baea-320">Пример:</span><span class="sxs-lookup"><span data-stu-id="4baea-320">For example:</span></span>

    :::image type="content" source="../media/dke-azure-add-app-service.png" alt-text="Добавление службы приложений":::

1. <span data-ttu-id="4baea-322">В нижней части страницы выберите пункт Просмотр и **Создание**, а затем нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="4baea-322">At the bottom of the page, select **Review + create**, and then select **Add**.</span></span>

1. <span data-ttu-id="4baea-323">Выполните одно из следующих действий, чтобы опубликовать созданные ключи в Azure:</span><span class="sxs-lookup"><span data-stu-id="4baea-323">Do one of the following to publish your generated keys to Azure:</span></span>

    - [<span data-ttu-id="4baea-324">Публикация с помощью Зипдеплойуи</span><span class="sxs-lookup"><span data-stu-id="4baea-324">Publish via ZipDeployUI</span></span>](#publish-via-zipdeployui)
    - [<span data-ttu-id="4baea-325">Опубликовать через FTP</span><span class="sxs-lookup"><span data-stu-id="4baea-325">Publish via FTP</span></span>](#publish-via-ftp)
    - [<span data-ttu-id="4baea-326">Публикация с помощью Visual Studio 2019 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="4baea-326">Publish via Visual Studio 2019 or later</span></span>](https://docs.microsoft.com/aspnet/core/tutorials/)
    - [<span data-ttu-id="4baea-327">Публикация в локальной системе</span><span class="sxs-lookup"><span data-stu-id="4baea-327">Publish to an on-premises system</span></span>](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli)

    > [!NOTE]
    > <span data-ttu-id="4baea-328">Вы можете предпочесть другие методы для развертывания ключей.</span><span class="sxs-lookup"><span data-stu-id="4baea-328">You may prefer other methods to deploy your keys.</span></span> <span data-ttu-id="4baea-329">Выберите метод, который лучше всего подходит для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="4baea-329">Select the method that works best for your organization.</span></span>

    > [!TIP]
    > <span data-ttu-id="4baea-330">[Публикация с помощью Visual Studio](https://docs.microsoft.com/aspnet/core/tutorials/) и [локальной системы](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli) описана в [документации по ASP .NET](https://docs.microsoft.com/aspnet/core/).</span><span class="sxs-lookup"><span data-stu-id="4baea-330">[Publishing via Visual Studio](https://docs.microsoft.com/aspnet/core/tutorials/) and to an [on-premises system](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli) is described in the [ASP .NET documentation](https://docs.microsoft.com/aspnet/core/).</span></span> <span data-ttu-id="4baea-331">Если вы используете один из этих методов, откройте инструкции на отдельной вкладке, чтобы вы могли вернуться к ней, когда все будет готово.</span><span class="sxs-lookup"><span data-stu-id="4baea-331">If you use one of these methods, open the instructions in a separate tab so that you can return here easily when you're done.</span></span>

#### <a name="publish-via-zipdeployui"></a><span data-ttu-id="4baea-332">Публикация с помощью Зипдеплойуи</span><span class="sxs-lookup"><span data-stu-id="4baea-332">Publish via ZipDeployUI</span></span>

1. <span data-ttu-id="4baea-333">Перейдите на сайт `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.</span><span class="sxs-lookup"><span data-stu-id="4baea-333">Go to `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.</span></span>

    <span data-ttu-id="4baea-334">Пример: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="4baea-334">For example: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span></span>

1. <span data-ttu-id="4baea-335">В базе кода для хранилища ключей перейдите в папку **Кустомер-Кэй-сторе\срк\кустомер-Кэй-Сторе** и убедитесь, что эта папка содержит файл **кустомеркэйсторе. csproj** .</span><span class="sxs-lookup"><span data-stu-id="4baea-335">In the codebase for the key store, go to the **customer-key-store\src\customer-key-store** folder, and verify that this folder contains the **customerkeystore.csproj** file.</span></span>

1. <span data-ttu-id="4baea-336">Выполнить: **Публикация DotNet**</span><span class="sxs-lookup"><span data-stu-id="4baea-336">Run: **dotnet publish**</span></span>

     <span data-ttu-id="4baea-337">В окне вывода отображается каталог, в котором была развернута публикация.</span><span class="sxs-lookup"><span data-stu-id="4baea-337">The output window displays the directory where the publish was deployed.</span></span>

    <span data-ttu-id="4baea-338">Пример: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="4baea-338">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

1. <span data-ttu-id="4baea-339">Отправьте все файлы в каталоге публикации в ZIP-файл.</span><span class="sxs-lookup"><span data-stu-id="4baea-339">Send all files in the publish directory to a .zip file.</span></span> <span data-ttu-id="4baea-340">При создании ZIP-файла убедитесь, что все файлы в каталоге находятся на корневом уровне ZIP-файла.</span><span class="sxs-lookup"><span data-stu-id="4baea-340">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

1. <span data-ttu-id="4baea-341">Перетащите созданный ZIP-файл на сайт Зипдеплойуи, который вы открыли ранее.</span><span class="sxs-lookup"><span data-stu-id="4baea-341">Drag and drop the .zip file you create to the ZipDeployUI site you opened above.</span></span> <span data-ttu-id="4baea-342">Пример: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="4baea-342">For example: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span></span>

<span data-ttu-id="4baea-343">ДКЕ развернута, и вы можете перейти к созданным тестовым ключам.</span><span class="sxs-lookup"><span data-stu-id="4baea-343">DKE is deployed and you can browse to the test keys you've created.</span></span> <span data-ttu-id="4baea-344">Продолжите [проверку развертывания](#validate-your-deployment) ниже.</span><span class="sxs-lookup"><span data-stu-id="4baea-344">Continue to [Validate your deployment](#validate-your-deployment) below.</span></span>

#### <a name="publish-via-ftp"></a><span data-ttu-id="4baea-345">Опубликовать через FTP</span><span class="sxs-lookup"><span data-stu-id="4baea-345">Publish via FTP</span></span>

1. <span data-ttu-id="4baea-346">Подключитесь к службе приложений, созданной [ранее](#publish-the-key-store).</span><span class="sxs-lookup"><span data-stu-id="4baea-346">Connect to the App Service you created [above](#publish-the-key-store).</span></span>

    <span data-ttu-id="4baea-347">В браузере перейдите по адресу: **Azure portal**  >  центр развертывания**службы приложений**портала Azure  >  **Deployment Center**  >  **развертывание**  >  **FTP**  >  **панели мониторинга**FTP.</span><span class="sxs-lookup"><span data-stu-id="4baea-347">In your browser, go to: **Azure portal** > **App Service** > **Deployment Center** > **Manual Deployment** > **FTP** > **Dashboard**.</span></span>

1. <span data-ttu-id="4baea-348">Скопируйте строки подключения, отображаемые в локальный файл.</span><span class="sxs-lookup"><span data-stu-id="4baea-348">Copy the connection strings displayed to a local file.</span></span> <span data-ttu-id="4baea-349">Эти строки будут использоваться для подключения к службе веб-приложений и отправки файлов через FTP.</span><span class="sxs-lookup"><span data-stu-id="4baea-349">You'll use these strings to connect to the Web App Service and upload files via FTP.</span></span>

    <span data-ttu-id="4baea-350">Пример:</span><span class="sxs-lookup"><span data-stu-id="4baea-350">For example:</span></span>

    :::image type="content" source="../media/dke-ftp-dashboard.png" alt-text="Копирование строк подключения из панели мониторинга FTP":::

1. <span data-ttu-id="4baea-352">В базе кода для хранилища ключей перейдите в **Каталог Кустомер-Кэй-сторе\срк\кустомер-Кэй-Сторе**.</span><span class="sxs-lookup"><span data-stu-id="4baea-352">In the codebase for the key storage, go to the **customer-key-store\src\customer-key-store directory**.</span></span>

1. <span data-ttu-id="4baea-353">Убедитесь, что этот каталог содержит файл **кустомеркэйсторе. csproj** .</span><span class="sxs-lookup"><span data-stu-id="4baea-353">Verify that this directory contains the **customerkeystore.csproj** file.</span></span>

1. <span data-ttu-id="4baea-354">Выполнить: **Публикация DotNet**</span><span class="sxs-lookup"><span data-stu-id="4baea-354">Run: **dotnet publish**</span></span>

    <span data-ttu-id="4baea-355">Выходные данные содержат каталог, в котором развернута публикация.</span><span class="sxs-lookup"><span data-stu-id="4baea-355">The output contains the directory where the publish was deployed.</span></span>

    <span data-ttu-id="4baea-356">Пример: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="4baea-356">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

1. <span data-ttu-id="4baea-357">Отправьте все файлы в каталоге публикации в ZIP-файл.</span><span class="sxs-lookup"><span data-stu-id="4baea-357">Send all files in the publish directory to a zip file.</span></span> <span data-ttu-id="4baea-358">При создании ZIP-файла убедитесь, что все файлы в каталоге находятся на корневом уровне ZIP-файла.</span><span class="sxs-lookup"><span data-stu-id="4baea-358">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

1. <span data-ttu-id="4baea-359">В клиенте FTP используйте сведения о подключении, скопированные для подключения к службе приложений.</span><span class="sxs-lookup"><span data-stu-id="4baea-359">From your FTP client, use the connection information you copied to connect to your App Service.</span></span> <span data-ttu-id="4baea-360">Отправьте ZIP-файл, созданный на предыдущем шаге, в корневой каталог веб-приложения.</span><span class="sxs-lookup"><span data-stu-id="4baea-360">Upload the .zip file you created in the previous step to the root directory of your Web App.</span></span>

<span data-ttu-id="4baea-361">ДКЕ развернута, и вы можете перейти к созданным тестовым ключам.</span><span class="sxs-lookup"><span data-stu-id="4baea-361">DKE is deployed and you can browse to the test keys you'd created.</span></span> <span data-ttu-id="4baea-362">Затем [Подтвердите развертывание](#validate-your-deployment).</span><span class="sxs-lookup"><span data-stu-id="4baea-362">Next, [Validate your deployment](#validate-your-deployment).</span></span>

### <a name="validate-your-deployment"></a><span data-ttu-id="4baea-363">Проверка развертывания</span><span class="sxs-lookup"><span data-stu-id="4baea-363">Validate your deployment</span></span>

<span data-ttu-id="4baea-364">После развертывания ДКЕ с помощью одного из методов, описанных выше, проверяйте развертывание и параметры хранилища ключей.</span><span class="sxs-lookup"><span data-stu-id="4baea-364">After deploying DKE using one of the methods described above, validate the deployment and the key store settings.</span></span>

<span data-ttu-id="4baea-365">Выполняем</span><span class="sxs-lookup"><span data-stu-id="4baea-365">Run:</span></span>

<span data-ttu-id="4baea-366">src\customer-key-store\scripts\key_store_tester.ps1 микэйстореурл/микэй</span><span class="sxs-lookup"><span data-stu-id="4baea-366">src\customer-key-store\scripts\key_store_tester.ps1 mykeystoreurl/mykey</span></span>

<span data-ttu-id="4baea-367">Пример:</span><span class="sxs-lookup"><span data-stu-id="4baea-367">For example:</span></span>

<span data-ttu-id="4baea-368">key_store_tester.ps1https://mycustomerkeystore.com/mykey</span><span class="sxs-lookup"><span data-stu-id="4baea-368">key_store_tester.ps1 https://mycustomerkeystore.com/mykey</span></span>

<span data-ttu-id="4baea-369">Убедитесь, что в выходных данных не отображаются ошибки.</span><span class="sxs-lookup"><span data-stu-id="4baea-369">Ensure that no errors appear in the output.</span></span> <span data-ttu-id="4baea-370">Когда вы будете готовы, [Зарегистрируйте свое хранилище ключей](#register-your-key-store).</span><span class="sxs-lookup"><span data-stu-id="4baea-370">When you're ready, [register your key store](#register-your-key-store).</span></span>

## <a name="register-your-key-store"></a><span data-ttu-id="4baea-371">Регистрация своего хранилища ключей</span><span class="sxs-lookup"><span data-stu-id="4baea-371">Register your key store</span></span>

<span data-ttu-id="4baea-372">Следующие действия позволяют зарегистрировать свое хранилище ключей.</span><span class="sxs-lookup"><span data-stu-id="4baea-372">The following steps enable you to register your key store.</span></span> <span data-ttu-id="4baea-373">Регистрация основного хранилища — это последний шаг в развертывании ДКЕ, прежде чем вы сможете создавать метки.</span><span class="sxs-lookup"><span data-stu-id="4baea-373">Registering your key store is the last step in deploying DKE before you can start creating labels.</span></span>

<span data-ttu-id="4baea-374">Чтобы зарегистрировать свое хранилище ключей:</span><span class="sxs-lookup"><span data-stu-id="4baea-374">To register your key store:</span></span>

1. <span data-ttu-id="4baea-375">В браузере откройте [портал Microsoft Azure](https://ms.portal.azure.com/)и перейдите ко **всем** \> **Identity** \> **регистрациям приложений**удостоверений для служб.</span><span class="sxs-lookup"><span data-stu-id="4baea-375">In your browser, open the [Microsoft Azure portal](https://ms.portal.azure.com/), and go to **All Services** \> **Identity** \> **App Registrations**.</span></span>

2. <span data-ttu-id="4baea-376">Нажмите кнопку **создать регистрацию**и введите понятное имя.</span><span class="sxs-lookup"><span data-stu-id="4baea-376">Select **New registration**, and enter a meaningful name.</span></span>

3. <span data-ttu-id="4baea-377">Выберите тип учетной записи в отображаемых параметрах.</span><span class="sxs-lookup"><span data-stu-id="4baea-377">Select an account type from the options displayed.</span></span>

    <span data-ttu-id="4baea-378">Если вы используете Microsoft Azure с нестандартным доменом, например **onmicrosoft.com**, выберите **учетные записи только в данном организационном каталоге (только Microsoft — один клиент).**</span><span class="sxs-lookup"><span data-stu-id="4baea-378">If you're using Microsoft Azure with a non-custom domain, such as **onmicrosoft.com**, select **Accounts in this organizational directory only (Microsoft only - Single tenant).**</span></span>

    <span data-ttu-id="4baea-379">Пример:</span><span class="sxs-lookup"><span data-stu-id="4baea-379">For example:</span></span>

    :::image type="content" source="../media/dke-app-registration.png" alt-text="Регистрация нового приложения":::

4. <span data-ttu-id="4baea-381">В нижней части страницы выберите пункт **Регистрация** , чтобы создать новую регистрацию приложения.</span><span class="sxs-lookup"><span data-stu-id="4baea-381">At the bottom of the page, select **Register** to create the new App Registration.</span></span>

5. <span data-ttu-id="4baea-382">В разделе Управление новой регистрацией приложения в разделе **Управление**выберите **Проверка подлинности**.</span><span class="sxs-lookup"><span data-stu-id="4baea-382">In your new App Registration, in the left pane, under **Manage**, select **Authentication**.</span></span>

6. <span data-ttu-id="4baea-383">Выберите **элемент добавить платформу**.</span><span class="sxs-lookup"><span data-stu-id="4baea-383">Select **Add a platform**.</span></span>
 
7. <span data-ttu-id="4baea-384">В меню **Настройка платформ** выберите пункт **веб**.</span><span class="sxs-lookup"><span data-stu-id="4baea-384">On the **Configure platforms** popup select **Web**.</span></span>
 
8. <span data-ttu-id="4baea-385">В разделе **URI перенаправления** введите универсальный код ресурса (URI) службы шифрования двойных ключей.</span><span class="sxs-lookup"><span data-stu-id="4baea-385">Under **Redirect URIs** enter the URI of your double key encryption service.</span></span> <span data-ttu-id="4baea-386">Введите URL-адрес службы приложений, включая имя узла и домен.</span><span class="sxs-lookup"><span data-stu-id="4baea-386">Enter the App Service URL, including both the hostname and domain.</span></span>

    <span data-ttu-id="4baea-387">Пример: https://mycustomerkeystoretest.com</span><span class="sxs-lookup"><span data-stu-id="4baea-387">For example: https://mycustomerkeystoretest.com</span></span>

    - <span data-ttu-id="4baea-388">Введенный URL-адрес должен быть соответствующим имени узла, на котором развернуто ваше хранилище ключей.</span><span class="sxs-lookup"><span data-stu-id="4baea-388">The URL you enter must match the hostname where your key store is deployed.</span></span>
    - <span data-ttu-id="4baea-389">Если вы тестируете локально с помощью Visual Studio, используйте **https://localhost:5001** .</span><span class="sxs-lookup"><span data-stu-id="4baea-389">If you're testing locally with Visual Studio, use **https://localhost:5001**.</span></span>
    - <span data-ttu-id="4baea-390">Во всех случаях схема должна иметь значение **HTTPS**.</span><span class="sxs-lookup"><span data-stu-id="4baea-390">In all cases, the scheme must be **https**.</span></span>

    <span data-ttu-id="4baea-391">Убедитесь, что имя узла совпадает с именем узла службы приложений.</span><span class="sxs-lookup"><span data-stu-id="4baea-391">Ensure the hostname exactly matches your App Service host name.</span></span> <span data-ttu-id="4baea-392">Возможно, вы изменили его на localhost, чтобы устранить неполадки с построением.</span><span class="sxs-lookup"><span data-stu-id="4baea-392">You may have changed it to localhost to troubleshoot the build.</span></span> <span data-ttu-id="4baea-393">В appsettings.json это имя узла, которое определено в качестве значения параметра Жвтаудиенце.</span><span class="sxs-lookup"><span data-stu-id="4baea-393">In appsettings.json, this is the hostname you identified as the value for the JwtAudience setting.</span></span>

6. <span data-ttu-id="4baea-394">В разделе **неявное предоставление разрешений**установите флажок **маркеры ID** .</span><span class="sxs-lookup"><span data-stu-id="4baea-394">Under **Implicit grant**, select the **ID tokens** checkbox.</span></span>

1. <span data-ttu-id="4baea-395">Нажмите кнопку **Сохранить**, чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="4baea-395">Select **Save** to save your changes.</span></span>

7. <span data-ttu-id="4baea-396">В левой области выберите **Показать API**, а затем рядом с URI идентификатора приложения выберите **Set (установить**).</span><span class="sxs-lookup"><span data-stu-id="4baea-396">On the left pane, select **Expose an API**, then next to Application ID URI, select **Set**.</span></span>

9. <span data-ttu-id="4baea-397">По-прежнему откройте страницу **API** , в области **области, определяемые этой** областью API выберите **Добавить область**.</span><span class="sxs-lookup"><span data-stu-id="4baea-397">Still on the **Expose an API** page, in the **Scopes defined by this API** area, select **Add a scope**.</span></span> <span data-ttu-id="4baea-398">В новой области:</span><span class="sxs-lookup"><span data-stu-id="4baea-398">In the new scope:</span></span>

    1. <span data-ttu-id="4baea-399">Определите имя области как **user_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="4baea-399">Define the scope name as **user_impersonation**.</span></span>

    2. <span data-ttu-id="4baea-400">Выберите администраторов и пользователей, которым разрешено согласие.</span><span class="sxs-lookup"><span data-stu-id="4baea-400">Select the administrators and users who can consent.</span></span>

    3. <span data-ttu-id="4baea-401">Определите все остальные необходимые значения.</span><span class="sxs-lookup"><span data-stu-id="4baea-401">Define any remaining values required.</span></span>

    4. <span data-ttu-id="4baea-402">Выберите **Добавить область.**</span><span class="sxs-lookup"><span data-stu-id="4baea-402">Select **Add scope.**</span></span>

    <span data-ttu-id="4baea-403">В верхней части нажмите кнопку **сохранить** , чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="4baea-403">Select **Save** at the top to save your changes.</span></span>

10. <span data-ttu-id="4baea-404">По-прежнему на странице " **предоставление доступа к API** " в области **Авторизованные клиентские приложения** выберите **добавить клиентское приложение**.</span><span class="sxs-lookup"><span data-stu-id="4baea-404">Still on the **Expose an API** page, in the **Authorized client applications** area, select **Add a client application**.</span></span>

    <span data-ttu-id="4baea-405">В новом клиентском приложении:</span><span class="sxs-lookup"><span data-stu-id="4baea-405">In the new client application:</span></span>

    1. <span data-ttu-id="4baea-406">Определите идентификатор клиента как **d3590ed6-52b3-4102-aeff-aad2292ab01c**.</span><span class="sxs-lookup"><span data-stu-id="4baea-406">Define the Client ID as **d3590ed6-52b3-4102-aeff-aad2292ab01c**.</span></span> <span data-ttu-id="4baea-407">Это значение является ИДЕНТИФИКАТОРом клиента Microsoft Office и позволяет Office получить маркер доступа для вашего хранилища ключей.</span><span class="sxs-lookup"><span data-stu-id="4baea-407">This value is the Microsoft Office client ID, and enables Office to obtain an access token for your key store.</span></span>

    2. <span data-ttu-id="4baea-408">В разделе **Разрешенные области**выберите область **user_impersonation** .</span><span class="sxs-lookup"><span data-stu-id="4baea-408">Under **Authorized scopes**, select the **user_impersonation** scope.</span></span>

    3. <span data-ttu-id="4baea-409">Нажмите кнопку **Добавить приложение**.</span><span class="sxs-lookup"><span data-stu-id="4baea-409">Select **Add application**.</span></span>

    4. <span data-ttu-id="4baea-410">В верхней части нажмите кнопку **сохранить** , чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="4baea-410">Select **Save** at the top to save your changes.</span></span>

<span data-ttu-id="4baea-411">Теперь ваше хранилище ключей ДКЕ зарегистрировано.</span><span class="sxs-lookup"><span data-stu-id="4baea-411">Your DKE key store is now registered.</span></span> <span data-ttu-id="4baea-412">Продолжите [Создание меток с помощью дке](#create-labels-using-dke).</span><span class="sxs-lookup"><span data-stu-id="4baea-412">Continue  by [creating labels using DKE](#create-labels-using-dke).</span></span>

## <a name="create-labels-using-dke"></a><span data-ttu-id="4baea-413">Создание меток с помощью ДКЕ</span><span class="sxs-lookup"><span data-stu-id="4baea-413">Create labels using DKE</span></span>

<span data-ttu-id="4baea-414">После регистрации своего хранилища ключей настройте метки конфиденциальности в центре соответствия требованиям Microsoft 365 и примените к ним шифрование с двойным ключом.</span><span class="sxs-lookup"><span data-stu-id="4baea-414">Once you've registered your key store, set up sensitivity labels in the Microsoft 365 compliance center and apply double key encryption to those labels.</span></span>

<span data-ttu-id="4baea-415">В пользовательском интерфейсе создания меток выберите параметр **использовать шифрование двойных ключей** и введите URL-адрес конечной точки для ключа.</span><span class="sxs-lookup"><span data-stu-id="4baea-415">In the label creation UI, select the **Use Double Key Encryption** option and enter the endpoint URL for your key.</span></span>

<span data-ttu-id="4baea-416">Пример:</span><span class="sxs-lookup"><span data-stu-id="4baea-416">For example:</span></span>

:::image type="content" source="../media/dke-use-dke.png" alt-text="Выберите использовать шифрование с двойным ключом в центре соответствия требованиям Microsoft 365":::

<span data-ttu-id="4baea-418">Все добавляемые метки ДКЕ будут отображаться для пользователей в последних версиях приложений Microsoft 365 для предприятий.</span><span class="sxs-lookup"><span data-stu-id="4baea-418">Any DKE labels you add will start appearing for users in the latest versions of Microsoft 365 Apps for enterprise.</span></span>

> [!NOTE]
> <span data-ttu-id="4baea-419">Для обновления клиентов с новыми метками может потребоваться до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="4baea-419">It may take up to 24 hours for the clients to refresh with the new labels.</span></span>

### <a name="enable-dke-in-your-client"></a><span data-ttu-id="4baea-420">Включение ДКЕ в клиенте</span><span class="sxs-lookup"><span data-stu-id="4baea-420">Enable DKE in your client</span></span>

<span data-ttu-id="4baea-421">Если метки ДКЕ не отображаются на ленте чувствительность в Microsoft Office, возможно, у клиента ДКЕ не включена.</span><span class="sxs-lookup"><span data-stu-id="4baea-421">If your DKE labels don't appear under the Sensitivity ribbon in Microsoft Office, your client may not have DKE enabled.</span></span>

<span data-ttu-id="4baea-422">Включите ДКЕ для клиента, добавив следующие разделы реестра:</span><span class="sxs-lookup"><span data-stu-id="4baea-422">Enable DKE for your client by adding the following registry keys:</span></span>

```ini
    [HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001

    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001
```
