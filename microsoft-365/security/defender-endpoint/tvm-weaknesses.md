---
title: Уязвимости в моей организации — контроль угроз и уязвимостей
description: Списки распространенных уязвимостей и уязвимостей (CVE) ID слабых мест, найденных в программном обеспечении, запущенного в вашей организации. Обнаружено функцией Microsoft Defender для контроль угроз и уязвимостей конечных точек.
keywords: Microsoft Defender для endpoint threat & управление уязвимостями, контроль угроз и уязвимостей, Microsoft Defender for Endpoint tvm weaknesses page, finding weaknesses through tvm, tvm vulnerability list, vulnerability details in tvm
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: a8039a06dc58c31158f90d39857ffbeba92138d5
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933077"
---
# <a name="vulnerabilities-in-my-organization---threat-and-vulnerability-management"></a>Уязвимости в моей организации — контроль угроз и уязвимостей

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Угроза и управление уязвимостями](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

Для проверки и обнаружения уязвимостей управление уязвимостями для защиты конечной точки Defender для конечной точки Defender используются те же сигналы.

На **странице "Недостатки"** перечислены уязвимости программного обеспечения, на которые могут быть выставлены устройства, перечисляя общий ID уязвимостей и воздействий (CVE). Вы также можете просмотреть степень серьезности, оценку системы оценки общей уязвимости (CVSS), распространенность в организации, соответствующие нарушения, сведения об угрозах и другие.

>[!NOTE]
>Если для уязвимости не назначен официальный CVE-ID, имя уязвимости назначено контроль угроз и уязвимостей.

>[!TIP]
>Чтобы получить сообщения о новых событиях уязвимости, см. в руб. Настройка уведомлений об уязвимости в [Microsoft Defender для endpoint](configure-vulnerability-email-notifications.md)

## <a name="navigate-to-the-weaknesses-page"></a>Перейдите на страницу "Слабые места"

Доступ к странице Недостатки несколько различных способов:

- Выбор **слабых мест** из меню контроль угроз и уязвимостей навигации в [Центр безопасности в Microsoft Defender](portal-overview.md)
- Глобальный поиск

### <a name="navigation-menu"></a>Меню навигации

Перейдите контроль угроз и уязвимостей меню навигации и выберите **Слабые места,** чтобы открыть список резюме.

### <a name="vulnerabilities-in-global-search"></a>Уязвимости в глобальном поиске

1. Перейдите в глобальное выпадаемое меню поиска.
2. Выберите **ИД** уязвимости и ключа в ИД "Общие уязвимости и воздействия" (CVE), который вы ищете, а затем выберите значок поиска. Страница **"Слабые** места" открывается сведениями CVE, которые вы ищете.
![Глобальное поле поиска с выбранным параметром "уязвимость" и примером CVE.](images/tvm-vuln-globalsearch.png)
3. Выберите CVE, чтобы открыть панель вылетов с дополнительными сведениями, в том числе описанием уязвимости, сведениями, сведениями об угрозах и выставленными устройствами.

Чтобы увидеть остальные уязвимости на странице **Недостатки,** введите CVE, а затем выберите поиск.

## <a name="weaknesses-overview"></a>Обзор слабых сторон

Исправление уязвимостей на открытых устройствах, чтобы снизить риск для ваших активов и организации. Если **столбец Exposed Devices** показывает 0, это означает, что вы не подвержены риску.

![Страница "Слабые места".](images/tvm-weaknesses-overview.png)

### <a name="breach-and-threat-insights"></a>Сведения о нарушениях и угрозах

Просмотр всех связанных с этим нарушений и представлений об угрозах в столбце **Угроза,** когда значки окрашены в красный цвет.

 >[!NOTE]
 > Всегда приоритизуйте рекомендации, связанные с текущими угрозами. Эти рекомендации отмечены значком "Понимание ![ угрозы" Простой рисунок красной ошибки.](images/tvm_bug_icon.png) и значок ![ проницательности нарушения Простой рисунок стрелки, поразив ](images/tvm_alert_icon.png) цель. .  

Значок анализа нарушений выделяется при обнаружении уязвимости в организации.
![Пример текста анализа нарушений, который может показываться при наведении на значок. В этой статье говорится, что "возможное активное оповещение связано с этой рекомендацией.](images/tvm-breach-insights.png)

Значок сведения об угрозах выделяется, если в уязвимости, обнаруженной в организации, имеются связанные эксплойты. Наведении на значок показывает, является ли угроза частью набора эксплойтов или подключена к определенным расширенным устойчивым кампаниям или группам действий. При наличии имеется ссылка на отчет Threat Analytics с новостями об эксплуатации, раскрытием информации или связанными с ними советами по безопасности.  

![Сведения об угрозах, которые могут показываться при наведении на значок. Этот имеет несколько точек пули и связанный текст.](images/tvm-threat-insights.png)

### <a name="gain-vulnerability-insights"></a>Получение информации об уязвимости

Если выбрать CVE, панель вылетов откроется дополнительными сведениями, такими как описание уязвимости, сведения, сведения об угрозах и выставленные устройства.

- Категория "ФУНКЦИЯ ОС" показана в соответствующих сценариях
- Вы можете перейти к связанной рекомендации по безопасности для каждого CVE с выставленным устройством

 ![Пример пролета слабых сторон.](images/tvm-weakness-flyout400.png)

### <a name="software-that-isnt-supported"></a>Программное обеспечение, которое не поддерживается

CVEs для программного обеспечения, которое в настоящее время не поддерживается угрозами& управление уязвимостями все еще присутствует на странице Недостатки. Поскольку программное обеспечение не поддерживается, доступны будут только ограниченные данные.

Сведения об открытых устройствах не будут доступны для резюме с неподтверченным программным обеспечением. Фильтруя неподтверченное программное обеспечение, выбрав параметр "Недоступный" в разделе "Подверженные устройствам".

 ![Фильтр устройств, подвергаемой воздействию.](images/tvm-exposed-devices-filter.png)

## <a name="view-common-vulnerabilities-and-exposures-cve-entries-in-other-places"></a>Просмотр записей об общих уязвимостях и воздействиях (CVE) в других местах

### <a name="top-vulnerable-software-in-the-dashboard"></a>Верхнее уязвимое программное обеспечение на панели мониторинга

1. Перейдите на контроль угроз и уязвимостей [панели мониторинга и](tvm-dashboard-insights.md) прокрутите вниз к **виджету верхнего уязвимого программного** обеспечения. Вы увидите количество уязвимостей, найденных в каждом программном обеспечении, а также сведения об угрозах и представление на высоком уровне экспозиции устройства с течением времени.

    ![Top vulnerable software card with four columns: software, weaknesses, threats, exposed devices.](images/tvm-top-vulnerable-software500.png)

2. Выберите программное обеспечение, которое необходимо исследовать, чтобы перейти на страницу сверления.
3. Выберите **вкладку Обнаруженные уязвимости.**
4. Выберите уязвимость, которую необходимо исследовать, чтобы получить дополнительные сведения о деталях уязвимости

    ![Windows Обзор сверлить сервер 2019.](images/windows-server-drilldown.png)

### <a name="discover-vulnerabilities-in-the-device-page"></a>Обнаружение уязвимостей на странице устройства

Просмотр связанных сведений о недостатках на странице устройства.

1. Перейдите в Центр безопасности в Microsoft Defender меню навигации, а затем выберите значок устройства. Откроется **страница списка Устройств.**
2. На странице **Список устройств** выберите имя устройства, которое необходимо исследовать.

    ![Список устройств с выбранным устройством для исследования.](images/tvm_machinetoinvestigate.png)

3. Страница устройства откроется с подробными сведениями и вариантами ответа для устройства, которое необходимо исследовать.
4. Выберите **обнаруженные уязвимости.**

    ![Страница устройства с подробными сведениями и вариантами ответа.](images/tvm-discovered-vulnerabilities.png)

5. Выберите уязвимость, которую необходимо исследовать, чтобы открыть панель вылетов с данными CVE, такими как: описание уязвимости, анализ угроз и логика обнаружения.

#### <a name="cve-detection-logic"></a>Логика обнаружения CVE

Как и данные программного обеспечения, теперь мы показывем логику обнаружения, которую мы применили на устройстве, чтобы указать, что оно уязвимо. Новый раздел называется "Логика обнаружения" (в любой обнаруженной уязвимости на странице устройства) и показывает логику обнаружения и источник.

Категория "ФУНКЦИЯ ОС" также показана в соответствующих сценариях. CVE влияет на устройства с уязвимой ОС только в том случае, если включен определенный компонент ОС. Предположим, Windows Server 2019 имеет уязвимость в компоненте DNS. С помощью этой новой возможности мы прикрепим этот CVE только к устройствам Windows Server 2019 с возможностью DNS, включенной в оси.

![Пример логики обнаружения, в котором перечислены программное обеспечение, обнаруженное на устройстве и КБ.](images/tvm-cve-detection-logic.png)

## <a name="report-inaccuracy"></a>Неточность отчета

Сообщаем о ложном срабатыве, когда вы видите какие-либо расплывчатые, неточные или неполные сведения. Вы также можете сообщить о рекомендациях по безопасности, которые уже исправлены.

1. Откройте CVE на странице Недостатки.
2. Выберите **неточность** Отчета и откроется поле для вылетов.
3. Выберите категорию неточности из выпадаемого меню и заполните адрес электронной почты и сведения о неточности.
4. Выберите **Отправить**. Ваши отзывы немедленно отправляются контроль угроз и уязвимостей экспертам.

## <a name="related-articles"></a>Связанные статьи

- [Обзор угроз и управление уязвимостями](next-gen-threat-and-vuln-mgt.md)
- [Рекомендации по безопасности](tvm-security-recommendation.md)
- [Инвентаризация программного обеспечения](tvm-software-inventory.md)
- [Панель мониторинга аналитики](tvm-dashboard-insights.md)
- [Просмотр и организация списка конечных устройств Microsoft Defender для конечных точек](machines-view-overview.md)
