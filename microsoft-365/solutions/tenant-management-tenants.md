---
title: Этап 1. Клиенты Microsoft 365 для предприятий
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
ms.custom:
- Ent_Solutions
description: Развертывание и управление одним или несколькими клиентами Microsoft 365 с возможностью поддержки нескольких регионов и перемещения местоположений.
ms.openlocfilehash: 567a2cb46e715ec560bf973a33ab83cfa63d403b
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908719"
---
# <a name="step-1-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="e8063-104">Этап 1.</span><span class="sxs-lookup"><span data-stu-id="e8063-104">Step 1.</span></span> <span data-ttu-id="e8063-105">Клиенты Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="e8063-105">Your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="e8063-106">Одно из первых решений клиента — количество клиентов.</span><span class="sxs-lookup"><span data-stu-id="e8063-106">One of your first tenant decisions is how many to have.</span></span> <span data-ttu-id="e8063-107">Каждый клиент Microsoft 365 является уникальным и отделен от всех остальных клиентов Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e8063-107">Each Microsoft 365 tenant is distinct, unique, and separate from all other Microsoft 365 tenants.</span></span> <span data-ttu-id="e8063-108">Соответствующий клиент Azure AD также отличается, уникален и отделен от всех остальных клиентов Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e8063-108">It’s corresponding Azure AD tenant is also distinct, unique, and separate from all other Microsoft 365 tenants.</span></span>

## <a name="single-tenant"></a><span data-ttu-id="e8063-109">Один клиент</span><span class="sxs-lookup"><span data-stu-id="e8063-109">Single tenant</span></span>
<span data-ttu-id="e8063-110">Наличие одного клиента упрощает многие аспекты использования Microsoft 365 в организации.</span><span class="sxs-lookup"><span data-stu-id="e8063-110">Having a single tenant simplifies many aspects of your organization’s use of Microsoft 365.</span></span> <span data-ttu-id="e8063-111">Под одним клиентом подразумевается один клиент Azure AD с одним набором учетных записей, групп и политик.</span><span class="sxs-lookup"><span data-stu-id="e8063-111">A single tenant means a single Azure AD tenant with a single set of accounts, groups, and policies.</span></span> <span data-ttu-id="e8063-112">Разрешения и общий доступ к ресурсам в организации можно получить с помощью этого центрального поставщика удостоверений.</span><span class="sxs-lookup"><span data-stu-id="e8063-112">Permissions and sharing of resources across your organization can be done through this central identity provider.</span></span>

<span data-ttu-id="e8063-113">Один клиент предоставляет пользователям наиболее богатые функции и упрощает совместную работу и производительность.</span><span class="sxs-lookup"><span data-stu-id="e8063-113">A single tenant provides the most feature-rich and simplified collaboration and productivity experience for your users.</span></span>

<span data-ttu-id="e8063-114">Ниже показан пример расположения по умолчанию и клиента Azure AD клиента Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e8063-114">Here is an example showing the default location and Azure AD tenant of a Microsoft 365 tenant.</span></span>

![Один клиент Microsoft 365 с клиентом Azure AD](../media/tenant-management-overview/tenant-management-example-tenant.png)

## <a name="multiple-tenants"></a><span data-ttu-id="e8063-116">Несколько клиентов</span><span class="sxs-lookup"><span data-stu-id="e8063-116">Multiple tenants</span></span>

<span data-ttu-id="e8063-117">Существует множество причин, по которым в организации может быть несколько клиентов:</span><span class="sxs-lookup"><span data-stu-id="e8063-117">There are many reasons why your organization could have multiple tenants:</span></span>

- <span data-ttu-id="e8063-118">Административная изоляци</span><span class="sxs-lookup"><span data-stu-id="e8063-118">Administrative isolation</span></span>
- <span data-ttu-id="e8063-119">Децентрализованная ИТ-система</span><span class="sxs-lookup"><span data-stu-id="e8063-119">Decentralized IT</span></span>
- <span data-ttu-id="e8063-120">Исторические решения</span><span class="sxs-lookup"><span data-stu-id="e8063-120">Historical decisions</span></span>
- <span data-ttu-id="e8063-121">Слияния, приобретения или инквизиалы</span><span class="sxs-lookup"><span data-stu-id="e8063-121">Mergers, acquisitions, or divestitures</span></span>
- <span data-ttu-id="e8063-122">Четкое разделение фирменности для организаций-конгломератов</span><span class="sxs-lookup"><span data-stu-id="e8063-122">Clear separation of branding for conglomerate organizations</span></span>
- <span data-ttu-id="e8063-123">Предварительные, тестовые или "песочницы" клиенты</span><span class="sxs-lookup"><span data-stu-id="e8063-123">Pre-production, test, or sandbox tenants</span></span>

