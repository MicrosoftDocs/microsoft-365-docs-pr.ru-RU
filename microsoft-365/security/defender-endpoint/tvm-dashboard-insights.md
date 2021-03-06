---
title: Сведения о панели мониторинга — контроль угроз и уязвимостей
description: Панель контроль угроз и уязвимостей может помочь администраторам secOps и безопасности в устранении угроз кибербезопасности и повысить устойчивость к безопасности своей организации.
keywords: Microsoft Defender для endpoint-tvm, панель мониторинга Microsoft Defender для endpoint-tvm, & управление уязвимостями, контроль угроз и уязвимостей, рисковые угрозы & управление уязвимостями, конфигурация безопасности, оценка безопасности Microsoft для устройств, оценка экспозиции
search.appverid: met150
search.product: eADQiWindows 10XVcnh
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
ms.openlocfilehash: 82b6123a99eb406918708c6bf23b870ef3bc3d79
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934145"
---
# <a name="dashboard-insights---threat-and-vulnerability-management"></a>Сведения о панели мониторинга — контроль угроз и уязвимостей

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**

- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Угроза и управление уязвимостями](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

Threat and управление уязвимостями является компонентом Defender для endpoint и предоставляет администраторам безопасности и группам операций безопасности уникальное значение, в том числе:


- Аналитика по обнаружению и устранению угроз на конечных точках (EDR) в режиме реального времени, связанная с уязвимостями конечных точек
- Бесценный контекст уязвимости устройства во время расследований инцидентов
- Встроенные процессы восстановления с помощью Microsoft Intune и Microsoft Endpoint Configuration Manager  
  
Вы можете использовать контроль угроз и уязвимостей в [Центр безопасности в Microsoft Defender:](https://securitycenter.windows.com/)

- Просмотр результатов воздействия и microsoft Secure Score для устройств, а также рекомендации по безопасности, уязвимость программного обеспечения, действия по исправлению и выставленные устройства
- Сопоставление EDR с уязвимостями конечной точки и их обработка
- Выберите параметры исправлений для отслеживания и отслеживания задач по исправлению.
- Выбор параметров исключений и отслеживание активных исключений

> [!NOTE]
> Устройства, не активные в течение последних 30 дней, не будут учитываться в данных, отражающих оценку контроль угроз и уязвимостей и microsoft Secure Score для устройств.

Просмотрите это видео, чтобы получить краткий обзор того, что находится на контроль угроз и уязвимостей панели мониторинга.

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r1nv]

## <a name="threat-and-vulnerability-management-dashboard"></a>Панель мониторинга угроз и управление уязвимостями

 ![Портал Microsoft Defender для конечных точек](images/tvm-dashboard-devices.png)

Область | Описание
:---|:---
**Выбранные группы устройств (#/#)**   | Фильтрация контроль угроз и уязвимостей данных, которые необходимо увидеть на панели мониторинга и картах группами устройств. Выбранный фильтр применяется на всех контроль угроз и уязвимостей страницах.
[**Показатель уязвимости**](tvm-exposure-score.md)   | См. текущее состояние воздействия устройств организации на угрозы и уязвимости. Оценка экспозиции организации влияет на несколько факторов: слабые места, обнаруженные на устройствах, вероятность взлома устройств, значение устройств для организации и соответствующие оповещения, обнаруженные на устройствах. Цель состоит в том, чтобы снизить оценку экспозиции вашей организации, чтобы быть более безопасной. Чтобы уменьшить количество баллов, необходимо устранять связанные проблемы с конфигурацией безопасности, перечисленные в рекомендациях по безопасности.
[**Оценка безопасности (Майкрософт) для устройств**](tvm-microsoft-secure-score-devices.md) | См. положение безопасности операционной системы, приложений, сетей, учетных записей и элементов управления безопасностью организации. Цель состоит в исправлении связанных с этим проблем с конфигурацией безопасности, чтобы увеличить ваш балл для устройств. Выбор баров поможет вам найти страницу рекомендаций **по безопасности.**
**Распределение экспозиции устройств** | Узнайте, сколько устройств подвергается воздействию на основе уровня экспозиции. Выберите раздел в кольцевой диаграмме, чтобы перейти на страницу списка **Устройств** и просмотреть имена затронутых устройств, уровень экспозиции, уровень риска и другие сведения, такие как домен, платформа операционной системы, состояние его здоровья, когда оно было в последний раз замечено, и его теги.
**Рекомендации по безопасности** | См. в соотноженных рекомендациях по безопасности, отсортированных и приоритизированных в зависимости от риска организации и требуемой срочности. Выберите **Показать больше,** чтобы увидеть остальные рекомендации по безопасности в списке. Выберите **Показать исключения** для списка рекомендаций, которые имеют исключение.
**Верхнее уязвимое программное обеспечение** | Получите возможность в режиме реального времени влиять на инвентаризацию программного обеспечения организации с помощью списка уязвимых программ, установленных на устройствах сети, и их влияния на оценку воздействия на организацию. Выберите элемент для получения дополнительных сведений или **покажите** дополнительные сведения, чтобы увидеть остальные уязвимые списки программного обеспечения на странице **инвентаризации программного** обеспечения.
**Топ действий по исправлению** | Отслеживание действий по исправлению, созданных из рекомендаций по безопасности. Вы можете выбрать каждый элемент в списке, чтобы просмотреть сведения на странице Исправление или показать больше для просмотра остальных действий по исправлению и активных исключений.  
**Устройства с верхним подвергаемом воздействию** | Просмотр открытых имен устройств и их уровня экспозиции. Выберите имя устройства из списка, чтобы перейти на страницу устройства, на которой можно просмотреть оповещения, риски, инциденты, рекомендации по безопасности, установленное программное обеспечение и обнаруженные уязвимости, связанные с выставленными устройствами. Выберите **Показать больше,** чтобы увидеть остальную часть списка выставленных устройств. Из списка устройств можно управлять тегами, инициировать автоматическое расследование, инициировать сеанс живого ответа, собирать пакет исследований, запускать антивирусное сканирование, ограничивать выполнение приложения и изолировать устройство.

Дополнительные сведения о значках, используемых на портале, см. в [иконах Microsoft Defender для конечных точек.](portal-overview.md#microsoft-defender-for-endpoint-icons)


## <a name="related-topics"></a>Статьи по теме

- [Обзор угроз и управление уязвимостями](next-gen-threat-and-vuln-mgt.md)
- [Показатель уязвимости](tvm-exposure-score.md)
- [Оценка безопасности (Майкрософт) для устройств](tvm-microsoft-secure-score-devices.md)
- [Рекомендации по безопасности](tvm-security-recommendation.md)
- [Инвентаризация программного обеспечения](tvm-software-inventory.md)
- [Временная шкала события](threat-and-vuln-mgt-event-timeline.md)

