---
title: Новые возможности центра соответствия требованиям Microsoft 365
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Будь то добавление новых решений в центр соответствия требованиям, обновление существующих функций на основе отзывов или развертывание свежей и обновленной документации, Microsoft 365 поможет вам оставаться на вершине постоянно меняющегося ландшафта соответствия требованиям. Узнайте, чем мы были в этом месяце.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1884989abba56a7da68a2a1372132015a81f5e03
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985016"
---
# <a name="whats-new-in-microsoft-365-compliance"></a>Новые возможности центра соответствия требованиям Microsoft 365

Будь то добавление новых решений в [Центр соответствия требованиям Microsoft 365,](microsoft-365-compliance-center.md)обновление существующих функций на основе отзывов или развертывание свежей и обновленной документации, Microsoft 365 поможет вам оставаться на вершине постоянно меняющегося ландшафта соответствия требованиям. См. ниже, чтобы узнать, что нового в Microsoft 365 соответствия требованиям.

> [!NOTE]
> Некоторые функции соответствия требованиям выкатываются с разной скоростью для наших клиентов. Если вы еще не видите функцию, попробуйте добавить себя в [целевой выпуск](/office365/admin/manage/release-options-in-office-365).

> [!TIP]
> Интересует, что происходит в других центрах администрирования? Ознакомьтесь с этими статьями:<br>[Что нового в Центр администрирования Microsoft 365](/office365/admin/whats-new-in-preview)<br>[Новые возможности центра администрирования SharePoint](/sharepoint/what-s-new-in-admin-center)<br>[Новые возможности Microsoft 365 Defender](../security/defender/whats-new.md)<br><br>
И посетите [Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap) дорожную карту, чтобы узнать Microsoft 365, которые были запущены, запущены, находятся в разработке, отменены или ранее выпущены.

## <a name="may-2021"></a>Май 2021 г.

### <a name="data-loss-prevention"></a>Защита от потери данных

- Новые рекомендации по [планированию стратегии предотвращения потери](dlp-overview-plan-for-dlp.md) данных.

### <a name="retention-and-records-management"></a>Управление хранением и записями

- Если вы освобождаете политику хранения с веб-SharePoint или OneDrive учетной записи, вам больше не придется ждать 30-дневного льготного периода, прежде чем можно удалить сайт или учетную запись. Популярный запрос клиентов, это изменение теперь завершено для всех клиентов.
- В предварительном просмотре можно просмотреть многоступенчатый обзор диспозиции. Теперь администратор может добавлять до пяти последовательных этапов проверки диспозиции для метки хранения, а рецензенты могут добавлять других пользователей в стадию рассмотрения диспозиции.  [](disposition.md) Вы также можете настроить уведомления и напоминания по электронной почте.

### <a name="sensitive-information-types"></a>Типы конфиденциальных сведений

- Добавлены новые сведения, которые помогут [изменить словарь ключевых слов.](sit-modify-keyword-dictionary.md)

### <a name="sensitivity-labels"></a>Метки конфиденциальности

