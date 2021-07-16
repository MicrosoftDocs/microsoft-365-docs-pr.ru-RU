---
title: Новые возможности Центра соответствия требованиям Microsoft 365
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
ms.openlocfilehash: acbad7a1c5fa541ee83da668768cc42af7a5afda
ms.sourcegitcommit: 84e70051bb61b1171cebfbabe500b4904dfac04f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/16/2021
ms.locfileid: "53464013"
---
# <a name="whats-new-in-microsoft-365-compliance"></a>Новые возможности Центра соответствия требованиям Microsoft 365

Будь то добавление новых решений в [Центр соответствия требованиям Microsoft 365,](microsoft-365-compliance-center.md)обновление существующих функций на основе отзывов или развертывание свежей и обновленной документации, Microsoft 365 поможет вам оставаться на вершине постоянно меняющегося ландшафта соответствия требованиям. См. ниже, чтобы узнать, что нового в Microsoft 365 соответствия требованиям.

> [!NOTE]
> Некоторые функции соответствия требованиям выкатываются с разной скоростью для наших клиентов. Если вы еще не видите функцию, попробуйте добавить себя в [целевой выпуск](/office365/admin/manage/release-options-in-office-365).

> [!TIP]
> Интересует, что происходит в других центрах администрирования? Ознакомьтесь с этими статьями:
>
> - [Что нового в Центр администрирования Microsoft 365](/office365/admin/whats-new-in-preview)
> - [Новые возможности центра администрирования SharePoint](/sharepoint/what-s-new-in-admin-center)
> - [Новые возможности Microsoft 365 Defender](../security/defender/whats-new.md)
>
> И посетите [Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap) дорожную карту, чтобы узнать Microsoft 365, которые были запущены, запущены, находятся в разработке, отменены или ранее выпущены.

## <a name="june-2021"></a>Июнь 2021 г.

### <a name="customer-key"></a>Ключ клиента

- [Шифрование службы с помощью ключа](customer-key-overview.md) клиента (dePs уровня клиентского ключа клиента теперь шифрует конфигурацию метки конфиденциальности для Microsoft Information Protection.)

### <a name="data-connectors"></a>Соединители данных

