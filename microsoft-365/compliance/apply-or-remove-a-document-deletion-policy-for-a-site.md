---
title: Применение или удаление политики удаления документов для сайта
ms.author: laurawi
author: laurawi
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3e92668-f9b2-46ee-8e5e-c623870588b6
description: Организациям часто приходится хранить документы в течение определенного периода времени в соответствии с нормативными, законодательными или другими требованиями. Однако хранение документов дольше, чем требуется, может привести к возникновению юридических рисков. Поэтому организации могут создать политику удаления документов для сайта. Например, общие бизнес-документы могут в обязательном порядке удаляться через пять лет после их создания.
ms.openlocfilehash: 2eaa864cda726e6e36625f81358da76856db7db4
ms.sourcegitcommit: e292e9f0181d722a11398fbd012bb84589aef052
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/25/2019
ms.locfileid: "39256766"
---
# <a name="apply-or-remove-a-document-deletion-policy-for-a-site"></a><span data-ttu-id="30cbf-105">Применение или удаление политики удаления документов для сайта</span><span class="sxs-lookup"><span data-stu-id="30cbf-105">Apply or remove a document deletion policy for a site</span></span>

<span data-ttu-id="30cbf-106">Организации часто подчиняются требованиям, юридическим требованиям или другим нормативам, которые требуют, чтобы они сохраняли документы в течение определенного периода времени.</span><span class="sxs-lookup"><span data-stu-id="30cbf-106">Organizations are often subject to compliance, legal, or other regulations that require them to retain documents for a certain period of time.</span></span> <span data-ttu-id="30cbf-107">Однако хранение документов на протяжении более длительного срока, нежели требуется, может подвергнуть организацию юридическим рискам.</span><span class="sxs-lookup"><span data-stu-id="30cbf-107">However, retaining documents for longer than required can expose the organization to legal risk.</span></span> <span data-ttu-id="30cbf-108">По этой причине в Организации может быть создана политика удаления документов для сайта&mdash;, например, после создания общих бизнес-документов может потребоваться удалить их из пяти лет.</span><span class="sxs-lookup"><span data-stu-id="30cbf-108">For this reason, your organization may have created a document deletion policy for your site&mdash;for example, general business documents might be required to be deleted five years after they were created.</span></span>
  
<span data-ttu-id="30cbf-109">В зависимости от организации существуют такие политики удаления документов:</span><span class="sxs-lookup"><span data-stu-id="30cbf-109">Depending on your organization, a document deletion policy might be:</span></span>
  
- <span data-ttu-id="30cbf-110">**Обязательный** параметр Владелец сайта не может отказаться от обязательной политики, которая автоматически применяется к сайту.</span><span class="sxs-lookup"><span data-stu-id="30cbf-110">**Mandatory** A site owner can't opt out of a mandatory policy, which is automatically applied to the site.</span></span> 
    
- <span data-ttu-id="30cbf-111">**Стандартная** Стандартная политика автоматически применяется к сайту, но его владелец может:</span><span class="sxs-lookup"><span data-stu-id="30cbf-111">**Default** A default policy is automatically applied to a site, but a site owner can:</span></span> 
    
  - <span data-ttu-id="30cbf-112">Выбрать другую политику, если она доступна.</span><span class="sxs-lookup"><span data-stu-id="30cbf-112">Choose another policy if available.</span></span>
    
  - <span data-ttu-id="30cbf-113">Отказаться от применения политики полностью, если она не подходит для контента сайта.</span><span class="sxs-lookup"><span data-stu-id="30cbf-113">Opt out of the policy entirely if it isn't relevant to the content in the site.</span></span>
    
- <span data-ttu-id="30cbf-114">**Не обязательная и не стандартная** В этом случае политика не применяется к сайту автоматически, и его владелец должен применить одну из них.</span><span class="sxs-lookup"><span data-stu-id="30cbf-114">**Neither mandatory nor default** In this case, no policy is automatically applied to the site, and the site owner needs to take action to apply one.</span></span> 
    
