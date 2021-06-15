---
title: Устранение неполадок с антивирусной программой в Microsoft Defender при миграции из сторонного решения
description: Устранение распространенных ошибок при миграции в антивирусная программа в Microsoft Defender
keywords: событие, код ошибки, ведение журнала, устранение неполадок, антивирус защитника Майкрософт, антивирус защитника Windows, миграция
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: article
author: martyav
ms.author: v-maave
ms.custom: nextgen
ms.date: 09/11/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3eb4d01957383efc8df47e9fee6eb6394c80015a
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924387"
---
# <a name="troubleshoot-microsoft-defender-antivirus-while-migrating-from-a-third-party-solution"></a>Устранение неполадок с антивирусной программой в Microsoft Defender при миграции из сторонного решения

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)


Вы можете найти помощь здесь, если вы столкнулись с проблемой при переходе из сторонного решения безопасности в антивирусная программа в Microsoft Defender.

## <a name="review-event-logs"></a>Просмотр журналов событий

Откройте приложение для просмотра событий, выбрав значок **Поиска** в панели задач и ищите *зрителя событий.*

Сведения о антивирусная программа в Microsoft Defender можно найти в журналах **приложений** и служб  >  **Microsoft**  >  **Windows**  >  **Защитник Windows.** 

Оттуда выберите **Открыть под операционной** . 

Выбор события из области сведений позволит вам получить дополнительные сведения о событии в нижней области в вкладке **Общие** и **Подробные** сведения.

## <a name="microsoft-defender-antivirus-wont-start"></a>антивирусная программа в Microsoft Defender не начнется

Эта проблема может проявляться в виде нескольких различных ИД событий, все из которых имеют ту же причину.

### <a name="associated-event-ids"></a>Связанные ID события

 Идентификатор события | Имя журнала | Описание | Источник
-|-|-|-
15 | Для приложений | Обновленный Защитник Windows успешно для SECURITY_PRODUCT_STATE_OFF. | Центр безопасности
5007 | Microsoft-Windows-Защитник Windows/operational | антивирусная программа Конфигурация изменилась.  Если это неожиданное событие, необходимо просмотреть параметры, так как это может быть результатом вредоносных программ.<br /><br />**Старое значение:** Default\IsServiceRunning = 0x0<br />**Новое значение:** HKLM\SOFTWARE\Microsoft\Защитник Windows\IsServiceRunning = 0x1 | Защитник Windows
5010 | Microsoft-Windows-Защитник Windows/operational | антивирусная программа для шпионских программ и другого потенциально нежелательного программного обеспечения отключен. | Защитник Windows

### <a name="how-to-tell-if-microsoft-defender-antivirus-wont-start-because-a-third-party-antivirus-is-installed"></a>Как узнать, антивирусная программа в Microsoft Defender не будет запускаться, так как установлен сторонний антивирус

На устройстве Windows 10, если вы не используете Microsoft Defender для endpoint и у вас установлен сторонний антивирус, антивирусная программа в Microsoft Defender автоматически отключается. Если вы используете Microsoft Defender для конечной точки с установленным сторонним антивирусом, антивирусная программа в Microsoft Defender начнется в пассивном режиме с пониженной функциональностью.

> [!TIP]
> Описанный сценарий применяется только к Windows 10. Другие версии Windows [имеют](microsoft-defender-antivirus-compatibility.md) различные ответы на антивирусная программа в Microsoft Defender, которые запускаются вместе с сторонним программным обеспечением безопасности.

#### <a name="use-services-app-to-check-if-microsoft-defender-antivirus-is-turned-off"></a>Используйте приложение Services для проверки антивирусная программа в Microsoft Defender отключения

Чтобы открыть приложение Services, выберите значок **Поиска** из панели задач и поиск *служб.* Вы также можете открыть приложение из командной строки, введя *services.msc*.

Сведения о антивирусная программа в Microsoft Defender будут перечислены в приложении Services в **Защитник Windows**  >  **Operational.** Имя антивирусной службы *антивирусная программа Service*.

При проверке приложения вы можете увидеть, что антивирусная программа *служба* настроена вручную, но при попытке запустить эту службу вручную вы получите предупреждение о том, что служба антивирусная программа на локальном компьютере запущена, а затем *остановлена. Некоторые службы автоматически останавливаются,* если они не используются другими службами или программами.

Это означает, антивирусная программа в Microsoft Defender автоматически отключен для сохранения совместимости с сторонним антивирусом.

#### <a name="generate-a-detailed-report"></a>Создание подробного отчета

Подробный отчет о текущих активных групповых политиках можно создать, открыв командную подсказку в **режиме Run as admin,** а затем введите следующую команду:

```powershell
GPresult.exe /h gpresult.html
```

