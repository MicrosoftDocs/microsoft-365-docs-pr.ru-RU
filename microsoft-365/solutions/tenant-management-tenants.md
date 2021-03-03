---
title: Этап 1. Microsoft 365 для корпоративных клиентов
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: Развертывание и управление одними или несколькими клиентами Microsoft 365 с возможностью размещения с несколькими гео- и перемещениями.
ms.openlocfilehash: 4d9bd685fce6fb2f11b8e17bebae6460e0c10bd2
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406388"
---
# <a name="step-1-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="6882e-104">Этап 1.</span><span class="sxs-lookup"><span data-stu-id="6882e-104">Step 1.</span></span> <span data-ttu-id="6882e-105">Microsoft 365 для корпоративных клиентов</span><span class="sxs-lookup"><span data-stu-id="6882e-105">Your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="6882e-106">Одно из первых решений клиента — это количество клиентов.</span><span class="sxs-lookup"><span data-stu-id="6882e-106">One of your first tenant decisions is how many to have.</span></span> <span data-ttu-id="6882e-107">Каждый клиент Microsoft 365 отличается, уникален и отделен от всех других клиентов Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6882e-107">Each Microsoft 365 tenant is distinct, unique, and separate from all other Microsoft 365 tenants.</span></span> <span data-ttu-id="6882e-108">Соответствующий клиент Azure AD также отличается, уникален и отличается от всех остальных клиентов Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6882e-108">It’s corresponding Azure AD tenant is also distinct, unique, and separate from all other Microsoft 365 tenants.</span></span>

## <a name="single-tenant"></a><span data-ttu-id="6882e-109">Единый клиент</span><span class="sxs-lookup"><span data-stu-id="6882e-109">Single tenant</span></span>
<span data-ttu-id="6882e-110">Наличие одного клиента упрощает многие аспекты использования Microsoft 365 в организации.</span><span class="sxs-lookup"><span data-stu-id="6882e-110">Having a single tenant simplifies many aspects of your organization’s use of Microsoft 365.</span></span> <span data-ttu-id="6882e-111">Один клиент означает одного клиента Azure AD с одним набором учетных записей, групп и политик.</span><span class="sxs-lookup"><span data-stu-id="6882e-111">A single tenant means a single Azure AD tenant with a single set of accounts, groups, and policies.</span></span> <span data-ttu-id="6882e-112">Разрешения и совместное использование ресурсов в организации можно сделать с помощью этого центрального поставщика удостоверений.</span><span class="sxs-lookup"><span data-stu-id="6882e-112">Permissions and sharing of resources across your organization can be done through this central identity provider.</span></span>

<span data-ttu-id="6882e-113">Один клиент предоставляет пользователям наиболее богатые функцией и упрощают совместную работу и производительность.</span><span class="sxs-lookup"><span data-stu-id="6882e-113">A single tenant provides the most feature-rich and simplified collaboration and productivity experience for your users.</span></span>

<span data-ttu-id="6882e-114">Вот пример расположения по умолчанию и клиента Azure AD клиента Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6882e-114">Here is an example showing the default location and Azure AD tenant of a Microsoft 365 tenant.</span></span>

![Один клиент Microsoft 365 с клиентом Azure AD](../media/tenant-management-overview/tenant-management-example-tenant.png)

## <a name="multiple-tenants"></a><span data-ttu-id="6882e-116">Несколько клиентов</span><span class="sxs-lookup"><span data-stu-id="6882e-116">Multiple tenants</span></span>

<span data-ttu-id="6882e-117">Существует множество причин, по которым в организации может быть несколько клиентов:</span><span class="sxs-lookup"><span data-stu-id="6882e-117">There are many reasons why your organization could have multiple tenants:</span></span>

