---
title: URL-адреса и диапазоны IP-адресов Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 03/01/2021
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- MOM160
- BCS160
ms.assetid: 8548a211-3fe7-47cb-abb1-355ea5aa88a2
description: Сводка. Для Office 365 требуется подключение к Интернету. Указанные ниже конечные точки должны быть доступны для клиентов, использующих планы Office 365, в том числе входящих в облако сообщества государственных учреждений (GCC).
hideEdit: true
ms.openlocfilehash: 1c0a2a486bf6964edc9b94fd670c96ade161cacd
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925272"
---
# <a name="office-365-urls-and-ip-address-ranges"></a><span data-ttu-id="246d7-104">URL-адреса и диапазоны IP-адресов Office 365</span><span class="sxs-lookup"><span data-stu-id="246d7-104">Office 365 URLs and IP address ranges</span></span>

<span data-ttu-id="246d7-p102">Для Office 365 требуется подключение к Интернету. Указанные ниже конечные точки должны быть доступны для клиентов, использующих планы Office 365, в том числе входящих в облако сообщества государственных учреждений (GCC).</span><span class="sxs-lookup"><span data-stu-id="246d7-p102">Office 365 requires connectivity to the Internet. The endpoints below should be reachable for customers using Office 365 plans, including Government Community Cloud (GCC).</span></span>
  
<span data-ttu-id="246d7-107">*Office 365 по всему миру (+ GCC)* | [Office 365, предоставляемый 21 Vianet](urls-and-ip-address-ranges-21vianet.md) | [Office 365 Germany](microsoft-365-germany-endpoints.md) | [Office 365 для DoD государственных организаций США](microsoft-365-u-s-government-dod-endpoints.md)  | [Office 365 для GCC High государственных организаций США](microsoft-365-u-s-government-gcc-high-endpoints.md) |</span><span class="sxs-lookup"><span data-stu-id="246d7-107">*Office 365 Worldwide (+GCC)* | [Office 365 operated by 21 Vianet](urls-and-ip-address-ranges-21vianet.md) | [Office 365 Germany](microsoft-365-germany-endpoints.md) | [Office 365 U.S. Government DoD](microsoft-365-u-s-government-dod-endpoints.md)  | [Office 365 U.S. Government GCC High](microsoft-365-u-s-government-gcc-high-endpoints.md) |</span></span>