- При настройке метки  конфиденциальности для групп и сайтов теперь доступен новый параметр для контекста [проверки подлинности.]( sensitivity-labels-teams-groups-sites.md) Этот параметр работает совместно с политиками условного доступа Azure AD для обеспечения более строгих условий при доступе пользователей SharePoint сайтов с меткой. Перед настройкой [](sensitivity-labels-teams-groups-sites.md#more-information-about-the-dependencies-for-the-authentication-context-option) этого параметра убедитесь, что вы читаете зависимости и ограничения.
- [Политики автоматической](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange) маркировки, настроенные только для Exchange, теперь поддерживают метки  конфиденциальности, применяющие шифрование с помощью разрешить пользователям назначать разрешения для параметров Do Not Forward или Encrypt-Only.
- [Обязательная маркировка](sensitivity-labels-office-apps.md#require-users-to-apply-a-label-to-their-email-and-documents) теперь, как правило, доступна для всех Office приложений на всех платформах.

## <a name="april-2021"></a>Апрель 2021 г.

### <a name="advanced-ediscovery"></a>Advanced eDiscovery

- [Ограничения в Advanced eDiscovery](/microsoft-365/compliance/limits-ediscovery20#export-limits---final-export-out-of-review-set). Теперь организации могут экспортировать до 5 миллионов элементов или 500 МБ, в зависимости от того, меньше, в одном экспорте элементов из набора обзоров.

### <a name="data-classification"></a>Классификация данных

- [Действия по маркировке, доступные в проводнике действий](/microsoft-365/compliance/data-classification-activity-explorer-available-events)

### <a name="data-connectors"></a>Соединители данных

- [Настройка соединителя для архива Cisco Jabber в данных Oracle](/microsoft-365/compliance/archive-ciscojabberonoracle-data)
- [Настройка соединителя для архива Cisco Jabber на данных PostgreSQL](/microsoft-365/compliance/archive-ciscojabberonpostgresql-data)

### <a name="data-loss-prevention"></a>Защита от потери данных

- Новая тема для [рекомендаций по предотвращению потери](/microsoft-365/compliance/dlp-policy-tips-reference)данных.
- Новая тема для [Сведения о предотвращении потери данных.](/microsoft-365/compliance/dlp-learn-about-dlp)
- Новая тема для [Начала работы с информационной панелью](/microsoft-365/compliance/dlp-alerts-dashboard-get-started)оповещений о предотвращении потери данных.

### <a name="retention-policies-and-retention-label-policies"></a>Политики хранения и политики меток хранения

- Расположение Microsoft 365 Groups теперь поддерживает применение параметров хранения только для Microsoft 365 почтовых ящиков или только подключенных сайтов SharePoint с помощью [комлета Set-RetentionCompliancePolicy PowerShell](/powershell/module/exchange/set-retentioncompliancepolicy) с параметром *Applications.*

### <a name="sensitivity-labels"></a>Метки конфиденциальности

Outlook выпусков и обновлений:
- [Различные параметры метки по](sensitivity-labels-office-apps.md#outlook-specific-options-for-default-label-and-mandatory-labeling) умолчанию и обязательной маркировки теперь поддерживаются для встроенной маркировки. Ранее эти параметры поддерживались только клиентом единой маркировки AIP.
- [Шифрование теперь](encryption-sensitivity-labels.md#let-users-assign-permissions) поддерживается macOS, iOS и Android.
- [Обязательная маркировка](sensitivity-labels-office-apps.md#require-users-to-apply-a-label-to-their-email-and-documents) развертывается на оставшихся платформах.
- [Динамическая разметка со всеми переменными](sensitivity-labels-office-apps.md#dynamic-markings-with-variables) поддерживается во всех Outlook клиентах.

## <a name="march-2021"></a>Март 2021 г.

Вот несколько изменений, внесенных в Microsoft 365 решений и контента за март.

### <a name="advanced-ediscovery"></a>Advanced eDiscovery

- **Advanced eDiscovery коллекции** теперь поддерживают новый инструмент и рабочий [процесс коллекций.](/microsoft-365/compliance/collections-overview) Другие новые темы [включают создание черновика коллекции,](/microsoft-365/compliance/create-draft-collection)фиксацию [черновика](/microsoft-365/compliance/commit-draft-collection)коллекции в набор обзоров, а также статистику коллекций [и отчеты](/microsoft-365/compliance/collection-statistics-reports).
- **Экспорт документов в** обзоре, за набором для [служба хранилища Azure учетной записи.](/microsoft-365/compliance/download-export-jobs)
- **Модуль прогностического кодирования для Advanced eDiscovery**. Сначала взгляните на [новую](/microsoft-365/compliance/predictive-coding-overview) функциональность прогностического кодирования, которая заменяет ушедшего модуля релевантности.

### <a name="data-classification"></a>Классификация данных

- **Проводник классификации данных**. [Начало работы с](/microsoft-365/compliance/data-classification-activity-explorer) проводником классификации данных.

### <a name="data-connectors"></a>Соединители данных

- **Частные ключи**. Поддержка закрытых ключей добавлена в [данные Bloomberg Message,](/microsoft-365/compliance/archive-bloomberg-message-data#set-up-a-connector-using-public-keys) [данные ICE Chat](/microsoft-365/compliance/archive-icechat-data#set-up-a-connector-using-public-keys) и мгновенные соединители данных [Bloomberg.](/microsoft-365/compliance/archive-instant-bloomberg-data#set-up-a-connector-using-public-keys)

### <a name="data-loss-prevention"></a>Защита от потери данных

- **Microsoft Teams поддержки**. Поддержка защиты от потери данных распространяется [на Microsoft Teams](/microsoft-365/compliance/dlp-teams-default-policy).
- **Расширение соответствия требованиям Майкрософт.** Начало работы с [расширением соответствия требованиям Майкрософт.](/microsoft-365/compliance/dlp-chrome-get-started)

### <a name="encryption"></a>Шифрование

- **Ключ клиента для Microsoft 365**. [Обзор ключа клиента](/microsoft-365/compliance/customer-key-tenant-level) для Microsoft 365 на уровне клиента (общедоступный предварительный просмотр).
- **Двойное шифрование ключей**. Дополнительные возможности [поддержки помеченных](/microsoft-365/compliance/double-key-encryption) и защищенных документов можно узнать в SharePoint и OneDrive для бизнеса.

### <a name="insider-risk-management"></a>Управление внутренними рисками

В марте для общего просмотра были выпущены следующие обновления функции управления рисками изнутри:

- Новая функция аналитики для определения рисков перед созданием политик риска для инсайдеров
- Поддержка и управление службами обнаружения и управления последовательностью действий с новыми рисками
- Новая накопительная поддержка обнаружения эксфильтрации
- Новая поддержка отчетов о состоянии здоровья политик в приложении и рекомендации
- Новые функции журнала аудита и отчеты
- Улучшения мастера создания политики
- Обновления обозревателя контента
- Новый процесс управления пользователями/поддержка (добавление/удаление пользователей из политик)
- Новая поддержка интеграции AAD (уходя из службы поддержки политики пользователей)
- Обновленная поддержка домена в политиках (REGEX)
- Усовершенствования и улучшения шаблона политики

В поддержку этих новых функций были обновлены или добавлены следующие разделы:

- [Сведения об управлении внутренними рисками](/microsoft-365/compliance/insider-risk-management)
- [Планирование управления внутренними рисками](/microsoft-365/compliance/insider-risk-management-plan)
- [Начало работы с настройками управления рисками изнутри](/microsoft-365/compliance/insider-risk-management-settings)
- [Приступая к управлению рисками утечки внутренней информации](/microsoft-365/compliance/insider-risk-management-configure)
- [Создание политик в отношении внутренних рисков и управление ими](/microsoft-365/compliance/insider-risk-management-policies)
- [Расследование оповещений о внутренних рисках](/microsoft-365/compliance/insider-risk-management-alerts)
- [Принятие мер в случае внутренних рисков](/microsoft-365/compliance/insider-risk-management-cases)
- [Просмотр действий с помощью журнала аудита внутренних рисков](/microsoft-365/compliance/insider-risk-management-audit-log)
- [Просмотр данных с помощью обозревателя содержимого внутреннего риска](/microsoft-365/compliance/insider-risk-management-content-explorer)
- [Управление рабочий процесс с помощью панели мониторинга пользователей](/microsoft-365/compliance/insider-risk-management-users)

### <a name="records-management"></a>Управление записями

- **Улучшения плана файлов**. Обновление плана [файла удаляет](file-plan-manager.md) или улучшает предыдущие ограничения длины для импорта.
- **Удаление меток хранения для записей.** Выпуск предварительного просмотра поддерживает возможность удаления меток [хранения,](create-apply-retention-labels.md#deleting-retention-labels) которые пометят элементы в качестве записей.

### <a name="sensitive-information-types"></a>Типы конфиденциальной информации

Содержимое было добавлено или обновлено в следующих темах:

- [Начало работы с настраиваемой конфиденциальной информацией](/microsoft-365/compliance/create-a-custom-sensitive-information-type)
- [Сведения о типах конфиденциальной информации](/microsoft-365/compliance/sensitive-information-type-learn-about)
- [Создание пользовательских типов конфиденциальной информации с помощью классификации на основе точного совпадения данных](/microsoft-365/compliance/create-custom-sensitive-information-types-with-exact-data-match-based-classification)
- [Создание уведомлений для точных действий совпадения данных](/microsoft-365/compliance/sit-edm-notifications-activities)
- [Определения объекта типа конфиденциальной информации](/microsoft-365/compliance/sensitive-information-type-entity-definitions)
- [Создание настраиваемого типа конфиденциальной информации с помощью PowerShell](/microsoft-365/compliance/create-a-custom-sensitive-information-type-in-scc-powershell)
- [Создание словаря ключевых слов](/microsoft-365/compliance/create-a-keyword-dictionary)

### <a name="sensitivity-labels"></a>Метки конфиденциальности

- **Поддержка DoD**. Поддержка правительственных клиентов США с помощью сред DoD.
- **Шифрование только для Outlook**. Параметры шифрования Outlook теперь включают Encrypt-Only при выборе [Разрешить пользователям назначать разрешения.](encryption-sensitivity-labels.md#let-users-assign-permissions)
- **Применение встроенных меток в приложениях Office.** Обновлено [руководство](sensitivity-labels-office-apps.md#office-built-in-labeling-client-and-the-azure-information-protection-client) по обеспечению применения встроенных меток в приложениях Office при установке клиента единой метки Azure Information Protection.

## <a name="february-2021"></a>Февраль 2021 г.

Вот несколько изменений в решениях и контенте microsoft 365 за февраль.

### <a name="auditing"></a>Аудит

- **Управление политиками хранения журналов аудита.** Дополнительные данные о новой панели [мониторинга политик хранения аудита.](/microsoft-365/compliance/audit-log-retention-policies#manage-audit-log-retention-policies-1)
- **Поиск журнала аудита**. [Для поиска журнала аудита используйте скрипт PowerShell.](/microsoft-365/compliance/audit-log-search-script)

### <a name="data-classification-content-explorer"></a>Обозреватель контента классификации данных

Содержимое было добавлено или обновлено в следующих темах:

- [Начало работы с обозревателем содержимого](/microsoft-365/compliance/data-classification-content-explorer)
- [Заметки о выпуске классификации данных](/microsoft-365/compliance/data-classification-pub-preview-relnotes)

### <a name="data-loss-prevention"></a>Защита от потери данных

Содержимое было добавлено или обновлено в следующих темах:

- [Узнайте о DLP конечных точек](/microsoft-365/compliance/endpoint-dlp-learn-about)
- [Отправка почтовых уведомлений и отображение подсказок для политик защиты от потери данных](/microsoft-365/compliance/use-notifications-and-policy-tips)
- [Сведения о локальном сканере предотвращения потери данных Microsoft 365](/microsoft-365/compliance/dlp-on-premises-scanner-learn)
- [Начало работы с локального сканера предотвращения потери данных](/microsoft-365/compliance/dlp-on-premises-scanner-get-started)
- [Создание политики защиты от потери данных для защиты документов с помощью FCI или других свойств](/microsoft-365/compliance/protect-documents-that-have-fci-or-other-properties)
- [Использование Защиты от потери данных в конечной точке](/microsoft-365/compliance/endpoint-dlp-using)
- [Начало работы с функцией защиты от потери данных в конечной точке](/microsoft-365/compliance/endpoint-dlp-getting-started)

### <a name="ediscovery"></a>Обнаружение электронных данных (eDiscovery)

Содержимое было добавлено или обновлено в следующих темах:

- [Расшифровка в средствах электронных данных Microsoft 365](/microsoft-365/compliance/ediscovery-decryption)
- [Запросы ключевых слов и условия поиска](/microsoft-365/compliance/keyword-queries-and-search-conditions#limitations-for-searching-sensitive-data-types)
- [Выход на пенсию модуля Релевантность в расширенных электронных обнаружений](/microsoft-365/compliance/relevance-module-retirement)
- [Использование скрипта для добавления пользователей в удержание в случае core eDiscovery](/microsoft-365/compliance/use-a-script-to-add-users-to-a-hold-in-ediscovery)

### <a name="encryption"></a>Шифрование

Содержимое было добавлено или обновлено в следующих темах:

#### <a name="azure-rights-management-service-rms"></a>Служба управления правами Azure (RMS)

- [Возможности шифрования под управлением клиента](/microsoft-365/compliance/office-365-customer-managed-encryption-features)
- [Шифрование электронной почты Exchange Online с помощью AD RMS.](/microsoft-365/compliance/information-rights-management-in-exchange-online) Поддержка этой службы была обесценяна. Вы больше не можете использовать AD RMS в гибридной среде Exchange. Вместо этого мигрировать в Azure RMS.

#### <a name="customer-key"></a>Ключ клиента

- [Ключ клиента для Microsoft 365 на уровне клиента](/microsoft-365/compliance/customer-key-tenant-level)
- [Обзор безопасности и соответствия требованиям](/microsoftteams/security-compliance-overview)

#### <a name="information-rights-management-irm"></a>(IRM) Управления Правами На Доступ К Данным

- [Применение управления правами на информацию (IRM) в списке или библиотеке.](/microsoft-365/compliance/configure-irm-to-use-an-on-premises-ad-rms-server) Эти национальные облака не поддерживают этот параметр:
    - Microsoft Cloud for US Government
    - Microsoft Cloud для Германии
    - Azure и Microsoft 365, управляемые 21Vianet в Китае)
- Настройка IRM для использования локального [сервера AD RMS.](/microsoft-365/compliance/configure-irm-to-use-an-on-premises-ad-rms-server) Поддержка этой службы в гибридной среде Exchange была обесценяна.

### <a name="sensitive-information-types"></a>Типы конфиденциальных сведений

Содержимое было добавлено или обновлено в следующих темах:

- [Сведения о типах конфиденциальной информации](/microsoft-365/compliance/sensitive-information-type-learn-about)
- [Создание пользовательского типа конфиденциальной информации с помощью PowerShell](/microsoft-365/compliance/create-a-custom-sensitive-information-type-in-scc-powershell)
- [Создание настраиваемой конфиденциальной информации с помощью классификации точного совпадения данных](/microsoft-365/compliance/create-custom-sensitive-information-types-with-exact-data-match-based-classification)
- [Определения объектов типов конфиденциальной информации](/microsoft-365/compliance/sensitive-information-type-entity-definitions)


### <a name="sensitivity-labels"></a>Метки конфиденциальности

Содержимое было добавлено или обновлено в следующих темах:

- **Внешний общий доступ к SharePoint.** Для [меток контейнера](sensitivity-labels-teams-groups-sites.md) опция внешнего общего доступа с сайтов SharePoint теперь выпущена в общем доступе. Кроме того, центр администрирования Microsoft 365 и планировщик теперь поддерживают применение этих меток конфиденциальности. 
- **Совместное авторство и AutoSave**. Поддержка [совместной работы и AutoSave](sensitivity-labels-coauthoring.md) для зашифрованных файлов выпущена в качестве предварительного просмотра для тестирования в несерийных клиентах.

## <a name="january-2021"></a>Январь 2021 г.

### <a name="support-for-card-content-in-teams"></a>Поддержка контента карт в Teams

Следующие решения по обеспечению соответствия требованиям Microsoft [](/microsoftteams/platform/task-modules-and-cards/what-are-cards) 365 теперь поддерживают обнаружение контента карт, генерируемого через приложения в сообщениях Teams:

- **Core и Advanced eDiscovery**. Теперь содержимое карты можно поместить [на удержание](create-ediscovery-holds.md#preserve-card-content) или включить в поиск [(применяется](/microsoftteams/ediscovery-investigation#search-for-card-content) и к поиску контента).
- **Аудит**. Теперь действие карты [записуется в журнал аудита.](/microsoftteams/audit-log-events#teams-activities)
- **Политики хранения**. Теперь можно использовать политики хранения для хранения [и удаления содержимого карты.](retention-policies-teams.md#whats-included-for-retention-and-deletion)

### <a name="information-governance-and-records-management"></a>Управление информацией и управление записями

[Новая оценка](retention-regulatory-requirements.md#new-zealand-public-records-act) для решения проблемы использования управления информацией и управления записями для выполнения обязательств по соблюдению Закона о публичных записях Новой Зеландии.

### <a name="sensitivity-labels"></a>Метки конфиденциальности

- Метки конфиденциальности теперь поддерживаются для клиентов правительства США (GCC и GCC-H).
- Новая [поддержка автоматической маркировки](sensitivity-labels-office-apps.md) для macOS.

## <a name="december-2020"></a>Декабрь 2020 г.

### <a name="spotlight-new-content-for-insider-risk-solutions"></a>Spotlight: новое содержимое для решений по инсайдерской опасности

Команда контента для соответствия требованиям Microsoft 365 трудна над созданием доков "решения контента", чтобы содействовать совместному использования возможностей соответствия требованиям для достижения целей соответствия требованиям.

Во-первых, это контент, который связывает наши внутренние решения риска: соответствие требованиям к коммуникации, управление рисками, информационные барьеры и управление привилегированным доступом. Вот что вы найдете:

- [Новая страница для решений по инсайдерской опасности.](insider-risk-solution-overview.md) Включает сведения о рисках, которые решения могут помочь смягчить, требования к лицензированию, последовательность развертывания, иллюстрации к архитектуре, учебные ресурсы и другие.
- Новые статьи обзоров для каждого решения по инсайдерской опасности. Руководство и ссылки на статьи, которые помогут вам узнать, спланировать, развернуть и управлять каждым решением:
  - [Соответствие требованиям к обмену данными](communication-compliance-solution-overview.md)
  - [Управление внутренними рисками](insider-risk-management-solution-overview.md)
  - [Информационные барьеры](information-barriers-solution-overview.md)
  - [Управление привилегированным доступом](privileged-access-management-solution-overview.md)
  
Дополнительные документы решений контента скоро!

### <a name="advanced-ediscovery"></a>Advanced eDiscovery

Улучшение рабочего процесса и функциональных возможностей [](non-custodial-data-sources.md) для добавления хранителей и источников данных, не в отношении хранения, в Advanced eDiscovery случае. [](add-custodians-to-case.md)

### <a name="data-connectors"></a>Соединители данных

Выпущено четыре новых соединителя [Veritas:](archiving-third-party-data.md#third-party-data-connectors)Redtail Speak, Salesforce Chatter, ServiceNow и Yieldbroker.

### <a name="encryption"></a>Шифрование

Введение [ключа](customer-key-tenant-level.md)клиента для Microsoft 365 на уровне клиента. Используя ключи, которые вы предоставляете, можно создать политику шифрования данных (DEP) и назначить ее клиенту. DeP шифрует данные в клиенте для этих рабочих нагрузок:

- Teams чатов (1:1 чаты, групповые чаты, чаты собраний и беседы на канале)
- Teams (изображения, фрагменты кода, видео, вики-изображения)
- Teams записи вызовов и собраний, хранимые в Teams хранилище
- Teams уведомления чата
- Teams чата Кортана
- Teams сообщений о состоянии
- Сведения о пользователях и сигналах для Exchange Online

### <a name="records-management"></a>Управление записями

Группа [ролей администратора управления](get-started-with-records-management.md#permissions-required-for-records-management) записями теперь предоставляет разрешения для всех функций управления записями, включая просмотр диспозиции.

### <a name="sensitivity-labels"></a>Метки конфиденциальности

- [Автоматически маркировать данные в Azure Purview (предварительный просмотр).](/azure/purview/create-sensitivity-label) Теперь можно создавать и автоматически применять метки конфиденциальности к активам в Azure Purview, таким как файлы в хранилищах Azure Blob и столбцах баз данных в SQL Server.
- [Требуется, чтобы пользователи применяли метку к элементу.](sensitivity-labels-office-apps.md#require-users-to-apply-a-label-to-their-email-and-documents) Этот новый параметр, также известный как "обязательная маркировка", требует от пользователей выбора и применения метки конфиденциальности в определенных сценариях.
