---
title: Планирование развертывания портала для запуска в SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
description: В этой статье описывается, как можно спланировать запуск портала в SharePoint Online и какие действия предпринять для успешного запуска.
ms.openlocfilehash: e22fa4d9cbfed79841d844f111e3eb91a708512e
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693539"
---
# <a name="planning-your-portal-launch-roll-out-plan-in-sharepoint-online"></a>Планирование развертывания портала для запуска в SharePoint Online

Портал — это сайт SharePoint в вашей интрасети, у которого есть большое количество посетителей сайта, использующих его содержимое. В крупных организациях могут быть некоторые из них. Например, портал компании и портал отдела кадров. Как правило,на порталах относительно немного людей, которые создают и являются авторами сайта и его содержимого. Большинство посетителей на портале только читают и используют содержимое.

В этой статье описано, как спланировать развертывание и развертывание плана в SharePoint Online. Кроме того, в SharePoint Online не разрешается соблюдение традиционных нагрузочного тестирования. SharePoint Online — это облачная служба, которая управляет возможностями нагрузки, работоспособностью и общим балансом нагрузки в службе.

Для создания успешного портала следуйте основным принципам, рекомендациям и рекомендациям, описанным в разделе [Создание, запуск и обслуживание работоспособного портала](https://go.microsoft.com/fwlink/?linkid=2105838) . 

Подход к развертыванию выделен ниже.

## <a name="overview-of-capacity-planning-in-sharepoint-online"></a>Обзор планирования мощности в SharePoint Online
Чтобы эффективно использовать возможности и работать с непредвиденным ростом, в любой ферме существует Автоматизация, которая отслеживает определенные сценарии использования. Хотя точное увеличение непредсказуемо для любого клиента в одной ферме, суммарная сумма запросов предсказуема по времени. Определяя тенденции роста в SharePoint Online, мы можем запланировать будущее расширение. Для получения дополнительных сведений о [планировании мощности и тестировании нагрузки SharePoint Online](capacity-planning-and-load-testing-sharepoint-online.md).

Основной частью успешного запуска является метод "Wave" или "поэтапная выгрузка", описанные ниже. 

## <a name="can-i-load-test-sharepoint-online"></a>Можно ли загрузить тест SharePoint Online?
SharePoint Online — это общедоступная многоклиентская среда, сбалансированная между фермами и масштабированием. Нагрузочное тестирование среды, например SharePoint Online, в которой изменения масштаба непрерывно не только приводят к непредвиденным результатам, но не разрешены. 

Дополнительные сведения:  [SharePoint Online по планированию мощности и тестированию нагрузки](capacity-planning-and-load-testing-sharepoint-online.md)

## <a name="optimize-pages-by-following-recommended-guidelines"></a>Оптимизируйте страницы, следуя рекомендациям
Страницы из локального развертывания не следует просто перемещать в SharePoint Online, не изменяя их на рекомендации для SharePoint Online. Наилучший подход состоит в том, чтобы всегда оптимизировать любую домашнюю страницу для любого сайта или портала в SharePoint, так как в этом случае большинство пользователей в организации будут иметь доступ к отправной точке для сайтов.

Следует учитывать несколько основных факторов:
- Локальные развертывания могут использовать традиционные кэши на стороне сервера, такие как кэш объектов, кэш вывода и кэш больших двоичных объектов. При различиях топологии в облаке эти параметры необязательно доступны, так как различия в масштабах делают их менее приемлемыми.
- Все страницы/функции и настройки, используемые для облачного использования, должны быть оптимизированы для большей задержки, а также для распределенных расположений пользователей, чтобы пользователи в разных областях или регионах могли использовать более единообразные возможности. В облаке предусмотрены такие оптимизации, как сети доставки контента (CDN) для оптимизации для распределенной базы пользователей, а также для современных сред SharePoint, что в ЛКГ используются наши преимущества (OOTB).

### <a name="what-to-do"></a>Что делать:
 - Для всех страниц сайта в SharePoint Online используйте [средство диагностики страниц](https://aka.ms/perftool), которое представляет собой расширение чромиум, которое поможет анализировать и предоставлять рекомендации. Они могут использоваться владельцами, редакторами, администраторами и разработчиками сайтов, так как они разрабатываются как отправную точку для анализа и оптимизации.
 - Разработчикам также следует использовать средства разработки, такие как средство разработчика F12, а также CTRL – F12 в браузере на современных страницах. [Fiddler](https://www.telerik.com/download/fiddler) также можно использовать для просмотра веса размера страницы, а также количества вызовов и элементов, влияющих на общую загрузку страницы. 

В этом разделе приведен краткий обзор оптимизации страниц.  Дополнительные сведения:  [Создание, запуск и обслуживание работоспособного портала](https://go.microsoft.com/fwlink/?linkid=2105838).

## <a name="follow-a-wave--phased-roll-out-approach"></a>Следуйте принципу поэтапного и поэтапного развертывания
Традиционный большой подход к отвосклицательному знаку для запуска сайта не позволит проверить, что настройки, внешние источники, службы или процессы были проверены в правильном масштабе. Это не означает, что для запуска потребуется заданный месяц, но рекомендуется по крайней мере несколько дней в зависимости от размера организации. После этого вы можете приостановить и устранить проблемы, прежде чем переходить к следующему этапу и, таким образом, уменьшить потенциальное количество пользователей, на которые влияют все проблемы. SharePoint в качестве службы масштабирует мощность на основе использования и прогнозирования использования и в течение этого нам не нужно уведомлять о своем запуске, следуйте рекомендациям по обеспечению успеха.
  
Как показано на следующем рисунке, часто это количество приглашенных пользователей значительно выше, чем на самом деле использует сайт. На этом рисунке показана стратегия развертывания выпуска. Этот метод помогает определить способы усовершенствования сайта SharePoint, прежде чем большинство пользователей увидят его.
  
![Диаграмма, показывающая приглашенных и активных пользователей](../media/0bc14a20-9420-4986-b9b9-fbcd2c6e0fb9.png)
  
На этапе пилотного развертывания удобно получать отзывы пользователей о том, что ваша организация доверяется и знает о них. Таким образом, можно оценить, как используется система, а также как она выполняется.
  
Во время каждой волны Соберите отзывы пользователей о функциях, а также о производительности во время каждой волны развертывания. Благодаря этому у вас есть преимущества медленного введения системы и улучшения работы системы. Это также позволяет нам реагировать на повышенную нагрузку при развертывании сайта до большего числа пользователей, а также в сочетании с соблюдением рекомендаций по оптимизации страниц, что позволяет пользователям получить положительную среду.

### <a name="what-to-do"></a>Что делать:
- Определите время каждого этапа и убедитесь, что у вас есть непредвиденная или временная возможность, прежде чем продолжить
- Запланируйте первую группу пользователей, которую вы хотите включить, чтобы убедиться, что вы получили отзывы, которые необходимо переместить вперед. Это означает, что если это возможно, выберите активную группу пользователей, которые будут своевременно предоставлять отзывы
- Когда вы планируете каждую из них, попробуйте и начните с маленькой пользовательской базы (менее 5000 пользователей), а затем увеличьте размер группы, как только вы продолжите с каждой волновой волны. Это позволяет создать побросой подход и упростить приостановку работы, которая может потребоваться.