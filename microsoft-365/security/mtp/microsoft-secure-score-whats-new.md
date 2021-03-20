---
title: Новые возможности в Microsoft Secure Score
description: Описывает, какие изменения произошли с Microsoft Secure Score в центре безопасности Microsoft 365.
keywords: microsoft secure score, secure score, office 365 secure score, microsoft security score, Microsoft 365 security center
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 7d24d010f7c16d6db0fd4f9e4817768529ed29d1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906750"
---
# <a name="whats-new-in-microsoft-secure-score"></a>Новые возможности в Microsoft Secure Score

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Чтобы сделать Microsoft Secure Score лучшим представителем вашей позиции в области безопасности, мы внося некоторые изменения. Чтобы узнать о запланированных изменениях, см. в записи "Что [будет в Microsoft Secure Score"?](microsoft-secure-score-whats-coming.md)

Microsoft Secure Score можно найти в https://security.microsoft.com/securescore [центре безопасности Microsoft 365.](overview-security-center.md)
    
## <a name="february-2021"></a>Февраль 2021 г.

### <a name="compatibility-with-graph-api"></a>Совместимость с API Graph

Рекомендации Microsoft Secure Score, доставленные с помощью API graph, будут выглядеть и взвешиться так же, как рекомендации, которые в настоящее время вы видите в центре безопасности Microsoft 365.

## <a name="january-2021"></a>Январь 2021 г.

### <a name="added-our-first-security-recommendation-for-microsoft-teams"></a>Добавлена наша первая рекомендация по безопасности для Microsoft Teams

Клиенты Microsoft Teams увидят "Ограничение анонимным пользователям присоединения к собраниям" в качестве нового действия по улучшению в Secure Score.

## <a name="december-2020"></a>Декабрь 2020 г.

### <a name="added-six-accounts-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a>Добавлено шесть действий по улучшению учетных записей для Microsoft Defender для конечной точки (ранее ATP Защитника Майкрософт):

- Установите "Минимальная длина пароля" до "14 или более символов"
- Установите "Принудить историю паролей" к '24 или более паролей (s)'
- Установите "Максимальный возраст пароля" до "60 или меньше дней, но не 0"
- Установите "Минимальный возраст пароля" до "1 или более дней(ы)"
- Отключение встроенной учетной записи администратора
- Отключение встроенной гостевой учетной записи

## <a name="november-2020"></a>Ноябрь 2020 г.

### <a name="removed-the-ability-to-create-servicenow-tickets-through-secure-score"></a>Удалена возможность создания билетов ServiceNow с помощью secure Score 

Возможность создания билетов ServiceNow с помощью secure Score с **помощью share > ServiceNow** больше недоступна. Благодарим вас за отзывы и поддержку, пока мы определяем дальнейшие действия.

### <a name="added-three-services-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a>Добавлены три действия по улучшению, связанные с службами для Microsoft Defender для конечной точки (ранее ATP Защитника Майкрософт):

- Исправление пути неквалификации службы Windows
- Изменение исполняемого пути службы в общее защищенное расположение
- Изменение учетной записи службы, чтобы избежать кэшного пароля в реестре Windows

## <a name="october-2020"></a>Октябрь 2020 г.

### <a name="remove-improvement-action-related-to-microsoft-defender-for-endpoint"></a>Удаление действия по улучшению, связанного с Microsoft Defender для конечной точки

- Установите проверку веб-контента приложения Microsoft Defender SmartScreen Windows Store, чтобы предупредить

## <a name="august-2020"></a>Август 2020 г.

### <a name="updated-improvement-action-for-azure-active-directory"></a>Обновленное действие по улучшению для Azure Active Directory

- Включить политику для блокировки устаревшей проверки подлинности

## <a name="incompatibility-with-identity-secure-score"></a>Несовместимость с показателем безопасности удостоверений

В недавнем выпуске Microsoft Secure Score была выпущена улучшенная модель оценки. Эти изменения позволяют обеспечить более гибкое и точное представление о вашей позиции безопасности. Однако эти обновления сделали Microsoft Secure Score временно несовместимой с показателем безопасности удостоверений.

Со временем, identity Secure Score примет новую модель скоринга. До этого времени клиенты будут видеть различия в оценках, отчитающихся в Microsoft Secure Score и Показателе безопасности удостоверений. Мы приносим свои извинения за все неудобства, которые это вызывает, и работаем над тем, чтобы обеспечить более совместимость этих опытом в будущем.

## <a name="updated-improvement-actions"></a>Обновленные действия по улучшению

- Добавлены действия по улучшению Azure Active Directory
- Добавлены действия по улучшению удостоверений в Microsoft Defender
- Поддержка рекомендаций по безопасности управления & [угрозы конечной](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) точки Microsoft Defender
    - Все выпущенные рекомендации по безопасности, предоставленные TVM, теперь доступны

## <a name="updated-interface-and-functionality"></a>Обновленный интерфейс и функциональные возможности

* Все новые представления показателей и тенденций для ciSO и обсуждений на уровне свинца
* Новые способы отслеживания и оценки результатов
* Улучшение отслеживания и понимания регрессий показателей
* Фильтрация, теги, поиск и группа действий по улучшению
* Управление будущими целями с помощью проекций показателей и запланированных действий
* И еще!

## <a name="we-want-to-hear-from-you"></a>Мы ждем ваших отзывов!

Если у вас есть какие-либо проблемы, дайте нам знать, разместив в сообществе [безопасность, конфиденциальность & соответствия](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) требованиям. Мы отслеживаем сообщество и предоставляем помощь.

## <a name="related-resources"></a>Связанные ресурсы

- [Оценка уровня безопасности](microsoft-secure-score-improvement-actions.md)
- [Отслеживание истории microsoft Secure Score и достижения целей](microsoft-secure-score-history-metrics-trends.md)
- [Что вскоре появится](microsoft-secure-score-whats-coming.md)