---
title: Новые возможности оценки безопасности Майкрософт
description: В этой статье описано, какие изменения были внесены в оценку безопасности Майкрософт в центре безопасности Майкрософт 365.
keywords: Оценка безопасности Майкрософт, Оценка безопасности, Оценка безопасности Office 365, Оценка безопасности Майкрософт, центр безопасности Майкрософт 365
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 6d1358da465bd7e31ca7b234f140aa8e48bb7508
ms.sourcegitcommit: aa8d2de6ffac0157fffd14d0ea7f51ef0c287607
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2020
ms.locfileid: "49373999"
---
# <a name="whats-new-in-microsoft-secure-score"></a>Новые возможности оценки безопасности Майкрософт

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Чтобы сделать Microsoft Secure рейтинг более подходящим для вашей безопасности, мы внесли некоторые изменения. Чтобы узнать о запланированных изменениях, посмотрите, [что поступает в рейтинге безопасности Майкрософт?](microsoft-secure-score-whats-coming.md).

Оценку безопасности Майкрософт можно найти https://security.microsoft.com/securescore в [центре безопасности Майкрософт 365](overview-security-center.md).

## <a name="november-2020"></a>Ноябрь 2020 г.

### <a name="added-3-services-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a>Добавлено 3 действия по улучшению, связанные со службами, для защитника Майкрософт для конечной точки (ранее для защитника Майкрософт):

- Исправление пути службы без кавычек для служб Windows
- Изменение пути к исполняемому файлу службы на общее защищенное расположение
- Изменение учетной записи службы для предотвращения кэширования паролей в реестре Windows

## <a name="october-2020"></a>Октябрь 2020 г.

### <a name="remove-improvement-action-related-to-microsoft-defender-for-endpoint"></a>Удаление действия улучшения, связанного с защитником Майкрософт для конечной точки

- Настройка фильтра SmartScreen защитника Майкрософт веб-контент приложения Windows Store для предупреждения

## <a name="august-2020"></a>Август 2020 г.

### <a name="updated-improvement-action-for-azure-active-directory"></a>Обновленное действие по улучшению для Azure Active Directory

- Включение политики для блокирования устаревшей проверки подлинности

## <a name="incompatibility-with-identity-secure-score-and-graph-api"></a>Несовместимость с оценками безопасности удостоверения и Graph API

В последней версии оценки безопасности Майкрософт была выпущена улучшенная модель оценки. Эти изменения обеспечивают более гибкое и точное представление обеспечения безопасности. Тем не менее, они временно несовместимы с оценкой безопасности Identity и API Graph.

В течение времени, Оценка безопасности удостоверения и API Graph приведут к новой модели определения показателей. Пока пользователи не увидят отличия от оценки безопасности Майкрософт, оценки безопасности удостоверения и API Graph. Приносим извинения за все неудобства, которые приносятся к этому, и работают над обеспечением совместимости этих возможностей в будущем.

## <a name="updated-improvement-actions"></a>Обновленные действия по улучшению

- Добавлены действия по улучшению Azure Active Directory
- Добавлены сведения о защитнике Майкрософт для действий по улучшению удостоверения
- Рекомендации по обеспечению безопасности уязвимостей защитником Майкрософт для конечных точек [& уязвимостей](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
    - Все выпущенные рекомендации по безопасности, предоставляемые ТВМ, теперь доступны

## <a name="updated-interface-and-functionality"></a>Обновленный интерфейс и функциональные возможности

* Все новые показатели и тенденции для ЦИСО и дискуссий на уровне ведущего
* Новые способы отслеживания и оценки оценки
* Улучшение отслеживания и понимания регрессий для оценок
* Фильтрация, пометка, Поиск и группировка действий по улучшению
* Управляйте своими будущими целями, используя проекции оценок и запланированные действия
* И многое другое!

## <a name="we-want-to-hear-from-you"></a>Мы хотим услышать вас

Если у вас возникли какие – либо проблемы, сообщите нам о публикации в разделе [безопасность, конфиденциальность & соответствие требованиям](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) . Мы отслеживаем сообщество и предоставите вам помощь.

## <a name="related-resources"></a>Связанные ресурсы

- [Оценка уровня безопасности](microsoft-secure-score-improvement-actions.md)
- [Отслеживание журнала оценки безопасности Майкрософт и соответствующих целей](microsoft-secure-score-history-metrics-trends.md)
- [Что вскоре появится](microsoft-secure-score-whats-coming.md)