<span data-ttu-id="30cbf-115">Политика удаления документов может содержать более одного правила&mdash;например, одно правило может сказать удалить документы через год после создания, но другое правило может сказать удалить документы через год после их последнего изменения.</span><span class="sxs-lookup"><span data-stu-id="30cbf-115">A document deletion policy may contain more than one rule&mdash;for example, one rule might say delete documents one year after they were created, but another rule might say delete documents one year after they were last modified.</span></span> <span data-ttu-id="30cbf-116">Если политика содержит несколько правил, вы можете выбрать правило, которое лучше всего подходит для вашего сайта.</span><span class="sxs-lookup"><span data-stu-id="30cbf-116">If a policy contains more than one rule, you can select the rule that best applies to your site.</span></span> <span data-ttu-id="30cbf-117">Правило удаления будет применено ко всем библиотекам на сайте.</span><span class="sxs-lookup"><span data-stu-id="30cbf-117">The delete rule will be applied to all libraries within the site.</span></span> <span data-ttu-id="30cbf-118">Только одна политика и одно правило могут быть активными в сайте одновременно.</span><span class="sxs-lookup"><span data-stu-id="30cbf-118">Only one policy and one rule can be active in a site at one time.</span></span> <span data-ttu-id="30cbf-119">Как и политика, правило можно задать по умолчанию, чтобы оно автоматически применялось при применении политики.</span><span class="sxs-lookup"><span data-stu-id="30cbf-119">Like a policy, a rule can be set as default, so that it's applied automatically when the policy is applied.</span></span>
  
<span data-ttu-id="30cbf-p104">Наконец, политики удаления документов наследуются. Все подсайты наследуют выбранную для сайта политику или правило. Владелец подсайта может прервать наследование, выбрав другую политику или правило. Выбирая политику или правило, примите во внимание подсайты, находящиеся ниже вашего сайта.</span><span class="sxs-lookup"><span data-stu-id="30cbf-p104">Finally, document deletion policies are inherited. When you select a policy or rule for your site, that selection is inherited by all subsites, although an owner of a subsite can break inheritance by selecting a different policy or rule. When you select a policy or rule, consider the content of any subsites below your site.</span></span>
  
## <a name="view-the-document-deletion-policies-available-in-a-site-collection"></a><span data-ttu-id="30cbf-123">Просмотр политик удаления документов, доступных в семействе веб-сайтов</span><span class="sxs-lookup"><span data-stu-id="30cbf-123">View the document deletion policies available in a site collection</span></span>

<span data-ttu-id="30cbf-p105">Организация может назначать различные политики для разных семейств веб-сайтов. На уровне семейства веб-сайтов его владелец может просматривать все политики удаления документов, доступные для такого семейства веб-сайтов. Политики могут быть доступными для шаблона семейства веб-сайтов (и, следовательно, для всех семейств веб-сайтов, созданных из этого шаблона) или для определенного семейства веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="30cbf-p105">Your organization may assign different policies to different site collections. At the site collection level, an owner of a site collection can view all of the document deletion policies that are available to that site collection. The policies may have been made available to the site collection template (and therefore all site collections created from this template) or to this specific site collection.</span></span>
  
1. <span data-ttu-id="30cbf-127">В сайте верхнего уровня в семействе веб-сайтов в правом верхнем углу выберите **Параметры** [значок шестеренки \> **].**</span><span class="sxs-lookup"><span data-stu-id="30cbf-127">In the top-level site in the site collection, in the upper-right corner, choose **Settings** [gear icon] \> **Site Settings**.</span></span>
    
2. <span data-ttu-id="30cbf-128">В разделе \> **политики удаления документов** **администрирования семейства веб-сайтов** .</span><span class="sxs-lookup"><span data-stu-id="30cbf-128">Under **Site Collection Administration** \> **Document Deletion Policies**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="30cbf-129">Ссылка **политики удаления документов** не отображается, если для семейства веб-сайтов не назначены политики.</span><span class="sxs-lookup"><span data-stu-id="30cbf-129">The **Document Deletion Policies** link won't appear unless policies have been assigned to the site collection.</span></span> <span data-ttu-id="30cbf-130">Кроме того, эта ссылка не появляется сразу после назначения политики сайту — при назначении политик **удаления документов** может потребоваться до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="30cbf-130">Also, the link doesn't appear immediately after policies have been assigned to the site — it can take up to 24 hours from when the policies are assigned to when the **Document Deletion Policies** link appears.</span></span> 
  
