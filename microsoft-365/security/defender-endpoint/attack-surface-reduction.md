---
title: Используйте правила уменьшения поверхности атаки, чтобы предотвратить заражение вредоносными программами
description: Правила уменьшения поверхности атаки могут предотвратить использование эксплойтов приложений и скриптов для заражения устройств вредоносными программами.
keywords: Правила уменьшения поверхности атаки, asr, hips, система предотвращения вторжения, правила защиты, антиэкспозиция, антиэксплойт, эксплойт, профилактика инфекций, Microsoft Defender для Endpoint
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: oogunrinde, sugamar, jcedola
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 0852cc5af2de6767e202e3a839c498e7e008eef3
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2021
ms.locfileid: "52593857"
---
# <a name="use-attack-surface-reduction-rules-to-prevent-malware-infection"></a>Используйте правила уменьшения поверхности атаки, чтобы предотвратить заражение вредоносными программами

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**

- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="why-attack-surface-reduction-rules-are-important"></a>Why attack surface reduction rules are important

Поверхность атаки организации включает все места, в которых злоумышленник может скомпрометировать устройства или сети организации. Уменьшение поверхности атаки означает защиту устройств и сети организации, что оставляет злоумышленникам меньше способов выполнения атак. Настройка правил уменьшения поверхности атаки в Microsoft Defender для конечной точки может помочь!

Правила уменьшения поверхности атаки ориентированы на определенные действия программного обеспечения, такие как:

- Запуск исполняемых файлов и скриптов, которые пытаются скачать или запустить файлы;
- Запуск запутывательных или иных подозрительных скриптов; и
- Выполнение поведения, которое приложения обычно не инициируют во время обычной ежедневной работы.

Такое поведение программного обеспечения иногда рассматривается в законных приложениях; однако эти действия часто считаются рискованными, так как злоумышленники часто злоупотребляют ими с помощью вредоносных программ. Правила уменьшения поверхности атаки могут ограничивать рискованное поведение и поддерживать безопасность организации.

Дополнительные сведения о настройке правил уменьшения поверхности атаки см. в дополнительных сведениях [о правилах](enable-attack-surface-reduction.md)уменьшения поверхности атаки.

## <a name="assess-rule-impact-before-deployment"></a>Оценка влияния правил перед развертыванием

