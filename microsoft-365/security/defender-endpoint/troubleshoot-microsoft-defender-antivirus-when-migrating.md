---
title: Устранение неполадок антивируса Microsoft Defender при миграции из сторонного решения
description: Устранение распространенных ошибок при переходе на антивирус Microsoft Defender
keywords: событие, код ошибки, ведение журнала, устранение неполадок, антивирус защитника Майкрософт, антивирус защитника Windows, миграция
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: martyav
ms.author: v-maave
ms.custom: nextgen
ms.date: 09/11/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 2ca486b86c24e18ae08753b5e88f2eb42986dddf
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691362"
---
# <a name="troubleshoot-microsoft-defender-antivirus-while-migrating-from-a-third-party-solution"></a>Устранение неполадок антивируса Microsoft Defender при миграции из сторонного решения

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)


Вы можете найти помощь здесь, если вы столкнулись с проблемой при переходе из сторонного решения безопасности в антивирус Microsoft Defender.

## <a name="review-event-logs"></a>Просмотр журналов событий

Откройте приложение для просмотра событий, выбрав значок **Поиска** в панели задач и ищите *зрителя событий.*

Сведения о антивирусе Microsoft Defender можно найти в журналах приложений и служб  >  **Microsoft**  >  **Windows**  >  **Защитник Windows.** 

Оттуда выберите **Открыть под операционной** . 

Выбор события из области сведений позволит вам получить дополнительные сведения о событии в нижней области в вкладке **Общие** и **Подробные** сведения.

## <a name="microsoft-defender-antivirus-wont-start"></a>Антивирус Microsoft Defender не запустится

Эта проблема может проявляться в виде нескольких различных ИД событий, все из которых имеют ту же причину.

### <a name="associated-event-ids"></a>Связанные ID события

 Идентификатор события | Имя журнала | Описание | Source
-|-|-|-
15  | Для приложений | Обновленный Защитник Windows успешно для SECURITY_PRODUCT_STATE_OFF. | Центр безопасности
5007 | Microsoft-Windows-Защитник Windows/Operational | Защитник Windows конфигурация антивирусов изменилась.  Если это неожиданное событие, необходимо просмотреть параметры, так как это может быть результатом вредоносных программ.<br /><br />**Старое значение:** Default\IsServiceRunning = 0x0<br />**Новое значение:** HKLM\SOFTWARE\Microsoft\Защитник Windows\IsServiceRunning = 0x1 | Защитник Windows
5010 | Microsoft-Windows-Защитник Windows/Operational | Защитник Windows антивирусное сканирование для программ-шпионов и других потенциально нежелательных программ отключено. | Защитник Windows

### <a name="how-to-tell-if-microsoft-defender-antivirus-wont-start-because-a-third-party-antivirus-is-installed"></a>Как узнать, не запустится ли антивирус Microsoft Defender из-за установки сторонного антивируса

На устройстве Windows 10, если вы не используете Microsoft Defender для конечной точки и у вас установлен сторонний антивирус, антивирус Microsoft Defender будет автоматически отключен. Если вы используете Microsoft Defender для конечной точки с установленным сторонним антивирусом, антивирус Microsoft Defender запустится в пассивном режиме с пониженной функциональностью.

> [!TIP]
> Описанный сценарий применяется только к Windows 10. Другие версии Windows имеют различные ответы [на](microsoft-defender-antivirus-compatibility.md) антивирус Microsoft Defender, который запускается вместе с сторонним программным обеспечением безопасности.

#### <a name="use-services-app-to-check-if-microsoft-defender-antivirus-is-turned-off"></a>Использование приложения Services для проверки отключения антивируса Microsoft Defender

Чтобы открыть приложение Services, выберите значок **Поиска** из панели задач и поиск *служб.* Вы также можете открыть приложение из командной строки, введя *services.msc*.

Сведения о антивирусе Microsoft Defender будут перечислены в приложении Services в **Защитник Windows**  >  **Operational.** Имя антивирусной службы *Защитник Windows антивирусной службы*.

При проверке приложения можно  увидеть, что Защитник Windows антивирусная служба настроена вручную, но при попытке запустить эту службу вручную вы получите предупреждение о том, что служба Защитник Windows антивирусной службы на локальном компьютере запущена, а затем *остановлена. Некоторые службы автоматически останавливаются,* если они не используются другими службами или программами.

Это означает, что антивирус Microsoft Defender автоматически отключен для сохранения совместимости с сторонним антивирусом.

#### <a name="generate-a-detailed-report"></a>Создание подробного отчета

Подробный отчет о текущих активных групповых политиках можно создать, открыв командную подсказку в **режиме Run as admin,** а затем введите следующую команду:

