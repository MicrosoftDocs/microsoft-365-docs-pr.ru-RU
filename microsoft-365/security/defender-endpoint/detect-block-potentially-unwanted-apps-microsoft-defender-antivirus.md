---
title: Блокировка потенциально нежелательных приложений с помощью антивирусной программы в Microsoft Defender
description: Включите функцию антивируса потенциально нежелательных приложений (PUA), чтобы блокировать нежелательное программное обеспечение, такое как программа для показа рекламы.
keywords: pua, включить, нежелательное программное обеспечение, нежелательные приложения, программа для показа рекламы, панель инструментов браузера, обнаружение, блокировка, антивирусная программа в Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: detect
ms.sitesec: library
localization_priority: Priority
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
audience: ITPro
ms.reviewer: mimilone, julih
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 06/02/2021
ms.openlocfilehash: d7f411c81e839d3929d4aa1a52fda29399c59dca
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772381"
---
# <a name="detect-and-block-potentially-unwanted-applications"></a>Обнаружение и блокировка потенциально нежелательных приложений

**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)
- [Microsoft Edge](/microsoft-edge/deploy/microsoft-edge)

Потенциально нежелательные приложения (PUA) — это категория программного обеспечения, которое может вызвать медленную работу вашего компьютера, отображение непредвиденной рекламы или, в худшем случае, установку другого программного обеспечения, которое может быть неожиданным или нежелательным. PUA не считаются вирусом, вредоносными программами или другим типом угрозы, но они могут выполнять действия с конечными точками, которые отрицательно влияют на производительность или использование конечной точки. Термин *PUA* также может ссылаться на приложение с плохой репутацией, по оценке Microsoft Defender для конечных точек, из-за определенных видов нежелательного поведения.

Ниже приводятся примеры:

- **Рекламные программное обеспечение**, которые отображают рекламу или рекламные акции, в том числе программное обеспечение, которое вставляет рекламные объявления на веб-страницы.
- **Организация программного обеспечения**, которое предлагает установить другое программное обеспечение, не имеющее цифровой подписи той же организации. Кроме того, программное обеспечение, которое предлагает установить другое программное обеспечение, которое квалифицируется как потенциально нежелательное приложение.
- **Уклонение программного обеспечения**, которое активно пытается уклониться от обнаружения продуктами безопасности, включая программное обеспечение, которое ведет себя иначе в присутствии продуктов безопасности.

> [!TIP]
> Дополнительные примеры и обсуждение критериев, которые используются для пометки приложений, требующих особого внимания со стороны функций безопасности, см. разделе [Как Майкрософт определяет вредоносные и потенциально нежелательные приложения](/windows/security/threat-protection/intelligence/criteria).

Потенциально нежелательные приложения могут повысить риск заражения вашей сети фактическими вредоносными программами, затруднить выявление заражений вредоносными программами или тратить ИТ-ресурсы на их очистку. Защита от потенциально нежелательных приложений поддерживается в Windows 10, Windows Server 2019 и Windows Server 2016. По умолчанию в Windows 10 (версия 2004 и более поздние версии) антивирусная программа в Microsoft Defender блокирует приложения, которые считаются потенциально нежелательными приложениями, для корпоративных устройств (E5).

## <a name="microsoft-edge"></a>Microsoft Edge

[Новый Microsoft Edge](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea), основанный на Chromium, блокирует загрузки потенциально нежелательных приложений и связанные URL-адреса ресурсов. Эта функция предоставляется через [фильтр SmartScreen в Microsoft Defender](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview).

### <a name="enable-pua-protection-in-chromium-based-microsoft-edge"></a>Включить защиту от потенциально нежелательных приложений в Microsoft Edge на основе Chromium

Хотя защита от потенциально нежелательных приложений в Microsoft Edge (на основе Chromium, версия 80.0.361.50) отключена по умолчанию, ее можно легко отключить в браузере.

1. В браузере Microsoft Edge выберите многоточие и затем выберите **Параметры**.

2. Выберите **Конфиденциальность, поиск и службы**.

3. В разделе **Безопасность** включите **Блокировка потенциально нежелательных приложений**.