<span data-ttu-id="e8063-124">Вот пример организации, которая имеет два клиента (клиент A и клиент Б) в одном географическом центре обработки данных по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e8063-124">Here is an example of an organization that has two tenants (Tenant A and Tenant B) in the same default datacenter geo.</span></span> <span data-ttu-id="e8063-125">Каждый клиент в качестве отдельного клиента Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e8063-125">Each tenant as a separate Azure AD tenant.</span></span>

![Несколько клиентов Microsoft 365 с собственными клиентами Azure AD](../media/tenant-management-overview/tenant-management-example-multi-tenant.png)

<span data-ttu-id="e8063-127">Если у вас несколько клиентов, при управлении ими и предоставлении услуг пользователям существуют ограничения и дополнительные соображения.</span><span class="sxs-lookup"><span data-stu-id="e8063-127">When you have multiple tenants, there are restrictions and additional considerations when managing them and providing services to your users.</span></span>

### <a name="inter-tenant-collaboration"></a><span data-ttu-id="e8063-128">Взаимодействие между клиентами</span><span class="sxs-lookup"><span data-stu-id="e8063-128">Inter-tenant collaboration</span></span>

<span data-ttu-id="e8063-129">Чтобы обеспечить надежную совместную работу пользователей в разных клиентах Microsoft 365, можно использовать централизованное расположение для файлов и бесед, общий доступ к календарям, обмен мгновенными сообщениями, аудио- и видеозвонки для общения и обеспечение безопасности доступа к ресурсам и приложениям.</span><span class="sxs-lookup"><span data-stu-id="e8063-129">If you want your users to collaborate more effectively across different Microsoft 365 tenants in a secure manner, inter-tenant collaboration options include using a central location for files and conversations, sharing calendars, using IM, audio/video calls for communication, and securing access to resources and applications.</span></span>

<span data-ttu-id="e8063-130">Дополнительные сведения см. в [совместной работе между клиентами Microsoft 365.](../enterprise/microsoft-365-inter-tenant-collaboration.md)</span><span class="sxs-lookup"><span data-stu-id="e8063-130">For more information, see [Microsoft 365 inter-tenant collaboration](../enterprise/microsoft-365-inter-tenant-collaboration.md).</span></span>

### <a name="cross-tenant-mailbox-migration-preview"></a><span data-ttu-id="e8063-131">Миграция почтовых ящиков между клиентами (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="e8063-131">Cross-tenant mailbox migration (preview)</span></span>

<span data-ttu-id="e8063-132">Перед миграцией почтовых ящиков между клиентами (в предварительной версии) при перемещении почтовых ящиков Exchange Online между клиентами необходимо полностью отключить почтовый ящик пользователя от текущего клиента (клиента-источника) к локальному, а затем ввести их в новый клиент (целевой клиент).</span><span class="sxs-lookup"><span data-stu-id="e8063-132">Prior to cross-tenant mailbox migration (in preview), when moving Exchange Online mailboxes between tenants, you have to completely offboard a user mailbox from their current tenant (the source tenant) to on-premises and then onboard them to a new tenant (the target tenant).</span></span> <span data-ttu-id="e8063-133">С помощью новой функции миграции почтовых ящиков между клиентами администраторы клиентов в исходных и целевых клиентах могут перемещать почтовые ящики между клиентами с минимальными зависимостями инфраструктуры в своих локальной системе.</span><span class="sxs-lookup"><span data-stu-id="e8063-133">With the new cross-tenant mailbox migration feature, tenant administrators in both source and target tenants can move mailboxes between the tenants with minimal infrastructure dependencies in their on-premises systems.</span></span> <span data-ttu-id="e8063-134">Это устраняет необходимость в отходящих и входящих почтовых ящиках.</span><span class="sxs-lookup"><span data-stu-id="e8063-134">This removes the need to off-board and onboard mailboxes.</span></span>

