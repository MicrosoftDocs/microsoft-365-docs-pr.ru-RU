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
ms.openlocfilehash: 3f5228c26cc4e12c129a57e2141e3eea50d029a2
ms.sourcegitcommit: 1eecd7b127462585c35b0c96a179d37db45f6013
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "37342962"
---
# <a name="apply-or-remove-a-document-deletion-policy-for-a-site"></a><span data-ttu-id="929b0-105">Применение или удаление политики удаления документов для сайта</span><span class="sxs-lookup"><span data-stu-id="929b0-105">Apply or remove a document deletion policy for a site</span></span>

<span data-ttu-id="929b0-p102">Организациям часто приходится хранить документы в течение определенного периода времени в соответствии с нормативными, законодательными или другими требованиями. Однако хранение документов дольше, чем требуется, может привести к возникновению юридических рисков. Поэтому организации могут создать политику удаления документов для сайта. Например, общие бизнес-документы могут в обязательном порядке удаляться через пять лет после их создания.</span><span class="sxs-lookup"><span data-stu-id="929b0-p102">Organizations are often subject to compliance, legal, or other regulations that require them to retain documents for a certain period of time. However, retaining documents for longer than required can expose the organization to legal risk. For this reason, your organization may have created a document deletion policy for your site — for example, general business documents might be required to be deleted five years after they were created.</span></span>
  
<span data-ttu-id="929b0-109">В зависимости от организации существуют такие политики удаления документов:</span><span class="sxs-lookup"><span data-stu-id="929b0-109">Depending on your organization, a document deletion policy might be:</span></span>
  
- <span data-ttu-id="929b0-110">**Обязательный** параметр Владелец сайта не может отказаться от обязательной политики, которая автоматически применяется к сайту.</span><span class="sxs-lookup"><span data-stu-id="929b0-110">**Mandatory** A site owner can't opt out of a mandatory policy, which is automatically applied to the site.</span></span> 
    
- <span data-ttu-id="929b0-111">**Стандартная** Стандартная политика автоматически применяется к сайту, но его владелец может:</span><span class="sxs-lookup"><span data-stu-id="929b0-111">**Default** A default policy is automatically applied to a site, but a site owner can:</span></span> 
    
  - <span data-ttu-id="929b0-112">Выбрать другую политику, если она доступна.</span><span class="sxs-lookup"><span data-stu-id="929b0-112">Choose another policy if available.</span></span>
    
  - <span data-ttu-id="929b0-113">Полностью отказаться от политики, если она не соответствует контенту сайта.</span><span class="sxs-lookup"><span data-stu-id="929b0-113">Opt out of the policy entirely if it is not relevant to the content in the site.</span></span>
    
- <span data-ttu-id="929b0-114">**Не обязательная и не стандартная** В этом случае политика не применяется к сайту автоматически, и его владелец должен применить одну из них.</span><span class="sxs-lookup"><span data-stu-id="929b0-114">**Neither mandatory nor default** In this case, no policy is automatically applied to the site, and the site owner needs to take action to apply one.</span></span> 
    
<span data-ttu-id="929b0-p103">Политика удаления документов может содержать несколько правил. Например, одно правило может предписывать удалять документы через один год после их создания, а другое правило — удалять документы через один год после последнего изменения. Если политика содержит несколько правил, вы можете выбрать то из них, которое лучше всего подходит для вашего сайта. Правило удаления будет применено ко всем библиотекам на сайте. Только одна политика и одно правило могут быть активными в сайте одновременно. Как и политика, правило может быть стандартным и применяться автоматически в случае применения политики.</span><span class="sxs-lookup"><span data-stu-id="929b0-p103">A document deletion policy may contain more than one rule — for example, one rule might say delete documents one year after they were created, but another rule might say delete documents one year after they were last modified. If a policy contains more than one rule, you can select the rule that best applies to your site. The delete rule will be applied to all libraries within the site. Only one policy and one rule can be active in a site at one time. Like a policy, a rule can be set as default, so that it is applied automatically when the policy is applied.</span></span>
  