Это позволит создать отчет, расположенный *на уровне ./gpresult.html*. Откройте этот файл, и вы можете увидеть следующие результаты, в зависимости от антивирусная программа в Microsoft Defender отключения.

##### <a name="group-policy-results"></a>Результаты групповой политики

##### <a name="if-security-settings-are-implemented-via-group-policy-gpo-at-the-domain-or-local-level-or-though-system-center-configuration-manager-sccm"></a>Если параметры безопасности реализованы с помощью групповой политики (GPO) на домене или локальном уровне, или если диспетчер конфигурации центра систем (SCCM)

В отчете GPResults в заголовке *Windows компоненты/антивирусная программа* вы можете увидеть что-то похожее на следующую запись, указав, что антивирусная программа в Microsoft Defender отключено.

Политика | Setting | Выигрыш GPO
-|-|-
Отключите антивирусная программа | Включено | Win10-Workstations

###### <a name="if-security-settings-are-implemented-via-group-policy-preference-gpp"></a>Если параметры безопасности реализованы с помощью предпочтений групповой политики (GPP)

В заголовке Элемент реестра *(ключевой путь: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender, имя значения: DisableAntiSpyware)* вы можете увидеть что-то похожее на следующую запись, указав, что антивирусная программа в Microsoft Defender отключено.

DisableAntiSpyware | -
-|-
Выигрыш GPO | Win10-Workstations
Результат: успех | 
**Общие** | 
Действие | Update
**Свойства** | 
Куст | HKEY_LOCAL_MACHINE
Путь ключа | SOFTWARE\Policies\Microsoft\Защитник Windows
Value name | DisableAntiSpyware
Тип значения | REG_DWORD
Value data | 0x1 (1)

###### <a name="if-security-settings-are-implemented-via-registry-key"></a>Если параметры безопасности реализованы с помощью ключа реестра

В отчете может содержаться следующий текст, указывающий, что антивирусная программа в Microsoft Defender отключен:
 
> Реестр (regedit.exe)
>
> HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender DisableAntiSpyware (dword) 1 (hex)

###### <a name="if-security-settings-are-set-in-windows-or-your-windows-server-image"></a>Если параметры безопасности установлены в Windows или изображении Windows Server

Ваш воображающий администратор мог установить политику **[безопасности, DisableAntiSpyware,](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)** локально через *GPEdit.exe,* *LGPO.exe* или путем изменения реестра в последовательности задач. Можно настроить [идентификатор доверенных изображений](/windows-hardware/manufacture/desktop/configure-a-trusted-image-identifier-for-windows-defender) для антивирусная программа в Microsoft Defender.

### <a name="turn-microsoft-defender-antivirus-back-on"></a>Включаем антивирусная программа в Microsoft Defender обратно

антивирусная программа в Microsoft Defender автоматически включит, если другой антивирус в настоящее время не активен. Чтобы полностью отключить сторонний антивирус, антивирусная программа в Microsoft Defender работать с полным функционалом.

> [!WARNING]
> Решения, предполагающие изменение значений *Защитник Windows* для *wdboot,* *wdfilter,* *wdnisdrv,* *wdnissvc* и *windefend* в HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services неподтвердимы, и могут заставить вас повторное изображение системы.

Пассивный режим доступен, если вы начинаете использовать Microsoft Defender для endpoint и сторонний антивирус вместе с антивирусная программа в Microsoft Defender. Пассивный режим позволяет Microsoft Defender сканировать файлы и обновлять себя, но не устраняет угрозы. Кроме того, мониторинг поведения в [режиме](configure-real-time-protection-microsoft-defender-antivirus.md) реального времени не доступен в пассивном режиме, если только не развернута защита от потери данных конечной точки [(DLP).](/microsoft-365/security/defender-endpoint/information-protection-in-windows-overview)

Еще одна функция, [известная](limited-periodic-scanning-microsoft-defender-antivirus.md)как ограниченное периодическое сканирование, доступна конечным пользователям, антивирусная программа в Microsoft Defender установлено автоматическое отключение. Эта функция позволяет антивирусная программа в Microsoft Defender периодически сканировать файлы рядом с сторонним антивирусом, используя ограниченное число обнаружения.

> [!IMPORTANT]
> Ограниченное периодическое сканирование не рекомендуется в корпоративных средах. Возможности обнаружения, управления и отчетов, доступные при антивирусная программа в Microsoft Defender в этом режиме, уменьшаются по сравнению с активным режимом.

### <a name="see-also"></a>См. также

* [антивирусная программа в Microsoft Defender совместимости](microsoft-defender-antivirus-compatibility.md)
* [антивирусная программа в Microsoft Defender в приложении Безопасность Windows](microsoft-defender-security-center-antivirus.md)