3. <span data-ttu-id="30cbf-131">На этой странице вы можете просмотреть такие сведения:</span><span class="sxs-lookup"><span data-stu-id="30cbf-131">On this page you can view:</span></span>
    
  - <span data-ttu-id="30cbf-p107">Текущая назначенная политика и связанные с ней правила. Выберите политику для просмотра правил в правой области.</span><span class="sxs-lookup"><span data-stu-id="30cbf-p107">The currently assigned policies and the associated rules. Select a policy to view the rules in the right pane.</span></span>
    
  - <span data-ttu-id="30cbf-134">При наличии стандартной политики в столбце **Стандартная** отображается **Да**.</span><span class="sxs-lookup"><span data-stu-id="30cbf-134">The default policy, if any, displays **Yes** in the **Default** column.</span></span> 
    
  - <span data-ttu-id="30cbf-135">Если политика назначена как **Обязательная**, под списком отображается сообщение.</span><span class="sxs-lookup"><span data-stu-id="30cbf-135">A message is displayed below the list if the policy has been assigned as **Mandatory**.</span></span>
    
<span data-ttu-id="30cbf-p108">Этот список предназначен только для просмотра, чтобы владелец сайта мог просмотреть все доступные политики и правила. Сведения о применении политики см. в разделе далее.</span><span class="sxs-lookup"><span data-stu-id="30cbf-p108">This list is view only, for the site collection owner to see all of the available policies and rules. To apply a policy, see the next section.</span></span>
  
![Просмотр политик удаления документов, назначенных семейству веб-сайтов](media/f2c0433b-2bb5-407d-a364-ae07c9627176.png)
  
## <a name="apply-or-remove-a-document-deletion-policy-for-a-site"></a><span data-ttu-id="30cbf-139">Применение или удаление политики удаления документов для сайта</span><span class="sxs-lookup"><span data-stu-id="30cbf-139">Apply or remove a document deletion policy for a site</span></span>

<span data-ttu-id="30cbf-140">Как владелец сайта или семейства веб-сайтов ваша организация может создавать политики, которые вы можете применять к своему сайту или полностью отказываться от них.</span><span class="sxs-lookup"><span data-stu-id="30cbf-140">As a site owner or site collection owner, your organization may have created policies that you can either apply to your site or opt out of entirely.</span></span>
  
1. <span data-ttu-id="30cbf-141">В правом верхнем углу выберите **настройки** [значок шестеренки] \> **Параметры сайта**.</span><span class="sxs-lookup"><span data-stu-id="30cbf-141">In the upper-right corner, choose **Settings** [gear icon] \> **Site Settings**.</span></span>
    
2. <span data-ttu-id="30cbf-142">В разделе \> **политики удаления документов** **администрирования сайта** .</span><span class="sxs-lookup"><span data-stu-id="30cbf-142">Under **Site Administration** \> **Document Deletion Policies**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="30cbf-143">Ссылка **политики удаления документов** не отображается, если для семейства веб-сайтов не назначены политики.</span><span class="sxs-lookup"><span data-stu-id="30cbf-143">The **Document Deletion Policies** link won't appear unless policies have been assigned to the site collection.</span></span> <span data-ttu-id="30cbf-144">Кроме того, эта ссылка не появляется сразу после назначения политики сайту — при назначении политик **удаления документов** может потребоваться до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="30cbf-144">Also, the link doesn't appear immediately after policies have been assigned to the site — it can take up to 24 hours from when the policies are assigned to when the **Document Deletion Policies** link appears.</span></span> 
  