<span data-ttu-id="929b0-p104">Наконец, политики удаления документов наследуются. Все подсайты наследуют выбранную для сайта политику или правило. Владелец подсайта может прервать наследование, выбрав другую политику или правило. Выбирая политику или правило, примите во внимание подсайты, находящиеся ниже вашего сайта.</span><span class="sxs-lookup"><span data-stu-id="929b0-p104">Finally, document deletion policies are inherited. When you select a policy or rule for your site, that selection is inherited by all subsites, although an owner of a subsite can break inheritance by selecting a different policy or rule. When you select a policy or rule, consider the content of any subsites below your site.</span></span>
  
## <a name="view-the-document-deletion-policies-available-in-a-site-collection"></a><span data-ttu-id="929b0-123">Просмотр политик удаления документов, доступных в семействе веб-сайтов</span><span class="sxs-lookup"><span data-stu-id="929b0-123">View the document deletion policies available in a site collection</span></span>

<span data-ttu-id="929b0-p105">Организация может назначать различные политики для разных семейств веб-сайтов. На уровне семейства веб-сайтов его владелец может просматривать все политики удаления документов, доступные для такого семейства веб-сайтов. Политики могут быть доступными для шаблона семейства веб-сайтов (и, следовательно, для всех семейств веб-сайтов, созданных из этого шаблона) или для определенного семейства веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="929b0-p105">Your organization may assign different policies to different site collections. At the site collection level, an owner of a site collection can view all of the document deletion policies that are available to that site collection. The policies may have been made available to the site collection template (and therefore all site collections created from this template) or to this specific site collection.</span></span>
  
1. <span data-ttu-id="929b0-127">В сайте верхнего уровня в семействе веб-сайтов в правом верхнем углу выберите **Параметры** [значок шестеренки \> **].**</span><span class="sxs-lookup"><span data-stu-id="929b0-127">In the top-level site in the site collection, in the upper-right corner, choose **Settings** [gear icon] \> **Site Settings**.</span></span>
    
2. <span data-ttu-id="929b0-128">В разделе \> **политики удаления документов** **администрирования семейства веб-сайтов** .</span><span class="sxs-lookup"><span data-stu-id="929b0-128">Under **Site Collection Administration** \> **Document Deletion Policies**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="929b0-129">Ссылка **политики удаления документов** не отображается, если для семейства веб-сайтов не назначены политики.</span><span class="sxs-lookup"><span data-stu-id="929b0-129">The **Document Deletion Policies** link won't appear unless policies have been assigned to the site collection.</span></span> <span data-ttu-id="929b0-130">Кроме того, эта ссылка не появляется сразу после назначения политики сайту — при назначении политик **удаления документов** может потребоваться до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="929b0-130">Also, the link doesn't appear immediately after policies have been assigned to the site — it can take up to 24 hours from when the policies are assigned to when the **Document Deletion Policies** link appears.</span></span> 
  
3. <span data-ttu-id="929b0-131">На этой странице вы можете просмотреть такие сведения:</span><span class="sxs-lookup"><span data-stu-id="929b0-131">On this page you can view:</span></span>
    
  - <span data-ttu-id="929b0-p107">Текущая назначенная политика и связанные с ней правила. Выберите политику для просмотра правил в правой области.</span><span class="sxs-lookup"><span data-stu-id="929b0-p107">The currently assigned policies and the associated rules. Select a policy to view the rules in the right pane.</span></span>
    
  - <span data-ttu-id="929b0-134">При наличии стандартной политики в столбце **Стандартная** отображается **Да**.</span><span class="sxs-lookup"><span data-stu-id="929b0-134">The default policy, if any, displays **Yes** in the **Default** column.</span></span> 
    
  - <span data-ttu-id="929b0-135">Если политика назначена как **Обязательная**, под списком отображается сообщение.</span><span class="sxs-lookup"><span data-stu-id="929b0-135">A message is displayed below the list if the policy has been assigned as **Mandatory**.</span></span>
    