- <span data-ttu-id="6882e-118">Административная изоляци</span><span class="sxs-lookup"><span data-stu-id="6882e-118">Administrative isolation</span></span>
- <span data-ttu-id="6882e-119">Децентрализованная ИТ-система</span><span class="sxs-lookup"><span data-stu-id="6882e-119">Decentralized IT</span></span>
- <span data-ttu-id="6882e-120">Исторические решения</span><span class="sxs-lookup"><span data-stu-id="6882e-120">Historical decisions</span></span>
- <span data-ttu-id="6882e-121">Слияния, приобретения или отгрузки</span><span class="sxs-lookup"><span data-stu-id="6882e-121">Mergers, acquisitions, or divestitures</span></span>
- <span data-ttu-id="6882e-122">Четкое разделение брендинга для организаций конгломератов</span><span class="sxs-lookup"><span data-stu-id="6882e-122">Clear separation of branding for conglomerate organizations</span></span>
- <span data-ttu-id="6882e-123">Клиенты предварительного производства, тестирования или "песочницы"</span><span class="sxs-lookup"><span data-stu-id="6882e-123">Pre-production, test, or sandbox tenants</span></span>

<span data-ttu-id="6882e-124">Вот пример организации с двумя арендаторами (Tenant A и Tenant B) в одном и том же геоцентре данных по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6882e-124">Here is an example of an organization that has two tenants (Tenant A and Tenant B) in the same default datacenter geo.</span></span> <span data-ttu-id="6882e-125">Каждый клиент в качестве отдельного клиента Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6882e-125">Each tenant as a separate Azure AD tenant.</span></span>

![Несколько клиентов Microsoft 365 с собственными клиентами Azure AD](../media/tenant-management-overview/tenant-management-example-multi-tenant.png)

<span data-ttu-id="6882e-127">Если у вас несколько клиентов, существуют ограничения и дополнительные соображения при управлении ими и предоставлении услуг пользователям.</span><span class="sxs-lookup"><span data-stu-id="6882e-127">When you have multiple tenants, there are restrictions and additional considerations when managing them and providing services to your users.</span></span>

### <a name="inter-tenant-collaboration"></a><span data-ttu-id="6882e-128">Взаимодействие между клиентами</span><span class="sxs-lookup"><span data-stu-id="6882e-128">Inter-tenant collaboration</span></span>

<span data-ttu-id="6882e-129">Если вы хотите, чтобы пользователи могли более эффективно взаимодействовать с различными клиентами Microsoft 365 безопасным образом, варианты совместной работы между клиентами включают использование центрального расположения для файлов и бесед, совместное использование календарей, использование вызовов обмена мгновенными данными, аудио- и видеосвязи и обеспечение доступа к ресурсам и приложениям.</span><span class="sxs-lookup"><span data-stu-id="6882e-129">If you want your users to collaborate more effectively across different Microsoft 365 tenants in a secure manner, inter-tenant collaboration options include using a central location for files and conversations, sharing calendars, using IM, audio/video calls for communication, and securing access to resources and applications.</span></span>

<span data-ttu-id="6882e-130">Дополнительные сведения см. в совместной работе [между клиентами Microsoft 365.](../enterprise/microsoft-365-inter-tenant-collaboration.md)</span><span class="sxs-lookup"><span data-stu-id="6882e-130">For more information, see [Microsoft 365 inter-tenant collaboration](../enterprise/microsoft-365-inter-tenant-collaboration.md).</span></span>

### <a name="cross-tenant-mailbox-migration-preview"></a><span data-ttu-id="6882e-131">Миграция почтовых ящиков с перекрестным клиентом (предварительный просмотр)</span><span class="sxs-lookup"><span data-stu-id="6882e-131">Cross-tenant mailbox migration (preview)</span></span>

<span data-ttu-id="6882e-132">Перед перекрестной миграцией почтовых ящиков клиента (в предварительном режиме) при перемещении почтовых ящиков Exchange Online между клиентами необходимо полностью отключить почтовый ящик пользователя от текущего клиента (клиента-источника) к локальному, а затем к новому клиенту (целевому клиенту).</span><span class="sxs-lookup"><span data-stu-id="6882e-132">Prior to cross-tenant mailbox migration (in preview), when moving Exchange Online mailboxes between tenants, you have to completely offboard a user mailbox from their current tenant (the source tenant) to on-premises and then onboard them to a new tenant (the target tenant).</span></span> <span data-ttu-id="6882e-133">С помощью новой функции миграции почтовых ящиков между клиентами администраторы клиентов в исходных и целевых клиентах могут перемещать почтовые ящики между арендаторами с минимальными зависимостями инфраструктуры в локальной системе.</span><span class="sxs-lookup"><span data-stu-id="6882e-133">With the new cross-tenant mailbox migration feature, tenant administrators in both source and target tenants can move mailboxes between the tenants with minimal infrastructure dependencies in their on-premises systems.</span></span> <span data-ttu-id="6882e-134">Это устраняет необходимость в бортовых и бортовых почтовых ящиках.</span><span class="sxs-lookup"><span data-stu-id="6882e-134">This removes the need to off-board and onboard mailboxes.</span></span>

