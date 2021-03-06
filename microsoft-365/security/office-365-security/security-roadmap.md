---
title: Microsoft 365 безопасности — главные приоритеты
f1.keywords:
- NOCSH
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 10/08/2018
audience: Admin
ms.topic: conceptual
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
ms.assetid: 28c86a1c-e4dd-4aad-a2a6-c768a21cb352
description: Рекомендации группы кибербезопасности Корпорации Майкрософт по внедрению возможностей безопасности для защиты Microsoft 365 среды.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 05ea4103abecb10d4eedddf8d5043e339b58804c
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083156"
---
# <a name="security-roadmap---top-priorities-for-the-first-30-days-90-days-and-beyond"></a>Дорожная карта безопасности — главные приоритеты для первых 30 дней, 90 дней и более

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


В этой статье содержатся рекомендации группы кибербезопасности Корпорации Майкрософт по внедрению возможностей безопасности для защиты Microsoft 365 среды. Эта статья адаптирована из сеанса Microsoft Ignite — secure Microsoft 365 как профессиональный кибербезопасность: главные приоритеты в течение первых [30 дней, 90](https://www.youtube.com/watch?v=luignzNyR-o)дней и далее . Этот сеанс был разработан и представлен Марком Симосом и Мэттом Кемелхаром, Enterprise архитекторами кибербезопасности.

В этой статье

- [Результаты roadmap](security-roadmap.md#Roadmap)
- [30 дней — мощные быстрые победы](security-roadmap.md#Thirdaydays)
- [90 дней — расширенные средства защиты](security-roadmap.md#Ninetydays)
- [Beyond](security-roadmap.md#Beyond)

## <a name="roadmap-outcomes"></a>Результаты roadmap
<a name="Roadmap"> </a>

Эти рекомендации дорожной карты поэтапно в три этапа в логическом порядке со следующими целями.

****

|Сроки|Результаты|
|---|---|
|30 дней|Быстрая конфигурация: <ul><li>Основные средства защиты администратора.</li><li>Ведение журнала и аналитика.</li><li>Основные средства защиты удостоверений.</li></ul> <p> Конфигурация клиента. <p> Подготовка заинтересованных лиц.|
|90 дней|Расширенные средства защиты: <ul><li>Учетные записи администратора.</li><li>Данные и учетные записи пользователей.</li></ul> <p> Видимость соответствия требованиям, угрозам и потребностям пользователей. <p> Адаптация и реализация политик и защиты по умолчанию.|
|Beyond|Настройка и уточнение ключевых политик и элементов управления. <p> Расширение защиты для локальной зависимости. <p> Интеграция с бизнес-процессами и процессами безопасности (юридическая, внутренняя угроза и т.д.).|
|

## <a name="30-days--powerful-quick-wins"></a>30 дней — мощные быстрые победы
<a name="Thirdaydays"> </a>

Эти задачи выполняются быстро и почти не влияют на пользователей.

****

|Область|Задачи|
|---|---|
|Управление безопасностью|<ul><li>Проверьте безопасную оценку и обратите внимание на текущий результат ( <https://securescore.office.com> ).</li><li>Включи журнал аудита для Office 365. См. [журнал поиска аудита.](../../compliance/search-the-audit-log-in-security-and-compliance.md)</li><li>[Настройка Microsoft 365 для повышения безопасности.](tenant-wide-setup-for-increased-security.md)</li><li>Регулярно просматривайте панели мониторинга и отчеты на портале Microsoft 365 Defender и Cloud App Security.</li></ul>|
|Защита от угроз|[Подключение Microsoft 365 Microsoft Cloud App Security](/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) начать мониторинг с помощью политик обнаружения угроз по умолчанию для аномального поведения. Создание базовой базы для обнаружения аномалий занимает семь дней. <p>  Реализация защиты учетных записей администратора:<ul><li>Используйте выделенные учетные записи администратора для действий администратора.</li><li>Обеспечение многофакторной проверки подлинности (MFA) для учетных записей администратора.</li><li>Используйте [высокобезопасный Windows 10 для](/windows-hardware/design/device-experiences/oem-highly-secure) действий администратора.</li></ul>|
|Управление идентификацией и доступом|<ul><li>[Включить Azure Active Directory identity Protection](/azure/active-directory/active-directory-identityprotection-enable).</li><li>В федерадных средах удостоверений применяйте безопасность учетных записей (длина пароля, возраст, сложность и т.д.).</li></ul>|
|Защита информации|Просмотрите примеры рекомендаций по защите информации. Защита информации требует координации по всей организации. Приступите к работе с помощью этих ресурсов:<ul><li>[Защита информации в Office 365 в соответствии с GDPR](/compliance/regulatory/gdpr)</li><li>[Настройка Teams](../../solutions/configure-teams-three-tiers-protection.md) с тремя уровнями защиты (включает общий доступ, классификацию, предотвращение потери данных и защиту информации Azure)</li></ul>|
|

## <a name="90-days--enhanced-protections"></a>90 дней — расширенные средства защиты
<a name="Ninetydays"> </a>

Планирование и реализация этих задач занимают немного больше времени, но это значительно повысит безопасность ваших данных.

****

|Область|Задача|
|---|---|
|Управление безопасностью|<ul><li>Проверьте безопасную оценку рекомендуемых действий для вашей среды ( <https://securescore.office.com> ).</li><li>Продолжайте регулярно проверять панели мониторинга и отчеты на портале Microsoft 365 Defender, Cloud App Security и средствах SIEM.</li><li>Найми и реализуй обновления программного обеспечения.</li><li>Проведение имитации атак для фишинга, спрея паролей и атак с использованием методов моделирования атак [(в](attack-simulation-training.md) том числе с [Office 365 Threat Intelligence).](office-365-ti.md)</li><li>Просмотрите встроенные отчеты в Cloud App Security (на вкладке Исследование).</li><li>Проверьте [диспетчер соответствия](../../compliance/compliance-manager.md) требованиям, чтобы просмотреть состояние правил, применимых к вашей организации (например, GDPR, NIST 800-171).</li></ul>|
|Защита от угроз|Реализация расширенной защиты учетных записей администратора: <ul><li>Настройка [рабочих станций привилегированного](/security/compass/privileged-access-devices) доступа (PAW) для действий администратора.</li><li>Настройка [azure AD управление привилегированными пользователями](/azure/active-directory/active-directory-privileged-identity-management-configure).</li><li>Настройте средство управления сведениями о безопасности и событиями (SIEM) для сбора данных ведения журнала из Office 365, Cloud App Security и других служб, включая AD FS. Журнал аудита хранит данные только в течение 90 дней. Хранение этих данных в средстве SIEM позволяет хранить данные в течение более длительного периода времени.</li></ul>|
|Управление идентификацией и доступом|<ul><li>Включить и применить MFA для всех пользователей.</li><li>Реализация набора [условных политик доступа и связанных политик.](microsoft-365-policies-configurations.md)</li></ul>|
|Защита информации| Адаптация и реализация политик защиты информации. К этим ресурсам относятся примеры: <ul><li>[Защита информации в Office 365 в соответствии с GDPR](/compliance/regulatory/gdpr)</li><li>[Настройка Teams с тремя уровнями защиты](../../solutions/configure-teams-three-tiers-protection.md)</li></ul> <p> Используйте политики предотвращения потери данных и средства мониторинга Microsoft 365 для данных, хранимых в Microsoft 365 (а не Cloud App Security). <p> Используйте Cloud App Security с Microsoft 365 для расширенных функций оповещения (кроме предотвращения потери данных).|
|

## <a name="beyond"></a>Beyond
<a name="Beyond"> </a>

Это важные меры безопасности, которые строятся на предыдущей работе.

****

|Область|Задача|
|---|---|
|Управление безопасностью|<ul><li>Продолжить планирование следующих действий с помощью secure Score ( <https://securescore.office.com> ).</li><li>Продолжайте регулярно проверять панели мониторинга и отчеты на портале Microsoft 365 Defender, Cloud App Security и средствах SIEM.</li><li>Продолжайте искать и внедрять обновления программного обеспечения.</li><li>Интеграция eDiscovery в процессы реагирования на юридические и угрозы.</li></ul>|
|Защита от угроз|<ul><li>Реализация [безопасного привилегированного](/windows-server/identity/securing-privileged-access/securing-privileged-access) доступа (SPA) для компонентов удостоверений в помещениях (AD, AD FS).</li><li>Используйте Cloud App Security для отслеживания инсайдерской угрозы.</li><li>Откройте для себя использование теневого ИТ-SaaS с помощью Cloud App Security.</li></ul>|
|Управление идентификацией и доступом|<ul><li>Уточнение политик и операционных процессов.</li><li>Используйте Службу Azure AD Identity Protection для выявления инсайдерской угрозы.</li></ul>|
|Защита информации|Уточнение политик защиты информации: <ul><li>Microsoft 365 и Office 365 метки конфиденциальности и предотвращение потери данных (DLP) или Azure Information Protection.</li><li>Cloud App Security политик и оповещений.</li></ul>|
|

См. также: Как смягчить быстрые кибератаки, такие как [Petya и WannaCrypt.](https://cloudblogs.microsoft.com/microsoftsecure/2018/02/21/how-to-mitigate-rapid-cyberattacks-such-as-petya-and-wannacrypt/)