||||
|:-----|:-----|:-----|
|<span data-ttu-id="246d7-108">**Последнее обновление:** 03.01.2021, ![RSS](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [подписка на журнал изменений](https://endpoints.office.com/version/worldwide?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="246d7-108">**Last updated:** 03/01/2021 - ![RSS](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [Change Log subscription](https://endpoints.office.com/version/worldwide?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span> <br/> |<span data-ttu-id="246d7-109">**Скачивание:** все обязательные и необязательные назначения в одном списке [в формате JSON](https://endpoints.office.com/endpoints/worldwide?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).</span><span class="sxs-lookup"><span data-stu-id="246d7-109">**Download:** all required and optional destinations in one [JSON formatted](https://endpoints.office.com/endpoints/worldwide?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) list.</span></span>  <br/> | <span data-ttu-id="246d7-110">**Используйте:** наши [PAC-файлы](managing-office-365-endpoints.md#pacfiles) прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="246d7-110">**Use:** our proxy [PAC files](managing-office-365-endpoints.md#pacfiles)</span></span> <br/> |

 <span data-ttu-id="246d7-111">Начните применять [управление конечными точками Office 365](managing-office-365-endpoints.md), чтобы освоить наши рекомендации по управлению сетевым соединением с использованием этих данных.</span><span class="sxs-lookup"><span data-stu-id="246d7-111">Start with [Managing Office 365 endpoints](managing-office-365-endpoints.md) to understand our recommendations for managing network connectivity using this data.</span></span> <span data-ttu-id="246d7-112">По мере необходимости в начале каждого месяца данные конечной точки обновляются новыми IP- и URL-адресами, публикуемыми за 30 дней до активации.</span><span class="sxs-lookup"><span data-stu-id="246d7-112">Endpoints data is updated as needed at the beginning of each month with new IP Addresses and URLs published 30 days in advance of being active.</span></span> <span data-ttu-id="246d7-113">Это позволяет клиентам, у которых еще не проводятся автоматические обновления, завершать свои процессы до того, как потребуется новое соединение.</span><span class="sxs-lookup"><span data-stu-id="246d7-113">This allows for customers who do not yet have automated updates to complete their processes before new connectivity is required.</span></span> <span data-ttu-id="246d7-114">Кроме того, конечные точки могут обновляться и в течение месяца, если это требуется для повышения уровня обращений в службу поддержки, устранения инцидентов в области безопасности или немедленного выполнения других действий.</span><span class="sxs-lookup"><span data-stu-id="246d7-114">Endpoints may also be updated during the month if needed to address support escalations, security incidents, or other immediate operational requirements.</span></span> <span data-ttu-id="246d7-115">Данные, представленные ниже на этой странице, сгенерированы с помощью веб-служб на основе REST.</span><span class="sxs-lookup"><span data-stu-id="246d7-115">The data shown on this page below is all generated from the REST-based web services.</span></span> <span data-ttu-id="246d7-116">Если для доступа к этим данным вы используете скрипт или сетевое устройство, вам нужно перейти непосредственно в раздел [Веб-служба](microsoft-365-ip-web-service.md).</span><span class="sxs-lookup"><span data-stu-id="246d7-116">If you are using a script or a network device to access this data, you should go to the [Web service](microsoft-365-ip-web-service.md) directly.</span></span>

<span data-ttu-id="246d7-p104">Ниже в данных конечной точки перечислены требования к подключениям с компьютера пользователя к Office 365. Они не включают сетевые подключения от корпорации Майкрософт к сети клиентов, которые иногда называются гибридными или входящими сетевыми подключениями. Подробные сведения см. в статье [Дополнительные конечные точки](additional-office365-ip-addresses-and-urls.md).</span><span class="sxs-lookup"><span data-stu-id="246d7-p104">Endpoint data below lists requirements for connectivity from a user's machine to Office 365. It does not include network connections from Microsoft into a customer network, sometimes called hybrid or inbound network connections. See [Additional endpoints](additional-office365-ip-addresses-and-urls.md) for more information.</span></span>

<span data-ttu-id="246d7-p105">Конечные точки сгруппированы в четыре области обслуживания. Первые три области обслуживания можно независимо выбирать для подключения. Четвертая область обслуживания — это общая зависимость (называемая Microsoft 365 Common and Office), которая всегда должна обеспечиваться сетевым подключением.</span><span class="sxs-lookup"><span data-stu-id="246d7-p105">The endpoints are grouped into four service areas. The first three service areas can be independently selected for connectivity. The fourth service area is a common dependency (called Microsoft 365 Common and Office) and must always have network connectivity.</span></span>

<span data-ttu-id="246d7-123">Показанные столбцы с данными:</span><span class="sxs-lookup"><span data-stu-id="246d7-123">Data columns shown are:</span></span>

- <span data-ttu-id="246d7-p106">**Идентификатор**. Код строки, также известный как набор конечной точки. Этот идентификатор совпадает с возвращаемым веб-службой для набора конечной точки.</span><span class="sxs-lookup"><span data-stu-id="246d7-p106">**ID**: The ID number of the row, also known as an endpoint set. This ID is the same as is returned by the web service for the endpoint set.</span></span>

- <span data-ttu-id="246d7-p107">**Категория**. Показывает, присвоена ли набору конечной точки категория "Оптимизация", "Разрешение" или "По умолчанию". С этими категориями и инструкцией по их управлению можно ознакомиться в разделе [Новые категории конечных точек Office 365](microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories). В этом столбце также указано, какие наборы конечной точки необходимы для обеспечения сетевого подключения. Для наборов конечной точки, не требующихся для сетевого подключения, в этом поле приводятся примечания о том, какие функции будут отсутствовать при блокировании этого набора конечной точки. При исключении всей области обслуживания наборы конечной точки, перечисленные как обязательные, не требуют подключения.</span><span class="sxs-lookup"><span data-stu-id="246d7-p107">**Category**: Shows whether the endpoint set is categorized as "Optimize", "Allow", or "Default". You can read about these categories and guidance for management of them at [New Office 365 endpoint categories](microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories). This column also lists which endpoint sets are required to have network connectivity. For endpoint sets which are not required to have network connectivity, we provide notes in this field to indicate what functionality would be missing if the endpoint set is blocked. If you are excluding an entire service area, the endpoint sets listed as required do not require connectivity.</span></span>

- <span data-ttu-id="246d7-p108">**ER**. Значение **Да**, если набор конечной точки поддерживается в Azure ExpressRoute с префиксами маршрутизации Office 365. Сообщество BGP, которое включает указанные префиксы маршрутизации, соответствует области службы в списке. Если значение ER соответствует **Нет**, это означает, что ExpressRoute не поддерживается для этого набора конечной точки. Тем не менее, не нужно считать, что для набора конечной точки со значением ER равным **Нет** отсутствуют объявленные маршруты.</span><span class="sxs-lookup"><span data-stu-id="246d7-p108">**ER**: This is **Yes** if the endpoint set is supported over Azure ExpressRoute with Office 365 route prefixes. The BGP community that includes the route prefixes shown aligns with the service area listed. When ER is **No**, this means that ExpressRoute is not supported for this endpoint set. However, it should not be assumed that no routes are advertised for an endpoint set where ER is **No**.</span></span>

- <span data-ttu-id="246d7-p109">**Адреса**. Перечисляет полные доменные имена или подстановочные доменные имена, а также диапазоны IP-адресов для набора конечной точки. Обратите внимание, что диапазон IP-адресов представлен в формате CIDR и может содержать несколько отдельных IP-адресов в указанной сети.</span><span class="sxs-lookup"><span data-stu-id="246d7-p109">**Addresses**: Lists the FQDNs or wildcard domain names and IP Address ranges for the endpoint set. Note that an IP Address range is in CIDR format and may include many individual IP Addresses in the specified network.</span></span>
 
- <span data-ttu-id="246d7-p110">**Порты**. Перечисляет порты TCP или UDP, которые объединяются с адресами для создания конечной точки сети. Можно заметить дублирование в диапазонах IP-адресов при перечислении разных портов.</span><span class="sxs-lookup"><span data-stu-id="246d7-p110">**Ports**: Lists the TCP or UDP ports that are combined with the Addresses to form the network endpoint. You may notice some duplication in IP Address ranges where there are different ports listed.</span></span>

[!INCLUDE [Office 365 worldwide endpoints](../includes/office-365-worldwide-endpoints.md)]

>[!Note]
><span data-ttu-id="246d7-139">Рекомендации по IP- и URL-адресам Yammer см. в статье [Использование жестко закодированных IP-адресов для Yammer не рекомендуется](https://techcommunity.microsoft.com/t5/Yammer-Blog/Using-hard-coded-IP-addresses-for-Yammer-is-not-recommended/ba-p/276592) в блоге Yammer.</span><span class="sxs-lookup"><span data-stu-id="246d7-139">For recommendations on Yammer IP addresses and URLs, see [Using hard-coded IP addresses for Yammer is not recommended](https://techcommunity.microsoft.com/t5/Yammer-Blog/Using-hard-coded-IP-addresses-for-Yammer-is-not-recommended/ba-p/276592) on the Yammer blog.</span></span>
>

## <a name="related-topics"></a><span data-ttu-id="246d7-140">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="246d7-140">Related Topics</span></span>

[<span data-ttu-id="246d7-141">Управление конечными точками Office 365</span><span class="sxs-lookup"><span data-stu-id="246d7-141">Managing Office 365 endpoints</span></span>](managing-office-365-endpoints.md)

[<span data-ttu-id="246d7-142">Общие конечные точки Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="246d7-142">General Microsoft Stream endpoints</span></span>](/stream/network-overview#general-microsoft-stream-endpoints)
  
[<span data-ttu-id="246d7-143">Проверка подключения Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="246d7-143">Monitor Microsoft 365 connectivity</span></span>](./monitor-connectivity.md)

[<span data-ttu-id="246d7-144">Набор корневого ЦС и промежуточного ЦС в системе стороннего приложения</span><span class="sxs-lookup"><span data-stu-id="246d7-144">Root CA and the Intermediate CA bundle on the third-party application system</span></span>](../compliance/encryption-office-365-certificate-chains.md)
  
[<span data-ttu-id="246d7-145">Подключение клиентских компьютеров</span><span class="sxs-lookup"><span data-stu-id="246d7-145">Client connectivity</span></span>](https://support.office.com/article/client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b)
  
[<span data-ttu-id="246d7-146">Сети доставки содержимого</span><span class="sxs-lookup"><span data-stu-id="246d7-146">Content delivery networks</span></span>](https://support.office.com/article/content-delivery-networks-0140f704-6614-49bb-aa6c-89b75dcd7f1f)
  
[<span data-ttu-id="246d7-147">Диапазоны IP-адресов и теги служб Microsoft Azure — общедоступное облако</span><span class="sxs-lookup"><span data-stu-id="246d7-147">Microsoft Azure IP Ranges and Service Tags – Public Cloud</span></span>](https://www.microsoft.com/download/details.aspx?id=56519)

[<span data-ttu-id="246d7-148">Диапазоны IP-адресов и теги служб Microsoft Azure — облако для государственных организаций США</span><span class="sxs-lookup"><span data-stu-id="246d7-148">Microsoft Azure IP Ranges and Service Tags – US Government Cloud</span></span>](https://www.microsoft.com/download/details.aspx?id=57063)

[<span data-ttu-id="246d7-149">Диапазоны IP-адресов и теги служб Microsoft Azure — облако в Германии</span><span class="sxs-lookup"><span data-stu-id="246d7-149">Microsoft Azure IP Ranges and Service Tags – Germany Cloud</span></span>](https://www.microsoft.com/download/details.aspx?id=57064)

[<span data-ttu-id="246d7-150">Диапазоны IP-адресов и теги служб Microsoft Azure — облако в Китае</span><span class="sxs-lookup"><span data-stu-id="246d7-150">Microsoft Azure IP Ranges and Service Tags – China Cloud</span></span>](https://www.microsoft.com/download/details.aspx?id=57062)
  
[<span data-ttu-id="246d7-151">Пространство публичных IP-адресов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="246d7-151">Microsoft Public IP Space</span></span>](https://www.microsoft.com/download/details.aspx?id=53602)

[<span data-ttu-id="246d7-152">Реестр имен служб и номеров портов транспортного протокола</span><span class="sxs-lookup"><span data-stu-id="246d7-152">Service Name and Transport Protocol Port Number Registry</span></span>](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml)