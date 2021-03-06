---
title: Управление антивирусная программа в Microsoft Defender обновлениями и применение базовых показателей
description: Управление получением антивирусная программа в Microsoft Defender защиты и обновлений продуктов.
keywords: обновления, базовые показатели безопасности, защита, обновления расписания, обновления сил, обновления мобильных устройств, wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr, mkaminska
manager: dansimp
ms.technology: mde
ms.date: 07/12/2021
ms.openlocfilehash: 0179c620c8ba00c987395a800ed335644048283f
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394969"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a>Управление антивирусная программа в Microsoft Defender обновлениями и применение базовых показателей

**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)
- Антивирусная программа в Microsoft Defender

Важно антивирусная программа в Microsoft Defender, чтобы убедиться, что устройства имеют новейшие технологии и функции, необходимые для защиты от новых вредоносных программ и методов атак. Убедитесь в обновлении антивирусной защиты, даже если антивирусная программа в Microsoft Defender работает в [пассивном режиме.](microsoft-defender-antivirus-compatibility.md) Существует два типа обновлений, связанных с антивирусная программа в Microsoft Defender обновлениями:

- Обновления аналитики безопасности
- Обновления продукта

> [!TIP]
> Чтобы увидеть наиболее актуальные даты движка, платформы и подписи, посетите обновления аналитики безопасности для антивирусная программа в Microsoft Defender и других антивирусных программ [Майкрософт](https://www.microsoft.com/en-us/wdsi/defenderupdates)

## <a name="security-intelligence-updates"></a>Обновления аналитики безопасности

антивирусная программа в Microsoft Defender использует облачную защиту [(также](cloud-protection-microsoft-defender-antivirus.md) называемую службой защиты Microsoft Advanced Protection Service или MAPS) и периодически загружает обновления разведки безопасности для обеспечения защиты.

> [!NOTE]
> Обновления выпускаются под номерами ниже KB:  
> - антивирусная программа в Microsoft Defender: KB2267602  
> - System Center Endpoint Protection: KB2461484

Защита с облачной доставкой всегда работает и требует активного подключения к Интернету для работы. Обновления сведении безопасности происходят в запланированной каденции (настраиваемой с помощью политики). Дополнительные сведения см. в [веб-сайте Use Microsoft cloud-provided protection in антивирусная программа в Microsoft Defender.](cloud-protection-microsoft-defender-antivirus.md) 

Список последних обновлений разведки безопасности см. в антивирусная программа в Microsoft Defender и других антивирусных программах [Microsoft.](https://www.microsoft.com/en-us/wdsi/defenderupdates)

Обновления двигателя включаются с обновлениями аналитики безопасности и выпускаются на ежемесячной основе.

## <a name="product-updates"></a>Обновления продукта

антивирусная программа в Microsoft Defender требует [ежемесячных обновлений (KB4052623),](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) известных как *обновления платформы.*

Вы можете управлять распространением обновлений с помощью одного из следующих методов: 

- [Windows Служба обновления сервера (WSUS)](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [Microsoft Endpoint Configuration Manager](/configmgr/sum/understand/software-updates-introduction)
- Обычный метод, который используется для развертывания microsoft и Windows обновлений конечных точек в сети.

Дополнительные сведения см. [в ссылке Управление источниками обновлений антивирусная программа в Microsoft Defender защиты.](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)

> [!NOTE]
> - Ежемесячные обновления выпускаются поэтапно, в результате чего в службах обновления window Server отображается несколько [пакетов.](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)
> - В этой статье перечислены изменения, включенные в широкий канал выпуска. [Последние выпуски широкого канала см. здесь.](https://www.microsoft.com/security/encyclopedia/adlpackages.aspx?action=info) 
> - Дополнительные сведения о постепенном процессе выкатки и дополнительные сведения о следующем выпуске см. в руб. Управление процессом постепенного выката обновлений [Microsoft Defender.](manage-gradual-rollout.md)
> - Дополнительные сведения об обновлениях сведений о безопасности см. в антивирусная программа в Microsoft Defender и других антивирусных программах [Майкрософт.](https://www.microsoft.com/wdsi/defenderupdates) 

## <a name="monthly-platform-and-engine-versions"></a>Ежемесячные версии платформы и двигателя

Сведения об обновлении или установке обновления платформы см. в Защитник Windows [update for Защитник Windows.](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)

Все обновления содержат 
- улучшения производительности;
- улучшения в обслуживании; и 
- улучшения интеграции (Cloud, [Microsoft 365 Defender).](/microsoft-365/security/defender/microsoft-365-defender)
<br/>
<details>
<summary> Июнь-2021 (платформа: 4.18.2106.5 | Двигатель: 1.1.18300.4)</summary>

&ensp;Версия обновления аналитики безопасности: **1.343.17.0**  
&ensp;Выпущено: **28 июня 2021 г.**  
&ensp;Платформа: **4.18.2106.5**  
&ensp;Двигатель: **1.1.18300.4**  
&ensp;Этап поддержки: **безопасность и критически важные обновления**
    
### <a name="whats-new"></a>Новые возможности
- Новые элементы управления процессом постепенного выкатки обновлений Microsoft Defender. См. [в рубке Управление постепенным процессом выкатки обновлений Microsoft Defender.](manage-gradual-rollout.md)
- Улучшение движка мониторинга поведения
- Улучшения в октановке определений противомалярийных программ
- Расширенные проверки сетевых событий Edge

### <a name="known-issues"></a>Известные проблемы
Отсутствие известных проблем  
<br/>
</details><details>
<summary> Май-2021 (платформа: 4.18.2105.4 | Двигатель: 1.1.18200.4)</summary>

&ensp;Версия обновления аналитики безопасности: **1.341.8.0**  
&ensp;Выпущено: **3 июня 2021 г.**  
&ensp;Платформа: **4.18.2105.4**  
&ensp;Двигатель: **1.1.18200.4**  
&ensp;Этап поддержки: **безопасность и критически важные обновления**
    
### <a name="whats-new"></a>Новые возможности
- Улучшения мониторинга [поведения](client-behavioral-blocking.md) 
- Функция [фильтрации уведомлений о](network-protection.md) фиксированной защите сети

### <a name="known-issues"></a>Известные проблемы
Отсутствие известных проблем  
<br/>
</details><details>
<summary> Апрель-2021 (платформа: 4.18.2104.14 | Двигатель: 1.1.18100.5)</summary>

&ensp;Версия обновления аналитики безопасности: **1.337.2.0**  
&ensp;Выпущено: **26 апреля 2021**  г. (Двигатель: 1.1.18100.6 выпущен 5 мая 2021 г.) &ensp; Платформа: **4.18.2104.14**  
&ensp;Двигатель: **1.1.18100.5**  
&ensp;Этап поддержки: **безопасность и критически важные обновления**
    
### <a name="whats-new"></a>Новые возможности
- Дополнительная логика мониторинга поведения
- Улучшено обнаружение регистратора ключей режима ядра
- Добавлены новые элементы управления для управления постепенным процессом выкатки обновлений [Microsoft Defender](manage-gradual-rollout.md)


### <a name="known-issues"></a>Известные проблемы
Отсутствие известных проблем  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a>Предыдущие обновления версий: только поддержка технического обновления

После выпуска новой версии пакета поддержка двух предыдущих версий снижается только до технической поддержки. Версии старше, чем указанные в этом разделе, и предоставляются только для технической поддержки обновления. 
<details>
<summary> Март-2021 (платформа: 4.18.2103.7 | Двигатель: 1.1.18000.5)</summary>

&ensp;Версия обновления аналитики безопасности: **1.335.36.0**  
&ensp;Выпущено: **2 апреля 2021 г.**  
&ensp;Платформа: **4.18.2103.7**  
&ensp;Двигатель: **1.1.18000.5**  
&ensp;Этап поддержки: **техническая поддержка обновления (только)**
    
### <a name="whats-new"></a>Новые возможности

- Улучшение движка мониторинга поведения 
- Смягчение последствий атак с расширенной сетью brute-force-attack 
- Дополнительное неудалось поколение событий попытки взлома при включенной защите [tamper](prevent-changes-to-security-settings-with-tamper-protection.md)

### <a name="known-issues"></a>Известные проблемы
Отсутствие известных проблем  
<br/>
</details><details>
<summary> Февраль-2021 (платформа: 4.18.2102.3 | Двигатель: 1.1.17900.7)</summary>

&ensp;Версия обновления аналитики безопасности: **1.333.7.0**  
&ensp;Выпущено: **9 марта 2021 г.**  
&ensp;Платформа: **4.18.2102.3**  
&ensp;Двигатель: **1.1.17900.7**  
&ensp;Этап поддержки: **техническая поддержка обновления (только)**
    
### <a name="whats-new"></a>Новые возможности

- Улучшение восстановления службы с [помощью защиты от взлома](prevent-changes-to-security-settings-with-tamper-protection.md)
- Расширение области защиты от взлома

### <a name="known-issues"></a>Известные проблемы
Отсутствие известных проблем  
<br/>
</details><details>
<summary> Январь-2021 (платформа: 4.18.2101.9 | Двигатель: 1.1.17800.5)</summary>

&ensp;Версия обновления аналитики безопасности: **1.327.1854.0**  
&ensp;Выпущено: **2 февраля 2021 г.**  
&ensp;Платформа: **4.18.2101.9**  
&ensp;Двигатель: **1.1.17800.5**  
&ensp;Этап поддержки: **техническая поддержка обновления (только)**
    
### <a name="whats-new"></a>Новые возможности

- Улучшения обнаружения эксплойтов Shellcode
- Повышенная видимость попыток кражи учетных данных
- Улучшения в области антиуставных функций в антивирусная программа в Microsoft Defender службах
- Улучшенная поддержка эмуляции ARM x64
- Исправление: EDR уведомление о блоке остается в истории угроз после первоначального обнаружения защиты в режиме реального времени

### <a name="known-issues"></a>Известные проблемы
Отсутствие известных проблем  
<br/>
</details><details>
<summary> Ноябрь-2020 (платформа: 4.18.2011.6 | Двигатель: 1.1.17700.4)</summary>

&ensp;Версия обновления аналитики безопасности: **1.327.1854.0**  
&ensp;Выпущено: **03 декабря 2020 г.**  
&ensp;Платформа: **4.18.2011.6**  
&ensp;Двигатель: **1.1.17700.4**  
&ensp;Этап поддержки: **техническая поддержка обновления (только)**
    
### <a name="whats-new"></a>Новые возможности

- Ведение журнала поддержки состояния [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)

### <a name="known-issues"></a>Известные проблемы
Отсутствие известных проблем  
<br/>
</details><details>
<summary> Октябрь-2020 (платформа: 4.18.2010.7 | Двигатель: 1.1.17600.5)</summary>

&ensp;Версия обновления аналитики безопасности: **1.327.7.0**  
&ensp;Выпущено: **29 октября 2020 г.**  
&ensp;Платформа: **4.18.2010.7**  
&ensp;Двигатель: **1.1.17600.5**  
&ensp;Этап поддержки: **техническая поддержка обновления (только)**
    
### <a name="whats-new"></a>Новые возможности

- Новые описания для специальных категорий угроз
- Улучшенные возможности эмуляции
- Улучшенный хост-адрес разрешить/заблокировать возможности
- Новый параметр в CSP Defender для игнорирования объединения локальных исключений пользователей

### <a name="known-issues"></a>Известные проблемы

Отсутствие известных проблем  
<br/>
</details><details>
<summary> Сентябрь-2020 (платформа: 4.18.2009.7 | Двигатель: 1.1.17500.4)</summary>

&ensp;Версия обновления аналитики безопасности: **1.325.10.0**  
&ensp;Выпущено: **01 октября 2020 г.**  
&ensp;Платформа: **4.18.2009.7**  
&ensp;Двигатель: **1.1.17500.4**  
&ensp;Этап поддержки: **техническая поддержка обновления (только)**
    
### <a name="whats-new"></a>Новые возможности

- Для восстановления файлов в карантине требуются разрешения администратора
- XML-форматированные события теперь поддерживаются
- Поддержка CSP для игнорирования слияний исключений
- Новые интерфейсы управления для:
   - Проверка UDP
   - Защита сети на сервере 2019
   - Исключения IP-адресов для защиты сети
- Улучшенная видимость измерений TPM
- Улучшенное сканирование Office VBA

### <a name="known-issues"></a>Известные проблемы

Отсутствие известных проблем  
<br/>
</details>
<details>
<summary> Август-2020 (платформа: 4.18.2008.9 | Двигатель: 1.1.17400.5)</summary>

&ensp;Версия обновления аналитики безопасности: **1.323.9.0**  
&ensp;Выпущено: **27 августа 2020 г.**  
&ensp;Платформа: **4.18.2008.9**  
&ensp;Двигатель: **1.1.17400.5**  
&ensp;Этап поддержки: **техническая поддержка обновления (только)**

### <a name="whats-new"></a>Новые возможности

- Добавление дополнительных событий телеметрии
- Улучшенная телеметрия событий сканирования
- Улучшенный мониторинг поведения при проверке памяти
- Улучшенное сканирование макропотоков
- Добавлен `AMRunningMode` в Get-MpComputerStatus PowerShell
- [ОтключениеAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) игнорируется. антивирусная программа в Microsoft Defender автоматически выключается при обнаружении другой антивирусной программы.


### <a name="known-issues"></a>Известные проблемы
Отсутствие известных проблем  
<br/>
</details>

<details>
<summary> Июль-2020 (платформа: 4.18.2007.8 | Двигатель: 1.1.17300.4)</summary>

&ensp;Версия обновления аналитики безопасности: **1.321.30.0**  
&ensp;Выпущено: **28 июля 2020 г.**  
&ensp;Платформа: **4.18.2007.8**  
&ensp;Двигатель: **1.1.17300.4**  
&ensp;Этап поддержки: **техническая поддержка обновления (только)**
    
### <a name="whats-new"></a>Новые возможности

- Улучшенная телеметрия для BITS
- Улучшенная проверка сертификата подписи кода Authenticode

### <a name="known-issues"></a>Известные проблемы
Отсутствие известных проблем  
<br/>
</details>

<details>
<summary> Июнь-2020 (платформа: 4.18.2006.10 | Двигатель: 1.1.17200.2)</summary>

&ensp;Версия обновления аналитики безопасности: **1.319.20.0**  
&ensp;Выпущено: **22 июня 2020 г.**  
&ensp;Платформа: **4.18.2006.10**  
&ensp;Двигатель: **1.1.17200.2**  
&ensp;Этап поддержки: **техническая поддержка обновления (только)**
    
### <a name="whats-new"></a>Новые возможности

- Возможность указать [расположение журналов поддержки](./collect-diagnostic-data.md)
- Пропуск агрессивной проверки догона в пассивном режиме.
- Разрешить Защитнику обновлять дозы подключений
- Настройка фиксированной производительности при отключении кэшинга 
- Запрос фиксированного реестра 
- Исправленная рандомизация времени сканирования в ADMX

### <a name="known-issues"></a>Известные проблемы
Отсутствие известных проблем  
<br/>
</details>

<details>
<summary> Май-2020 (платформа: 4.18.2005.4 | Двигатель: 1.1.17100.2)</summary>

&ensp;Версия обновления аналитики безопасности: **1.317.20.0**  
&ensp;Выпущено: **26 мая 2020 г.**  
&ensp;Платформа: **4.18.2005.4**  
&ensp;Двигатель: **1.1.17100.2**  
&ensp;Этап поддержки: **техническая поддержка обновления (только)**
    
### <a name="whats-new"></a>Новые возможности

- Улучшенная ведение журнала для событий сканирования
- Улучшенная обработка сбоя режима пользователя.
- Добавлена трассировка событий для защиты Tamper
- Исправленная отправка образца AMSI
- Исправленная блокировка облака AMSI
- Журнал установки фиксированного обновления безопасности

### <a name="known-issues"></a>Известные проблемы
Отсутствие известных проблем  
<br/>
</details>

<details>
<summary> Апрель-2020 (платформа: 4.18.2004.6 | Двигатель: 1.1.17000.2)</summary>

&ensp;Версия обновления аналитики безопасности: **1.315.12.0**  
&ensp;Выпущено: **30 апреля 2020 г.**  
&ensp;Платформа: **4.18.2004.6**  
&ensp;Двигатель: **1.1.17000.2**  
&ensp;Этап поддержки: **техническая поддержка обновления (только)**
    
### <a name="whats-new"></a>Новые возможности
- Улучшения WDfilter
- Добавление дополнительных данных событий для атак на события обнаружения уменьшения поверхности
- Сведения о фиксированной версии в диагностических данных и WMI
- Исправлена неправильная версия платформы в пользовательском интерфейсе после обновления платформы
- Динамический URL-адрес для защиты от угроз без файлов
- Возможность сканирования UEFI
- Расширение ведения журнала для обновлений

### <a name="known-issues"></a>Известные проблемы
Отсутствие известных проблем  
<br/>
</details>

<details>
<summary> Март-2020 (платформа: 4.18.2003.8 | Двигатель: 1.1.16900.2)</summary>

&ensp;Версия обновления аналитики безопасности: **1.313.8.0**  
&ensp;Выпущено: **24 марта 2020 г.**  
&ensp;Платформа: **4.18.2003.8**  
&ensp;Двигатель: **1.1.16900.4**  
&ensp;Этап поддержки: **техническая поддержка обновления (только)**
    
### <a name="whats-new"></a>Новые возможности

- Параметр регулирования ЦП, добавленный в [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)
- Улучшение возможностей диагностики
- уменьшение времени разведданных безопасности (5 минут)
- Расширение возможностей внутреннего журнала двигателя AMSI
- Улучшение уведомления о блокировке процесса
   
### <a name="known-issues"></a>Известные проблемы
**[Исправлено]** антивирусная программа в Microsoft Defender пропускает файлы при запуске сканирования.

<br/>
</details>

<details>

<summary> Февраль-2020 (платформа: - | Двигатель: 1.1.16800.2)</summary>
  

&ensp;Версия обновления аналитики безопасности: **1.311.4.0**   
&ensp;Выпущено: **25 февраля 2020 г.**  
&ensp;Платформа/клиент: **-**  
&ensp;Двигатель: **1.1.16800.2**  
&ensp;Этап поддержки: **техническая поддержка обновления (только)**
     
### <a name="whats-new"></a>Новые возможности

  
### <a name="known-issues"></a>Известные проблемы
Отсутствие известных проблем
<br/>
</details>

<details>
<summary> Январь-2020 (платформа: 4.18.2001.10 | Двигатель: 1.1.16700.2)</summary>
  

Версия обновления аналитики безопасности: **1.309.32.0**  
Выпущено: **30 января 2020 г.**  
Платформа/клиент: **4.18.2001.10**  
Двигатель: **1.1.16700.2**  
&ensp;Этап поддержки: **техническая поддержка обновления (только)**
     
### <a name="whats-new"></a>Новые возможности

- Исправлена BSOD на WS2016 с Exchange
- Обновления платформы поддержки при перенаправлении TMP на сетевой путь
- Версии платформы и двигателя добавляются в [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates) <!-- The preceding URL must include "/en-us" -->
- расширение обновления подписи аварийной ситуации до [пассивного режима](./microsoft-defender-antivirus-compatibility.md)
- Fix 4.18.1911.3 hang
   
### <a name="known-issues"></a>Известные проблемы

**[Исправленные]** устройства, использующие современный режим ожидания, могут испытывать зависание с драйвером Защитник Windows фильтра, что приводит к разрыву защиты. [](/windows-hardware/design/device-experiences/modern-standby)  Затронутые компьютеры, как представляется, не обновляются до последней платформы антивирусного обеспечения.  
<br/>
> [!IMPORTANT]
> Это обновление:
> - для устройств RS1 с более низкой версией платформы для поддержки SHA2;
> - имеет флаг перезагрузки для систем с висячими вопросами;
> - повторно выпущен в апреле 2020 г. и не будет совмещаяся с новыми обновлениями для сохраняемой доступности в будущем;  
> - классифицируются как обновление из-за требования перезагрузки; и
> - предлагается только с [Windows update](https://support.microsoft.com/help/4027667/windows-10-update).
<br/>
</details>

<details>
<summary> Ноябрь-2019 (платформа: 4.18.1911.3 | Двигатель: 1.1.16600.7)</summary>

Версия обновления аналитики безопасности: **1.307.13.0**  
Выпущено: **7 декабря 2019 г.**  
Платформа: **4.18.1911.3**  
Двигатель: **1.1.17000.7**  
Этап поддержки: **поддержка не поддерживается**  
     
### <a name="whats-new"></a>Новые возможности

- Фиксированный уровень отслеживания MpCmdRun
- Исправленная информация версии WDFilter
- Улучшение уведомлений (PUA)
- добавление журналов MRT для поддержки файлов
   
### <a name="known-issues"></a>Известные проблемы
При установке этого обновления устройству требуется пакет скачок 4.18.2001.10 для обновления до последней версии платформы.
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a>антивирусная программа в Microsoft Defender поддержки платформы
Обновления платформы и двигателя предоставляются на ежемесячной основе. Чтобы получить полную поддержку, следите за последними обновлениями платформы. Наша структура поддержки динамична и развивается в два этапа в зависимости от доступности последней версии платформы:

- **Этап обслуживания служб** безопасности и критически важных обновлений . При запуске последней версии платформы вы сможете получать как обновления безопасности, так и критические обновления для платформы защиты от вредоносных программ.
 
- **Этап технической поддержки (только)** — после выпуска новой версии платформы поддержка более старых версий (N-2) будет сокращена только до технической поддержки. Версии платформы старше N-2 больше не будут поддерживаться.*

\*Техническая поддержка будет по-прежнему предоставляться для обновлений из версии Windows 10 версии (см. версию [Platform,](#platform-version-included-with-windows-10-releases)включенную в Windows 10 выпусках) до последней версии платформы.

На этапе технической поддержки (только) коммерчески обоснованные инциденты поддержки будут предоставляться через Службу поддержки клиентов Майкрософт & поддержку и управляемые предложения поддержки Майкрософт (например, Premier Support). Если инцидент поддержки требует эскалации для разработки для получения дополнительных указаний, требует обновления без обеспечения безопасности или обновления безопасности, клиентам будет предложено обновить до последней версии платформы или промежуточного обновления (*).

### <a name="platform-version-included-with-windows-10-releases"></a>Версия платформы, включенная в Windows 10 выпусков
В приведенной ниже таблице приведены антивирусная программа в Microsoft Defender платформы и версии двигателей, которые поставляются с последними Windows 10 выпусками:    

|Windows 10 выпуска  |Версия платформы  |Версия двигателя |Этап поддержки |
|:---|:---|:---|:---|
|2004 (20H1/20H2) |4.18.1909.6 |1.1.17000.2 | Техническая поддержка обновления (только) |
|1909 (19H2) |4.18.1902.5 |1.1.16700.3 | Техническая поддержка обновления (только) |
|1903 (19H1) |4.18.1902.5 |1.1.15600.4 | Техническая поддержка обновления (только) |
|1809 (RS5) |4.18.1807.18075 |1.1.15000.2 | Техническая поддержка обновления (только) |
|1803 (RS4) |4.13.17134.1 |1.1.14600.4 | Техническая поддержка обновления (только) |
|1709 (RS3) |4.12.16299.15 |1.1.14104.0 | Техническая поддержка обновления (только) |
|1703 (RS2) |4.11.15603.2 |1.1.13504.0 | Техническая поддержка обновления (только) |
|1607 (RS1) |4.10.14393.3683 |1.1.12805.0 | Техническая поддержка обновления (только) |  

Сведения Windows 10 релиза см. в Windows [информационном листе жизненного цикла.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a>Обновления для обслуживания и управления изображениями развертывания (DISM)

Рекомендуется обновить Windows 10 (Enterprise, Pro и Домашние выпуски), Windows Server 2019 и Windows Server 2016 изображений установки ОС с последними обновлениями антивирусных и антивирусных программ. Сохранение изображений установки ОС в курсе данных помогает избежать пробела в защите. 

Дополнительные сведения см. в [обновлении Microsoft Defender для Windows изображений установки операционной системы.](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)

<details>
<summary>1.1.2107.02</summary>

&ensp;Версия пакета: **1.1.2107.02**    
&ensp;Версия платформы: **4.18.2105.5**   
&ensp;Версия двигателя: **1.1.18300.4**  
&ensp;Версия подписи: **1.343.658.0**    
    
### <a name="fixes"></a>Исправления
- Нет

### <a name="additional-information"></a>Дополнительные сведения
- Нет  
<br/>
</details><details>
<summary>1.1.2106.01</summary>

&ensp;Версия пакета: **1.1.2106.01**    
&ensp;Версия платформы: **4.18.2104.14**   
&ensp;Версия двигателя: **1.1.18100.6**  
&ensp;Версия подписи: **1.339.1923.0**    
    
### <a name="fixes"></a>Исправления
- Нет

### <a name="additional-information"></a>Дополнительные сведения
- Нет  
<br/>
</details><details>
<summary>1.1.2105.01</summary>

&ensp;Версия пакета: **1.1.2105.01**    
&ensp;Версия платформы: **4.18.2103.7**   
&ensp;Версия двигателя: **1.1.18100.6**  
&ensp;Версия подписи: **1.339.42.0**    
    
### <a name="fixes"></a>Исправления
- Нет

### <a name="additional-information"></a>Дополнительные сведения
- Нет  
<br/>
</details><details>
<summary>1.1.2104.01</summary>

&ensp;Версия пакета: **1.1.2104.01**    
&ensp;Версия платформы: **4.18.2102.4**   
&ensp;Версия двигателя: **1.1.18000.5**  
&ensp;Версия подписи: **1.335.232.0**    
    
### <a name="fixes"></a>Исправления
- Нет

### <a name="additional-information"></a>Дополнительные сведения
- Нет  
<br/>
</details><details>
<summary>1.1.2103.01</summary>

&ensp;Версия пакета: **1.1.2103.01**    
&ensp;Версия платформы: **4.18.2101.9**   
&ensp;Версия двигателя: **1.1.17800.5**  
&ensp;Версия подписи: **1.331.2302.0**    
    
### <a name="fixes"></a>Исправления
- Нет

### <a name="additional-information"></a>Дополнительные сведения
- Нет  
<br/>
</details><details>
<summary>1.1.2102.03</summary>

&ensp;Версия пакета: **1.1.2102.03**    
&ensp;Версия платформы: **4.18.2011.6**   
&ensp;Версия двигателя: **1.1.17800.5**  
&ensp;Версия подписи: **1.331.174.0**    
    
### <a name="fixes"></a>Исправления
- Нет

### <a name="additional-information"></a>Дополнительные сведения
- Нет  
<br/>
</details><details>
<summary>1.1.2101.02</summary>

&ensp;Версия пакета: **1.1.2101.02**    
&ensp;Версия платформы: **4.18.2011.6**   
&ensp;Версия двигателя: **1.1.17700.4**  
&ensp;Версия подписи: **1.329.1796.0**    
    
### <a name="fixes"></a>Исправления
- Нет

### <a name="additional-information"></a>Дополнительные сведения
- Нет  
<br/>
</details><details>
<summary>1.1.2012.01</summary>

&ensp;Версия пакета: **1.1.2012.01**    
&ensp;Версия платформы: **4.18.2010.7**   
&ensp;Версия двигателя: **1.1.17600.5**  
&ensp;Версия для подписи: **1.327.1991.0**    
    
### <a name="fixes"></a>Исправления
- Нет

### <a name="additional-information"></a>Дополнительные сведения
- Нет  
<br/>
</details><details>
<summary>1.1.2011.02</summary>

&ensp;Версия пакета: **1.1.2011.02**    
&ensp;Версия платформы: **4.18.2010.7**   
&ensp;Версия двигателя: **1.1.17600.5**  
&ensp;Версия подписи: **1.327.658.0**    
    
### <a name="fixes"></a>Исправления
- Нет

### <a name="additional-information"></a>Дополнительные сведения
- Обновленные антивирусная программа в Microsoft Defender подписи  
<br/>
</details><details>
<summary>1.1.2011.01</summary>

&ensp;Версия пакета: **1.1.2011.01**    
&ensp;Версия платформы: **4.18.2009.7**  
&ensp;Версия двигателя: **1.1.17600.5**  
&ensp;Версия подписи: **1.327.344.0**    
    
### <a name="fixes"></a>Исправления
- Нет

### <a name="additional-information"></a>Дополнительные сведения
- Нет  
<br/>
</details><details>
<summary>1.1.2009.10</summary>

&ensp;Версия пакета: **1.1.2011.01**    
&ensp;Версия платформы: **4.18.2008.9**   
&ensp;Версия двигателя: **1.1.17400.5**  
&ensp;Версия для подписи: **1.327.2216.0**    
    
### <a name="fixes"></a>Исправления
- Нет

### <a name="additional-information"></a>Дополнительные сведения
- Добавлена поддержка Windows 10 RS1 или более поздней оси установки изображений.  
<br/>
</details>

## <a name="additional-resources"></a>Дополнительные ресурсы

| Статья | Описание  |
|:---|:---|
|[Обновление Microsoft Defender для Windows изображений установки операционной системы](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | Просмотрите пакеты обновления антивирусных программ для изображений установки ОС (WIM и VHD-файлы). Получите антивирусная программа в Microsoft Defender обновления для Windows 10 (Enterprise, Pro и домашних выпусков), Windows Server 2019 и Windows Server 2016 изображений установки.  |
|[Управление загрузкой и приложением обновлений защиты](manage-protection-updates-microsoft-defender-antivirus.md) | Обновления защиты могут быть доставлены из многих источников. |
|[Управление загрузкой и приложением обновлений защиты](manage-protection-update-schedule-microsoft-defender-antivirus.md) | Можно запланировать загрузку обновлений защиты. |
|[Управление обновлениями для устарели конечных точек](manage-outdated-endpoints-microsoft-defender-antivirus.md) | Если конечная точка пропустит обновление или запланированное сканирование, вы можете принудить к обновлению или сканировать при следующем взявке пользователя. |
|[Управление принудительными обновлениями на основе событий](manage-event-based-updates-microsoft-defender-antivirus.md) | Можно установить обновления защиты для скачивания при запуске или после определенных событий защиты с облачной доставкой. |
|[Управление обновлениями для мобильных устройств и виртуальных машин (ВМ)](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| Можно указать параметры, например, следует ли обновлять заряд батареи, которые особенно полезны для мобильных устройств и виртуальных машин. |