```powershell
GPresult.exe /h gpresult.html
```

Это позволит создать отчет, расположенный *на уровне ./gpresult.html*. Откройте этот файл, и вы увидите следующие результаты в зависимости от того, как был отключен антивирус Microsoft Defender.

##### <a name="group-policy-results"></a>Результаты групповой политики

##### <a name="if-security-settings-are-implemented-via-group-policy-gpo-at-the-domain-or-local-level-or-though-system-center-configuration-manager-sccm"></a>Если параметры безопасности реализованы с помощью групповой политики (GPO) на домене или локальном уровне, или если диспетчер конфигурации центра систем (SCCM)

В отчете GPResults в статье Windows *Components/Защитник Windows Antivirus* можно увидеть что-то похожее на следующую запись, указывающее на отключение антивируса Microsoft Defender.

Политика | Setting | Выигрыш GPO
-|-|-
Отключение Защитник Windows антивируса | Включено | Win10-Workstations

###### <a name="if-security-settings-are-implemented-via-group-policy-preference-gpp"></a>Если параметры безопасности реализованы с помощью предпочтений групповой политики (GPP)

В заголовке Элемент реестра *(ключевой путь: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender, имя значения: DisableAntiSpyware)* вы можете увидеть что-то похожее на следующую запись, указав, что антивирус Microsoft Defender отключен.

DisableAntiSpyware | -
-|-
Выигрыш GPO | Win10-Workstations
Результат: успех | 
**Общие** | 
Action | Update
**Свойства** | 
Куст | HKEY_LOCAL_MACHINE
Путь ключа | SOFTWARE\Policies\Microsoft\Защитник Windows
Value name | DisableAntiSpyware
Тип значения | REG_DWORD
Value data | 0x1 (1)

###### <a name="if-security-settings-are-implemented-via-registry-key"></a>Если параметры безопасности реализованы с помощью ключа реестра

В отчете может содержаться следующий текст, указывающий на отключение антивируса Microsoft Defender:
 
> Реестр (regedit.exe)
>
> HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender DisableAntiSpyware (dword) 1 (hex)

###### <a name="if-security-settings-are-set-in-windows-or-your-windows-server-image"></a>Если параметры безопасности установлены в Windows или на изображении Windows Server

Ваш воображающий администратор мог установить политику **[безопасности, DisableAntiSpyware,](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)** локально через *GPEdit.exe,* *LGPO.exe* или путем изменения реестра в последовательности задач. Можно настроить [надежный идентификатор изображения для](/windows-hardware/manufacture/desktop/configure-a-trusted-image-identifier-for-windows-defender) антивируса Microsoft Defender.

### <a name="turn-microsoft-defender-antivirus-back-on"></a>Включив антивирус Microsoft Defender

Антивирус Microsoft Defender автоматически включит, если другой антивирус в настоящее время не активен. Чтобы убедиться, что антивирус Microsoft Defender может работать с полным функционалом, необходимо полностью отключить сторонний антивирус.

> [!WARNING]
> Решения, предполагающие изменение *значений Защитник Windows* для *wdboot,* *wdfilter,* *wdnisdrv, wdnissvc* и *windefend* в HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services, неподтвердимы, и могут заставить вас повторно образ вашей системы. 

Пассивный режим доступен, если вы начинаете использовать Microsoft Defender для конечной точки и сторонний антивирус вместе с антивирусом Microsoft Defender. Пассивный режим позволяет Microsoft Defender сканировать файлы и обновлять себя, но не устраняет угрозы. Кроме того, мониторинг поведения в [режиме](configure-real-time-protection-microsoft-defender-antivirus.md) реального времени не доступен в пассивном режиме, если только не развернута защита от потери данных конечной точки [(DLP).](/microsoft-365/security/defender-endpoint/information-protection-in-windows-overview)

Еще одна функция, [известная](limited-periodic-scanning-microsoft-defender-antivirus.md)как ограниченное периодическое сканирование, доступна конечным пользователям при автоматическом отключении антивируса Microsoft Defender. Эта функция позволяет антивирусу Microsoft Defender периодически сканировать файлы вместе с сторонним антивирусом, используя ограниченное число обнаружения.

> [!IMPORTANT]
> Ограниченное периодическое сканирование не рекомендуется в корпоративных средах. Возможности обнаружения, управления и отчетов, доступные при запуске антивируса Microsoft Defender в этом режиме, сокращаются по сравнению с активным режимом.

### <a name="see-also"></a>См. также

* [Совместимость антивируса Microsoft Defender](microsoft-defender-antivirus-compatibility.md)
* [Антивирус Microsoft Defender в приложении Безопасности Windows](microsoft-defender-security-center-antivirus.md)