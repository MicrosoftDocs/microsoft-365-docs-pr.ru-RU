---
title: Microsoft Defender для конечной точки для государственных клиентов США
description: Узнайте о доступных требованиях и возможностях Microsoft Defender для конечной точки для государственных клиентов США
keywords: правительство, gcc, высокая, требования, возможности, защитник, защитник atp, mdatp, конечная точка, dod
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 31928deddc2a504cc0b6c91af287e4977791c920
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073909"
---
# <a name="microsoft-defender-for-endpoint-for-us-government-customers"></a>Microsoft Defender для конечной точки для государственных клиентов США

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Microsoft Defender для конечных клиентов правительства США, встроенный в среду правительства Azure в США, использует те же самые лежащие технологии, что и Defender for Endpoint в Azure Commercial.

Это предложение доступно клиентам GCC, GCC High и DoD и основано на той же профилактике, обнаружении, расследовании и исправлении, что и коммерческая версия. Однако существуют некоторые различия в доступности возможностей для этого предложения.

> [!NOTE]
> Если вы клиент GCC, использующий Defender для конечной точки в коммерческих целях, обратитесь к страницам общедоступных документов.

## <a name="licensing-requirements"></a>Требования к лицензированию
Microsoft Defender для конечных точек для государственных клиентов США требует одно из следующих предложений по лицензированию томов Корпорации Майкрософт:

### <a name="desktop-licensing"></a>Лицензирование настольных компьютеров
GCC | GCC High | DoD
:---|:---|:---
Windows 10 Корпоративный GCC E5 | Windows 10 Enterprise E5 для GCC High | Windows 10 Enterprise E5 для DOD
| | Microsoft 365 E5 для GCC High | 
| | Microsoft 365 G5 Security for GCC High | 
Защитник Майкрософт для конечной точки — GCC | Microsoft Defender для конечной точки для GCC High | Microsoft Defender для конечной точки для DOD

### <a name="server-licensing"></a>Лицензирование сервера
GCC | GCC High | DoD
:---|:---|:---
Microsoft Defender для GCC конечного сервера | Microsoft Defender для конечного сервера для GCC High | Защитник Microsoft для конечного сервера для DOD
Защитник Azure для серверов | Защитник Azure для серверов — правительство | Защитник Azure для серверов — правительство

> [!NOTE]
> Лицензирование doD будет доступно только в общей доступности DoD.

<br>

## <a name="portal-urls"></a>URL-адреса портала
Ниже приводится URL-адрес портала Microsoft Defender для конечных точек для государственных клиентов США:

Тип клиента | URL-адрес портала
:---|:---
GCC | https://gcc.securitycenter.microsoft.us
GCC High | https://securitycenter.microsoft.us
DoD (PREVIEW) | https://securitycenter.microsoft.us

<br>

## <a name="endpoint-versions"></a>Версии конечной точки

### <a name="standalone-os-versions"></a>Автономные версии ОС
Поддерживаются следующие версии ОС:

Версия ОС | GCC | GCC High | DoD (PREVIEW)
:---|:---|:---|:---
Windows 10, версия 20H2 (с [KB4586853)](https://support.microsoft.com/help/4586853) | ![Да](images/svg/check-yes.svg) | ![Да](images/svg/check-yes.svg) | ![Да](images/svg/check-yes.svg)
Windows 10, версия 2004 (с [KB4586853)](https://support.microsoft.com/help/4586853) | ![Да](/security/defender-endpoint/images/svg/check-yes) | ![Да](/security/defender-endpoint/images/svg/check-yes) | ![Да](/security/defender-endpoint/images/svg/check-yes)
Windows 10, версия 1909 (с [KB4586819)](https://support.microsoft.com/help/4586819) | ![Да](/security/defender-endpoint/images/svg/check-yes) | ![Да](/security/defender-endpoint/images/svg/check-yes) | ![Да](/security/defender-endpoint/images/svg/check-yes)
Windows 10, версия 1903 (с [KB4586819)](https://support.microsoft.com/help/4586819) | ![Да](/security/defender-endpoint/images/svg/check-yes) | ![Да](/security/defender-endpoint/images/svg/check-yes) | ![Да](/security/defender-endpoint/images/svg/check-yes)
Windows 10, версия 1809 (с [KB4586839)](https://support.microsoft.com/help/4586839) | ![Да](/security/defender-endpoint/images/svg/check-yes) | ![Да](/security/defender-endpoint/images/svg/check-yes) | ![Да](/security/defender-endpoint/images/svg/check-yes)
Windows 10, версия 1803 (с [KB4598245)](https://support.microsoft.com/help/4598245) | ![Да](/security/defender-endpoint/images/svg/check-yes) | ![Да](/security/defender-endpoint/images/svg/check-yes) | ![Да](/security/defender-endpoint/images/svg/check-yes)
Windows 10, версия 1709 | ![Нет](/security/defender-endpoint/images/svg/check-no)<br>Примечание. Не будет поддерживаться | ![Да ](/security/defender-endpoint/images/svg/check-yes) с [KB4499147](https://support.microsoft.com/help/4499147)<br>Примечание: [Deprecated](https://docs.microsoft.com/lifecycle/announcements/revised-end-of-service-windows-10-1709), пожалуйста, обновление | ![Нет](/security/defender-endpoint/images/svg/check-no)<br>Примечание. Не будет поддерживаться
Windows 10, версия 1703 и ранее | ![Нет](/security/defender-endpoint/images/svg/check-no)<br>Примечание. Не будет поддерживаться | ![Нет](/security/defender-endpoint/images/svg/check-no)<br>Примечание. Не будет поддерживаться | ![Нет](/security/defender-endpoint/images/svg/check-no)<br>Примечание. Не будет поддерживаться
Windows Server 2019 [(с KB4586839)](https://support.microsoft.com/help/4586839) | ![Да](/security/defender-endpoint/images/svg/check-yes) | ![Да](/security/defender-endpoint/images/svg/check-yes) | ![Да](/security/defender-endpoint/images/svg/check-yes)
Windows Server 2016 | ![Да](/security/defender-endpoint/images/svg/check-yes) | ![Да](/security/defender-endpoint/images/svg/check-yes) | ![Да](/security/defender-endpoint/images/svg/check-yes)
Windows Server 2012 R2 | ![Да](/security/defender-endpoint/images/svg/check-yes) | ![Да](/security/defender-endpoint/images/svg/check-yes) | ![Да](/security/defender-endpoint/images/svg/check-yes)
Windows Server 2008 R2 с пакетом обновления 1 (SP1) | ![Да](/security/defender-endpoint/images/svg/check-yes) | ![Да](/security/defender-endpoint/images/svg/check-yes) | ![Да](/security/defender-endpoint/images/svg/check-yes)
Windows 8.1 Корпоративная | ![Да](/security/defender-endpoint/images/svg/check-yes) | ![Да](/security/defender-endpoint/images/svg/check-yes) | ![Да](/security/defender-endpoint/images/svg/check-yes)
Windows 8 профессиональная | ![Да](/security/defender-endpoint/images/svg/check-yes) | ![Да](/security/defender-endpoint/images/svg/check-yes) | ![Да](/security/defender-endpoint/images/svg/check-yes)
Windows 7 SP1 Enterprise | ![Да](/security/defender-endpoint/images/svg/check-yes) | ![Да](/security/defender-endpoint/images/svg/check-yes) | ![Да](/security/defender-endpoint/images/svg/check-yes)
Windows 7 SP1 Pro | ![Да](/security/defender-endpoint/images/svg/check-yes) | ![Да](/security/defender-endpoint/images/svg/check-yes) | ![Да](/security/defender-endpoint/images/svg/check-yes)
Linux | ![Нет](/security/defender-endpoint/images/svg/check-no) В разработке | ![Нет](/security/defender-endpoint/images/svg/check-no) В разработке | ![Нет](/security/defender-endpoint/images/svg/check-no) В разработке
macOS | ![Нет](/security/defender-endpoint/images/svg/check-no) В разработке | ![Нет](/security/defender-endpoint/images/svg/check-no) В разработке | ![Нет](/security/defender-endpoint/images/svg/check-no) В разработке
Android | ![Нет](/security/defender-endpoint/images/svg/check-no) На неополненном техническом отставание | ![Нет](/security/defender-endpoint/images/svg/check-no) На неополненном техническом отставание | ![Нет](/security/defender-endpoint/images/svg/check-no) На неополненном техническом отставание
iOS | ![Нет](/security/defender-endpoint/images/svg/check-no) На неополненном техническом отставание | ![Нет](/security/defender-endpoint/images/svg/check-no) На неополненном техническом отставание | ![Нет](/security/defender-endpoint/images/svg/check-no) На неополненном техническом отставание

> [!NOTE]
> Если исправление задано, оно должно быть развернуто до встройки устройства, чтобы настроить Defender для конечной точки в правильную среду.

> [!NOTE]
> Попытка на борту устройств Windows старше Windows 10 или Windows Server 2019 с помощью [агента мониторинга Майкрософт?](configure-server-endpoints.md#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma) Вам необходимо выбрать "Azure US Government" в "Azure Cloud", если с [](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line) помощью мастера настройки [или](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)с помощью командной строки или скрипта [задан](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation) параметр "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" до 1.

### <a name="os-versions-when-using-azure-defender-for-servers"></a>Версии ОС при использовании Azure Defender для серверов
При использовании Azure Defender для серверов поддерживаются следующие версии [ОС:](https://docs.microsoft.com/azure/security-center/security-center-wdatp)

Версия ОС | GCC | GCC High | DoD (PREVIEW)
:---|:---|:---|:---
Windows Server 2016 | ![Да](/security/defender-endpoint/images/svg/check-yes) | ![Да](/security/defender-endpoint/images/svg/check-yes) | ![Да](/security/defender-endpoint/images/svg/check-yes)
Windows Server 2012 R2 | ![Да](/security/defender-endpoint/images/svg/check-yes) | ![Да](/security/defender-endpoint/images/svg/check-yes) | ![Да](/security/defender-endpoint/images/svg/check-yes)
Windows Server 2008 R2 с пакетом обновления 1 (SP1) | ![Да](/security/defender-endpoint/images/svg/check-yes) | ![Да](/security/defender-endpoint/images/svg/check-yes) | ![Да](/security/defender-endpoint/images/svg/check-yes)

<br>

## <a name="required-connectivity-settings"></a>Необходимые параметры подключения
Если прокси-сервер или брандмауэр блокирует весь трафик по умолчанию и пропускает только определенные домены, добавьте домены, перечисленные в загружаемой электронной таблице, в список разрешенных доменов.

В следующей загружаемой таблице перечислены службы и связанные с ними URL-адреса, к которые должна подключиться ваша сеть. Убедитесь, что нет правил фильтрации брандмауэра или сети,  которые бы отказывали в доступе к этим URL-адресам, или создали правило разрешить специально для них.

Таблица списка доменов | Описание
:-----|:-----
![Изображение пальца для таблицы URL-адресов Microsoft Defender для конечных точек](images/mdatp-urls.png)<br/> | Таблица определенных DNS-записей для расположения служб, географических местоположений и ОС. <br><br>[Скачайте таблицу здесь.](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) 

Дополнительные сведения см. в [перенастройке](configure-proxy-internet.md)параметров прокси-сервера устройства и подключения к Интернету.

> [!NOTE]
> Таблица также содержит коммерческие URL-адреса, чтобы проверить вкладки "Us Gov". <br> При фильтрации и посмотрите записи с меткой "US Gov" и ваше облако в столбце географии.

<br>

## <a name="api"></a>API
Вместо общедоступных URL-адресов, перечисленных в документации [API,](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/apis-intro)необходимо использовать следующие URL-адреса:

Тип конечной точки | GCC | GCC High & DoD (PREVIEW)
:---|:---|:---
Вход | `https://login.microsoftonline.com` | `https://login.microsoftonline.us`
Защитник для API конечной точки | `https://api-gcc.securitycenter.microsoft.us` | `https://api-gov.securitycenter.microsoft.us`
SIEM | `https://wdatp-alertexporter-us.gcc.securitycenter.windows.us` | `https://wdatp-alertexporter-us.securitycenter.windows.us`

<br>

## <a name="feature-parity-with-commercial"></a>Паритет функций с коммерческими
Defender for Endpoint не имеет полного паритета с коммерческим предложением. Хотя наша цель заключается в том, чтобы предоставить все коммерческие функции и функции нашим государственным клиентам США, есть некоторые возможности, которые еще не доступны, которые мы хотим выделить.

Это известные пробелы на февраль 2021 г.:

Функция | GCC | GCC High | DoD (PREVIEW)
:---|:---|:---|:---
Автоматическое расследование и исправление: живой ответ | ![Да](/security/defender-endpoint/images/svg/check-yes) | ![Да](/security/defender-endpoint/images/svg/check-yes) | ![Да](/security/defender-endpoint/images/svg/check-yes)
Автоматическое расследование и исправление: реагирование на оповещения Office 365 | ![Нет](/security/defender-endpoint/images/svg/check-no) На неополненном техническом отставание | ![Нет](/security/defender-endpoint/images/svg/check-no) На неополненном техническом отставание | ![Нет](/security/defender-endpoint/images/svg/check-no) На неополненном техническом отставание
Уведомления по электронной почте | ![Нет](/security/defender-endpoint/images/svg/check-no) Развертывание | ![Нет](/security/defender-endpoint/images/svg/check-no) Развертывание | ![Нет](/security/defender-endpoint/images/svg/check-no) Развертывание
Лаборатория оценки | ![Да](/security/defender-endpoint/images/svg/check-yes) | ![Да](/security/defender-endpoint/images/svg/check-yes) | ![Да](/security/defender-endpoint/images/svg/check-yes)
Управление и API: отчет о состоянии устройств и соблюдении требований | ![Да](/security/defender-endpoint/images/svg/check-yes) | ![Да](/security/defender-endpoint/images/svg/check-yes) | ![Да](/security/defender-endpoint/images/svg/check-yes)
Управление и API: интеграция с сторонними продуктами | ![Нет](/security/defender-endpoint/images/svg/check-no) В разработке | ![Нет](/security/defender-endpoint/images/svg/check-no) В разработке | ![Нет](/security/defender-endpoint/images/svg/check-no) В разработке
Управление и API: потоковый API | ![Да](/security/defender-endpoint/images/svg/check-yes) | ![Нет](/security/defender-endpoint/images/svg/check-no) В разработке | ![Нет](/security/defender-endpoint/images/svg/check-no) В разработке
Управление и API: отчет о защите от угроз | ![Да](/security/defender-endpoint/images/svg/check-yes) | ![Да](/security/defender-endpoint/images/svg/check-yes) | ![Да](/security/defender-endpoint/images/svg/check-yes)
Управление & уязвимостей | ![Да](/security/defender-endpoint/images/svg/check-yes) | ![Да](/security/defender-endpoint/images/svg/check-yes) | ![Да](/security/defender-endpoint/images/svg/check-yes)
Аналитика угроз | ![Да](/security/defender-endpoint/images/svg/check-yes) | ![Да](/security/defender-endpoint/images/svg/check-yes) | ![Да](/security/defender-endpoint/images/svg/check-yes)
Фильтрация веб-контента | ![Нет](/security/defender-endpoint/images/svg/check-no) В разработке | ![Нет](/security/defender-endpoint/images/svg/check-no) В разработке | ![Нет](/security/defender-endpoint/images/svg/check-no) В разработке
Интеграция: Azure Sentinel | ![Да](/security/defender-endpoint/images/svg/check-yes) | ![Нет](/security/defender-endpoint/images/svg/check-no) В разработке | ![Нет](/security/defender-endpoint/images/svg/check-no) В разработке
Интеграция: безопасность облачных приложений Майкрософт | ![Нет](/security/defender-endpoint/images/svg/check-no) На неополненном техническом отставание | ![Нет](/security/defender-endpoint/images/svg/check-no) На неополненном техническом отставание | ![Нет](/security/defender-endpoint/images/svg/check-no) На неополненном техническом отставание
Интеграция: Microsoft Compliance Manager | ![Нет](/security/defender-endpoint/images/svg/check-no) На неополненном техническом отставание | ![Нет](/security/defender-endpoint/images/svg/check-no) На неополненном техническом отставание | ![Нет](/security/defender-endpoint/images/svg/check-no) На неополненном техническом отставание
Интеграция: Защитник Microsoft для удостоверений | ![Нет](/security/defender-endpoint/images/svg/check-no) На неополненном техническом отставание | ![Нет](/security/defender-endpoint/images/svg/check-no) На неополненном техническом отставание | ![Нет](/security/defender-endpoint/images/svg/check-no) На неополненном техническом отставание
Интеграция: Microsoft Defender для Office 365 | ![Нет](/security/defender-endpoint/images/svg/check-no) На неополненном техническом отставание | ![Нет](/security/defender-endpoint/images/svg/check-no) На неополненном техническом отставание | ![Нет](/security/defender-endpoint/images/svg/check-no) На неополненном техническом отставание
Интеграция: DLP конечной точки Майкрософт | ![Нет](/security/defender-endpoint/images/svg/check-no) На неополненном техническом отставание | ![Нет](/security/defender-endpoint/images/svg/check-no) На неополненном техническом отставание | ![Нет](/security/defender-endpoint/images/svg/check-no) На неополненном техническом отставание
Интеграция: Microsoft Intune | ![Да](/security/defender-endpoint/images/svg/check-yes) | ![Нет](/security/defender-endpoint/images/svg/check-no) В разработке | ![Нет](/security/defender-endpoint/images/svg/check-no) В разработке
Интеграция: Microsoft Power Automate & Azure Logic Apps | ![Да](/security/defender-endpoint/images/svg/check-yes) | ![Нет](/security/defender-endpoint/images/svg/check-no) В разработке | ![Нет](/security/defender-endpoint/images/svg/check-no) В разработке
Интеграция: Skype для бизнеса / Teams | ![Да](/security/defender-endpoint/images/svg/check-yes) | ![Да](/security/defender-endpoint/images/svg/check-yes) | ![Да](/security/defender-endpoint/images/svg/check-yes)
Microsoft Threat Experts | ![Нет](/security/defender-endpoint/images/svg/check-no) На неополненном техническом отставание | ![Нет](/security/defender-endpoint/images/svg/check-no) На неополненном техническом отставание | ![Нет](/security/defender-endpoint/images/svg/check-no) На неополненном техническом отставание