3. <span data-ttu-id="30cbf-145">Выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="30cbf-145">Do one of the following:</span></span>
    
  - <span data-ttu-id="30cbf-146">**Применение политики** Выберите политику \> . Выберите правило в этой политике \> **сохранения**.</span><span class="sxs-lookup"><span data-stu-id="30cbf-146">**To apply a policy** Select a policy \> select a rule in that policy \> **Save**.</span></span>
    
    <span data-ttu-id="30cbf-p110">Только одна политика и одно правило могут быть активными в сайте одновременно. Ваша организация может предоставить несколько политик и правил, из которых можно выбрать, либо всего одну политику или правило.</span><span class="sxs-lookup"><span data-stu-id="30cbf-p110">Only one policy and one rule can be active in a site at one time. Your organization may provide several policies and rules to choose from, or only one policy or rule.</span></span>
    
    ![Выбор параметра политики](media/f7c7c055-fca7-4a4f-bb97-63e35a65beac.png)
  
  - <span data-ttu-id="30cbf-150">**Отказ от использования политики** Выберите вариант **отказаться: Do Note Delete** \> **Save**.</span><span class="sxs-lookup"><span data-stu-id="30cbf-150">**To opt out of a policy** Choose **Opt-Out: Do Note Delete** \> **Save**.</span></span>
    
    <span data-ttu-id="30cbf-151">Как владелец сайта, вы можете отказаться от политики удаления документов, если вы определили, что эта политика не применяется к контенту на вашем сайте.</span><span class="sxs-lookup"><span data-stu-id="30cbf-151">As a site owner, you can opt out of a document deletion policy if you determine that the policy isn't applicable to the content in your site.</span></span> <span data-ttu-id="30cbf-152">Однако вы не можете отказаться от политики, помеченной как **обязательная**.</span><span class="sxs-lookup"><span data-stu-id="30cbf-152">However, you can't opt out of a policy that has been marked as **Mandatory**.</span></span>
    
    ![Вариант отказаться](media/efac709c-bef7-4a02-a09d-5bc7d2b4ec63.png)
  
## <a name="document-deletion-policies-override-other-policies"></a><span data-ttu-id="30cbf-154">Политики удаления документов переопределяют другие политики</span><span class="sxs-lookup"><span data-stu-id="30cbf-154">Document deletion policies override other policies</span></span>

<span data-ttu-id="30cbf-155">На сайте могут использоваться другие политики хранения и удаления контента:</span><span class="sxs-lookup"><span data-stu-id="30cbf-155">A site may use other policies for retaining and deleting content:</span></span>
  
- <span data-ttu-id="30cbf-156">Политики типов контента для семейства веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="30cbf-156">Content type policies for the site collection.</span></span>
    
- <span data-ttu-id="30cbf-157">Политики управления сведениями для списка или библиотеки.</span><span class="sxs-lookup"><span data-stu-id="30cbf-157">Information management policies for a list or library.</span></span>
    
<span data-ttu-id="30cbf-158">Если вы применяете политику удаления документов к сайту, на котором уже используются политики типов контента или политики управления сведениями для списка или библиотеки, такие политики игнорируются, пока действует политика удаления документов.</span><span class="sxs-lookup"><span data-stu-id="30cbf-158">If you apply a document deletion policy to a site that already uses content type policies or information management policies for a list or library, those policies are ignored while the document deletion policy is in effect.</span></span> <span data-ttu-id="30cbf-159">Если другие политики игнорируются, отобразится сообщение "контент на этом сайте использует политики удаления документов".</span><span class="sxs-lookup"><span data-stu-id="30cbf-159">If other policies are ignored, you'll see the message "Content on this site uses Document Deletion Policies".</span></span>
  
<span data-ttu-id="30cbf-160">Это означает, что вы должны планировать использование на сайте исключительно политик, предназначенных для структурированного (политики управления сведениями и политики типов контента) или неструктурированного контента (политики удаления документов), но не тех и других одновременно.</span><span class="sxs-lookup"><span data-stu-id="30cbf-160">This means you should plan for a site to use only policies meant for structured content (information management policies and content type policies) or unstructured content (document deletion policies), not both.</span></span> <span data-ttu-id="30cbf-161">Если вы отказываетесь от политики удаления документов, предупреждение не отображается, а другие типы политик продолжат работу.</span><span class="sxs-lookup"><span data-stu-id="30cbf-161">If you opt out of a document deletion policy, the warning won't be displayed and other types of policies will continue to work.</span></span>
  
<span data-ttu-id="30cbf-162">Политика удаления документов не влияет на политики сайта.</span><span class="sxs-lookup"><span data-stu-id="30cbf-162">Site policies are not affected by document deletion policies.</span></span>
  
### <a name="determine-if-content-type-policies-are-being-ignored"></a><span data-ttu-id="30cbf-163">Определение того, игнорируются ли политики типов контента</span><span class="sxs-lookup"><span data-stu-id="30cbf-163">Determine if content type policies are being ignored</span></span>