- Мы выпустили 17 новых соединители данных в партнерстве с [17a-4 LLC](archiving-third-party-data.md#17a-4-data-connectors) и один новый соединитель в партнерстве с [CellTrust](archiving-third-party-data.md#celltrust-data-connectors). Мы также выпустили дополнительные соединители данных в партнерстве с [Veritas](archiving-third-party-data.md#veritas-data-connectors) и [TeleMessage.](archiving-third-party-data.md#telemessage-data-connectors) На сегодняшний день это позволяет в общей сложности 65 подключений к данным импортировать и архивировать сторонние данные для Microsoft 365.

### <a name="ediscovery"></a>Обнаружение электронных данных

- [Запрос и фильтрация](review-set-search.md) контента в наборе обзоров (новая возможность фильтрации и запроса в новом формате UX для фильтрации и поиска контента в наборе отзывов)
- Тег документов в наборе обзоров в [Advanced eDiscovery](tagging-documents.md) (новые функции тегов и UX, чтобы сделать теги документов в наборе отзывов быстрее и проще; включает новые возможности пометки документов с помощью запроса и с помощью фильтров для быстрого поиска или исключения элементов набора обзоров в зависимости от того, как элемент помечен)
- Настройка границ соответствия требованиям для расследований по обнаружению электронных данных [(Корпорация](set-up-compliance-boundaries.md) Майкрософт удалила требование связаться с службой поддержки MS для запроса синхронизации атрибута соответствия с учетными записями OneDrive; теперь фильтр разрешений поиска почтовых ящиков используется для обеспечения соблюдения границ соответствия требованиям для OneDrive)

### <a name="sensitivity-labels"></a>Метки конфиденциальности

- Мастер политики политики меток [](sensitivity-labels-office-apps.md#outlook-specific-options-for-default-label-and-mandatory-labeling) конфиденциальности теперь поддерживает Outlook для метки по умолчанию и обязательной маркировки в качестве более простой конфигурации, чем расширенные параметры PowerShell (поддерживаемые до сих пор).
- Поддержка [динамической разметки с](sensitivity-labels-office-apps.md#dynamic-markings-with-variables ) переменными теперь развертывается для Word, Excel и PowerPoint в Интернете
- Для [политик автоматической](apply-sensitivity-label-automatically.md) маркировки для Exchange, если метка настроена для шифрования, это шифрование не применяется. Кроме того, Exchange политики автоматической маркировки теперь можно настроить исключения и следующие новые условия: шаблоны адресов субъекта, адреса получателей или адреса отправитель; адрес получателя содержит слова; домен отправитель является, получатель является членом; отправитель.
- При использовании меток конфиденциальности с группами, группами и сайтами можно использовать Set-SPOTenant с параметром BlockSendLabelMismatchEmail  для предотвращения автоматического сгенерации электронной почты при обнаружении несоответствия конфиденциальности документов.  Дополнительные сведения см. в сведениях о действиях [метки "Проверка чувствительности".](sensitivity-labels-teams-groups-sites.md#auditing-sensitivity-label-activities )
- Параметр [контекста проверки подлинности](sensitivity-labels-teams-groups-sites.md#more-information-about-the-dependencies-for-the-authentication-context-option) теперь полностью выкатился в предварительном режиме для меток конфиденциальности. Кроме того, эта конфигурация теперь поддерживается Microsoft Teams.
- Файлы, которые помечены и шифруются по имени принципа службы (например, Microsoft Cloud App Security), а затем загружены в SharePoint и OneDrive теперь могут быть открыты в Office для Интернета, когда вы включили метки чувствительности для Office файлов в SharePoint и [OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).
- Совместное авторство и [AutoSave](sensitivity-labels-coauthoring.md) больше не ограничиваются тестированием клиентов и теперь поддерживаются в производстве при использовании версии 2105: 18 июня для Windows и версии 16.50+ для macOS. Обратите внимание, что эта функция по-прежнему не поддерживается iOS и Android и остается в предварительном просмотре.

## <a name="may-2021"></a>Май 2021 г.

### <a name="data-loss-prevention"></a>Защита от потери данных

- Новые рекомендации по [планированию стратегии предотвращения потери](dlp-overview-plan-for-dlp.md) данных.

### <a name="retention-and-records-management"></a>Управление хранением и записями

- Если вы освобождаете политику хранения с веб-SharePoint или OneDrive учетной записи, вам больше не придется ждать 30-дневного льготного периода, прежде чем можно удалить сайт или учетную запись. Популярный запрос клиентов, это изменение теперь завершено для всех клиентов.
- В предварительном просмотре можно просмотреть многоступенчатый обзор диспозиции. Теперь администратор может добавлять до пяти последовательных этапов проверки диспозиции для метки хранения, а рецензенты могут добавлять других пользователей в стадию рассмотрения диспозиции.  [](disposition.md) Вы также можете настроить уведомления и напоминания по электронной почте.

### <a name="sensitive-information-types"></a>Типы конфиденциальных сведений

- Добавлены новые сведения, которые помогут [изменить словарь ключевых слов.](sit-modify-keyword-dictionary.md)

### <a name="sensitivity-labels"></a>Метки конфиденциальности

- При настройке метки  конфиденциальности для групп и сайтов теперь доступен новый параметр для контекста [проверки подлинности.](sensitivity-labels-teams-groups-sites.md) Этот параметр работает совместно с политиками условного доступа Azure AD для обеспечения более строгих условий при доступе пользователей SharePoint сайтов с меткой. Перед настройкой [](sensitivity-labels-teams-groups-sites.md#more-information-about-the-dependencies-for-the-authentication-context-option) этого параметра убедитесь, что вы читаете зависимости и ограничения.
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

### <a name="insider-risk-management"></a>Управление рисками, связанными с инсайдерами

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
- [Создание уведомлений для действий точного соответствия данных](/microsoft-365/compliance/sit-edm-notifications-activities)
- [Определения объекта типа конфиденциальной информации](/microsoft-365/compliance/sensitive-information-type-entity-definitions)
- [Создание настраиваемого типа конфиденциальной информации с помощью PowerShell](/microsoft-365/compliance/create-a-custom-sensitive-information-type-in-scc-powershell)
- [Создание словаря ключевых слов](/microsoft-365/compliance/create-a-keyword-dictionary)

### <a name="sensitivity-labels"></a>Метки конфиденциальности

- **Поддержка DoD**. Поддержка правительственных клиентов США с помощью сред DoD.
- **Шифровать только для Outlook**. Параметры шифрования для Outlook теперь включают Encrypt-Only при выборе [Разрешить пользователям назначать разрешения.](encryption-sensitivity-labels.md#let-users-assign-permissions)
- **Применение встроенных меток в Office приложениях.** Обновлено [руководство](sensitivity-labels-office-apps.md#office-built-in-labeling-client-and-the-azure-information-protection-client) по обеспечению применения встроенных меток в Office приложениях при установке клиента единой метки Azure Information Protection.

## <a name="february-2021"></a>Февраль 2021 г.

Вот несколько изменений в решениях Microsoft 365 и контенте за февраль.

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
- [Сведения о локальном сканере Microsoft 365 защиты от потери данных](/microsoft-365/compliance/dlp-on-premises-scanner-learn)
- [Начало работы с локального сканера предотвращения потери данных](/microsoft-365/compliance/dlp-on-premises-scanner-get-started)
- [Создание политики защиты от потери данных для защиты документов с помощью FCI или других свойств](/microsoft-365/compliance/protect-documents-that-have-fci-or-other-properties)
- [Использование защиты от потери данных в конечной точке](/microsoft-365/compliance/endpoint-dlp-using)
- [Начало работы с функцией защиты от потери данных в конечной точке](/microsoft-365/compliance/endpoint-dlp-getting-started)

### <a name="ediscovery"></a>Обнаружение электронных данных

Содержимое было добавлено или обновлено в следующих темах:

- [Расшифровка в Microsoft 365 средствах eDiscovery](/microsoft-365/compliance/ediscovery-decryption)
- [Запросы ключевых слов и условия поиска](/microsoft-365/compliance/keyword-queries-and-search-conditions#limitations-for-searching-sensitive-data-types)
- [Выход на пенсию модуля Релевантность в Advanced eDiscovery](/microsoft-365/compliance/relevance-module-retirement)
- [Использование скрипта для добавления пользователей в удержание в случае core eDiscovery](/microsoft-365/compliance/use-a-script-to-add-users-to-a-hold-in-ediscovery)

### <a name="encryption"></a>Шифрование

Содержимое было добавлено или обновлено в следующих темах:

#### <a name="azure-rights-management-service-rms"></a>Служба управления правами Azure (RMS)

- [Возможности шифрования под управлением клиента](/microsoft-365/compliance/office-365-customer-managed-encryption-features)
- [Exchange Online шифрование почты с помощью AD RMS](/microsoft-365/compliance/information-rights-management-in-exchange-online). Поддержка этой службы была обесценяна. Вы больше не можете использовать AD RMS в Exchange гибридной среде. Вместо этого мигрировать в Azure RMS.

#### <a name="customer-key"></a>Ключ клиента

- [Ключ клиента для Microsoft 365 на уровне клиента](/microsoft-365/compliance/customer-key-tenant-level)
- [Обзор безопасности и соответствия требованиям](/microsoftteams/security-compliance-overview)

#### <a name="information-rights-management-irm"></a>(IRM) Управления Правами На Доступ К Данным

- [Применение управления правами на информацию (IRM) в списке или библиотеке.](/microsoft-365/compliance/configure-irm-to-use-an-on-premises-ad-rms-server) Эти национальные облака не поддерживают этот параметр:
  - Microsoft Cloud for US Government
  - Microsoft Cloud для Германии
  - Azure и Microsoft 365 21Vianet в Китае)
- Настройка IRM для использования локального [сервера AD RMS.](/microsoft-365/compliance/configure-irm-to-use-an-on-premises-ad-rms-server) Поддержка этой службы в Exchange гибридной среде была обесценилась.

### <a name="sensitive-information-types"></a>Типы конфиденциальных сведений

Содержимое было добавлено или обновлено в следующих темах:

- [Сведения о типах конфиденциальной информации](/microsoft-365/compliance/sensitive-information-type-learn-about)
- [Создание пользовательского типа конфиденциальной информации с помощью PowerShell](/microsoft-365/compliance/create-a-custom-sensitive-information-type-in-scc-powershell)
- [Создание настраиваемой конфиденциальной информации с помощью классификации точного совпадения данных](/microsoft-365/compliance/create-custom-sensitive-information-types-with-exact-data-match-based-classification)
- [Определения объектов типов конфиденциальной информации](/microsoft-365/compliance/sensitive-information-type-entity-definitions)

### <a name="sensitivity-labels"></a>Метки конфиденциальности

Содержимое было добавлено или обновлено в следующих темах:

- **SharePoint внешнего обмена**. Для [меток контейнера](sensitivity-labels-teams-groups-sites.md) опция внешнего SharePoint сайтов теперь выпущена в общем доступе. Кроме того, Центр администрирования Microsoft 365 и планировщик теперь поддерживают применение этих меток конфиденциальности. 
- **Совместное авторство и AutoSave**. Поддержка [совместной работы и AutoSave](sensitivity-labels-coauthoring.md) для зашифрованных файлов выпущена в качестве предварительного просмотра для тестирования в несерийных клиентах.

## <a name="january-2021"></a>Январь 2021 г.

### <a name="support-for-card-content-in-teams"></a>Поддержка контента карт в Teams

Следующие решения Microsoft 365 теперь поддерживают обнаружение контента карт, генерируемого через приложения в Teams сообщениях: [](/microsoftteams/platform/task-modules-and-cards/what-are-cards)

- **Core и Advanced eDiscovery**. Теперь содержимое карты можно поместить [на удержание](create-ediscovery-holds.md#preserve-card-content) или включить в поиск [(применяется](/microsoftteams/ediscovery-investigation#search-for-card-content) и к поиску контента).
- **Аудит**. Теперь действие карты [записуется в журнал аудита.](/microsoftteams/audit-log-events#teams-activities)
- **Политики хранения**. Теперь можно использовать политики хранения для хранения [и удаления содержимого карты.](retention-policies-teams.md#whats-included-for-retention-and-deletion)

### <a name="information-governance-and-records-management"></a>Управление информацией и управление записями

[Новая оценка](retention-regulatory-requirements.md#new-zealand-public-records-act) для решения проблемы использования управления информацией и управления записями для выполнения обязательств по соблюдению Закона о публичных записях Новой Зеландии.

### <a name="sensitivity-labels"></a>Метки конфиденциальности

- Метки конфиденциальности теперь поддерживаются для клиентов правительства США (GCC и GCC-H).
- Новая [поддержка автоматической маркировки](sensitivity-labels-office-apps.md) для macOS.