<span data-ttu-id="929b0-p108">Этот список предназначен только для просмотра, чтобы владелец сайта мог просмотреть все доступные политики и правила. Сведения о применении политики см. в разделе далее.</span><span class="sxs-lookup"><span data-stu-id="929b0-p108">This list is view only, for the site collection owner to see all of the available policies and rules. To apply a policy, see the next section.</span></span>
  
![Просмотр политик удаления документов, назначенных семейству веб-сайтов](media/f2c0433b-2bb5-407d-a364-ae07c9627176.png)
  
## <a name="apply-or-remove-a-document-deletion-policy-for-a-site"></a><span data-ttu-id="929b0-139">Применение или удаление политики удаления документов для сайта</span><span class="sxs-lookup"><span data-stu-id="929b0-139">Apply or remove a document deletion policy for a site</span></span>

<span data-ttu-id="929b0-140">Как владелец сайта или семейства веб-сайтов ваша организация может создавать политики, которые вы можете применять к своему сайту или полностью отказываться от них.</span><span class="sxs-lookup"><span data-stu-id="929b0-140">As a site owner or site collection owner, your organization may have created policies that you can either apply to your site or opt out of entirely.</span></span>
  
1. <span data-ttu-id="929b0-141">В правом верхнем углу выберите **настройки** [значок шестеренки] \> **Параметры сайта**.</span><span class="sxs-lookup"><span data-stu-id="929b0-141">In the upper-right corner, choose **Settings** [gear icon] \> **Site Settings**.</span></span>
    
2. <span data-ttu-id="929b0-142">В разделе \> **политики удаления документов** **администрирования сайта** .</span><span class="sxs-lookup"><span data-stu-id="929b0-142">Under **Site Administration** \> **Document Deletion Policies**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="929b0-143">Ссылка **политики удаления документов** не отображается, если для семейства веб-сайтов не назначены политики.</span><span class="sxs-lookup"><span data-stu-id="929b0-143">The **Document Deletion Policies** link won't appear unless policies have been assigned to the site collection.</span></span> <span data-ttu-id="929b0-144">Кроме того, эта ссылка не появляется сразу после назначения политики сайту — при назначении политик **удаления документов** может потребоваться до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="929b0-144">Also, the link doesn't appear immediately after policies have been assigned to the site — it can take up to 24 hours from when the policies are assigned to when the **Document Deletion Policies** link appears.</span></span> 
  
3. <span data-ttu-id="929b0-145">Выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="929b0-145">Do one of the following:</span></span>
    
  - <span data-ttu-id="929b0-146">**Применение политики** Выберите политику \> . Выберите правило в этой политике \> **сохранения**.</span><span class="sxs-lookup"><span data-stu-id="929b0-146">**To apply a policy** Select a policy \> select a rule in that policy \> **Save**.</span></span>
    
    <span data-ttu-id="929b0-p110">Только одна политика и одно правило могут быть активными в сайте одновременно. Ваша организация может предоставить несколько политик и правил, из которых можно выбрать, либо всего одну политику или правило.</span><span class="sxs-lookup"><span data-stu-id="929b0-p110">Only one policy and one rule can be active in a site at one time. Your organization may provide several policies and rules to choose from, or only one policy or rule.</span></span>
    
    ![Выбор параметра политики](media/f7c7c055-fca7-4a4f-bb97-63e35a65beac.png)
  
  - <span data-ttu-id="929b0-150">**Отказ от использования политики** Выберите вариант **отказаться: Do Note Delete** \> **Save**.</span><span class="sxs-lookup"><span data-stu-id="929b0-150">**To opt out of a policy** Choose **Opt-Out: Do Note Delete** \> **Save**.</span></span>
    
    <span data-ttu-id="929b0-p111">Как владелец сайта вы можете отказаться от политики удаления документов, если определите, что такая политика неприменима к контенту вашего сайта. Однако невозможно отказаться от политики, которая помечена как **Обязательная**.</span><span class="sxs-lookup"><span data-stu-id="929b0-p111">As a site owner, you can opt out of a document deletion policy if you determine that the policy is not applicable to the content in your site. However, you cannot opt out of a policy that has been marked as **Mandatory**.</span></span>
    
    ![Вариант отказаться](media/efac709c-bef7-4a02-a09d-5bc7d2b4ec63.png)
  
