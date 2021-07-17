---
title: Просмотрите требования к архитектуре Конечной точки и ключевые концепции Microsoft Defender для конечной точки
description: Техническая схема для Microsoft Defender для конечной точки в Microsoft 365 Defender поможет вам понять личность в Microsoft 365 перед созданием пробной лаборатории или пилотной среды.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-jweston
author: jweston-1
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 4df1ac2ca5fdfaa88ec2d08c85112f52da26b873
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458604"
---
# <a name="review-microsoft-defender-for-endpoint-architecture-requirements-and-key-concepts"></a>Просмотрите требования к архитектуре Конечной точки и ключевые концепции Microsoft Defender для конечной точки

**Применяется к:** Microsoft 365 Defender

Эта статья поможет вам в процессе настройки оценки для среды Microsoft Defender для конечной точки.

Дополнительные сведения об этом процессе см. в статье [обзор.](eval-defender-endpoint-overview.md)

Прежде чем включить Microsoft Defender для конечной точки, убедитесь, что вы понимаете архитектуру и можете соответствовать требованиям.

## <a name="understand-the-architecture"></a>Знакомство с архитектурой

Следующая схема иллюстрирует архитектуру и интеграцию Microsoft Defender для конечных точек. 

![Действия по добавлению Microsoft Defender для Office среды оценки Defender](../../media/defender/m365-defender-endpoint-architecture.png)

В следующей таблице описывается иллюстрация.

Вызов | Описание
:---|:---|
1 | Устройства находятся на борту с помощью одного из поддерживаемых средств управления. 
2 | На бортовые устройства предоставляют и реагируют на данные сигнала Microsoft Defender для конечных точек.
3 | Управляемые устройства присоединяются и/или регистрются в Azure Active Directory.
4  | Устройства с Windows 10 с доменом синхронизируются с Azure Active Directory с Azure Active Directory Подключение.
5  | Microsoft Defender для оповещений конечной точки, расследований и ответов управляется в Microsoft 365 Defender.

## <a name="understand-key-concepts"></a>Понимание ключевых понятий

В следующей таблице определены ключевые понятия, которые важны для понимания при оценке, настройке и развертывании Microsoft Defender для конечной точки: 

Понятие | Описание | Дополнительная информация
:---|:---|:---|
Портал администрирования | Microsoft 365 Defender для мониторинга и оказания помощи в реагировании на оповещения о потенциальной постоянной угрозе или нарушениях данных. | [Обзор портала Microsoft Defender для конечных точек](/defender-endpoint/portal-overview)
Уменьшение поверхности атаки | Помогите уменьшить поверхности атак, минимизируя места, в которых ваша организация уязвима для киберугроз и атак. | [Обзор сокращения направлений атак](/defender-endpoint/overview-attack-surface-reduction)
Обнаружение и реагирование конечных точек | Возможности обнаружения и реагирования конечных точек обеспечивают расширенные обнаружения атак, которые находятся в режиме реального времени и могут быть готовы к действию. | [Обзор обнаружение и нейтрализация атак на конечные точки возможностей](/defender-endpoint/overview-endpoint-detection-response)
Поведенческая блокировка и сдерживание | Возможности поведенческой блокировки и сдерживания могут помочь определить и остановить угрозы, основываясь на их поведении и деревьях обработки даже при выполнении угрозы. | [Блокировка с учетом поведения и автономность](/defender-endpoint/behavioral-blocking-containment)
Автоматическое исследование и ответ | Автоматизированное расследование использует различные алгоритмы проверки на основе процессов, используемых аналитиками безопасности и предназначенных для проверки оповещений и принятия незамедлительных действий для устранения нарушений. | [Использование автоматизированных расследований для расследования и устранения угроз](/defender-endpoint/automated-investigations)
Расширенная охота | Расширенный поиск — это средство охоты на угрозы на основе запросов, которое позволяет исследовать до 30 дней необработанных данных, чтобы можно было активно проверять события в сети, чтобы найти индикаторы и объекты угрозы. | [Обзор передовой охоты](/defender-endpoint/advanced-hunting-overview)
Аналитика угроз | Аналитика угроз — это набор отчетов экспертов microsoft security researchers, охватывающих наиболее релевантные угрозы. | [Отслеживание возникающих угроз и реагирование на них](/defender-endpoint/threat-analytics)


Дополнительные сведения о возможностях, включенных в Microsoft Defender для конечной точки, см. в дополнительных сведениях о том, что такое [Microsoft Defender для конечной точки.](/defender-endpoint/microsoft-defender-endpoint)

## <a name="siem-integration"></a>Интеграция SIEM

Вы можете интегрировать Microsoft Defender для конечной точки с Azure Sentinel для более полного анализа событий безопасности в организации и создания книг для эффективного и немедленного реагирования. 

Microsoft Defender для конечной точки также может быть интегрирован в другие решения по управлению сведениями о безопасности и событиями (SIEM). Дополнительные сведения см. в [веб-сайте Включить интеграцию SIEM в Microsoft Defender для конечной точки.](/defender-endpoint/enable-siem-integration)


## <a name="next-steps"></a>Дальнейшие действия
[Включить оценку](eval-defender-endpoint-enable-eval.md)

Возвращение к обзору [оценки Microsoft Defender для конечной точки](eval-defender-endpoint-overview.md)

Возвращайся к обзору [для оценки и пилотных Microsoft 365 Defender](eval-overview.md)