> [!TIP]
> Если вы работаете в Microsoft Edge (на основе Chromium), вы можете безопасно изучить функцию блокировки URL-адресов защиты от потенциально нежелательных приложений, протестировав ее на одной из наших [демонстрационных страниц фильтра SmartScreen в Microsoft Defender](https://demo.smartscreen.msft.net/).

### <a name="block-urls-with-microsoft-defender-smartscreen"></a>Блокировка URL-адресов с помощью фильтра SmartScreen в Microsoft Defender

В Edge на основе Chromium с включенной защитой от потенциально нежелательных приложений фильтр SmartScreen в Microsoft Defender защищает вас от URL-адресов, связанных с потенциально нежелательными приложениями.

Администраторы безопасности могут [настраивать](/DeployEdge/configure-microsoft-edge) совместную работу Microsoft Edge и фильтр SmartScreen в Microsoft Defender для защиты групп пользователей от URL-адресов, связанных с потенциально нежелательными приложениями. Существует несколько [параметров групповой политики](/DeployEdge/microsoft-edge-policies#smartscreen-settings) исключительно для фильтра SmartScreen в Microsoft Defender, в том числе [один для блокировки потенциально нежелательных приложений](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled). Кроме того, администраторы могут [настраивать фильтр SmartScreen в Microsoft Defender](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) в целом, используя параметры групповой политики, чтобы включить или отключить фильтр SmartScreen в Microsoft Defender.

Несмотря на то что Microsoft Defender для конечной точки имеет собственный список блокировок на основе набора данных, управляемом Майкрософт, вы можете настроить этот список на основе собственной аналитики угроз. При [создании и управлении индикаторами](manage-indicators.md) на портале Microsoft Defender для конечной точки, SmartScreen в Microsoft Defender учитывает новые параметры.

## <a name="microsoft-defender-antivirus-and-pua-protection"></a>Защита от вирусов и потенциально нежелательных приложений в антивирусной программе в Microsoft Defender

Функция защиты от потенциально нежелательных приложений (PUA) в антивирусной программе в Microsoft Defender может обнаруживать и блокировать потенциально нежелательные приложения на конечных точках в вашей сети.

> [!NOTE]
> Эта функция доступна в Windows 10, Windows Server 2019 и Windows Server 2016.

Антивирусная программа в Microsoft Defender блокирует обнаруженные PUA-файлы и все попытки их скачивания, перемещения, запуска или установки. После этого заблокированные PUA-файлы перемещаются в карантин. При обнаружении PUA-файла в конечной точке антивирусная программа в Microsoft Defender отправляет пользователю уведомление ([если уведомления не отключены](configure-notifications-microsoft-defender-antivirus.md)) в том же формате, что и другие обнаруженные угрозы. Перед уведомлением указывается `PUA:` для указания его содержимого.

Уведомление отображается в обычном [списке карантина в приложении "Безопасность Windows"](microsoft-defender-security-center-antivirus.md).

## <a name="configure-pua-protection-in-microsoft-defender-antivirus"></a>Настройка защиты от потенциально нежелательных приложений в антивирусной программе в Microsoft Defender

Защиту от потенциально нежелательных приложений можно включить с помощью [Microsoft Intune](/mem/intune/protect/device-protect), [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection), [групповой политики](/azure/active-directory-domain-services/manage-group-policy) или с помощью [командлетов PowerShell](/powershell/module/defender/?preserve-view=true&view=win10-ps).

Вы также можете использовать защиту от потенциально нежелательных приложений в режиме аудита для обнаружения потенциально нежелательных приложений, не блокируя их. Обнаружения записываются в журнале событий Windows.

> [!TIP]
> Посетите демонстрационный веб-сайт Microsoft Defender для конечной точки по ссылке [demo.wd.microsoft.com](https://demo.wd.microsoft.com/Page/UrlRep), чтобы проверить, работает ли функция, и увидеть, как она работает.

Защита от потенциально нежелательных приложений в режиме аудита полезна, если ваша организация проводит внутреннюю проверку соответствия требованиям безопасности программного обеспечения, и вы хотите избежать ложных срабатываний.

### <a name="use-intune-to-configure-pua-protection"></a>Настройка защиты от потенциально нежелательных приложений с помощью Intune

Дополнительные сведения см. в статьях [Настройка параметров ограничения устройств в Microsoft Intune](/intune/device-restrictions-configure) и [Параметры ограничений устройств антивирусной программы в Microsoft Defender для Windows 10 в Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).

### <a name="use-configuration-manager-to-configure-pua-protection"></a>Настройка защиты от потенциально нежелательных приложений с помощью Configuration Manager

Защита от потенциально нежелательных приложений по умолчанию включена в Microsoft Endpoint Manager (Current Branch).

Дополнительные сведения о настройке Microsoft Endpoint Manager (Current Branch) см. в статье [Создание и развертывание политик защиты от вредоносных программ: параметры запланированных проверок](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings).

Сведения о диспетчере конфигураций System Center 2012 см. в статье [Развертывание политики защиты от потенциально нежелательных приложений для Endpoint Protection в Configuration Manager](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA).

> [!NOTE]
> События PUA, заблокированные антивирусной программой в Microsoft Defender, отображаются в средстве просмотра событий Windows, а не в Microsoft Endpoint Configuration Manager.

### <a name="use-group-policy-to-configure-pua-protection"></a>Настройка защиты от потенциально нежелательных приложений с помощью групповой политики

1. Скачивание и установка [административных шаблонов (.ADMX) для обновления Windows 10 за октябрь 2020 г. (20H2)](https://www.microsoft.com/download/details.aspx?id=102157)

2. На компьютере управления групповыми политиками откройте [консоль управления групповыми политиками](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).

3. Выберите объект групповой политики, который необходимо настроить, а затем выберите **Изменить**.

4. В **редакторе управления групповыми политиками** перейдите к **конфигурации компьютера** и выберите **Административные шаблоны**.

5. Разверните дерево до **Компонентов Windows** > **антивирусной программы в Microsoft Defender**.

6. Дважды щелкните на пункт **Настройка обнаружения потенциально нежелательных приложений**.

7. Выберите **Включено**, чтобы включить защиту от потенциально нежелательных приложений.

8. В разделе **Параметры** выберите **Заблокировать**, чтобы заблокировать потенциально нежелательные приложения, или выберите **Режим аудита**, чтобы проверить, как этот параметр работает в вашей среде. Нажмите **ОК**.

9. Разверните объект групповой политики, как обычно.

### <a name="use-powershell-cmdlets-to-configure-pua-protection"></a>Настройка защиты от потенциально нежелательных приложений с помощью командлетов PowerShell

#### <a name="to-enable-pua-protection"></a>Чтобы включить защиту от потенциально нежелательных приложений:

```PowerShell
Set-MpPreference -PUAProtection Enabled
```

Установите для этого командлета значение `Enabled`, чтобы включить функцию, если она была отключена.

#### <a name="to-set-pua-protection-to-audit-mode"></a>Чтобы настроить защиту от потенциально нежелательных приложений в режиме аудита:

```PowerShell
Set-MpPreference -PUAProtection AuditMode
```

Установите `AuditMode` для обнаружения потенциально нежелательных приложений, не блокируя их.

#### <a name="to-disable-pua-protection"></a>Чтобы отключить защиту от потенциально нежелательных приложений:

Рекомендуем не отключать защиту от потенциально нежелательных приложений. Однако её можно отключить с помощью следующего командлета:

```PowerShell
Set-MpPreference -PUAProtection Disabled
```

Установите для этого командлета значение `Disabled`, чтобы отключить функцию, если она была включена.

Дополнительные сведения см. в разделах [Использование командлетов PowerShell для настройки и запуска антивирусной программы в Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) и [Командлеты Defender](/powershell/module/defender/index).

## <a name="view-pua-events-using-powershell"></a>Просмотр событий PUA с помощью PowerShell

О событиях PUA сообщается в средстве просмотра событий Windows, но не в Microsoft Endpoint Manager или в Intune. Вы также можете использовать командлет `Get-MpThreat` для просмотра угроз, обработанных антивирусной программой в Microsoft Defender. Пример:

```console
CategoryID       : 27
DidThreatExecute : False
IsActive         : False
Resources        : {webfile:_q:\Builds\Dalton_Download_Manager_3223905758.exe|http://d18yzm5yb8map8.cloudfront.net/
                    fo4yue@kxqdw/Dalton_Download_Manager.exe|pid:14196,ProcessStart:132378130057195714}
RollupStatus     : 33
SchemaVersion    : 1.0.0.0
SeverityID       : 1
ThreatID         : 213927
ThreatName       : PUA:Win32/InstallCore
TypeID           : 0
PSComputerName   :
```

## <a name="get-email-notifications-about-pua-detections"></a>Получение уведомлений об обнаружении PUA по электронной почте

Вы можете включить уведомления по электронной почте, чтобы получать сообщения об обнаружении потенциально нежелательных приложений.

Дополнительные сведения о просмотре событий Microsoft Defender Antivirus см. в разделе [Устранение неполадок с событиями идентификаторов](troubleshoot-microsoft-defender-antivirus.md). События PUA записываются в соответствии с идентификатором события **1160**.

## <a name="view-pua-events-using-advanced-hunting"></a>Просмотр событий PUA с помощью методов расширенной охоты

Если вы используете [Microsoft Defender для конечной точки](microsoft-defender-endpoint.md), вы можете использовать запрос расширенной охоты для просмотра событий PUA. Пример:

```console
DeviceEvents
| where ActionType == "AntivirusDetection"
| extend x = parse_json(AdditionalFields)
| project Timestamp, DeviceName, FolderPath, FileName, SHA256, ThreatName = tostring(x.ThreatName), WasExecutingWhileDetected = tostring(x.WasExecutingWhileDetected), WasRemediated = tostring(x.WasRemediated)
| where ThreatName startswith_cs 'PUA:'
```

Дополнительные информацию о расширенной охоте см. в разделе [Превентивная охота на угрозы с расширенной охотой](advanced-hunting-overview.md).

## <a name="exclude-files-from-pua-protection"></a>Исключение файлов из защиты от PUA

Иногда файл ошибочно блокируется защитой от потенциально нежелательных приложений или для выполнения задачи требуется функция PUA. В таких случаях файл можно добавить в список исключений.

Дополнительные сведения см. в статье [Настройка и проверка исключений с учетом расширения файла и расположения папки](configure-extension-file-exclusions-microsoft-defender-antivirus.md).

## <a name="see-also"></a>См. также

- [Защита нового поколения](microsoft-defender-antivirus-in-windows-10.md)
- [Настройка поведенческой, эвристической защиты и защиты в режиме реального времени](configure-protection-features-microsoft-defender-antivirus.md)