## <a name="document-deletion-policies-override-other-policies"></a><span data-ttu-id="929b0-154">Политики удаления документов переопределяют другие политики</span><span class="sxs-lookup"><span data-stu-id="929b0-154">Document deletion policies override other policies</span></span>

<span data-ttu-id="929b0-155">На сайте могут использоваться другие политики хранения и удаления контента:</span><span class="sxs-lookup"><span data-stu-id="929b0-155">A site may use other policies for retaining and deleting content:</span></span>
  
- <span data-ttu-id="929b0-156">Политики типов контента для семейства веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="929b0-156">Content type policies for the site collection.</span></span>
    
- <span data-ttu-id="929b0-157">Политики управления сведениями для списка или библиотеки.</span><span class="sxs-lookup"><span data-stu-id="929b0-157">Information management policies for a list or library.</span></span>
    
<span data-ttu-id="929b0-158">Если вы применяете политику удаления документов к сайту, на котором уже используются политики типов контента или политики управления сведениями для списка или библиотеки, такие политики игнорируются, пока действует политика удаления документов.</span><span class="sxs-lookup"><span data-stu-id="929b0-158">If you apply a document deletion policy to a site that already uses content type policies or information management policies for a list or library, those policies are ignored while the document deletion policy is in effect.</span></span> <span data-ttu-id="929b0-159">Если другие политики игнорируются, отобразится сообщение "контент на этом сайте использует политики удаления документов".</span><span class="sxs-lookup"><span data-stu-id="929b0-159">If other policies are ignored, you will see the message "Content on this site uses Document Deletion Policies".</span></span>
  
<span data-ttu-id="929b0-p113">Это означает, что вы должны планировать использование на сайте исключительно политик, предназначенных для структурированного (политики управления сведениями и политики типов контента) или неструктурированного контента (политики удаления документов), но не тех и других одновременно. Если вы откажитесь от политики удаления документов, предупреждение не отобразится и другие типы политик будут продолжать работать.</span><span class="sxs-lookup"><span data-stu-id="929b0-p113">This means you should plan for a site to use only policies meant for structured content (information management policies and content type policies) or unstructured content (document deletion policies), not both. If you opt out of a document deletion policy, the warning will not be displayed and other types of policies will continue to work.</span></span>
  
<span data-ttu-id="929b0-162">Политика удаления документов не влияет на политики сайта.</span><span class="sxs-lookup"><span data-stu-id="929b0-162">Site policies are not affected by document deletion policies.</span></span>
  
### <a name="determine-if-content-type-policies-are-being-ignored"></a><span data-ttu-id="929b0-163">Определение того, игнорируются ли политики типов контента</span><span class="sxs-lookup"><span data-stu-id="929b0-163">Determine if content type policies are being ignored</span></span>

