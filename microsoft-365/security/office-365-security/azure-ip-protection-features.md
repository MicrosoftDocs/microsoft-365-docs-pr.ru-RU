---
title: Функции защиты в Azure Information Protection, развертывание для существующих клиентов
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 7ad6f58e-65d7-4c82-8e65-0b773666634d
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: В этой статье объясняются изменения, которые были внесены в функции защиты в Azure Information Protection.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 32f21c7b57f4f81ea153f7fe1fe84de1f041c592
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921268"
---
# <a name="protection-features-in-azure-information-protection-rolling-out-to-existing-tenants"></a><span data-ttu-id="d7994-103">Функции защиты в Azure Information Protection, развертывание для существующих клиентов</span><span class="sxs-lookup"><span data-stu-id="d7994-103">Protection features in Azure Information Protection rolling out to existing tenants</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d7994-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="d7994-104">**Applies to**</span></span>
- [<span data-ttu-id="d7994-105">Microsoft Defender для Office 365 (план 2)</span><span class="sxs-lookup"><span data-stu-id="d7994-105">Microsoft Defender for Office 365 plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="d7994-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d7994-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="d7994-107">Чтобы помочь на начальном этапе защиты информации, с июля 2018 г. все клиенты Azure Information Protection будут иметь функции защиты в Azure Information Protection, включенной по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d7994-107">To help with the initial step in protecting your information, starting July 2018 all Azure Information Protection eligible tenants will have the protection features in Azure Information Protection turned on by default.</span></span> <span data-ttu-id="d7994-108">Функции защиты в Azure Information Protection ранее были известны в Office 365 как Управление правами или Azure RMS.</span><span class="sxs-lookup"><span data-stu-id="d7994-108">The protection features in Azure Information Protection were formerly known in Office 365 as Rights Management or Azure RMS.</span></span> <span data-ttu-id="d7994-109">Если в вашей организации есть план служб Office E3 или более высокий план службы, вы получите возможность начать защиту информации через Azure Information Protection при запуске этих функций.</span><span class="sxs-lookup"><span data-stu-id="d7994-109">If your organization has an Office E3 service plan or a higher service plan you will now get a head start protecting information through Azure Information Protection when we roll out these features.</span></span>

## <a name="changes-beginning-july-1-2018"></a><span data-ttu-id="d7994-110">Изменения с 1 июля 2018 г.</span><span class="sxs-lookup"><span data-stu-id="d7994-110">Changes beginning July 1, 2018</span></span>

<span data-ttu-id="d7994-111">С 1 июля 2018 г. Корпорация Майкрософт будет использовать возможности защиты в Azure Information Protection для всех организаций с одним из следующих планов подписки:</span><span class="sxs-lookup"><span data-stu-id="d7994-111">Starting July 1, 2018, Microsoft will enable the protection capability in Azure Information Protection for all organizations with one of the following subscription plans:</span></span>

- <span data-ttu-id="d7994-112">Шифрование сообщений Office 365 предлагается в составе Office 365 E3 и E5, Microsoft E3 и E5, Office 365 A1, A3 и A5 и Office 365 G3 и G5.</span><span class="sxs-lookup"><span data-stu-id="d7994-112">Office 365 Message Encryption is offered as part of Office 365 E3 and E5, Microsoft E3 and E5, Office 365 A1, A3, and A5, and Office 365 G3 and G5.</span></span> <span data-ttu-id="d7994-113">Вам не нужны дополнительные лицензии для получения новых возможностей защиты с помощью Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="d7994-113">You do not need additional licenses to receive the new protection capabilities powered by Azure Information Protection.</span></span>

- <span data-ttu-id="d7994-114">Вы также можете добавить План 1 по защите информации Azure к следующим планам получения новых возможностей шифрования сообщений Office 365: Exchange Online Plan 1, Exchange Online Plan 2, Office 365 F1, Microsoft 365 Business Basic, Microsoft 365 Business Standard или Office 365 Enterprise E1.</span><span class="sxs-lookup"><span data-stu-id="d7994-114">You can also add Azure Information Protection Plan 1 to the following plans to receive the new Office 365 Message Encryption capabilities: Exchange Online Plan 1, Exchange Online Plan 2, Office 365 F1, Microsoft 365 Business Basic, Microsoft 365 Business Standard, or Office 365 Enterprise E1.</span></span>

- <span data-ttu-id="d7994-115">Каждый пользователь, пользующийся шифрованием сообщений Office 365, должен иметь лицензию, чтобы она была охвачена этой функцией.</span><span class="sxs-lookup"><span data-stu-id="d7994-115">Each user benefiting from Office 365 Message Encryption needs to be licensed to be covered by the feature.</span></span>

- <span data-ttu-id="d7994-116">Полный список см. в описании [службы Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description) для шифрования сообщений Office 365.</span><span class="sxs-lookup"><span data-stu-id="d7994-116">For the full list, see the [Exchange Online service descriptions](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description) for Office 365 Message Encryption.</span></span>

<span data-ttu-id="d7994-117">Администраторы клиента могут проверить состояние защиты на портале администратора Office 365.</span><span class="sxs-lookup"><span data-stu-id="d7994-117">Tenant administrators can check the protection status in the Office 365 administrator portal.</span></span>

![Снимок экрана, на который показано, что активируется управление правами в Office 365.](../../media/303453c8-e4a5-4875-b49f-e80c3eb7b91e.png)

## <a name="why-are-we-making-this-change"></a><span data-ttu-id="d7994-119">Почему мы внося эти изменения?</span><span class="sxs-lookup"><span data-stu-id="d7994-119">Why are we making this change?</span></span>

<span data-ttu-id="d7994-120">Шифрование сообщений Office 365 использует возможности защиты в Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="d7994-120">Office 365 Message Encryption leverages the protection capabilities in Azure Information Protection.</span></span> <span data-ttu-id="d7994-121">В основе последних улучшений шифрования сообщений Office 365 и более широких инвестиций в защиту информации в Microsoft 365 мы упрощаем для организаций возможность включить и использовать наши возможности защиты, так как исторически технологии шифрования трудно настроить.</span><span class="sxs-lookup"><span data-stu-id="d7994-121">At the heart of the recent improvements to Office 365 Message Encryption and our broader investments to information protection in Microsoft 365, we are making it easier for organizations to turn on and use our protection capabilities, as historically, encryption technologies have been difficult to set up.</span></span> <span data-ttu-id="d7994-122">Включив функции защиты в Azure Information Protection по умолчанию, можно быстро начать защищать конфиденциальные данные.</span><span class="sxs-lookup"><span data-stu-id="d7994-122">By turning on the protection features in Azure Information Protection by default, you can quickly get started to protect your sensitive data.</span></span>

## <a name="does-this-impact-me"></a><span data-ttu-id="d7994-123">Влияет ли это на меня?</span><span class="sxs-lookup"><span data-stu-id="d7994-123">Does this impact me?</span></span>

<span data-ttu-id="d7994-124">Если ваша организация приобрела лицензию Office 365, это изменение повлияет на клиента.</span><span class="sxs-lookup"><span data-stu-id="d7994-124">If your organization has purchased an eligible Office 365 license, then your tenant will be impacted by this change.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d7994-125">Если вы используете служба управления правами Active Directory (AD RMS) в локальной среде, необходимо либо немедленно отказаться от этого изменения, либо перейти в Azure Information Protection, прежде чем мы выкатим это изменение в течение следующих 30 дней.</span><span class="sxs-lookup"><span data-stu-id="d7994-125">If you're using Active Directory Rights Management Services (AD RMS) in your on-premises environment, you must either opt-out of this change immediately or migrate to Azure Information Protection before we roll out this change within the next 30 days.</span></span> <span data-ttu-id="d7994-126">Сведения о том, как отказаться от использования, см. в "Я использую AD RMS, как отказаться?"</span><span class="sxs-lookup"><span data-stu-id="d7994-126">For information on how to opt-out, see "I use AD RMS, how do I opt out?"</span></span> <span data-ttu-id="d7994-127">далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="d7994-127">later in this article.</span></span> <span data-ttu-id="d7994-128">Если вы предпочитаете мигрировать, см. в руб. Миграция из [AD RMS в Azure Information Protection.](/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms).</span><span class="sxs-lookup"><span data-stu-id="d7994-128">If you prefer to migrate, see [Migrating from AD RMS to Azure Information Protection.](/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms).</span></span>

## <a name="can-i-use-azure-information-protection-with-active-directory-rights-management-services-ad-rms"></a><span data-ttu-id="d7994-129">Можно ли использовать Azure Information Protection с служба управления правами Active Directory (AD RMS)?</span><span class="sxs-lookup"><span data-stu-id="d7994-129">Can I use Azure Information Protection with Active Directory Rights Management Services (AD RMS)?</span></span>

<span data-ttu-id="d7994-130">Нет.</span><span class="sxs-lookup"><span data-stu-id="d7994-130">No.</span></span> <span data-ttu-id="d7994-131">Это не поддерживаемый сценарий развертывания.</span><span class="sxs-lookup"><span data-stu-id="d7994-131">This is not a supported deployment scenario.</span></span> <span data-ttu-id="d7994-132">Без дополнительных действий по отказу некоторые компьютеры могут автоматически приступить к использованию службы управления правами Azure, а также подключиться к кластеру AD RMS.</span><span class="sxs-lookup"><span data-stu-id="d7994-132">Without taking the additional opt-out steps, some computers might automatically start using the Azure Rights Management service and also connect to your AD RMS cluster.</span></span> <span data-ttu-id="d7994-133">Этот сценарий не поддерживается и имеет ненадежные результаты, поэтому важно отказаться от этого изменения в течение следующих 30 дней, прежде чем мы выкатим эти новые функции.</span><span class="sxs-lookup"><span data-stu-id="d7994-133">This scenario isn't supported and has unreliable results, so it's important that you opt out of this change within the next 30 days before we roll out these new features.</span></span> <span data-ttu-id="d7994-134">Сведения о том, как отказаться от использования, см. в "Я использую AD RMS, как отказаться?"</span><span class="sxs-lookup"><span data-stu-id="d7994-134">For information on how to opt-out, see "I use AD RMS, how do I opt out?"</span></span> <span data-ttu-id="d7994-135">далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="d7994-135">later in this article.</span></span> <span data-ttu-id="d7994-136">Если вы предпочитаете мигрировать, см. в видеоролике Миграция из [AD RMS в Azure Information Protection.](/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)</span><span class="sxs-lookup"><span data-stu-id="d7994-136">If you prefer to migrate, see [Migrating from AD RMS to Azure Information Protection.](/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)</span></span>

## <a name="how-do-i-know-if-im-using-ad-rms"></a><span data-ttu-id="d7994-137">Как узнать, использую ли Я AD RMS?</span><span class="sxs-lookup"><span data-stu-id="d7994-137">How do I know if I'm using AD RMS?</span></span>

<span data-ttu-id="d7994-138">Используйте эти инструкции по подготовке среды для управления правами Azure, если у вас также есть служба управления правами Active Directory [(AD RMS),](/azure/information-protection/deploy-use/prepare-environment-adrms) чтобы проверить, развернули ли вы службу AD RMS:</span><span class="sxs-lookup"><span data-stu-id="d7994-138">Use these instructions from [Preparing the environment for Azure Rights Management when you also have Active Directory Rights Management Services (AD RMS)](/azure/information-protection/deploy-use/prepare-environment-adrms) to check if you have deployed AD RMS:</span></span>

1. <span data-ttu-id="d7994-139">Хотя это необязательно, большинство развертывания AD RMS публикуют точку подключения службы (SCP) к Active Directory, чтобы доменные компьютеры могли обнаружить кластер AD RMS.</span><span class="sxs-lookup"><span data-stu-id="d7994-139">Although optional, most AD RMS deployments publish the service connection point (SCP) to Active Directory so that domain computers can discover the AD RMS cluster.</span></span>

   <span data-ttu-id="d7994-140">Чтобы узнать, опубликован ли SCP в Active Directory, используйте редактирование ADSI: CN=Configuration [имя сервера], CN=Services, CN=RightsManagementServices, CN=SCP</span><span class="sxs-lookup"><span data-stu-id="d7994-140">Use ADSI Edit to see whether you have an SCP published in Active Directory: CN=Configuration [server name], CN=Services, CN=RightsManagementServices, CN=SCP</span></span>

2. <span data-ttu-id="d7994-141">Если вы не используете SCP, компьютеры Windows, подключаемые к кластеру AD RMS, должны быть настроены для обнаружения службы клиента или перенаправления лицензирования с помощью реестра Windows: `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation or HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSIPC\ServiceLocation` .</span><span class="sxs-lookup"><span data-stu-id="d7994-141">If you are not using an SCP, Windows computers that connect to an AD RMS cluster must be configured for client-side service discovery or licensing redirection by using the Windows registry: `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation or HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSIPC\ServiceLocation`.</span></span>

<span data-ttu-id="d7994-142">Дополнительные сведения об этих конфигурациях реестра см. в дополнительных сведениях об открытии клиентской службы с помощью реестра [Windows](/azure/information-protection/rms-client/client-deployment-notes#enabling-client-side-service-discovery-by-using-the-windows-registry) и перенаправления трафика серверов [лицензирования.](/azure/information-protection/rms-client/client-deployment-notes#redirecting-licensing-server-traffic)</span><span class="sxs-lookup"><span data-stu-id="d7994-142">For more information about these registry configurations, see [Enabling client-side service discovery by using the Windows registry](/azure/information-protection/rms-client/client-deployment-notes#enabling-client-side-service-discovery-by-using-the-windows-registry) and [Redirecting licensing server traffic](/azure/information-protection/rms-client/client-deployment-notes#redirecting-licensing-server-traffic).</span></span>

## <a name="i-use-ad-rms-how-do-i-opt-out"></a><span data-ttu-id="d7994-143">Как отказаться от использования AD RMS?</span><span class="sxs-lookup"><span data-stu-id="d7994-143">I use AD RMS, how do I opt out?</span></span>

<span data-ttu-id="d7994-144">Чтобы отказаться от предстоящих изменений, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="d7994-144">To opt out of the upcoming change, complete these steps:</span></span>

1. <span data-ttu-id="d7994-145">С помощью учетной записи для работы или учебного заведения с глобальными разрешениями администратора в организации запустите сеанс Windows PowerShell и подключите его к Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d7994-145">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="d7994-146">Инструкции см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="d7994-146">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="d7994-147">Запустите Set-IRMConfiguration с помощью следующего синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="d7994-147">Run the Set-IRMConfiguration cmdlet using the following syntax:</span></span>

  ```powershell
  Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false
  ```

## <a name="what-can-i-expect-after-this-change-has-been-made"></a><span data-ttu-id="d7994-148">Что можно ожидать после внося этого изменения?</span><span class="sxs-lookup"><span data-stu-id="d7994-148">What can I expect after this change has been made?</span></span>

<span data-ttu-id="d7994-149">После включения, при условии, что вы не отключались, можно начать использовать новую версию шифрования сообщений Office 365, которая была объявлена на [Microsoft Ignite 2017](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Email-Encryption-and-Rights-Protection/ba-p/110801) и использует возможности шифрования и защиты azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="d7994-149">Once this is enabled, provided you haven't opted out, you can start using the new version of Office 365 Message Encryption which was announced at [Microsoft Ignite 2017](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Email-Encryption-and-Rights-Protection/ba-p/110801) and leverages the encryption and protection capabilities of Azure Information Protection.</span></span>

![Снимок экрана, на который показано защищенное сообщение OME в Outlook в Интернете.](../../media/599ca9e7-c05a-429e-ae8d-359f1291a3d8.png)

<span data-ttu-id="d7994-151">Дополнительные сведения о новых усовершенствованиях см. в [сообщении Office 365.](../../compliance/ome.md)</span><span class="sxs-lookup"><span data-stu-id="d7994-151">For more information about the new enhancements, see [Office 365 Message Encryption](../../compliance/ome.md).</span></span>