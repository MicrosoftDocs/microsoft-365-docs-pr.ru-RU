---
title: URL-адреса и диапазоны IP-адресов Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/28/2021
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
ms.openlocfilehash: 22294294ba35f00ff33a9b849f320f0e8b42e0ba
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290259"
---
# <a name="office-365-urls-and-ip-address-ranges"></a>URL-адреса и диапазоны IP-адресов Office 365

Для Office 365 требуется подключение к Интернету. Указанные ниже конечные точки должны быть доступны для клиентов, использующих планы Office 365, в том числе входящих в облако сообщества государственных учреждений (GCC).
  
*Office 365 Worldwide (+GCC)* \| [Office 365, предоставляемый 21 Vianet](urls-and-ip-address-ranges-21vianet.md) \| [Office 365 Germany](microsoft-365-germany-endpoints.md) \| [Office 365 U.S. Government DoD](microsoft-365-u-s-government-dod-endpoints.md) \| [Office 365 U.S. Government GCC High](microsoft-365-u-s-government-gcc-high-endpoints.md) \|

|Примечания|Скачать|Использовать|
|---|---|---|
|**Последнее обновление:** 28.06.2021, ![RSS](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [подписка на журнал изменений](https://endpoints.office.com/version/worldwide?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)|**Скачивание:** все обязательные и необязательные назначения в одном списке [в формате JSON](https://endpoints.office.com/endpoints/worldwide?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).|**Используйте:** наши [PAC-файлы](managing-office-365-endpoints.md#pacfiles) прокси-сервера|
|

Сначала ознакомьтесь со статьей [Управление конечными точками Office 365](managing-office-365-endpoints.md), содержащей рекомендации по управлению сетевым подключением с использованием этих данных. В начале каждого месяца по мере необходимости данные конечных точек обновляются новыми IP-адресами и URL-адресами, публикуемыми за 30 дней до их активации. Это позволяет пользователям, не имеющим автоматических обновлений, завершить свои процессы до того, как новое подключение станет обязательным. Конечные точки также могут обновляться в течение месяца, если это требуется для устранения проблем, выявленных службой поддержки, инцидентов безопасности или в связи с другими экстренными рабочими требованиями. Данные, представленные ниже на этой странице, получены из веб-служб на базе REST. Если вы используете скрипт или сетевое устройство для доступа к этим данным, сразу переходите к разделу [Веб-служба](microsoft-365-ip-web-service.md).

Ниже в данных конечной точки перечислены требования к подключениям с компьютера пользователя к Office 365. Они не включают сетевые подключения от корпорации Майкрософт к сети клиентов, которые иногда называются гибридными или входящими сетевыми подключениями. Подробные сведения см. в статье [Дополнительные конечные точки](additional-office365-ip-addresses-and-urls.md).

Конечные точки сгруппированы в четыре области обслуживания. Первые три области обслуживания можно независимо выбирать для подключения. Четвертая область обслуживания — это общая зависимость (называемая Microsoft 365 Common and Office), которая всегда должна обеспечиваться сетевым подключением.

Показанные столбцы с данными:

- **Идентификатор**. Код строки, также известный как набор конечной точки. Этот идентификатор совпадает с возвращаемым веб-службой для набора конечной точки.

- **Категория**. Показывает, присвоена ли набору конечной точки категория "Оптимизация", "Разрешение" или "По умолчанию". С этими категориями и инструкцией по их управлению можно ознакомиться в разделе [Новые категории конечных точек Office 365](microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories). В этом столбце также указано, какие наборы конечной точки необходимы для обеспечения сетевого подключения. Для наборов конечной точки, не требующихся для сетевого подключения, в этом поле приводятся примечания о том, какие функции будут отсутствовать при блокировании этого набора конечной точки. При исключении всей области обслуживания наборы конечной точки, перечисленные как обязательные, не требуют подключения.

- **ER**. Значение **Да**, если набор конечной точки поддерживается в Azure ExpressRoute с префиксами маршрутизации Office 365. Сообщество BGP, которое включает указанные префиксы маршрутизации, соответствует области службы в списке. Если значение ER соответствует **Нет**, это означает, что ExpressRoute не поддерживается для этого набора конечной точки. Тем не менее, не нужно считать, что для набора конечной точки со значением ER равным **Нет** отсутствуют объявленные маршруты.

- **Адреса**. Перечисляет полные доменные имена или подстановочные доменные имена, а также диапазоны IP-адресов для набора конечной точки. Обратите внимание, что диапазон IP-адресов представлен в формате CIDR и может содержать несколько отдельных IP-адресов в указанной сети.

- **Порты**. Перечисляет порты TCP или UDP, которые объединяются с адресами для создания конечной точки сети. Можно заметить дублирование в диапазонах IP-адресов при перечислении разных портов.

[!INCLUDE [Office 365 worldwide endpoints](../includes/office-365-worldwide-endpoints.md)]

> [!NOTE]
> Рекомендации по IP- и URL-адресам Yammer см. в статье [Использование жестко закодированных IP-адресов для Yammer не рекомендуется](https://techcommunity.microsoft.com/t5/Yammer-Blog/Using-hard-coded-IP-addresses-for-Yammer-is-not-recommended/ba-p/276592) в блоге Yammer.

## <a name="related-topics"></a>Статьи по теме

[Дополнительные конечные точки не включены в веб-службу IP-адресов и URL-адресов Office 365](additional-office365-ip-addresses-and-urls.md)

[Управление конечными точками Office 365](managing-office-365-endpoints.md)

[Общие конечные точки Microsoft Stream](/stream/network-overview#general-microsoft-stream-endpoints)
  
[Проверка подключения Microsoft 365](./monitor-connectivity.md)

[Набор корневого ЦС и промежуточного ЦС в системе стороннего приложения](../compliance/encryption-office-365-certificate-chains.md)
  
[Подключение клиентских компьютеров](https://support.office.com/article/client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b)
  
[Сети доставки содержимого](https://support.office.com/article/content-delivery-networks-0140f704-6614-49bb-aa6c-89b75dcd7f1f)
  
[Диапазоны IP-адресов и теги служб Microsoft Azure — общедоступное облако](https://www.microsoft.com/download/details.aspx?id=56519)

[Диапазоны IP-адресов и теги служб Microsoft Azure — облако для государственных организаций США](https://www.microsoft.com/download/details.aspx?id=57063)

[Диапазоны IP-адресов и теги служб Microsoft Azure — облако в Германии](https://www.microsoft.com/download/details.aspx?id=57064)

[Диапазоны IP-адресов и теги служб Microsoft Azure — облако в Китае](https://www.microsoft.com/download/details.aspx?id=57062)
  
[Пространство публичных IP-адресов корпорации Майкрософт](https://www.microsoft.com/download/details.aspx?id=53602)

[Реестр имен служб и номеров портов транспортного протокола](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml)
