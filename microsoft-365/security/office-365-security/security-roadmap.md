---
title: 'План безопасности Microsoft 365 : главные приоритеты'
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
description: Рекомендации от группы майкрософт по кибербезопасности по реализации возможностей безопасности для защиты среды Microsoft 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a7d376eb7266975dc7582b83bfd4fa5e930ccea4
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288173"
---
# <a name="security-roadmap---top-priorities-for-the-first-30-days-90-days-and-beyond"></a>План безопасности : приоритеты на первые 30, 90 и более дней

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


В этой статье содержатся рекомендации от группы майкрософт по кибербезопасности по реализации возможностей безопасности для защиты среды Microsoft 365. Эта статья адаптирована из сеанса Microsoft Ignite — защита Microsoft 365, как для кибербезопасности: первые приоритеты на первые [30, 90](https://www.youtube.com/watch?v=luignzNyR-o)и более дней. Этот сеанс был разработан и представлен Марком Симосом (Mark Simos) и Майклом Кенхааром (Matt Keharhar), корпоративными архитекторами кибербезопасности.

В этой статье

- [Результаты работы с планами](security-roadmap.md#Roadmap)
- [30 дней — мощные быстрые решения](security-roadmap.md#Thirdaydays)
- [90 дней — расширенные средства защиты](security-roadmap.md#Ninetydays)
- [За пределами](security-roadmap.md#Beyond)

## <a name="roadmap-outcomes"></a>Результаты работы с планами
<a name="Roadmap"> </a>

Эти рекомендации по плану поэтапно разбиты на три этапа в логическом порядке с указанными ниже целями.

****

|Период времени|Результаты|
|---|---|
|30 дней|Быстрая настройка: <ul><li>Основные средства защиты администратора.</li><li>Ведение журнала и аналитика.</li><li>Основные средства защиты удостоверений.</li></ul> <p> Конфигурация клиента. <p> Подготовка заинтересованных лиц.|
|90 дней|Дополнительные средства защиты: <ul><li>Учетные записи администраторов.</li><li>Данные и учетные записи пользователей.</li></ul> <p> Видимость соответствия требованиям, угроз и потребностей пользователей. <p> Адаптируем и реализуем политики и средства защиты по умолчанию.|
|За пределами|Настройка и уточнение ключевых политик и элементов управления. <p> Расширение защиты для зависимостей локальной среды. <p> Интеграция с бизнес-процессами и процессами безопасности (юридические, внутренние угрозы и т. д.).|
|

## <a name="30-days--powerful-quick-wins"></a>30 дней — мощные быстрые решения
<a name="Thirdaydays"> </a>

Эти задачи выполняются быстро и почти не влияют на пользователей.

****

|Область|Задачи|
|---|---|
|Управление безопасностью|<ul><li>Проверьте оценку безопасности и заметьте текущую оценку ( <https://securescore.office.com> ).</li><li>Включив ведение журнала аудита для Office 365. См. [поиск в журнале аудита.](../../compliance/search-the-audit-log-in-security-and-compliance.md)</li><li>[Настройка Microsoft 365 для повышения безопасности.](tenant-wide-setup-for-increased-security.md)</li><li>Регулярно просматривайте панели мониторинга и отчеты в Центре безопасности Microsoft 365 и Cloud App Security.</li></ul>|
|Защита от угроз|[Подключите Microsoft 365 к Microsoft Cloud App Security,](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) чтобы начать мониторинг с помощью политик обнаружения угроз по умолчанию для аномального поведения. Создание базового плана для обнаружения аномалий занимает семь дней. <p>  Реализация защиты учетных записей администраторов:<ul><li>Используйте выделенные учетные записи администраторов для действий администратора.</li><li>Обеспечение многофакторной проверки подлинности (MFA) для учетных записей администраторов.</li><li>Используйте устройство [с Windows 10 с высокой безопасностью](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-highly-secure) для действий администратора.</li></ul>|
|Управление идентификацией и доступом|<ul><li>[Включить защиту идентификации Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable)</li><li>Для федератных сред удостоверений принудительно применяйте безопасность учетных записей (длина пароля, возраст, сложность и т. д.).</li></ul>|
|Защита информации|Просмотрите примеры рекомендаций по защите информации. Для защиты информации требуется координация во всей организации. Приступите к работе с помощью этих ресурсов:<ul><li>[Защита информации в Office 365 в соответствии с GDPR](https://aka.ms/o365gdpr)</li><li>[Настройка Teams с тремя уровнями](../../solutions/configure-teams-three-tiers-protection.md) защиты (включая общий доступ, классификацию, защиту от потери данных и Azure Information Protection)</li></ul>|
|

## <a name="90-days--enhanced-protections"></a>90 дней — расширенные средства защиты
<a name="Ninetydays"> </a>

Планирование и реализация этих задач занимают немного больше времени, но это значительно повысит безопасность ваших данных.

****

|Область|Task|
|---|---|
|Управление безопасностью|<ul><li>Проверьте оценку безопасности на рекомендуемые действия для вашей среды ( <https://securescore.office.com> ).</li><li>Продолжайте регулярно проверять панели мониторинга и отчеты в Центре безопасности Microsoft 365, Cloud App Security и средствах SIEM.</li><li>Найми и реализуй обновления программного обеспечения.</li><li>Проводите моделирование атак для фишинга, распыления паролей и [](attack-simulator.md) атак методом атак с помощью имитатора атак (включаемого в [Office 365 Threat Intelligence).](office-365-ti.md)</li><li>Найди риск общего доступа, просмотрев встроенные отчеты в Cloud App Security (на вкладке "Исследование").</li><li>Проверьте [в диспетчере](../../compliance/compliance-manager.md) соответствия требованиям состояние нормативов, применимых к вашей организации (например, GDPR, NIST 800-171).</li></ul>|
|Защита от угроз|Внедрить расширенные средства защиты для учетных записей администраторов: <ul><li>Настройка [рабочих станций привилегированного доступа](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/privileged-access-workstations) (PAW) для действий администратора.</li><li>Настройка [azure AD Privileged Identity Management.](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)</li><li>Настройте средство SIEM для сбора данных журналов из Office 365, Cloud App Security и других служб, включая AD FS. В журнале аудита данные хранится только 90 дней. Запись этих данных в средстве SIEM позволяет хранить данные в течение более длительного периода.</li></ul>|
|Управление идентификацией и доступом|<ul><li>Включить и применить MFA для всех пользователей.</li><li>Реализация набора [условного доступа и связанных политик.](microsoft-365-policies-configurations.md)</li></ul>|
|Защита информации| Адаптация и внедрение политик защиты информации. К этим ресурсам относятся примеры: <ul><li>[Защита информации в Office 365 в соответствии с GDPR](https://aka.ms/o365gdpr)</li><li>[Настройка Teams с тремя уровнями защиты](../../solutions/configure-teams-three-tiers-protection.md)</li></ul> <p> Используйте политики защиты от потери данных и средства мониторинга в Microsoft 365 для данных, хранимых в Microsoft 365 (а не Cloud App Security). <p> Используйте Cloud App Security с Microsoft 365 для расширенных функций оповещения (кроме защиты от потери данных).|
|

## <a name="beyond"></a>За пределами
<a name="Beyond"> </a>

Это важные меры безопасности, которые на основе предыдущей работы.

****

|Область|Task|
|---|---|
|Управление безопасностью|<ul><li>Продолжить планирование следующих действий с помощью оценки безопасности ( <https://securescore.office.com> ).</li><li>Продолжайте регулярно проверять панели мониторинга и отчеты в Центре безопасности Microsoft 365, Cloud App Security и средствах SIEM.</li><li>Продолжайте искать и внедрять обновления программного обеспечения.</li><li>Интеграция eDiscovery в юридические процессы и процессы реагирования на угрозы.</li></ul>|
|Защита от угроз|<ul><li>Реализация [безопасного привилегированного доступа](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access) (SPA) для компонентов удостоверений в локальной сети (AD, AD FS).</li><li>Используйте Cloud App Security для отслеживания угроз внутри системы.</li><li>Обнаружение теневого использования ИТ-SaaS с помощью Cloud App Security.</li></ul>|
|Управление идентификацией и доступом|<ul><li>Уточнение политик и операционных процессов.</li><li>Используйте защиту идентификации Azure AD для выявления угроз внутри системы.</li></ul>|
|Защита информации|Уточнение политик защиты информации: <ul><li>Метки конфиденциальности Microsoft 365 и Office 365 и защита от потери данных (DLP) или Azure Information Protection.</li><li>Политики и оповещения Cloud App Security.</li></ul>|
|

См. также: как устранить быстрые кибератаки, такие как [Петя и WannaCrypt.](https://cloudblogs.microsoft.com/microsoftsecure/2018/02/21/how-to-mitigate-rapid-cyberattacks-such-as-petya-and-wannacrypt/)
