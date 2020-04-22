---
title: Создание политики удаления документов
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
ms.assetid: 41b2ed73-eb8d-4429-945e-a8197894585a
description: Часто организациям необходимо сохранять документы в течение определенного периода времени согласно требованиям соответствия, правовым и другим нормам. Однако хранение документов на протяжении более длительного срока, нежели требуется, может подвергнуть организацию юридическим рискам.
ms.openlocfilehash: 5550f65e5b2ecb5dca775e1d851548913b8e8517
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632264"
---
# <a name="create-a-document-deletion-policy"></a><span data-ttu-id="08a71-104">Создание политики удаления документов</span><span class="sxs-lookup"><span data-stu-id="08a71-104">Create a document deletion policy</span></span>

> [!IMPORTANT]
> <span data-ttu-id="08a71-105">В дальнейшем рекомендуется использовать политику хранения или метки хранения, созданные в центре соответствия требованиям Microsoft 365, центре безопасности 365 Майкрософт или &amp; центре безопасности, а не политике удаления документов.</span><span class="sxs-lookup"><span data-stu-id="08a71-105">Moving forward, we recommend that you use a retention policy or retention labels created in the Microsoft 365 compliance center, Microsoft 365 security center, or Security &amp; Compliance Center instead of a document deletion policy.</span></span> <span data-ttu-id="08a71-106">Политики удаления документов продолжат работать параллельно с политиками хранения, но если вам нужно сохранить или удалить контент везде в Office 365, рекомендуем использовать политику хранения.</span><span class="sxs-lookup"><span data-stu-id="08a71-106">Document deletion policies will continue to work side by side with retention policies, but if you need to retain or delete content anywhere in Office 365, we recommend that you use a retention policy.</span></span> <span data-ttu-id="08a71-107">Дополнительные сведения см. [в статье Использование политики хранения вместо этих функций](retention-policies.md#use-a-retention-policy-instead-of-these-features).</span><span class="sxs-lookup"><span data-stu-id="08a71-107">For more information, see [Use a retention policy instead of these features](retention-policies.md#use-a-retention-policy-instead-of-these-features).</span></span> 
  
<span data-ttu-id="08a71-p103">Часто организациям необходимо сохранять документы в течение определенного периода времени согласно требованиям соответствия, правовым и другим нормам. Однако хранение документов на протяжении более длительного срока, нежели требуется, может подвергнуть организацию юридическим рискам.</span><span class="sxs-lookup"><span data-stu-id="08a71-p103">Organizations are often required to retain documents for a certain period of time due to compliance, legal, or other regulations. However, retaining documents for longer than required can expose the organization to legal risk.</span></span>
  
<span data-ttu-id="08a71-110">С помощью политики удаления документов вы можете снизить риск, удалив документы на сайте по истечении определенного периода времени, например, вы можете удалять документы в OneDrive для бизнеса сайтов пользователей через пять лет после создания документов.</span><span class="sxs-lookup"><span data-stu-id="08a71-110">With a document deletion policy, you can proactively reduce risk by deleting documents in a site after a specific period of time—for example, you can delete documents in users' OneDrive for Business sites five years after the documents were created.</span></span> 
  
<span data-ttu-id="08a71-p104">Создав политику удаления документов, вы можете назначить ее шаблону семейства веб-сайтов, чтобы эта политика была доступна всем семействам веб-сайтов, созданным по указанному шаблону. Кроме того, можно назначить политику определенному семейству веб-сайтов, и она станет приоритетнее любых политик, назначенных шаблону для этого семейства веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="08a71-p104">After you create a document deletion policy, you can assign it to a site collection template, so that the policy is available to all site collections created from that template. You can also assign a policy to a specific a site collection, which overrides any policies that may have been assigned to the template for that site collection.</span></span>
  
![Домашняя страница Центра политики удаления документов](../media/IP-Document-Deletion-Policy-Center-home-page.png)
  
## <a name="policy-templates"></a><span data-ttu-id="08a71-114">Шаблоны политики</span><span class="sxs-lookup"><span data-stu-id="08a71-114">Policy templates</span></span>

<span data-ttu-id="08a71-p105">Вы можете создать политику удаления документов с нуля или использовать один из примеров политик. В Центре политики соответствия есть примеры политик, которые можно использовать либо как готовые политики, либо в качестве отправной точки для создания собственных.</span><span class="sxs-lookup"><span data-stu-id="08a71-p105">You can create a document deletion policy from scratch, or you can use one of the sample policies. The Compliance Policy Center includes sample policies that you can use as is, or you can use them as a starting point and then rename or modify them.</span></span>
  
![Примеры политик удаления документов](../media/IP-Sample-deletion-policies.png)
  
## <a name="examples-of-how-to-use-document-deletion-policies"></a><span data-ttu-id="08a71-118">Примеры</span><span class="sxs-lookup"><span data-stu-id="08a71-118">Examples of how to use document deletion policies</span></span>

<span data-ttu-id="08a71-119">Семейству веб-сайтов или шаблону семейства веб-сайтов может быть назначено несколько политик, при этом каждая из них может иметь несколько правил.</span><span class="sxs-lookup"><span data-stu-id="08a71-119">A site collection or a site collection template can have one more policies assigned to it, and each of those policies can have one or more rules.</span></span> <span data-ttu-id="08a71-120">Тем не менее, на каждом сайте может быть только одна политика, и в любой момент времени для библиотек на сайте может быть только одно правило удаления.</span><span class="sxs-lookup"><span data-stu-id="08a71-120">However, there can be only one policy that's active per site, and there can be only one deletion rule that's active at any time for the libraries within the site.</span></span>
  
![Схема отношений между политиками](../media/IP-Two-policies-four-rules.png)
  
<span data-ttu-id="08a71-122">Кроме того, вы можете отметить политику как обязательную или как политику по умолчанию, а также отметить правило удаления как правило по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="08a71-122">In addition, you can select a policy as mandatory or default, and you can select a deletion rule as a default rule:</span></span> 
  
- <span data-ttu-id="08a71-123">**Обязательная политика** Если политика помечена как обязательная, семейству веб-сайтов или шаблону может быть назначена только одна политика.</span><span class="sxs-lookup"><span data-stu-id="08a71-123">**Mandatory policy**When a policy is marked as mandatory, only one policy can be assigned to the site collection or template.</span></span> <span data-ttu-id="08a71-124">Политика должна быть помечена как используемая по умолчанию, и она будет применена ко всем сайтам.</span><span class="sxs-lookup"><span data-stu-id="08a71-124">The policy must be marked as default and will be applied to all sites.</span></span> <span data-ttu-id="08a71-125">Владельцы сайтов не могут отказаться от применения политики.</span><span class="sxs-lookup"><span data-stu-id="08a71-125">Site owners cannot opt out of the policy.</span></span>
    
- <span data-ttu-id="08a71-126">**Политика по умолчанию** Если политика задана по умолчанию, она автоматически становится активной во всех сайтах, которым она назначена, без каких-либо действий, необходимых владельцам сайта.</span><span class="sxs-lookup"><span data-stu-id="08a71-126">**Default policy**When a policy is set as default, the policy is automatically active in all sites that it's assigned to with no action required by site owner.</span></span>
    
- <span data-ttu-id="08a71-127">**Правило по умолчанию** Когда правило удаления устанавливается по умолчанию, оно автоматически применяется ко всем библиотекам на сайтах, использующих эту политику.</span><span class="sxs-lookup"><span data-stu-id="08a71-127">**Default rule**When a deletion rule is set as default, it is automatically applied to all libraries in the sites that use the policy.</span></span>
    
<span data-ttu-id="08a71-128">В приведенных ниже примерах описаны ситуации, когда может потребоваться использование обязательной политики или политики по умолчанию, а также правила.</span><span class="sxs-lookup"><span data-stu-id="08a71-128">The following examples explain when you might want to use a mandatory policy or default policies and rules.</span></span>
  
### <a name="example-1-apply-a-single-policy-with-a-single-rule-to-a-site-collection-template"></a><span data-ttu-id="08a71-129">Пример 1. Применение одной политики с одним правилом к шаблону семейства веб-сайтов</span><span class="sxs-lookup"><span data-stu-id="08a71-129">Example 1: Apply a single policy with a single rule to a site collection template</span></span>

<span data-ttu-id="08a71-p108">Может потребоваться применить политику удаления документов к широкому спектру неструктурированного контента, например ко всем веб-сайтам OneDrive для бизнеса или ко всем веб-сайтам групп. Чтобы убедиться, что одна политика удаления документов активна на всех веб-сайтах, созданных по шаблону семейства веб-сайтов, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="08a71-p108">You may want to enforce a document deletion policy across a broad range of unstructured content, such as all OneDrive for Business sites or all team sites. If you want to ensure that a single document deletion policy is active in all sites created from a site collection template, you can:</span></span>
  
1. <span data-ttu-id="08a71-132">Создайте одну политику с одним правилом удаления по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="08a71-132">Create a single policy with a single default deletion rule.</span></span>
    
2. <span data-ttu-id="08a71-133">Установите ее как обязательную и как политику по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="08a71-133">Set the policy as mandatory and default.</span></span>
    
3. <span data-ttu-id="08a71-134">Назначьте политику для шаблона семейства веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="08a71-134">Assign the policy to a site collection template.</span></span>
    
<span data-ttu-id="08a71-p109">В этом примере правило удаления по умолчанию применяется ко всем библиотекам в семействах веб-сайтов, созданных по этому шаблону, а владельцы веб-сайта не могут отменять политику. Это самый простой способ широкого и строгого применения политики удаления документов.</span><span class="sxs-lookup"><span data-stu-id="08a71-p109">In this example, the default deletion rule will be applied to all libraries in all site collections created from the template, and site owners cannot opt out of the policy. This is the simplest way to broadly and rigidly enforce a document deletion policy.</span></span>
  
![Схема, на которой показана одна обязательная политика](../media/IP-Example-1-doc-deletion-policies.png)
  
### <a name="example-2-apply-a-single-policy-with-several-rules-to-a-site-collection-template"></a><span data-ttu-id="08a71-138">Пример 2: применение одной политики с несколькими правилами к шаблону семейства веб-сайтов</span><span class="sxs-lookup"><span data-stu-id="08a71-138">Example 2: Apply a single policy with several rules to a site collection template</span></span>

<span data-ttu-id="08a71-p110">Как правило, владельцы веб-сайтов лучше знают, контент какого типа содержится на их веб-сайте, потому вы можете предоставить возможность владельцам веб-сайтов выбрать правило удаления, которое лучше подходит их веб-сайту. Можно также разрешить владельцам веб-сайта полностью отказаться от политики.</span><span class="sxs-lookup"><span data-stu-id="08a71-p110">Site owners often know best what type of content their site contains, so you may choose to allow site owners to select the deletion rule that best applies to their site. You may also want to allow site owners to opt out of a policy entirely.</span></span>
  
<span data-ttu-id="08a71-p111">В то же время можно по-прежнему централизованно создавать политики и управлять ими. Вы также можете отметить одну политику и правило как значения по умолчанию, чтобы они всегда выполнялись, пока владелец веб-сайта не выберет другие или не отменит их. Чтобы обеспечить такую гибкость владельцам веб-сайтов, выполните указанные действия.</span><span class="sxs-lookup"><span data-stu-id="08a71-p111">At the same time, you can still centrally create and manage the policies. You can also select one policy and rule as the default, so that a policy is always in effect until the site owner chooses a different one or opts out. If you want to provide such flexibility to site owners, you can:</span></span>
  
1. <span data-ttu-id="08a71-143">Создайте одну политику с несколькими правилами удаления и установите одно правило в качестве правила по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="08a71-143">Create a single policy with several deletion rules, and set one rule as the default.</span></span>
    
2. <span data-ttu-id="08a71-144">Установите политику как политику по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="08a71-144">Set the policy as the default policy.</span></span>
    
3. <span data-ttu-id="08a71-145">Назначьте политику для шаблона семейства веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="08a71-145">Assign the policy to a site collection template.</span></span>
    
<span data-ttu-id="08a71-146">Владельцы веб-сайтов могут выбрать одно из альтернативных правил удаления, отменить политику, а могут не выполнять никаких действий и подчиняться политике и правилу по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="08a71-146">Site owners can select one of the alternate deletion rules, opt out of the policy, or do nothing and be subject to the default policy and rule.</span></span>
  
![Схема, на которой показана одна политика со множеством правил](../media/IP-Example-2-doc-deletion-policies.png)
  
### <a name="example-3-apply-several-policies-with-one-or-more-rules-to-a-site-collection"></a><span data-ttu-id="08a71-148">Пример 3. Применение нескольких политик с одним или несколькими правилами к семейству веб-сайтов</span><span class="sxs-lookup"><span data-stu-id="08a71-148">Example 3: Apply several policies with one or more rules to a site collection</span></span>

<span data-ttu-id="08a71-p112">В этом примере владельцы веб-сайтов получают максимальную гибкость, поскольку они могут выбирать из нескольких политик, а выбрав политику, выбрать из нескольких правил. Одна политика и правило установлены как значения по умолчанию, чтобы они всегда выполнялись, пока владелец веб-сайта не выберет другие или не отменит их. Обратите внимание на то, что если не отметить политику и правило как значения по умолчанию, ни одна политика или правило не будут активны для библиотек документов на веб-сайте, пока владелец веб-сайта не выполнит необходимые действия для их выбора и применения.</span><span class="sxs-lookup"><span data-stu-id="08a71-p112">This example provides the maximum flexibility to site owners because they can choose from several policies, and after selecting a policy they can often choose from several rules. One policy and rule are set as default, so that a policy is always in effect until the site owner chooses a different one or opts out. Note that if you do not set a policy and rule as the default, then no policies or rules will be active for the document libraries in the site until the site owner takes action to select and apply them.</span></span>
  
<span data-ttu-id="08a71-p113">В отличие от двух предыдущих примеров эти политики назначаются определенному семейству веб-сайтов, а не шаблону семейства веб-сайтов. Это означает, что их можно лучше подстроить под конкретный контент определенного семейства веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="08a71-p113">Unlike the previous two examples, these policies are assigned to a specific site collection — not the site collection template. This means the policies can be more specifically tailored for the content in a specific site collection.</span></span>
  
<span data-ttu-id="08a71-p114">Политики и правила являются наследуемыми. Владельцы веб-сайтов могут выбрать политику и правило для своего веб-сайта, а все дочерние сайты наследуют эту политику от родительского сайта. Однако владелец дочернего веб-сайта может остановить наследование, выбрав другую политику или правило, которые будут применены ко всем дочерним сайтам, пока наследование не будет остановлено снова.</span><span class="sxs-lookup"><span data-stu-id="08a71-p114">Policies and rules are inherited. Site owners can select a policy and rule for their site, and all subsites inherit the policy from the parent. However, an owner of a subsite can break inheritance by selecting a different policy and rule, which in turn applies to all subsites until inheritance is broken again.</span></span>
  
<span data-ttu-id="08a71-156">Чтобы настроить этот сценарий, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="08a71-156">To set up this scenario, you can:</span></span>
  
1. <span data-ttu-id="08a71-157">Создайте несколько политик, каждая из которых содержит одно или несколько правил.</span><span class="sxs-lookup"><span data-stu-id="08a71-157">Create several policies that each contains one or more rules.</span></span>
    
2. <span data-ttu-id="08a71-158">Установите политику и правило как значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="08a71-158">Set a policy and rule as the default.</span></span>
    
3. <span data-ttu-id="08a71-159">Назначьте политики для определенного семейства веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="08a71-159">Assign the policies to a specific site collection.</span></span>
    
<span data-ttu-id="08a71-160">Кроме того, политики и правила можно подстроить под определенное семейство веб-сайтов, при этом владельцы веб-сайтов могут остановить наследование, выбрав политику и правило, которые лучше всего подходят веб-сайту.</span><span class="sxs-lookup"><span data-stu-id="08a71-160">In addition, the policies and rules are tailored to a specific site collection, where site owners can break inheritance by selecting the policy and rule that best applies to their site.</span></span>
  
![Схема, на которой показано множество политик и правил](../media/IP-Example-3-doc-deletion-policies.png)
  
## <a name="create-a-document-deletion-policy"></a><span data-ttu-id="08a71-162">Создание политики удаления документов</span><span class="sxs-lookup"><span data-stu-id="08a71-162">Create a document deletion policy</span></span>

1. <span data-ttu-id="08a71-163">В центре соответствия требованиям &amp; Office 365Security перейдите к разделу \> **Хранение** **управления данными** .</span><span class="sxs-lookup"><span data-stu-id="08a71-163">In the Office 365Security &amp; Compliance Center, navigate to **Data management** \> **Retention**.</span></span> <span data-ttu-id="08a71-164">В разделе **Delete (удалить**) щелкните **Управление политиками удаления документов для SharePoint Online и OneDrive для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="08a71-164">Under **Delete**, click **Manage document deletion policies for SharePoint Online and OneDrive for Business**.</span></span> <span data-ttu-id="08a71-165">Центр политики удаления документов откроется на новой вкладке браузера.</span><span class="sxs-lookup"><span data-stu-id="08a71-165">The Document Deletion Policy Center opens in a new browser tab.</span></span>
    
    <span data-ttu-id="08a71-166">При первом переходе с центра соответствия требованиям &amp; безопасности в центр политики удаления документов центр политики автоматически создается автоматически.</span><span class="sxs-lookup"><span data-stu-id="08a71-166">The first time you navigate from the Security &amp; Compliance Center to the Document Deletion Policy Center, the policy center is automatically created for you.</span></span> <span data-ttu-id="08a71-167">Кроме того, можно вручную создать центр политик, [создав семейство сайтов](https://go.microsoft.com/fwlink/p/?LinkID=404342) и выбрав **центр политики соответствия** на вкладке **Корпоративный** .</span><span class="sxs-lookup"><span data-stu-id="08a71-167">Alternatively, you can manually create the policy center by [creating the site collection](https://go.microsoft.com/fwlink/p/?LinkID=404342) and choosing **Compliance Policy Center** on the **Enterprise** tab.</span></span> 
    
2. <span data-ttu-id="08a71-168">Выберите **политики удаления**.</span><span class="sxs-lookup"><span data-stu-id="08a71-168">Choose **Deletion Policies**.</span></span>
    
    ![Параметр удаления политик](../media/IP-Deletion-Policies-option.png)
  
3. <span data-ttu-id="08a71-170">Выберите **новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="08a71-170">Choose **new item**.</span></span>
    
4. <span data-ttu-id="08a71-p117">Введите имя и описание политики. Владельцы веб-сайтов могут выбирать политику для своего сайта по предоставленному имени и описанию, потому добавьте достаточно сведений для выбора нужной политики.</span><span class="sxs-lookup"><span data-stu-id="08a71-p117">Enter a policy name and description. Site owners may be selecting a policy for their site based on this name and description, so include enough information for them to choose the correct policy.</span></span>
    
5. <span data-ttu-id="08a71-173">Чтобы создать правило, нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="08a71-173">To create a rule, choose **New**.</span></span>
    
6. <span data-ttu-id="08a71-174">Введите имя и выберите указанные ниже параметры.</span><span class="sxs-lookup"><span data-stu-id="08a71-174">Enter a name and choose the following options:</span></span>
    
  - <span data-ttu-id="08a71-175">Выберите, будут ли документы удаляться окончательно или перемещаться в корзину.</span><span class="sxs-lookup"><span data-stu-id="08a71-175">Choose whether the rule will permanently delete documents or delete them to the Recycle Bin.</span></span> <span data-ttu-id="08a71-176">Корзина предназначена для предупреждения окончательного удаления элементов с сайта.</span><span class="sxs-lookup"><span data-stu-id="08a71-176">The Recycle Bin provides a second-stage safety net before an item is permanently deleted from a site.</span></span> <span data-ttu-id="08a71-177">Более подробную информацию о корзине можно узнать в статье [Очистка корзины или восстановление файлов](https://go.microsoft.com/fwlink/p/?LinkID=404348).</span><span class="sxs-lookup"><span data-stu-id="08a71-177">For more information about the Recycle Bin, see [Empty the Recycle Bin or restore your files](https://go.microsoft.com/fwlink/p/?LinkID=404348).</span></span>
    
  - <span data-ttu-id="08a71-178">Выберите, на основе чего будет рассчитываться дата удаления — с момента создания документа или его последнего изменения.</span><span class="sxs-lookup"><span data-stu-id="08a71-178">Choose whether the deletion date is calculated from the date when a document was created or last modified.</span></span>
    
  - <span data-ttu-id="08a71-179">Введите количество дней, месяцев или годов в качестве периода времени, после которого документ будет удален.</span><span class="sxs-lookup"><span data-stu-id="08a71-179">Enter a number of days, months, or years as the time period after which a document will be deleted.</span></span>
    
  - <span data-ttu-id="08a71-p119">Укажите, является ли это правило правилом по умолчанию. Первое созданное правило автоматически задается в качестве правила по умолчанию. Правило по умолчанию автоматически применяется ко всем библиотекам на сайтах, использующих эту политику.</span><span class="sxs-lookup"><span data-stu-id="08a71-p119">Choose whether the rule is a default rule. The first rule that you create is automatically set as the default rule. A default rule is automatically applied to all libraries in the sites that use the policy.</span></span>
    
![Страница создания правила удаления](../media/IP-New-deletion-rule.png)
  
7. <span data-ttu-id="08a71-184">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="08a71-184">Click **Save**.</span></span>
    
8. <span data-ttu-id="08a71-p120">Создайте дополнительные правила, если необходимо, чтобы владельцы веб-сайтов могли выбирать различные правила и применять их к своим сайтам. При наличии правило по умолчанию будет применяться, если владелец веб-сайта не выполняет никаких действий.</span><span class="sxs-lookup"><span data-stu-id="08a71-p120">Create additional rules if you want site owners to be able to choose different rules to apply to their site. The default rule, if any, will be applied if the site owner takes no action.</span></span>
    
9. <span data-ttu-id="08a71-187">Чтобы удалить правило из политики, выберите правило, нажмите кнопку **Удалить**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="08a71-187">To remove a rule from a policy, select the rule, click **Delete**, and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="08a71-188">Если вы удаляете правило, а политика не содержит правило по умолчанию, то никакие правила не будут применяться к этой политике — другими словами, не будет удалено ни одного документа.</span><span class="sxs-lookup"><span data-stu-id="08a71-188">If you delete a rule, and the policy does not contain a default rule, then no rule will be in effect for that policy—in other words, no documents will be deleted.</span></span> 
  
![Сообщение о подтверждении удаления правила из политики](../media/IP-Remove-rule-from-policy-message.png)
  
## <a name="assign-the-document-deletion-policy-to-a-site-collection-template"></a><span data-ttu-id="08a71-190">Назначение политики удаления документов шаблону семейства веб-сайтов</span><span class="sxs-lookup"><span data-stu-id="08a71-190">Assign the document deletion policy to a site collection template</span></span>

<span data-ttu-id="08a71-191">Назначая политику шаблону семейства веб-сайтов, вы делаете ее доступной для всех семейств веб-сайтов, созданных по этому шаблону, включая как существующие семейства веб-сайтов, так и те, которые будут созданы в будущем.</span><span class="sxs-lookup"><span data-stu-id="08a71-191">By assigning a policy to a site collection template, you make the policy available to all site collections created from that template, including both existing site collections and site collections created in the future.</span></span>
  
<span data-ttu-id="08a71-192">Важно понимать, что период времени, указанный для политики удаления документов, указывает время, прошедшее с момента создания или изменения документа, а не с момента назначения политики.</span><span class="sxs-lookup"><span data-stu-id="08a71-192">It's important to understand that the time period specified for a document deletion policy means the time since the document was created or modified, not the time since the policy was assigned.</span></span> <span data-ttu-id="08a71-193">При первом назначении политики все документы на сайте оцениваются и в случае соответствия критериям удаляются.</span><span class="sxs-lookup"><span data-stu-id="08a71-193">When you assign the policy for the first time, all documents in the site are evaluated and, if they meet the criteria, they will be deleted.</span></span> <span data-ttu-id="08a71-194">Это применимо ко всем существующим документам, а не только к новым документам, созданным после назначения политики.</span><span class="sxs-lookup"><span data-stu-id="08a71-194">This applies to all existing documents, not just new documents created since the policy was assigned.</span></span>
  
1. <span data-ttu-id="08a71-195">В центре безопасности &amp; и соответствия требованиям перейдите к разделу \> **Хранение** **управления данными** .</span><span class="sxs-lookup"><span data-stu-id="08a71-195">In the Security &amp; Compliance Center, navigate to **Data management** \> **Retention**.</span></span> <span data-ttu-id="08a71-196">В разделе **Delete (удалить**) щелкните **Управление политиками удаления документов для SharePoint Online и OneDrive для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="08a71-196">Under **Delete**, click **Manage document deletion policies for SharePoint Online and OneDrive for Business**.</span></span> <span data-ttu-id="08a71-197">Центр политики удаления документов откроется на новой вкладке браузера.</span><span class="sxs-lookup"><span data-stu-id="08a71-197">The Document Deletion Policy Center opens in a new browser tab.</span></span>
    
2. <span data-ttu-id="08a71-198">Выберите **Назначения политик для шаблонов**.</span><span class="sxs-lookup"><span data-stu-id="08a71-198">Choose **Policy Assignments for Templates**.</span></span>
    
    ![Параметр "Назначение политик для шаблонов"](../media/IP-Policy-Assignments-for-Templates-option.png)
  
3. <span data-ttu-id="08a71-200">Выберите **новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="08a71-200">Choose **new item**.</span></span>
    
4. <span data-ttu-id="08a71-201">Выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="08a71-201">Do one of the following:</span></span>
    
  - <span data-ttu-id="08a71-202">Чтобы назначить политику шаблону семейства веб-сайтов (например, шаблону веб-сайта группы), выберите команду **Назначить шаблону семейства веб-сайтов**, а затем выберите нужный шаблон.</span><span class="sxs-lookup"><span data-stu-id="08a71-202">To assign the policy to a site collection template such as the Team Site template, select **Assign to site collection template**, and then select the site collection template.</span></span>
    
  - <span data-ttu-id="08a71-203">Чтобы назначить политику для пользователя на один диск для бизнеса, выберите пункт **назначить шаблону OneDrive для бизнеса**, выделенный ниже.</span><span class="sxs-lookup"><span data-stu-id="08a71-203">To assign the policy to users' One Drive for Business, choose **Assign to OneDrive for Business Template**, highlighted below.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="08a71-204">После назначения политики шаблону семейства веб-сайтов эта политика будет доступна как для существующих семейств веб-сайтов, созданных по этому шаблону, так и для семейств веб-сайтов, который будут созданы в будущем.</span><span class="sxs-lookup"><span data-stu-id="08a71-204">When you assign a policy to a site collection template, that policy will be available both to existing site collections created from that template and to site collections created in the future.</span></span> 
  
![Страница выбора шаблона с параметром OneDrive](../media/IP-Choose-a-template.png)
  
5. <span data-ttu-id="08a71-206">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="08a71-206">Click **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="08a71-207">Каждому шаблону можно назначить только один набор политик.</span><span class="sxs-lookup"><span data-stu-id="08a71-207">Each template can have only one set of policies assigned to it.</span></span> <span data-ttu-id="08a71-208">Если отображается сообщение об ошибке, сообщающее о том, что этому шаблону уже назначены политики, выберите **отменить** \> **назначение для семейства веб-сайтов** в левой панели навигации \> выберите семейство веб-сайтов для просмотра и управления уже назначенными политиками.</span><span class="sxs-lookup"><span data-stu-id="08a71-208">If you see an error saying that this template already has policies assigned to it, choose **Cancel** \> **Assign to Site Collection** in the left navigation \> select a site collection to view and manage the set of policies that are already assigned.</span></span> 
  
6. <span data-ttu-id="08a71-209">В разделе **Управление назначенными политиками** выберите политики, которые требуется назначить, а затем укажите, будет ли одна политика политикой по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="08a71-209">Choose **Manage Assigned Policies**, select the policies that you want to assign, and then choose whether one policy is the default policy.</span></span> <span data-ttu-id="08a71-210">После установки политики по умолчанию она станет активной для всех веб-сайтов, которым она назначена, при этом не требуются действия владельца сайта.</span><span class="sxs-lookup"><span data-stu-id="08a71-210">When you set a default policy, all sites assigned to the policy automatically have the policy active with no action required by site owner.</span></span>
    
    ![Страница добавления политик и управления ими](../media/IP-Add-and-manage-policies-page.png)
  
7. <span data-ttu-id="08a71-212">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="08a71-212">Click **Save**.</span></span>
    
8. <span data-ttu-id="08a71-p125">Если требуется применить политику ко всем веб-сайтам, не позволяя владельцам сайтов отменять ее, выберите команду **Отметить политику как обязательную**. Если политика является обязательной, то только она может назначаться шаблону семейства веб-сайтов. Политика также должна быть отмечена как политика по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="08a71-p125">If you want to enforce the policy on all sites without allowing site owners to opt out, choose **Mark Policy as Mandatory**. When you make a policy mandatory, only that single policy can be assigned to the site collection template. The policy must also be marked as default.</span></span>
    
    <span data-ttu-id="08a71-216">Если этот параметр деактивирован, выберите **Управление назначенными политиками** и убедитесь, что по крайней мере одна политика назначена и отмечена как политика по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="08a71-216">If this option is grayed out, choose **Manage Assigned Policies** and make sure that at least one policy is assigned and set as default.</span></span> 
    
9. <span data-ttu-id="08a71-217">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="08a71-217">Click **Save**.</span></span>
    
## <a name="assign-the-document-deletion-policy-to-a-site-collection"></a><span data-ttu-id="08a71-218">Назначение политики удаления документов семейству веб-сайтов</span><span class="sxs-lookup"><span data-stu-id="08a71-218">Assign the document deletion policy to a site collection</span></span>

<span data-ttu-id="08a71-p126">Назначив политику определенному семейству веб-сайтов, вы делаете ее доступной только для указанного семейства веб-сайтов. Это означает, что можно лучше подстраивать политики к контенту в семействе веб-сайтов. Кроме того, политики, назначенные определенному семейству веб-сайтов, будет иметь приоритет над любыми политиками, которые назначены шаблону этого семейства веб-сайтов. Например, политика, назначенная семейству веб-сайтов отдела продаж (созданному по шаблону сайта группы), будет иметь приоритет над любыми политиками, назначенными шаблону сайта группы.</span><span class="sxs-lookup"><span data-stu-id="08a71-p126">By assigning a policy to a specific site collection, you make the policy available only to that specific site collection. This means you can tailor policies more closely to the content in the site collection. Also, policies assigned to a specific site collection will override any policies that are assigned to the template for that site collection. For example, a policy assigned to the Sales Department site collection (created from the Team Site template) will override any policies assigned to the Team Site template.</span></span>
  
<span data-ttu-id="08a71-223">Важно понимать, что период времени, указанный для политики удаления документов, указывает время, прошедшее с момента создания или изменения документа, а не с момента назначения политики.</span><span class="sxs-lookup"><span data-stu-id="08a71-223">It's important to understand that the time period specified for a document deletion policy means the time since the document was created or modified, not the time since the policy was assigned.</span></span> <span data-ttu-id="08a71-224">При первом назначении политики все документы на сайте оцениваются и в случае соответствия критериям удаляются.</span><span class="sxs-lookup"><span data-stu-id="08a71-224">When you assign the policy for the first time, all documents in the site are evaluated and, if they meet the criteria, they will be deleted.</span></span> <span data-ttu-id="08a71-225">Это применимо ко всем существующим документам, а не только к новым документам, созданным после назначения политики.</span><span class="sxs-lookup"><span data-stu-id="08a71-225">This applies to all existing documents, not just new documents created since the policy was assigned.</span></span>
  
1. <span data-ttu-id="08a71-226">В центре безопасности &amp; и соответствия требованиям перейдите к разделу \> **Хранение** **управления данными** .</span><span class="sxs-lookup"><span data-stu-id="08a71-226">In the Security &amp; Compliance Center, navigate to **Data management** \> **Retention**.</span></span> <span data-ttu-id="08a71-227">В разделе **Delete (удалить**) выберите пункт **Управление политиками удаления документов для SharePoint Online и OneDrive для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="08a71-227">Under **Delete**, choose **Manage document deletion policies for SharePoint Online and OneDrive for Business**.</span></span> <span data-ttu-id="08a71-228">Центр политики удаления документов откроется на новой вкладке браузера.</span><span class="sxs-lookup"><span data-stu-id="08a71-228">The Document Deletion Policy Center opens in a new browser tab.</span></span>
    
2. <span data-ttu-id="08a71-229">Выберите **Назначения политик для семейств веб-сайтов**.</span><span class="sxs-lookup"><span data-stu-id="08a71-229">Choose **Policy Assignments for Site Collections**.</span></span>
    
    ![Параметр "Назначение политик для семейств веб-сайтов"](../media/IP-Policy-Assignments-for-Site-Collections-option.png)
  
3. <span data-ttu-id="08a71-231">Выберите **новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="08a71-231">Choose **new item**.</span></span>
    
4. <span data-ttu-id="08a71-232">Выберите **пункт Выбор семейства веб-сайтов**.</span><span class="sxs-lookup"><span data-stu-id="08a71-232">Choose **Choose a site collection**.</span></span> <span data-ttu-id="08a71-233">Поиск семейства веб-сайтов по имени или URL-адресу выберите семейство сайтов и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="08a71-233">Search for the site collection by name or URL, select the site collection and click **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="08a71-234">Каждому семейству веб-сайтов может быть назначен только один набор политик.</span><span class="sxs-lookup"><span data-stu-id="08a71-234">Each site collection can have only one set of policies assigned to it.</span></span> <span data-ttu-id="08a71-235">Если отображается сообщение об ошибке с сообщением о том, что этому семейству веб-сайтов уже назначены политики, выберите **отменить** \> **назначение в семействе веб-сайтов** и выберите семейство веб-сайтов для просмотра набора политик, который уже назначен, и управления им.</span><span class="sxs-lookup"><span data-stu-id="08a71-235">If you see an error saying that this site collection already has policies assigned to it, choose **Cancel** \> **Assign to Site Collection** and select a site collection to view and manage the set of policies that are already assigned.</span></span> 
  
![Страница выбора семейства веб-сайтов](../media/IP-Choose-a-site-collection-page.png)
  
5. <span data-ttu-id="08a71-237">В разделе **Управление назначенными политиками** выберите политики, которые требуется назначить, а затем укажите, будет ли одна политика политикой по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="08a71-237">Choose **Manage Assigned Policies**, select the policies that you want to assign, and then choose whether one policy is the default policy.</span></span> <span data-ttu-id="08a71-238">После установки политики по умолчанию она станет активной для всех веб-сайтов, которым она назначена, при этом не требуются действия владельца сайта.</span><span class="sxs-lookup"><span data-stu-id="08a71-238">When you set a default policy, all sites assigned to the policy automatically have the policy active with no action required by site owner.</span></span>
    
    ![Страница добавления политик и управления ими](../media/IP-Add-and-manage-policies-page.png)
  
6. <span data-ttu-id="08a71-240">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="08a71-240">Click **Save**.</span></span>
    
7. <span data-ttu-id="08a71-p132">Если требуется применить политику ко всем веб-сайтам, не позволяя владельцам сайтов отменять ее, выберите команду **Отметить политику как обязательную**. Если политика является обязательной, то только она может назначаться семейству веб-сайтов. Политика также должна быть отмечена как политика по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="08a71-p132">If you want to enforce the policy on all sites without allowing site owners to opt out, choose **Mark Policy as Mandatory**. When you make a policy mandatory, only that single policy can be assigned to the site collection. The policy must also be marked as default.</span></span>
    
    <span data-ttu-id="08a71-244">Если этот параметр деактивирован, выберите **Управление назначенными политиками** и убедитесь, что по крайней мере одна политика назначена и отмечена как политика по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="08a71-244">If this option is grayed out, choose **Manage Assigned Policies** and make sure that at least one policy is assigned and set as default.</span></span> 
    
8. <span data-ttu-id="08a71-245">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="08a71-245">Click **Save**.</span></span>
    
## <a name="delete-a-policy-assignment"></a><span data-ttu-id="08a71-246">Удаление назначения политики</span><span class="sxs-lookup"><span data-stu-id="08a71-246">Delete a policy assignment</span></span>

<span data-ttu-id="08a71-247">После удаления назначения назначенные политики не будут применяться к сайтам в семействе веб-сайтов или шаблону семейства веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="08a71-247">When you delete an assignment, the assigned policies will no longer apply to any sites in the site collection or site collection template.</span></span>
  
1. <span data-ttu-id="08a71-248">В центре безопасности &amp; и соответствия требованиям перейдите к разделу \> **Хранение** **управления данными** .</span><span class="sxs-lookup"><span data-stu-id="08a71-248">In the Security &amp; Compliance Center, navigate to **Data management** \> **Retention**.</span></span> <span data-ttu-id="08a71-249">В разделе **Delete (удалить**) выберите пункт **Управление политиками удаления документов для SharePoint Online и OneDrive для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="08a71-249">Under **Delete**, choose **Manage document deletion policies for SharePoint Online and OneDrive for Business**.</span></span> <span data-ttu-id="08a71-250">Центр политики удаления документов откроется на новой вкладке браузера.</span><span class="sxs-lookup"><span data-stu-id="08a71-250">The Document Deletion Policy Center opens in a new browser tab.</span></span>
    
2. <span data-ttu-id="08a71-251">Выберите **Назначения политик для шаблонов** или **Назначения политик для семейств веб-сайтов**.</span><span class="sxs-lookup"><span data-stu-id="08a71-251">Choose either **Policy Assignments for Templates** or **Policy Assignments for Site Collections**.</span></span>
    
3. <span data-ttu-id="08a71-252">Выберите элемент назначения и нажмите кнопку **удалить элемент**.</span><span class="sxs-lookup"><span data-stu-id="08a71-252">Select the assignment item and click **Delete Item**.</span></span>
    
    ![Команда удаления элемента для назначения политики](../media/IP-Delete-policy-assignment.png)
  
## <a name="delete-a-policy"></a><span data-ttu-id="08a71-254">Удаление политики</span><span class="sxs-lookup"><span data-stu-id="08a71-254">Delete a policy</span></span>

<span data-ttu-id="08a71-255">Вы не можете удалить используемую политику.</span><span class="sxs-lookup"><span data-stu-id="08a71-255">You can't delete a policy that's in use.</span></span> <span data-ttu-id="08a71-256">Прежде чем удалять политику, сначала необходимо удалить все назначения для семейств веб-сайтов и шаблонов семейств веб-сайтов, включающих эту политику, в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="08a71-256">Before you can delete a policy, you first need to delete all assignments to site collections and site collection templates that include that policy—see the previous section.</span></span>
  
1. <span data-ttu-id="08a71-257">В центре &amp; \> безопасности и соответствия требованиям выберите **Хранение** \> **данных** \> в левой области переходов под надписью **Удалить** \> **Управление политиками удаления документов для SharePoint Online и OneDrive для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="08a71-257">In the Security &amp; Compliance Center \> choose **Data management** \> **Retention** in the left navigation \> under **Delete** \> **Manage document deletion policies for SharePoint Online and OneDrive for Business**.</span></span> <span data-ttu-id="08a71-258">Центр политики удаления документов откроется на новой вкладке браузера.</span><span class="sxs-lookup"><span data-stu-id="08a71-258">The Document Deletion Policy Center opens in a new browser tab.</span></span>
    
2. <span data-ttu-id="08a71-259">Выберите \* \* политики удаления \* \*.</span><span class="sxs-lookup"><span data-stu-id="08a71-259">Choose \*\* Deletion Policies \*\*.</span></span>
    
    ![Параметр удаления политик](../media/IP-Deletion-Policies-option.png)
  
3. <span data-ttu-id="08a71-261">Выберите политику.</span><span class="sxs-lookup"><span data-stu-id="08a71-261">Select the policy.</span></span>
    
4. <span data-ttu-id="08a71-262">На вкладке \> **Items** \> элементы ленты **Удаление политики**.</span><span class="sxs-lookup"><span data-stu-id="08a71-262">On the Ribbon \> **Items** tab \> **Remove Policy**.</span></span>
    
    ![Кнопка "Удалить политику" на ленте](../media/IP-Remove-Policy-button-on-Ribbon.png)
  
5. <span data-ttu-id="08a71-264">Если политика используется, вам будет предложено удалить политику из всех семейств веб-сайтов, где она используется.</span><span class="sxs-lookup"><span data-stu-id="08a71-264">If the policy is in use, you'll be asked if you want to remove the policy from all of the site collections where it's being used.</span></span> <span data-ttu-id="08a71-265">Если вы уверены, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="08a71-265">If you're sure, choose **OK**.</span></span>
    
    ![Сообщение о подтверждении удаления политики](../media/IP-Delete-policy-confirmation.png)
  
## <a name="see-also"></a><span data-ttu-id="08a71-267">См. также</span><span class="sxs-lookup"><span data-stu-id="08a71-267">See also</span></span>

[<span data-ttu-id="08a71-268">Обзор политик удаления документов</span><span class="sxs-lookup"><span data-stu-id="08a71-268">Overview of document deletion policies</span></span>](document-deletion-policies.md)

[<span data-ttu-id="08a71-269">Применение или удаление политики удаления документов для сайта</span><span class="sxs-lookup"><span data-stu-id="08a71-269">Apply or remove a document deletion policy for a site</span></span>](apply-or-remove-a-document-deletion-policy-for-a-site.md)
 