<span data-ttu-id="6882e-135">Вот два примера клиентов и их почтовых ящиков перед миграцией почтовых ящиков между клиентом.</span><span class="sxs-lookup"><span data-stu-id="6882e-135">Here are two example tenants and their mailboxes before cross-tenant mailbox migration.</span></span>

![Несколько клиентов Microsoft 365 и их почтовые ящики](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-before.png)

<span data-ttu-id="6882e-137">На этой иллюстрации два отдельных клиента имеют собственные домены и набор почтовых ящиков Exchange.</span><span class="sxs-lookup"><span data-stu-id="6882e-137">In this illustration, two separate tenants have their own domains and set of Exchange mailboxes.</span></span>

<span data-ttu-id="6882e-138">Вот целевой клиент (Tenant A) после миграции почтовых ящиков между клиентом.</span><span class="sxs-lookup"><span data-stu-id="6882e-138">Here is the target tenant (Tenant A) after cross-tenant mailbox migration.</span></span>

![Целевой клиент после миграции почтовых ящиков между клиентами](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-after.png)

<span data-ttu-id="6882e-140">На этом рисунке один клиент имеет как домены, так и оба набора почтовых ящиков Exchange.</span><span class="sxs-lookup"><span data-stu-id="6882e-140">In this illustration, a single tenant has both domains and both sets of Exchange mailboxes.</span></span>

<span data-ttu-id="6882e-141">Дополнительные сведения см. в [перекрестной миграции почтовых ящиков клиента.](../enterprise/cross-tenant-mailbox-migration.md)</span><span class="sxs-lookup"><span data-stu-id="6882e-141">For more information, see [Cross-tenant mailbox migration](../enterprise/cross-tenant-mailbox-migration.md).</span></span>

### <a name="tenant-to-tenant-migrations"></a><span data-ttu-id="6882e-142">Миграция между клиентами</span><span class="sxs-lookup"><span data-stu-id="6882e-142">Tenant-to-tenant migrations</span></span>

<span data-ttu-id="6882e-143">Существует несколько архитектурных подходов для слияний, приобретений, сделок и других сценариев, которые могут привести к переносу существующего клиента Microsoft 365 в нового клиента.</span><span class="sxs-lookup"><span data-stu-id="6882e-143">There are several architectural approaches for mergers, acquisitions, divestitures, and other scenarios that might lead you to migrate an existing Microsoft 365 tenant to a new tenant.</span></span> 

<span data-ttu-id="6882e-144">Подробные сведения см. в описании миграции клиента от клиента к арендатору в [Microsoft 365.](../enterprise/microsoft-365-tenant-to-tenant-migrations.md)</span><span class="sxs-lookup"><span data-stu-id="6882e-144">For detailed guidance, see [Microsoft 365 tenant-to-tenant migrations](../enterprise/microsoft-365-tenant-to-tenant-migrations.md).</span></span>

## <a name="multi-geo-for-a-tenant"></a><span data-ttu-id="6882e-145">Multi-Geo для клиента</span><span class="sxs-lookup"><span data-stu-id="6882e-145">Multi-Geo for a tenant</span></span>

<span data-ttu-id="6882e-146">С помощью Microsoft 365 Multi-Geo вы можете хранить данные в других географических расположениях центра обработки данных, которые вы выбрали для удовлетворения требований оседлости данных, и в то же время разблокировать глобальное предоставление рабочим современного опыта по повышению производительности.</span><span class="sxs-lookup"><span data-stu-id="6882e-146">With Microsoft 365 Multi-Geo, you can provision and store data at rest in the other datacenter geo locations that you've chosen to meet data residency requirements, and at the same time unlock your global rollout of modern productivity experiences to your workers.</span></span>