<span data-ttu-id="30cbf-164">Если на сайте используются политики типов контента, и теперь вы видите это сообщение, эти политики больше не действуют.</span><span class="sxs-lookup"><span data-stu-id="30cbf-164">If your site was using content type policies and you now see this message, those policies are no longer in effect.</span></span> <span data-ttu-id="30cbf-165">Чтобы восстановить политики типов контента, можно удалить политику удаления документов с сайта, как описано выше, если есть возможность отказаться от использования.</span><span class="sxs-lookup"><span data-stu-id="30cbf-165">To restore the content type policies, you can remove the document deletion policy from your site, as described earlier, if there's an opt-out option available.</span></span> <span data-ttu-id="30cbf-166">Если нет возможности отказаться от использования, Политика удаления документов является обязательной и необходимо обратиться к сотруднику отдела соответствия требованиям в Организации.</span><span class="sxs-lookup"><span data-stu-id="30cbf-166">If there's no option to opt out, the document deletion policy is mandatory, and you need to contact the compliance officer in your organization.</span></span>
  
1. <span data-ttu-id="30cbf-167">В правом верхнем углу выберите **настройки** [значок шестеренки] \> **Параметры сайта**.</span><span class="sxs-lookup"><span data-stu-id="30cbf-167">In the upper-right corner, choose **Settings** [gear icon] \> **Site Settings**.</span></span>
    
2. <span data-ttu-id="30cbf-168">В разделе \> **шаблоны политики типа контента**" **Администрирование сайта** ".</span><span class="sxs-lookup"><span data-stu-id="30cbf-168">Under **Site Administration** \> **Content Type Policy Templates**.</span></span>
    
    ![Предупреждение на сайте, для которого используются политики удаления документов](media/4cc3d703-9aff-4695-9670-f78c291c0010.png)
  
### <a name="determine-if-information-management-policies-are-being-ignored"></a><span data-ttu-id="30cbf-170">Определение того, игнорируются ли политики управления сведениями</span><span class="sxs-lookup"><span data-stu-id="30cbf-170">Determine if information management policies are being ignored</span></span>

<span data-ttu-id="30cbf-171">Если на сайте используются политики управления сведениями, а теперь вы видите это сообщение, эти политики больше не действуют.</span><span class="sxs-lookup"><span data-stu-id="30cbf-171">If your site was using information management policies and you now see this message, those policies are no longer in effect.</span></span> <span data-ttu-id="30cbf-172">Чтобы восстановить политики управления сведениями, можно удалить политику удаления документов с сайта, как описано выше, если есть вариант отказа.</span><span class="sxs-lookup"><span data-stu-id="30cbf-172">To restore the information management policies, you can remove the document deletion policy from your site, as described earlier, if there's an opt-out option available.</span></span> <span data-ttu-id="30cbf-173">Если нет возможности отказаться от использования, Политика удаления документов является обязательной и необходимо обратиться к сотруднику отдела соответствия требованиям в Организации.</span><span class="sxs-lookup"><span data-stu-id="30cbf-173">If there's no option to opt out, the document deletion policy is mandatory, and you need to contact the compliance officer in your organization.</span></span>
  
- <span data-ttu-id="30cbf-174">Для списка или библиотеки на вкладке \> \*\*\*\* \> Библиотека ленты **Параметры** \> библиотеки управления настройками **разрешений и управления** \> **сведениями об**управлении.</span><span class="sxs-lookup"><span data-stu-id="30cbf-174">For a list or library, on the Ribbon \> **Library** tab \> **Library Settings** \> under **Permissions and Management** \> **Information Management Policy Settings**.</span></span>
    
    ![Предупреждение на сайте, для которого используются политики удаления документов](media/3f043057-a741-4cd8-a165-6d139b986064.png)
  
## <a name="see-also"></a><span data-ttu-id="30cbf-176">См. также</span><span class="sxs-lookup"><span data-stu-id="30cbf-176">See also</span></span>

[<span data-ttu-id="30cbf-177">Обзор политик удаления документов</span><span class="sxs-lookup"><span data-stu-id="30cbf-177">Overview of document deletion policies</span></span>](document-deletion-policies.md)
  
[<span data-ttu-id="30cbf-178">Создание политики удаления документов</span><span class="sxs-lookup"><span data-stu-id="30cbf-178">Create a document deletion policy</span></span>](create-a-document-deletion-policy.md)