Вы можете оценить, как правило уменьшения поверхности атаки может повлиять на сеть, открыв рекомендации по безопасности для этого правила в [контроль угроз и уязвимостей](/windows/security/threat-protection/#tvm).

:::image type="content" source="images/asrrecommendation.png" alt-text="Reco безопасности для правила уменьшения поверхности атаки":::

В области сведений о рекомендациях проверьте влияние пользователя, чтобы определить, какой процент устройств может принять новую политику, позволяющую использовать правило в режиме блокировки без отрицательного влияния на производительность.

## <a name="audit-mode-for-evaluation"></a>Режим аудита для оценки

Используйте [режим аудита,](audit-windows-defender.md) чтобы оценить, как правила уменьшения поверхности атаки влияют на организацию, если они включены. Сначала запустите все правила в режиме аудита, чтобы вы могли понять, как они влияют на ваши бизнес-приложения. Многие бизнес-приложения написаны с ограниченными соображениями безопасности, и они могут выполнять задачи, которые кажутся похожими на вредоносные программы. Отслеживая данные аудита и добавляя [исключения](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) для необходимых приложений, можно развернуть правила уменьшения поверхности атаки без снижения производительности.

## <a name="warn-mode-for-users"></a>Режим предупреждения для пользователей

(**NEW**!) Перед предупреждением о возможностях режима правила уменьшения поверхности атаки, включенные, можно настроить в режиме аудита или режиме блокировки. В новом режиме предупреждения каждый раз, когда содержимое блокируется правилом уменьшения поверхности атаки, пользователи видят диалоговое окно, которое указывает на блокировку контента. Диалоговое окно также предлагает пользователю возможность разблокировать контент. Затем пользователь может повторить свое действие, и операция завершится. Когда пользователь разблокирует контент, содержимое будет разблокировано в течение 24 часов, а затем блокируется резюме.

Режим Warn помогает организации иметь правила уменьшения поверхности атаки, не мешая пользователям получать доступ к контенту, необходимому для выполнения задач.

### <a name="requirements-for-warn-mode-to-work"></a>Требования к режиму предупреждения для работы

Режим Warn поддерживается на устройствах, работающих в следующих версиях Windows:

- [Windows 10 версии 1809](/windows/whats-new/whats-new-windows-10-version-1809) или более поздней версии
- [Windows Server версии 1809](/windows-server/get-started/whats-new-in-windows-server-1809) или более поздней версии

антивирусная программа в Microsoft Defender должна работать с защитой в режиме реального времени в [режиме Active.](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state)

Кроме того, убедитесь, [что антивирусная программа в Microsoft Defender и антивирусных обновлений](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions) установлены.

- Минимальное требование к выпуску платформы: `4.18.2008.9`
- Минимальное требование к выпуску двигателя: `1.1.17400.5`

Дополнительные сведения и обновления см. в сайте [Update for Microsoft Defender antimalware platform.](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform)

### <a name="cases-where-warn-mode-is-not-supported"></a>Случаи, когда режим предупреждения не поддерживается

Режим Warn не поддерживается для трех правил уменьшения поверхности атаки при настройке Microsoft Endpoint Manager. (Если вы используете групповую политику для настройки правил уменьшения поверхности атаки, поддерживается режим предупреждения.) Три правила, которые не поддерживают режим предупреждения при настройке Microsoft Endpoint Manager, являются следующими:

- [Блокировка JavaScript или VBScript при запуске загружаемого исполняемого контента](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) `d3e037e1-3eb8-44c8-a917-57927947596d` (GUID)
- [Блокировка сохраняемости через подписку на](#block-persistence-through-wmi-event-subscription) события WMI (GUID) `e6db77e5-3df2-4cf1-b95a-636979351e5b`
- [Используйте расширенные средства защиты от программ-вымогателей](#use-advanced-protection-against-ransomware) `c1db55ab-c21a-4637-bb3f-a12568109d35` (GUID)

Кроме того, режим предупреждения не поддерживается на устройствах с более старыми версиями Windows. В этих случаях правила уменьшения поверхности атаки, настроенные для работы в режиме предупреждения, будут работать в режиме блокировки.

## <a name="notifications-and-alerts"></a>Уведомления и оповещения

Всякий раз, когда срабатывает правило уменьшения поверхности атаки, на устройстве отображается уведомление. Вы можете [настроить уведомление](customize-attack-surface-reduction.md#customize-the-notification), указав сведения о вашей организации и контактные данные.

Кроме того, при запуске определенных правил уменьшения поверхности атаки создаются оповещения.

Уведомления и все генерируемые оповещения можно просмотреть в Центр безопасности в Microsoft Defender () и в центре Microsoft 365 [https://securitycenter.windows.com](https://securitycenter.windows.com) безопасности ( [https://security.microsoft.com](https://security.microsoft.com) ).

## <a name="advanced-hunting-and-attack-surface-reduction-events"></a>Расширенные события уменьшения поверхности охоты и атаки

Вы можете использовать расширенный поиск для просмотра событий уменьшения поверхности атаки. Чтобы оптимизировать объем входящих данных, с помощью продвинутой охоты можно просматривать только уникальные процессы для каждого часа. Время события уменьшения поверхности атаки — это первый раз, когда это событие рассматривается в течение часа.

Например, предположим, что событие уменьшения поверхности атаки происходит на 10 устройствах в течение 14:00 часов. Предположим, что первое событие произошло в 2:15, а последнее — в 2:45. При продвинутой охоте вы увидите один экземпляр этого события (даже если оно действительно произошло на 10 устройствах), а его время будет 2:15 вечера.

Дополнительные сведения о продвинутой охоте см. в ссылке [Proactively hunt for threats with advanced hunting.](advanced-hunting-overview.md)

## <a name="attack-surface-reduction-features-across-windows-versions"></a>Функции уменьшения поверхности атаки в Windows версиях

Вы можете установить правила уменьшения поверхности атаки для устройств, которые работают с любыми из следующих выпусков и версий Windows:

- Windows 10 Pro версии [1709](/windows/whats-new/whats-new-windows-10-version-1709) или более поздней версии
- Windows 10 Корпоративная версии [1709](/windows/whats-new/whats-new-windows-10-version-1709) или более поздней версии
- Windows Сервер, [версия 1803 (полугодовой канал)](/windows-server/get-started/whats-new-in-windows-server-1803) или более поздний
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

Хотя правила уменьшения поверхности атаки не требуют лицензии Windows E5, если у вас есть Windows [E5,](/windows/deployment/deploy-enterprise-licenses)вы получите расширенные возможности управления. Эти возможности, доступные только в Windows E5, включают мониторинг, аналитику и рабочий процесс, доступные в [Defender для](microsoft-defender-endpoint.md)конечной точки, а также возможности отчетности и [конфигурации](/microsoft-365/security/defender/overview-security-center)в центре безопасности Microsoft 365 безопасности . Эти расширенные возможности недоступны с лицензией Windows Professional или Windows E3; Однако, если у вас есть эти лицензии, вы можете использовать журналы viewer и антивирусная программа в Microsoft Defender для просмотра событий правила уменьшения поверхности атаки.

## <a name="review-attack-surface-reduction-events-in-the-microsoft-defender-security-center"></a>Просмотр событий уменьшения поверхности атаки в Центр безопасности в Microsoft Defender

Defender for Endpoint предоставляет подробные отчеты о событиях и блоках в рамках сценариев расследования оповещений.

Вы можете запрашивать данные Defender для конечных точек с помощью [расширенных методов охоты.](advanced-hunting-query-language.md) Если вы работаете в режиме [аудита,](audit-windows-defender.md)вы можете использовать расширенный режим охоты, чтобы понять, как правила уменьшения поверхности атаки могут повлиять на среду.

Вот пример запроса:

```kusto
DeviceEvents
| where ActionType startswith 'Asr'
```

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a>Просмотр событий уменьшения поверхности атаки в Windows viewer событий

Вы можете просмотреть журнал Windows событий, чтобы просмотреть события, созданные правилами уменьшения поверхности атаки:

1. Скачайте [пакет оценки](https://aka.ms/mp7z2w) и извлеките *файл* cfa-events.xmlв доступное расположение на устройстве.
2. Введите слова *"Просмотр событий"* в меню "Пуск", чтобы открыть Windows просмотра событий.
3. В **статье Действия** выберите импорт **настраиваемого представления...**.
4. Выберите файл *cfa-events.xml,* откуда он был извлечен. Кроме того, [скопируйте XML напрямую.](event-views.md)
5. Нажмите **ОК**.

Можно создать настраиваемую точку зрения, которая фильтрует события, чтобы показывать только следующие события, все из которых связаны с управляемым доступом к папкам:

|Идентификатор события|Описание|
|---|---|
|5007|Событие при смене параметров|
|1121|Событие при пожаре правила в block-mode|
|1122|Событие при пожаре правила в режиме аудита|

"Версия двигателя", указанная для событий уменьшения поверхности атаки в журнале событий, создается защитником для конечной точки, а не операционной системой. Defender for Endpoint интегрирован с Windows 10, поэтому эта функция работает на всех устройствах с Windows 10 установленной.

## <a name="attack-surface-reduction-rules"></a>Правила сокращения направлений атак

В следующей таблице и подсекциях описаны все 15 правил уменьшения поверхности атаки. Правила уменьшения поверхности атаки перечислены в алфавитном порядке по имени правила.

Если вы настраиваете правила уменьшения поверхности атаки с помощью групповой политики или PowerShell, вам потребуется GUID. С другой стороны, если вы Microsoft Endpoint Manager или Microsoft Intune, вам не нужны GUID.

|Имя правила|GUID|Исключения & папки|Минимальная поддержка ОС|
|---|:---:|---|---|
|[Блокировка злоупотреблений с использованием уязвимых подписанных драйверов](#block-abuse-of-exploited-vulnerable-signed-drivers)|`56a863a9-875e-4185-98a7-b882c64b5ce5`|Поддерживается|[Windows 10 версии 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, сборка 16299) или больше) |
|[Блокировка Adobe Reader от создания детских процессов](#block-adobe-reader-from-creating-child-processes)|`7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`|Поддерживается|[Windows 10 версии 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, сборка 16299) или более|
|[Блокировка всех Office приложений от создания детских процессов](#block-all-office-applications-from-creating-child-processes)|`D4F940AB-401B-4EFC-AADC-AD5F3C50688A`|Поддерживается|[Windows 10 версии 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, сборка 16299) или более|
|[Блокировка кражи учетных данных из Windows локальной подсистемы органов безопасности (lsass.exe)](#block-credential-stealing-from-the-windows-local-security-authority-subsystem)|`9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`|Поддерживается|[Windows 10 версии 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, сборка 16299) или более|
|[Блокировка исполняемого контента из клиента электронной почты и веб-почты](#block-executable-content-from-email-client-and-webmail)|`BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`|Поддерживается|[Windows 10 версии 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, сборка 16299) или более|
|[Блокировать выполнение файлов, если они не соответствуют критерию распространенности, возраста или доверенного списка](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion)|`01443614-cd74-433a-b99e-2ecdc07bfc25`|Поддерживается|[Windows 10 версии 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, сборка 16299) или более|
|[Блокировка выполнения потенциально запутаных скриптов](#block-execution-of-potentially-obfuscated-scripts)|`5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`|Поддерживается|[Windows 10 версии 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, сборка 16299) или более|
|[Блокировка JavaScript или VBScript от запуска загружаемого исполняемого контента](#block-javascript-or-vbscript-from-launching-downloaded-executable-content)|`D3E037E1-3EB8-44C8-A917-57927947596D`|Поддерживается|[Windows 10 версии 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, сборка 16299) или более|
|[Блокировка Office приложений от создания исполняемого контента](#block-office-applications-from-creating-executable-content)|`3B576869-A4EC-4529-8536-B80A7769E899`|Поддерживается|[Windows 10 версии 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, сборка 16299) или более|
|[Блокировка Office приложений от внесения кода в другие процессы](#block-office-applications-from-injecting-code-into-other-processes)|`75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`|Поддерживается|[Windows 10 версии 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, сборка 16299) или более|
|[Блокировка Office приложения связи от создания детских процессов](#block-office-communication-application-from-creating-child-processes)|`26190899-1602-49e8-8b27-eb1d0a1ce869`|Поддерживается|[Windows 10 версии 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, сборка 16299) или более|
|[Блокировка сохраняемости с помощью подписки на события WMI](#block-persistence-through-wmi-event-subscription)|`e6db77e5-3df2-4cf1-b95a-636979351e5b`|Не поддерживается|[Windows 10 версии 1903](/windows/whats-new/whats-new-windows-10-version-1903) (сборка 18362) или более|
|[Блокировка создания процессов, происходящих из команд PSExec и WMI](#block-process-creations-originating-from-psexec-and-wmi-commands)|`d1e49aac-8f56-4280-b9ba-993a6d77406c`|Поддерживается|[Windows 10 версии 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, сборка 16299) или более|
|[Блокировка ненарушимых и неподписаных процессов, которые запускают из USB](#block-untrusted-and-unsigned-processes-that-run-from-usb)|`b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`|Поддерживается|[Windows 10 версии 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, сборка 16299) или более|
|[Блоки вызовов API Win32 из Office макрос](#block-win32-api-calls-from-office-macros)|`92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`|Поддерживается|[Windows 10 версии 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, сборка 16299) или более|
|[Используйте расширенные средства защиты от программ-вымогателей](#use-advanced-protection-against-ransomware)|`c1db55ab-c21a-4637-bb3f-a12568109d35`|Поддерживается|[Windows 10 версии 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, сборка 16299) или более|
|

### <a name="block-abuse-of-exploited-vulnerable-signed-drivers"></a>Блокировка злоупотреблений с использованием уязвимых подписанных драйверов

Это правило не позволяет приложению писать уязвимый, подписанный драйвер на диск. В дикой природе уязвимые подписанные драйверы могут использоваться локальными приложениями, которые имеют достаточные привилегии для получения доступа \-  \- к ядру. Уязвимые подписанные драйверы позволяют злоумышленникам отключать или обходить решения безопасности, что в конечном итоге приводит к системным компромиссам.

Это правило не блокирует загрузку уже существующего в системе драйвера.

>[!NOTE]
>
> Это правило можно настроить с помощью процедурных сведений [meM OMA-URI](enable-attack-surface-reduction.md#mem) для пользовательских правил MEM OMA-URI.
>
> Это правило также можно настроить с помощью [PowerShell.](enable-attack-surface-reduction.md#powershell)
>
> Этот веб-сайт можно использовать для [отправки драйвера для анализа.](https://www.microsoft.com/en-us/wdsi/driversubmission)

Это правило поддерживается во всех версиях, в которых поддерживается ASR; который:

- [Windows 10 Pro версии 1709](/windows/whats-new/whats-new-windows-10-version-1709) или более поздней версии
- [Windows 10 Корпоративная версии 1709](/windows/whats-new/whats-new-windows-10-version-1709) или более поздней версии
- [Windows Server, версия 1803 (полугодовой канал)](/windows-server/get-started/whats-new-in-windows-server-1803) или более поздней версии
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

Имя Intune: `Block abuse of exploited vulnerable signed drivers`

GUID:  `56a863a9-875e-4185-98a7-b882c64b5ce5`

### <a name="block-adobe-reader-from-creating-child-processes"></a>Блокировка Adobe Reader от создания детских процессов

Это правило предотвращает атаки, блокируя процессы Adobe Reader.

С помощью социальной инженерии или эксплойтов вредоносные программы могут загружать и запускать полезной нагрузки, а также выйти из Adobe Reader. Блокируя детские процессы, созданные Adobe Reader, вредоносные программы, пытающиеся использовать их в качестве вектора, не распространяются.

Это правило было введено в:

- [Windows 10 версии 1809](/windows/whats-new/whats-new-windows-10-version-1809)
- [Windows Сервер, версия 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

Имя Intune: `Process creation from Adobe Reader (beta)`

Имя диспетчера конфигурации: еще не доступно

GUID: `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`

### <a name="block-all-office-applications-from-creating-child-processes"></a>Блокировка всех Office приложений от создания детских процессов

Это правило блокирует Office приложения от создания детских процессов. Office приложения включают Word, Excel, PowerPoint, OneNote и Access.

Создание вредоносных детских процессов — это общая стратегия вредоносных программ. Вредоносные программы, Office как вектор, часто запускают макрос VBA и используют код для скачивания и попыток запуска дополнительных полезной нагрузки. Однако некоторые законные бизнес-приложения также могут создавать детские процессы для доброкачественной цели, например для нереста командной строки или с помощью PowerShell для настройки параметров реестра.

Это правило было введено в:

- [Windows 10 версии 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Сервер, версия 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Диспетчер конфигурации CB 1710](/configmgr/core/servers/manage/updates)

Имя Intune: `Office apps launching child processes`

Имя диспетчера конфигурации: `Block Office application from creating child processes`

GUID: `D4F940AB-401B-4EFC-AADC-AD5F3C50688A`

### <a name="block-credential-stealing-from-the-windows-local-security-authority-subsystem"></a>Блокировка кражи учетных данных из Windows подсистемы местного органа безопасности

Это правило помогает предотвратить кражу учетных данных путем блокировки службы подсистемы местного органа безопасности (LSASS).

LSASS позволяет проверить подлинность пользователей, входивших на Windows компьютера. Microsoft Defender Credential Guard в Windows 10 обычно предотвращает попытки извлечения учетных данных из LSASS. Однако некоторые организации не могут включить Службу учетных данных на всех компьютерах из-за проблем с совместимостью с настраиваемой драйверами смарт-карт или другими программами, которые загружаются в Местный орган безопасности (LSA). В этих случаях злоумышленники могут использовать средства взлома, такие как Mimikatz, чтобы очистить пароли cleartext и хэши NTLM из LSASS.

> [!NOTE]
> В некоторых приложениях код передает все запущенные процессы и пытается открыть их с исчерпывающими разрешениями. Это правило не позволяет приложению открывать процесс и внося сведения в журнал событий безопасности. Это правило может создавать много шума. Если у вас есть приложение, которое просто перечисляет LSASS, но не оказывает реального влияния на функциональные возможности, нет необходимости добавлять его в список исключений. Сама по себе эта запись журнала событий не обязательно указывает на вредоносную угрозу.

Это правило было введено в:

- [Windows 10 версии 1803](/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows Сервер, версия 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Диспетчер конфигурации CB 1802](/configmgr/core/servers/manage/updates)

Имя Intune: `Flag credential stealing from the Windows local security authority subsystem`

Имя диспетчера конфигурации: `Block credential stealing from the Windows local security authority subsystem`

GUID: `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`

### <a name="block-executable-content-from-email-client-and-webmail"></a>Блокировка исполняемого контента из клиента электронной почты и веб-почты

Это правило блокирует запуск следующих типов файлов из электронной почты, открытой в приложении Microsoft Outlook или Outlook.com и других популярных поставщиков веб-почты:

- Исполняемые файлы (например, .exe, .dll или .scr)
- Файлы скриптов (например, PowerShell .ps, Visual Basic vbs или файл JavaScript .js)

Это правило было введено в:

- [Windows 10 версии 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Сервер, версия 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Microsoft Endpoint Manager CB 1710](/configmgr/core/servers/manage/updates)

Имя Intune: `Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions)`

Microsoft Endpoint Manager:`Block executable content from email client and webmail`

GUID: `BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`

> [!NOTE]
> Правило Блокировать **исполняемый контент из клиента электронной** почты и веб-почты имеет следующие альтернативные описания, в зависимости от того, какое приложение вы используете:
>
> - Intune (Профили конфигурации): выполнение исполняемого контента (exe, dll, ps, js, vbs и т.д.) исключено из электронной почты (клиент веб-почты или почты) (без исключений).
> - Endpoint Manager: блокировать загрузку исполняемого контента из клиентов электронной почты и веб-почты.
> - Групповой политики: блокировка исполняемого контента из клиента электронной почты и веб-почты.

### <a name="block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion"></a>Блокировать выполнение файлов, если они не соответствуют критерию распространенности, возраста или доверенного списка

Это правило блокирует запуск следующих типов файлов, если они не соответствуют критериям распространенности или возраста, или они в доверенного списка или списка исключений:

- Исполняемые файлы (например, .exe, .dll или .scr)

Запуск неустановленных или неизвестных исполняемых файлов может быть рискованным, так как изначально может быть не ясно, являются ли файлы вредоносными.

> [!IMPORTANT]
> Вы должны [включить облачную защиту для](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) использования этого правила.
>
> Правило Блокировать выполнение файлов, если они не отвечают критерию **распространенности,** возраста или доверенного списка с GUID, принадлежат Корпорации Майкрософт и не указаны `01443614-cd74-433a-b99e-2ecdc07bfc25` администраторами. Это правило использует облачную защиту для регулярного обновления доверенного списка.
>
> Вы можете указать отдельные файлы или папки (используя пути папок или полностью квалифицированные имена ресурсов), но вы не можете указать, к которым применяются правила или исключения.

Это правило было введено в:

- [Windows 10 версии 1803](/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows Сервер, версия 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Диспетчер конфигурации CB 1802](/configmgr/core/servers/manage/updates)

Имя Intune: `Executables that don't meet a prevalence, age, or trusted list criteria`

Имя диспетчера конфигурации: `Block executable files from running unless they meet a prevalence, age, or trusted list criteria`

GUID: `01443614-cd74-433a-b99e-2ecdc07bfc25`

### <a name="block-execution-of-potentially-obfuscated-scripts"></a>Блокировка выполнения потенциально запутаных скриптов

Это правило обнаруживает подозрительные свойства в запутавом скрипте.

Запутывания скриптов — это распространенный метод, который как авторы вредоносных программ, так и законные приложения используют для сокрытия интеллектуальной собственности или уменьшения времени загрузки скриптов. Авторы вредоносных программ также используют запутывания, чтобы сделать вредоносный код более читаемым, что предотвращает тщательное изучение людьми и программным обеспечением безопасности.

Это правило было введено в:

- [Windows 10 версии 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Сервер, версия 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Диспетчер конфигурации CB 1710](/configmgr/core/servers/manage/updates)

Имя Intune: `Obfuscated js/vbs/ps/macro code`

Имя диспетчера конфигурации: `Block execution of potentially obfuscated scripts`

GUID: `5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`

### <a name="block-javascript-or-vbscript-from-launching-downloaded-executable-content"></a>Блокировка JavaScript или VBScript от запуска загружаемого исполняемого контента

Это правило не позволяет скриптам запускать потенциально вредоносный загруженный контент. Вредоносные программы, написанные на JavaScript или VBScript, часто выступают в качестве загрузщика для получения и запуска других вредоносных программ из Интернета.

Несмотря на то, что это не часто, бизнес-приложения иногда используют скрипты для скачивания и запуска установщиков.

Это правило было введено в:

- [Windows 10 версии 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Сервер, версия 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Диспетчер конфигурации CB 1710](/configmgr/core/servers/manage/updates)

Имя Intune: `js/vbs executing payload downloaded from Internet (no exceptions)`

Имя диспетчера конфигурации: `Block JavaScript or VBScript from launching downloaded executable content`

GUID: `D3E037E1-3EB8-44C8-A917-57927947596D`

### <a name="block-office-applications-from-creating-executable-content"></a>Блокировка Office приложений от создания исполняемого контента

Это правило не позволяет Office приложениям, включая Word, Excel и PowerPoint, создавать потенциально вредоносный контент, блокируя написание вредоносного кода на диск.

Вредоносные программы, Office как вектор, могут пытаться выйти из Office и сохранить вредоносные компоненты на диске. Эти вредоносные компоненты выживут при перезагрузке компьютера и будут сохраняться в системе. Поэтому это правило защищает от обычной техники сохранения.

Это правило было введено в:

- [Windows 10 версии 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Сервер, версия 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [System Center Configuration Manager](/configmgr/core/servers/manage/updates) (SCCM) CB 1710 (SCCM теперь Microsoft Endpoint Configuration Manager)

Имя Intune: `Office apps/macros creating executable content`

Имя SCCM: `Block Office applications from creating executable content`

GUID: `3B576869-A4EC-4529-8536-B80A7769E899`

### <a name="block-office-applications-from-injecting-code-into-other-processes"></a>Блокировка Office приложений от внесения кода в другие процессы

Это правило блокирует попытки впрыска кода из Office приложений в другие процессы.

Злоумышленники могут пытаться использовать Office для переноса вредоносного кода в другие процессы с помощью впрыскивания кода, поэтому код может маскировка как чистый процесс.

Нет известных законных бизнес-целей для использования впрыска кода.

Это правило применяется к Word, Excel и PowerPoint.

Это правило было введено в:

- [Windows 10 версии 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Сервер, версия 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Диспетчер конфигурации CB 1710](/configmgr/core/servers/manage/updates)

Имя Intune: `Office apps injecting code into other processes (no exceptions)`

Имя диспетчера конфигурации: `Block Office applications from injecting code into other processes`

GUID: `75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`

### <a name="block-office-communication-application-from-creating-child-processes"></a>Блокировка Office приложения связи от создания детских процессов

Это правило не позволяет Outlook детских процессов, при этом разрешая законные Outlook функции.

Это правило защищает от атак социальной инженерии и предотвращает использование кода от использования уязвимостей в Outlook. Он также защищает Outlook [правил](https://blogs.technet.microsoft.com/office365security/defending-against-rules-and-forms-injection/) и форм эксплойтов, которые злоумышленники могут использовать при взломе учетных данных пользователя.

> [!NOTE]
> Это правило блокирует советы политики DLP и ToolTips в Outlook. Это правило применяется только к Outlook и Outlook.com. 

Это правило было введено в:

- [Windows 10 версии 1809](/windows/whats-new/whats-new-windows-10-version-1809)
- [Windows Сервер, версия 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

Имя Intune: `Process creation from Office communication products (beta)`

Имя диспетчера конфигурации: недоступны

GUID: `26190899-1602-49e8-8b27-eb1d0a1ce869`

### <a name="block-persistence-through-wmi-event-subscription"></a>Блокировка сохраняемости с помощью подписки на события WMI

Это правило не позволяет вредоносным программам злоупотреблять WMI для достижения сохраняемости на устройстве.

> [!IMPORTANT]
> Исключения файлов и папок не применяются к этому правилу уменьшения поверхности атаки.

Без файловой угрозы используют различные тактики, чтобы оставаться скрытыми, чтобы не быть замеченными в файловой системе и получить контроль за периодическим выполнением. Некоторые угрозы могут злоупотреблять репозиторием WMI и моделью событий, чтобы оставаться скрытыми.

Это правило было введено в:

- [Windows 10 версии 1903 г.](/windows/whats-new/whats-new-windows-10-version-1903)
- [Windows Server 1903](/windows-server/get-started-19/whats-new-in-windows-server-1903-1909)

Имя Intune. Недоступный

Имя диспетчера конфигурации: недоступны

GUID: `e6db77e5-3df2-4cf1-b95a-636979351e5b`

### <a name="block-process-creations-originating-from-psexec-and-wmi-commands"></a>Блокировка создания процессов, происходящих из команд PSExec и WMI

Это правило блокирует запуск процессов, созданных [с помощью PsExec](/sysinternals/downloads/psexec) [и WMI.](/windows/win32/wmisdk/about-wmi) PsExec и WMI могут удаленно выполнять код, поэтому существует риск злоупотребления этой функцией вредоносными программами в командных и контрольных целях или распространения инфекции по всей сети организации.

> [!WARNING]
> Используйте это правило только в том случае, если вы управляете устройствами с [помощью intune](/intune) или другого решения MDM. Это правило несовместимо с управлением с помощью [Microsoft Endpoint Configuration Manager,](/configmgr) так как это правило блокирует команду WMI, которая используется клиентом Configuration Manager для правильной работы.

Это правило было введено в:

- [Windows 10 версии 1803](/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows Сервер, версия 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

Имя Intune: `Process creation from PSExec and WMI commands`

Имя диспетчера конфигурации: не применимо

GUID: `d1e49aac-8f56-4280-b9ba-993a6d77406c`

### <a name="block-untrusted-and-unsigned-processes-that-run-from-usb"></a>Блокировка ненарушимых и неподписаных процессов, которые запускают из USB

С помощью этого правила администраторы могут запретить запуск неподписанных или ненадежных исполняемых файлов на съемных дисках USB, включая SD-карты. Заблокированные типы файлов включают исполняемые файлы (например, .exe, .dll или .scr)

Это правило было введено в:

- [Windows 10 версии 1803](/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows Сервер, версия 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Диспетчер конфигурации CB 1802](/configmgr/core/servers/manage/updates)

Имя Intune: `Untrusted and unsigned processes that run from USB`

Имя диспетчера конфигурации: `Block untrusted and unsigned processes that run from USB`

GUID: `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`

### <a name="block-win32-api-calls-from-office-macros"></a>Блоки вызовов API Win32 из Office макрос

Это правило не позволяет макросам VBA вызывать API Win32.

Office VBA включает вызовы API Win32. Вредоносные программы могут злоупотреблять этой возможностью, например вызывать [API Win32](https://www.microsoft.com/security/blog/2018/09/12/office-vba-amsi-parting-the-veil-on-malicious-macros/) для запуска вредоносного кода оболочки, не записывая ничего непосредственно на диск. Большинство организаций не полагаются на возможность вызова API Win32 в их ежедневном функционировании, даже если они используют макрос другими способами.

Это правило было введено в:

- [Windows 10 версии 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Сервер, версия 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Диспетчер конфигурации CB 1710](/configmgr/core/servers/manage/updates)

Имя Intune: `Win32 imports from Office macro code`

Имя диспетчера конфигурации: `Block Win32 API calls from Office macros`

GUID: `92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`

### <a name="use-advanced-protection-against-ransomware"></a>Используйте расширенные средства защиты от программ-вымогателей

Это правило обеспечивает дополнительный уровень защиты от программ-вымогателей. Он использует как клиентскую, так и облачную heuristics, чтобы определить, похож ли файл на вымогателей. Это правило не блокирует файлы, которые имеют одну или несколько следующих характеристик:

- Уже установлено, что файл неуявительный в облаке Microsoft.
- Файл является допустимым подписанным файлом.
- Файл достаточно распространен, чтобы не считаться программой-вымогателями.

Правило, как правило, забвению на стороне осторожности, чтобы предотвратить вымогателей.

> [!NOTE]
> Вы должны [включить облачную защиту для](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) использования этого правила.

Это правило было введено в:

- [Windows 10 версии 1803](/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows Сервер, версия 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Диспетчер конфигурации CB 1802](/configmgr/core/servers/manage/updates)

Имя Intune: `Advanced ransomware protection`

Имя диспетчера конфигурации: `Use advanced protection against ransomware`

GUID: `c1db55ab-c21a-4637-bb3f-a12568109d35`

## <a name="see-also"></a>См. также

- [Сокращение направлений атак: вопросы и ответы](attack-surface-reduction-faq.md)
- [Включить правила сокращения направлений атак](enable-attack-surface-reduction.md)
- [Оценка правил сокращения направлений атак](evaluate-attack-surface-reduction.md)
- [Совместимость антивирусная программа в Microsoft Defender с другими решениями по антивирусной и антивирусной программам](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)