<span data-ttu-id="6882e-147">В среде Multi-Geo клиент Microsoft 365 состоит из расположения по умолчанию или центра, где изначально была создана подписка microsoft 365, а также одно или несколько спутниковых расположений.</span><span class="sxs-lookup"><span data-stu-id="6882e-147">In a Multi-Geo environment, your Microsoft 365 tenant consists of a default or central location where your Microsoft 365 subscription was originally created and one or more satellite locations.</span></span> <span data-ttu-id="6882e-148">В клиенте с несколькими географическими данными сведения о географических расположениях, группах и сведениях пользователей освояются в глобальном клиенте Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6882e-148">In a multi-geo tenant, the information about geo locations, groups, and user information is mastered in a global Azure AD tenant.</span></span> <span data-ttu-id="6882e-149">Поскольку сведения об клиентах освояются централизованно и синхронизируются в каждом географическом расположении, опыт совместной работы с кем-либо из вашей компании передается по всем расположениям.</span><span class="sxs-lookup"><span data-stu-id="6882e-149">Because your tenant information is mastered centrally and synchronized into each geo location, collaboration experiences involving anyone from your company are shared across the locations.</span></span>

<span data-ttu-id="6882e-150">Вот пример организации, которая имеет свое расположение по умолчанию в Европе и спутниковое расположение в Северной Америке.</span><span class="sxs-lookup"><span data-stu-id="6882e-150">Here is an example of an organization that has its default location in Europe and a satellite location in North America.</span></span> <span data-ttu-id="6882e-151">Оба расположения имеют один и тот же глобальный клиент Azure AD для одного клиента Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6882e-151">Both locations share the same global Azure AD tenant for the single Microsoft 365 tenant.</span></span>

![Пример клиента с несколькими geo Microsoft 365](../media/tenant-management-overview/tenant-management-example-multi-geo.png)