<span data-ttu-id="e8063-135">Вот два примера клиентов и их почтовых ящиков перед миграцией почтовых ящиков между клиентами.</span><span class="sxs-lookup"><span data-stu-id="e8063-135">Here are two example tenants and their mailboxes before cross-tenant mailbox migration.</span></span>

![Несколько клиентов Microsoft 365 и их почтовые ящики](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-before.png)

<span data-ttu-id="e8063-137">На этой иллюстрации два отдельных клиента имеют собственные домены и набор почтовых ящиков Exchange.</span><span class="sxs-lookup"><span data-stu-id="e8063-137">In this illustration, two separate tenants have their own domains and set of Exchange mailboxes.</span></span>

<span data-ttu-id="e8063-138">Вот целевой клиент (клиент А) после миграции почтовых ящиков между клиентами.</span><span class="sxs-lookup"><span data-stu-id="e8063-138">Here is the target tenant (Tenant A) after cross-tenant mailbox migration.</span></span>

![Целевой клиент после миграции почтовых ящиков между клиентами](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-after.png)

<span data-ttu-id="e8063-140">На этом рисунке у одного клиента есть как домены, так и оба набора почтовых ящиков Exchange.</span><span class="sxs-lookup"><span data-stu-id="e8063-140">In this illustration, a single tenant has both domains and both sets of Exchange mailboxes.</span></span>

<span data-ttu-id="e8063-141">Дополнительные сведения см. в [перекрестной миграции почтовых ящиков.](../enterprise/cross-tenant-mailbox-migration.md)</span><span class="sxs-lookup"><span data-stu-id="e8063-141">For more information, see [Cross-tenant mailbox migration](../enterprise/cross-tenant-mailbox-migration.md).</span></span>

### <a name="tenant-to-tenant-migrations"></a><span data-ttu-id="e8063-142">Миграция между клиентами</span><span class="sxs-lookup"><span data-stu-id="e8063-142">Tenant-to-tenant migrations</span></span>

<span data-ttu-id="e8063-143">Существует несколько архитектурных подходов для слияний, приобретений, сделок и других сценариев, которые могут привести к переносу существующего клиента Microsoft 365 в новый.</span><span class="sxs-lookup"><span data-stu-id="e8063-143">There are several architectural approaches for mergers, acquisitions, divestitures, and other scenarios that might lead you to migrate an existing Microsoft 365 tenant to a new tenant.</span></span> 

<span data-ttu-id="e8063-144">Подробные инструкции см. в описании миграции между клиентами [Microsoft 365.](../enterprise/microsoft-365-tenant-to-tenant-migrations.md)</span><span class="sxs-lookup"><span data-stu-id="e8063-144">For detailed guidance, see [Microsoft 365 tenant-to-tenant migrations](../enterprise/microsoft-365-tenant-to-tenant-migrations.md).</span></span>

## <a name="multi-geo-for-a-tenant"></a><span data-ttu-id="e8063-145">Multi-Geo для клиента</span><span class="sxs-lookup"><span data-stu-id="e8063-145">Multi-Geo for a tenant</span></span>

<span data-ttu-id="e8063-146">С помощью Microsoft 365 с несколькими регионами вы можете хранить неачные данные в других географических расположениях центров обработки данных, выбранных для удовлетворения требований к месту расположения данных, и в то же время разблокировать глобальное предоставление современных рабочих мест сотрудникам.</span><span class="sxs-lookup"><span data-stu-id="e8063-146">With Microsoft 365 Multi-Geo, you can provision and store data at rest in the other datacenter geo locations that you've chosen to meet data residency requirements, and at the same time unlock your global rollout of modern productivity experiences to your workers.</span></span>