<span data-ttu-id="929b0-164">Если на сайте используются политики типов контента, и теперь вы видите это сообщение, эти политики больше не действуют.</span><span class="sxs-lookup"><span data-stu-id="929b0-164">If your site was using content type policies and you now see this message, those policies are no longer in effect.</span></span> <span data-ttu-id="929b0-165">Чтобы восстановить политики типов контента, можно удалить политику удаления документов с сайта, как описано выше, если есть возможность отказаться от использования.</span><span class="sxs-lookup"><span data-stu-id="929b0-165">To restore the content type policies, you can remove the document deletion policy from your site, as described earlier, if there's an opt-out option available.</span></span> <span data-ttu-id="929b0-166">Если нет возможности отказаться от использования, Политика удаления документов является обязательной и необходимо обратиться к сотруднику отдела соответствия требованиям в Организации.</span><span class="sxs-lookup"><span data-stu-id="929b0-166">If there's no option to opt out, the document deletion policy is mandatory, and you need to contact the compliance officer in your organization.</span></span>
  
1. <span data-ttu-id="929b0-167">В правом верхнем углу выберите **настройки** [значок шестеренки] \> **Параметры сайта**.</span><span class="sxs-lookup"><span data-stu-id="929b0-167">In the upper-right corner, choose **Settings** [gear icon] \> **Site Settings**.</span></span>
    
2. <span data-ttu-id="929b0-168">В разделе \> **шаблоны политики типа контента**" **Администрирование сайта** ".</span><span class="sxs-lookup"><span data-stu-id="929b0-168">Under **Site Administration** \> **Content Type Policy Templates**.</span></span>
    
    ![Предупреждение на сайте, для которого используются политики удаления документов](media/4cc3d703-9aff-4695-9670-f78c291c0010.png)
  
### <a name="determine-if-information-management-policies-are-being-ignored"></a><span data-ttu-id="929b0-170">Определение того, игнорируются ли политики управления сведениями</span><span class="sxs-lookup"><span data-stu-id="929b0-170">Determine if information management policies are being ignored</span></span>

<span data-ttu-id="929b0-171">Если на сайте используются политики управления сведениями, а теперь вы видите это сообщение, эти политики больше не действуют.</span><span class="sxs-lookup"><span data-stu-id="929b0-171">If your site was using information management policies and you now see this message, those policies are no longer in effect.</span></span> <span data-ttu-id="929b0-172">Чтобы восстановить политики управления сведениями, можно удалить политику удаления документов с сайта, как описано выше, если есть вариант отказа.</span><span class="sxs-lookup"><span data-stu-id="929b0-172">To restore the information management policies, you can remove the document deletion policy from your site, as described earlier, if there's an opt-out option available.</span></span> <span data-ttu-id="929b0-173">Если нет возможности отказаться от использования, Политика удаления документов является обязательной и необходимо обратиться к сотруднику отдела соответствия требованиям в Организации.</span><span class="sxs-lookup"><span data-stu-id="929b0-173">If there's no option to opt out, the document deletion policy is mandatory, and you need to contact the compliance officer in your organization.</span></span>
  
- <span data-ttu-id="929b0-174">Для списка или библиотеки на вкладке \> \*\*\*\* \> Библиотека ленты **Параметры** \> библиотеки управления настройками **разрешений и управления** \> **сведениями об**управлении.</span><span class="sxs-lookup"><span data-stu-id="929b0-174">For a list or library, on the Ribbon \> **Library** tab \> **Library Settings** \> under **Permissions and Management** \> **Information Management Policy Settings**.</span></span>
    
    ![Предупреждение на сайте, для которого используются политики удаления документов](media/3f043057-a741-4cd8-a165-6d139b986064.png)
  
## <a name="see-also"></a><span data-ttu-id="929b0-176">См. также</span><span class="sxs-lookup"><span data-stu-id="929b0-176">See also</span></span>

[<span data-ttu-id="929b0-177">Обзор политик удаления документов</span><span class="sxs-lookup"><span data-stu-id="929b0-177">Overview of document deletion policies</span></span>](document-deletion-policies.md)
  
[<span data-ttu-id="929b0-178">Создание политики удаления документов</span><span class="sxs-lookup"><span data-stu-id="929b0-178">Create a document deletion policy</span></span>](create-a-document-deletion-policy.md)