<span data-ttu-id="6882e-153">Дополнительные сведения см. на странице [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="6882e-153">For more information, see [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md).</span></span>

## <a name="moving-core-data-to-a-new-datacenter-geo"></a><span data-ttu-id="6882e-154">Перемещение основных данных в новый геоцентр обработки данных</span><span class="sxs-lookup"><span data-stu-id="6882e-154">Moving core data to a new datacenter geo</span></span>

<span data-ttu-id="6882e-155">Корпорация Майкрософт продолжает открывать новые геоцентры центра обработки данных для служб Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6882e-155">Microsoft continues to open new datacenter geos for Microsoft 365 services.</span></span> <span data-ttu-id="6882e-156">Эти новые геоцентры данных добавляют мощности и вычислительные ресурсы для поддержки текущего спроса клиентов и роста использования.</span><span class="sxs-lookup"><span data-stu-id="6882e-156">These new datacenter geos add capacity and compute resources to support our ongoing customer demand and usage growth.</span></span> <span data-ttu-id="6882e-157">Кроме того, новые геоцентры центра обработки данных предоставляют резидентство данных для основных данных клиентов.</span><span class="sxs-lookup"><span data-stu-id="6882e-157">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="6882e-158">Несмотря на то, что открытие нового геоцентра данных не влияет на вас и основные данные, хранимые в уже существующем геоцентре данных, Корпорация Майкрософт позволяет запрашивать ранний перенос основных данных клиентов организации в остальное время в новый геоцентр обработки данных.</span><span class="sxs-lookup"><span data-stu-id="6882e-158">Although opening a new datacenter geo does not impact you and your core data stored in an already existing datacenter geo, Microsoft allows you to request an early migration of your organization's core customer data at rest to a new datacenter geo.</span></span>

<span data-ttu-id="6882e-159">Вот пример, в котором клиент Microsoft 365 был перемещен из центра обработки данных Европейского союза (ЕС) в центр данных, расположенный в Соединенном Королевстве (Великобритания).</span><span class="sxs-lookup"><span data-stu-id="6882e-159">Here is an example in which a Microsoft 365 tenant was moved from the European Union (EU) datacenter geo to the one located in the United Kingdom (UK).</span></span>

![Пример перемещения клиента Microsoft 365 между геоцентром данных](../media/tenant-management-overview/tenant-management-example-tenant-move.png)

<span data-ttu-id="6882e-161">Дополнительные сведения см. в дополнительных сведениях о перемещении основных данных в новые геоцентры центра обработки данных Microsoft [365.](../enterprise/moving-data-to-new-datacenter-geos.md)</span><span class="sxs-lookup"><span data-stu-id="6882e-161">For more information, see [Moving core data to new Microsoft 365 datacenter geos](../enterprise/moving-data-to-new-datacenter-geos.md).</span></span>

## <a name="products-and-licenses-for-a-tenant"></a><span data-ttu-id="6882e-162">Продукты и лицензии для клиента</span><span class="sxs-lookup"><span data-stu-id="6882e-162">Products and licenses for a tenant</span></span>

<span data-ttu-id="6882e-163">Клиент Microsoft 365 создается при покупке первого продукта, например Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="6882e-163">Your Microsoft 365 tenant gets created when you purchase your first product, such as Microsoft 365 E3.</span></span> <span data-ttu-id="6882e-164">Наряду с продуктом имеются лицензии, с которых взимается ежемесячная или годовая плата.</span><span class="sxs-lookup"><span data-stu-id="6882e-164">Along with the product are licenses, which are charged a monthly or annual fee.</span></span> <span data-ttu-id="6882e-165">Затем администратор назначает доступную лицензию от одного из ваших продуктов учетной записи пользователя непосредственно или через членство в группе.</span><span class="sxs-lookup"><span data-stu-id="6882e-165">An administrator then assigns an available license from one of your products to a user account, either directly or through group membership.</span></span> <span data-ttu-id="6882e-166">В зависимости от бизнес-потребностей организации у вас может быть набор продуктов, каждый из которых имеет собственный пул лицензий.</span><span class="sxs-lookup"><span data-stu-id="6882e-166">Depending on your organization's business needs, you might have a set of products, each with their own pool of licenses.</span></span> 

<span data-ttu-id="6882e-167">Определение набора продуктов и количества лицензий для каждого из них требует определенного планирования:</span><span class="sxs-lookup"><span data-stu-id="6882e-167">Determining the set of products and the number of licenses for each requires some planning to:</span></span>

- <span data-ttu-id="6882e-168">Убедитесь, что у вас достаточно лицензий для учетных записей пользователей, которые нуждаются в расширенных функций.</span><span class="sxs-lookup"><span data-stu-id="6882e-168">Ensure you have enough licenses for the user accounts that need advanced features.</span></span>
- <span data-ttu-id="6882e-169">Запретить вам убегать от лицензий или иметь слишком много ненаписаных лицензий на основе изменений в штатном расписыве в организации.</span><span class="sxs-lookup"><span data-stu-id="6882e-169">Prevent you from running out of licenses or having too many unassigned licenses, based on changes in staffing at your organization.</span></span>


## <a name="results-of-step-1"></a><span data-ttu-id="6882e-170">Результаты этапа 1</span><span class="sxs-lookup"><span data-stu-id="6882e-170">Results of Step 1</span></span>

<span data-ttu-id="6882e-171">Для клиента Microsoft 365 для корпоративных клиентов вы определили:</span><span class="sxs-lookup"><span data-stu-id="6882e-171">For your Microsoft 365 for enterprise tenants, you have determined:</span></span>

- <span data-ttu-id="6882e-172">Сколько клиентов у вас есть или требуется.</span><span class="sxs-lookup"><span data-stu-id="6882e-172">How many tenants you have or need.</span></span>
- <span data-ttu-id="6882e-173">Для каждого клиента, какие продукты и лицензии необходимо приобрести.</span><span class="sxs-lookup"><span data-stu-id="6882e-173">For each tenant, which products and licenses must be purchased.</span></span>
- <span data-ttu-id="6882e-174">Должен ли клиент быть multi-Geo, чтобы соответствовать требованиям оседлости данных.</span><span class="sxs-lookup"><span data-stu-id="6882e-174">Whether a tenant needs to be Multi-Geo to comply with data residency requirements.</span></span>
- <span data-ttu-id="6882e-175">Необходимо ли настроить совместную работу между арендаторами.</span><span class="sxs-lookup"><span data-stu-id="6882e-175">Whether you need to set up inter-tenant collaboration.</span></span>
- <span data-ttu-id="6882e-176">Необходимо ли перенести одного клиента на другой.</span><span class="sxs-lookup"><span data-stu-id="6882e-176">Whether you need to migrate one tenant to another.</span></span>
- <span data-ttu-id="6882e-177">Необходимо ли переместить основные данные из одного центра обработки данных в новый.</span><span class="sxs-lookup"><span data-stu-id="6882e-177">Whether you need to move core data from one datacenter geo to new one.</span></span>

<span data-ttu-id="6882e-178">Вот пример нового клиента.</span><span class="sxs-lookup"><span data-stu-id="6882e-178">Here is an example of a new tenant.</span></span>

![Пример нового клиента](../media/tenant-management-overview/tenant-management-tenant-build-step1.png)

<span data-ttu-id="6882e-180">На этой иллюстрации у клиента есть:</span><span class="sxs-lookup"><span data-stu-id="6882e-180">In this illustration, the tenant has:</span></span>

- <span data-ttu-id="6882e-181">Расположение по умолчанию, соответствующее геоцентру данных Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6882e-181">A default location corresponding to a Microsoft 365 datacenter geo.</span></span>
- <span data-ttu-id="6882e-182">Набор продуктов и лицензий.</span><span class="sxs-lookup"><span data-stu-id="6882e-182">A set of products and licenses.</span></span>
- <span data-ttu-id="6882e-183">Набор приложений облачной производительности, некоторые из которых специфично для продуктов.</span><span class="sxs-lookup"><span data-stu-id="6882e-183">The set of cloud productivity apps, some of which are specific to products.</span></span>
- <span data-ttu-id="6882e-184">Клиент Azure AD, содержащий глобальные учетные записи администратора и начальное доменное имя DNS.</span><span class="sxs-lookup"><span data-stu-id="6882e-184">An Azure AD tenant that contains global administrator accounts and an initial DNS domain name.</span></span>

<span data-ttu-id="6882e-185">При переходе к дополнительным шагам этого решения мы создам эту фигуру.</span><span class="sxs-lookup"><span data-stu-id="6882e-185">As we move through the additional steps of this solution, we will build out this figure.</span></span>

## <a name="ongoing-maintenance-for-tenants"></a><span data-ttu-id="6882e-186">Текущее обслуживание клиентов</span><span class="sxs-lookup"><span data-stu-id="6882e-186">Ongoing maintenance for tenants</span></span>

<span data-ttu-id="6882e-187">На постоянной основе может потребоваться:</span><span class="sxs-lookup"><span data-stu-id="6882e-187">On an ongoing basis, you might need to:</span></span>

- <span data-ttu-id="6882e-188">Добавьте нового клиента.</span><span class="sxs-lookup"><span data-stu-id="6882e-188">Add a new tenant.</span></span>
- <span data-ttu-id="6882e-189">Добавьте новые продукты в клиента с начальным числом лицензий.</span><span class="sxs-lookup"><span data-stu-id="6882e-189">Add new products to a tenant with an initial number of licenses.</span></span>
- <span data-ttu-id="6882e-190">Измените набор лицензий для продукта в клиенте, чтобы изменить требования к персоналу.</span><span class="sxs-lookup"><span data-stu-id="6882e-190">Change the set of licenses for a product in a tenant to adjust for changing staff requirements.</span></span>
- <span data-ttu-id="6882e-191">Переместите основные данные из клиента в новое геолокационное расположение центра обработки данных.</span><span class="sxs-lookup"><span data-stu-id="6882e-191">Move your core data from a tenant to a new datacenter geo location.</span></span>
- <span data-ttu-id="6882e-192">Добавьте Multi-Geo для требований к оседлости данных.</span><span class="sxs-lookup"><span data-stu-id="6882e-192">Add Multi-Geo for data residency requirements.</span></span>
- <span data-ttu-id="6882e-193">Настройка междометной совместной работы.</span><span class="sxs-lookup"><span data-stu-id="6882e-193">Set up inter-tenant collaboration.</span></span>

## <a name="next-step"></a><span data-ttu-id="6882e-194">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="6882e-194">Next step</span></span>

<span data-ttu-id="6882e-195">[![Шаг 2. Оптимизация клиента для сети для доступа](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)</span><span class="sxs-lookup"><span data-stu-id="6882e-195">[![Step 2. Optimize your tenant for network for access](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)</span></span>

<span data-ttu-id="6882e-196">Продолжайте работу [с сетью,](tenant-management-networking.md) чтобы обеспечить оптимальную сеть от сотрудников до облачных служб Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6882e-196">Continue with [networking](tenant-management-networking.md) to provide optimal networking from your workers to Microsoft 365 cloud services.</span></span>