<span data-ttu-id="e8063-147">В среде с несколькими регионами клиент Microsoft 365 состоит из расположения по умолчанию или центрального расположения, в котором изначально была создана подписка на Microsoft 365, и одного или нескольких дополнительных расположений.</span><span class="sxs-lookup"><span data-stu-id="e8063-147">In a Multi-Geo environment, your Microsoft 365 tenant consists of a default or central location where your Microsoft 365 subscription was originally created and one or more satellite locations.</span></span> <span data-ttu-id="e8063-148">В клиенте с несколькими регионами сведения о географических расположениях, группах и пользовательских данных освояются в глобальном клиенте Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e8063-148">In a multi-geo tenant, the information about geo locations, groups, and user information is mastered in a global Azure AD tenant.</span></span> <span data-ttu-id="e8063-149">Так как сведения о клиенте централизованно и синхронизируются в каждом географическом расположении, взаимодействие совместной работы с любыми клиентами из вашей компании совместно работает в разных расположениях.</span><span class="sxs-lookup"><span data-stu-id="e8063-149">Because your tenant information is mastered centrally and synchronized into each geo location, collaboration experiences involving anyone from your company are shared across the locations.</span></span>

<span data-ttu-id="e8063-150">Вот пример организации с расположением по умолчанию в Европе и с дополнительным расположением в Северной Америке.</span><span class="sxs-lookup"><span data-stu-id="e8063-150">Here is an example of an organization that has its default location in Europe and a satellite location in North America.</span></span> <span data-ttu-id="e8063-151">В обоих расположениях имеется один глобальный клиент Azure AD для одного клиента Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e8063-151">Both locations share the same global Azure AD tenant for the single Microsoft 365 tenant.</span></span>

![Пример клиента Microsoft 365 с несколькими географическими службами](../media/tenant-management-overview/tenant-management-example-multi-geo.png)

