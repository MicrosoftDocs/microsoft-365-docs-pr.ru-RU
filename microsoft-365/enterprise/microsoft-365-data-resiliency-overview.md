---
title: Устойчивость данных в Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: В этой статье рассказывается о проектировании и принципах обеспечения устойчивости и восстановлению данных в Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a0e6ca643fe9842a71102fbabd3c05324ba52b70
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693147"
---
# <a name="data-resiliency-in-microsoft-365"></a>Устойчивость данных в Microsoft 365

Имея сложную природу облачных вычислений, корпорация Майкрософт осторожным, что это не так, если бы что-то пойдет не так, а когда. Мы разрабатываем облачные службы, чтобы обеспечить максимальную надежность и свести к минимуму негативные последствия для пользователей, когда они происходят неправильно. Мы перешли за традиционную стратегию использования сложной физической инфраструктуры, и мы создали избыточность непосредственно в наших облачных службах. Мы используем сочетание менее сложной физической инфраструктуры и более интеллектуального программного обеспечения, которое создает устойчивость данных в наших службах и обеспечивает высокий уровень доступности наших клиентов. 

## <a name="resiliency-and-recoverability-are-built-in"></a>Устойчивость и возможность восстановления — встроенные 

Создание устойчивости и восстановление начинается с предположения, что базовая инфраструктура и процессы завершатся неисправности в некоторый момент: оборудование (инфраструктура) завершится с ошибками, а кто-то выполнит ошибки и программное обеспечение будет иметь ошибки. Несмотря на то, что разработчики программного обеспечения не думают об этих возможностях перед облаком, как эти проблемы были обработаны в типичной ИТ-реализации, мы сильно изменили его перед облаком:

- Для начала были существенные средства защиты оборудования и инфраструктуры. Таким образом, у центров обработки данных с 99,99% требуется значительная избыточность питания и сети, а серверы были реализованы с помощью аппаратной кластеризации, двойного источника питания, сдвоенных сетевых интерфейсов и т. д. 
- Во вторых, процесс был первостепенное. Операционные системы поддерживали строгие процедуры, изменения, принятые в Windows, и часто были значительными затратами на управление проектами. 
- В третьих, развертывание выполнялось с использованием глаЦиалной скорости. Развертывание кода без владельца источника предполагалось ожидать выпусков исправлений, а также основные выпуски, связанные с заменой оборудования и важное аутлай. Кроме того, единственный способ исправить проблему — выполнить откат. Таким образом, большинство ИТ ИТ могут развертывать только основные выпуски, чтобы не обновлять работу. 
- Наконец, масштаб развернутых систем, а также уровень их интерконнектеднесс был исторически гораздо меньше, чем теперь. 

Сегодня клиенты ожидают непрерывные инновации от корпорации Майкрософт без ослабления качества, и это одна из причин, по которым службы и программное обеспечение Майкрософт и программное обеспечение создаются с учетом устойчивости и возможности восстановления. 

## <a name="microsoft-365-data-resiliency-principles"></a>Принципы устойчивости данных Microsoft 365

Устойчивость — это способность облачной службы выдерживаться определенных типов сбоев и все еще полностью работоспособна с точки зрения клиентов. Устойчивость данных означает, что неисправностей в Microsoft 365 не возникает, а критические данные клиента остаются без изменений и не затрагиваются. К этому конечному пользователю службы Microsoft 365 были разработаны на основе пяти определенных принципов устойчивости:

- Имеются критические и некритические данные. Некритические данные (например, сведения о том, было ли сообщение прочитано) могут быть удалены в редких случаях сбоя. Важные данные (например, данные клиентов, такие как сообщения электронной почты) должны быть защищены от экстремальных затрат. В качестве цели проекта Доставка почтовых сообщений всегда является критической, а подобные сообщения не являются критическими. 
- Копии данных клиентов необходимо разделить на различные зоны сбоя или максимально возможное количество возможных доменов сбоя (например, центров обработки данных, доступных по одному учетным данным (процесс, сервер или оператор)) для обеспечения изоляции отказов. 
- Важные данные клиентов необходимо отслеживать для отказа любой части атомарности, согласованности, изоляции, устойчивости (ACID). 
- Данные клиента должны быть защищены от повреждения. Она должна быть активно проверена или отслеживаться, исправлена и восстановлена. 
- Большинство результатов потери данных от действий клиентов, поэтому пользователям разрешается самостоятельно восстанавливать себя с помощью графического интерфейса пользователя, который позволяет им восстанавливать случайно удаленные элементы. 
 
Благодаря созданию облачных служб для этих принципов, связанных с надежным тестированием и проверкой, Microsoft 365 может удовлетворить и превышать требования клиентов, обеспечивая платформу для непрерывного внедрения и улучшения. 

## <a name="related-links"></a>Дополнительные ссылки

- [Меры в отношении повреждения данных](microsoft-365-dealing-with-data-corruption.md)
- [Защита от вредоносных программ и программ-шантажистов](microsoft-365-malware-and-ransomware-protection.md)
- [Мониторинг и самовосстановление](microsoft-365-monitoring-and-self-healing.md)
- [Устойчивость данных Exchange](microsoft-365-exchange-data-resiliency.md)