<span data-ttu-id="e8063-153">Дополнительные сведения см. на странице [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="e8063-153">For more information, see [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md).</span></span>

## <a name="moving-core-data-to-a-new-datacenter-geo"></a><span data-ttu-id="e8063-154">Перемещение основных данных в новый геоцентр данных</span><span class="sxs-lookup"><span data-stu-id="e8063-154">Moving core data to a new datacenter geo</span></span>

<span data-ttu-id="e8063-155">Корпорация Майкрософт продолжает открывать новые геоцентры для служб Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e8063-155">Microsoft continues to open new datacenter geos for Microsoft 365 services.</span></span> <span data-ttu-id="e8063-156">Эти новые геостойки центра обработки данных добавляют мощности и вычислительные ресурсы для поддержки текущего роста потребностей клиентов и роста использования.</span><span class="sxs-lookup"><span data-stu-id="e8063-156">These new datacenter geos add capacity and compute resources to support our ongoing customer demand and usage growth.</span></span> <span data-ttu-id="e8063-157">Кроме того, новые геополии центра обработки данных обеспечивают географическое место хранения данных для основных данных клиента.</span><span class="sxs-lookup"><span data-stu-id="e8063-157">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="e8063-158">Хотя открытие нового географического центра обработки данных не влияет на вас и основные данные, хранимые в уже существующем географическом центре данных, Корпорация Майкрософт позволяет запросить ранний перенос основных данных клиентов организации в новый геоо центр обработки данных.</span><span class="sxs-lookup"><span data-stu-id="e8063-158">Although opening a new datacenter geo does not impact you and your core data stored in an already existing datacenter geo, Microsoft allows you to request an early migration of your organization's core customer data at rest to a new datacenter geo.</span></span>

<span data-ttu-id="e8063-159">Вот пример, в котором клиент Microsoft 365 был перемещен из географического центра обработки данных Европейского Союза (ЕС) в соединенное Королевство.</span><span class="sxs-lookup"><span data-stu-id="e8063-159">Here is an example in which a Microsoft 365 tenant was moved from the European Union (EU) datacenter geo to the one located in the United Kingdom (UK).</span></span>

![Пример перемещения клиента Microsoft 365 между географическими центрами обработки данных](../media/tenant-management-overview/tenant-management-example-tenant-move.png)

<span data-ttu-id="e8063-161">Дополнительные сведения см. в перемещении основных данных в новые географические области центра обработки данных [Microsoft 365.](../enterprise/moving-data-to-new-datacenter-geos.md)</span><span class="sxs-lookup"><span data-stu-id="e8063-161">For more information, see [Moving core data to new Microsoft 365 datacenter geos](../enterprise/moving-data-to-new-datacenter-geos.md).</span></span>

## <a name="products-and-licenses-for-a-tenant"></a><span data-ttu-id="e8063-162">Продукты и лицензии для клиента</span><span class="sxs-lookup"><span data-stu-id="e8063-162">Products and licenses for a tenant</span></span>

<span data-ttu-id="e8063-163">Клиент Microsoft 365 создается при покупке первого продукта, например Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="e8063-163">Your Microsoft 365 tenant gets created when you purchase your first product, such as Microsoft 365 E3.</span></span> <span data-ttu-id="e8063-164">Наряду с продуктом это лицензии, с которых взимается ежемесячная или годовая плата.</span><span class="sxs-lookup"><span data-stu-id="e8063-164">Along with the product are licenses, which are charged a monthly or annual fee.</span></span> <span data-ttu-id="e8063-165">Затем администратор назначает доступную лицензию из одного из ваших продуктов учетной записи пользователя напрямую или через членство в группах.</span><span class="sxs-lookup"><span data-stu-id="e8063-165">An administrator then assigns an available license from one of your products to a user account, either directly or through group membership.</span></span> <span data-ttu-id="e8063-166">В зависимости от бизнес-потребностей организации у вас может быть набор продуктов, каждый из которых имеет собственный пул лицензий.</span><span class="sxs-lookup"><span data-stu-id="e8063-166">Depending on your organization's business needs, you might have a set of products, each with their own pool of licenses.</span></span> 

<span data-ttu-id="e8063-167">Определение набора продуктов и количества лицензий для каждого из них требует определенного планирования:</span><span class="sxs-lookup"><span data-stu-id="e8063-167">Determining the set of products and the number of licenses for each requires some planning to:</span></span>

- <span data-ttu-id="e8063-168">Убедитесь, что у вас достаточно лицензий для учетных записей пользователей, которые нуждаются в расширенных функций.</span><span class="sxs-lookup"><span data-stu-id="e8063-168">Ensure you have enough licenses for the user accounts that need advanced features.</span></span>
- <span data-ttu-id="e8063-169">Запретить вам неиссякание лицензий или слишком много ненаписаных лицензий в зависимости от изменений в персонале организации.</span><span class="sxs-lookup"><span data-stu-id="e8063-169">Prevent you from running out of licenses or having too many unassigned licenses, based on changes in staffing at your organization.</span></span>


## <a name="results-of-step-1"></a><span data-ttu-id="e8063-170">Результаты этапа 1</span><span class="sxs-lookup"><span data-stu-id="e8063-170">Results of Step 1</span></span>

<span data-ttu-id="e8063-171">Для корпоративных клиентов Microsoft 365 вы определили:</span><span class="sxs-lookup"><span data-stu-id="e8063-171">For your Microsoft 365 for enterprise tenants, you have determined:</span></span>

- <span data-ttu-id="e8063-172">Количество клиентов, которые у вас есть или необходимы.</span><span class="sxs-lookup"><span data-stu-id="e8063-172">How many tenants you have or need.</span></span>
- <span data-ttu-id="e8063-173">Для каждого клиента, какие продукты и лицензии необходимо приобрести.</span><span class="sxs-lookup"><span data-stu-id="e8063-173">For each tenant, which products and licenses must be purchased.</span></span>
- <span data-ttu-id="e8063-174">Сведения о том, должен ли клиент быть клиентом с несколькими географическими потребностями в соответствии с требованиями к месту хранения данных.</span><span class="sxs-lookup"><span data-stu-id="e8063-174">Whether a tenant needs to be Multi-Geo to comply with data residency requirements.</span></span>
- <span data-ttu-id="e8063-175">Нужно ли настроить совместную работу между клиентами.</span><span class="sxs-lookup"><span data-stu-id="e8063-175">Whether you need to set up inter-tenant collaboration.</span></span>
- <span data-ttu-id="e8063-176">Нужно ли перенести один клиент в другой.</span><span class="sxs-lookup"><span data-stu-id="e8063-176">Whether you need to migrate one tenant to another.</span></span>
- <span data-ttu-id="e8063-177">Нужно ли перемещать основные данные из одного географического центра обработки данных в новый.</span><span class="sxs-lookup"><span data-stu-id="e8063-177">Whether you need to move core data from one datacenter geo to new one.</span></span>

<span data-ttu-id="e8063-178">Вот пример нового клиента.</span><span class="sxs-lookup"><span data-stu-id="e8063-178">Here is an example of a new tenant.</span></span>

![Пример нового клиента](../media/tenant-management-overview/tenant-management-tenant-build-step1.png)

<span data-ttu-id="e8063-180">На этой иллюстрации клиент имеет:</span><span class="sxs-lookup"><span data-stu-id="e8063-180">In this illustration, the tenant has:</span></span>

- <span data-ttu-id="e8063-181">Расположение по умолчанию, соответствующее географическому расположению центра обработки данных Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e8063-181">A default location corresponding to a Microsoft 365 datacenter geo.</span></span>
- <span data-ttu-id="e8063-182">Набор продуктов и лицензий.</span><span class="sxs-lookup"><span data-stu-id="e8063-182">A set of products and licenses.</span></span>
- <span data-ttu-id="e8063-183">Набор облачных приложений для повышения производительности, некоторые из которых специфично для продуктов.</span><span class="sxs-lookup"><span data-stu-id="e8063-183">The set of cloud productivity apps, some of which are specific to products.</span></span>
- <span data-ttu-id="e8063-184">Клиент Azure AD, содержащий учетные записи глобального администратора и начальное доменное имя DNS.</span><span class="sxs-lookup"><span data-stu-id="e8063-184">An Azure AD tenant that contains global administrator accounts and an initial DNS domain name.</span></span>

<span data-ttu-id="e8063-185">По мере того как мы проймем дополнительные шаги этого решения, мы создаим этот рисунок.</span><span class="sxs-lookup"><span data-stu-id="e8063-185">As we move through the additional steps of this solution, we will build out this figure.</span></span>

## <a name="ongoing-maintenance-for-tenants"></a><span data-ttu-id="e8063-186">Текущее обслуживание клиентов</span><span class="sxs-lookup"><span data-stu-id="e8063-186">Ongoing maintenance for tenants</span></span>

<span data-ttu-id="e8063-187">На постоянной основе может потребоваться:</span><span class="sxs-lookup"><span data-stu-id="e8063-187">On an ongoing basis, you might need to:</span></span>

- <span data-ttu-id="e8063-188">Добавление нового клиента.</span><span class="sxs-lookup"><span data-stu-id="e8063-188">Add a new tenant.</span></span>
- <span data-ttu-id="e8063-189">Добавление новых продуктов в клиент с начальным количеством лицензий.</span><span class="sxs-lookup"><span data-stu-id="e8063-189">Add new products to a tenant with an initial number of licenses.</span></span>
- <span data-ttu-id="e8063-190">Измените набор лицензий для продукта в клиенте, чтобы изменить требования к персоналу.</span><span class="sxs-lookup"><span data-stu-id="e8063-190">Change the set of licenses for a product in a tenant to adjust for changing staff requirements.</span></span>
- <span data-ttu-id="e8063-191">Переместите основные данные из клиента в новое географическое расположение центра обработки данных.</span><span class="sxs-lookup"><span data-stu-id="e8063-191">Move your core data from a tenant to a new datacenter geo location.</span></span>
- <span data-ttu-id="e8063-192">Добавьте multi-Geo для требований к месту хранения данных.</span><span class="sxs-lookup"><span data-stu-id="e8063-192">Add Multi-Geo for data residency requirements.</span></span>
- <span data-ttu-id="e8063-193">Настройка совместной работы между арендаторами.</span><span class="sxs-lookup"><span data-stu-id="e8063-193">Set up inter-tenant collaboration.</span></span>

## <a name="next-step"></a><span data-ttu-id="e8063-194">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="e8063-194">Next step</span></span>

<span data-ttu-id="e8063-195">[![Шаг 2. Оптимизация клиента для доступа к сети](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)</span><span class="sxs-lookup"><span data-stu-id="e8063-195">[![Step 2. Optimize your tenant for network for access](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)</span></span>

<span data-ttu-id="e8063-196">Продолжайте работу [с сетью,](tenant-management-networking.md) чтобы обеспечить оптимальную сеть от сотрудников к облачным службам Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e8063-196">Continue with [networking](tenant-management-networking.md) to provide optimal networking from your workers to Microsoft 365 cloud services.</span></span>
