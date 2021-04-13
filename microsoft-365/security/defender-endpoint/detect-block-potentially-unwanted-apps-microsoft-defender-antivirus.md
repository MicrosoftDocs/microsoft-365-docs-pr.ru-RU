---
title: Блокировка потенциально нежелательных приложений с помощью антивируса Microsoft Defender
description: Включить антивирусную функцию потенциально нежелательного приложения (PUA) для блокировки нежелательного программного обеспечения, например adware.
keywords: pua, включить нежелательное программное обеспечение, нежелательные приложения, adware, панель инструментов браузера, обнаружить, заблокировать, Антивирус Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: detect
ms.sitesec: library
ms.localizationpriority: high
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
audience: ITPro
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: bee92dfa998596578c27bda579a86776bc77c07b
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691482"
---
# <a name="detect-and-block-potentially-unwanted-applications"></a>Обнаружение и блокировка потенциально нежелательных приложений

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)
- [Microsoft Edge](/microsoft-edge/deploy/microsoft-edge)

> [!NOTE]
> Потенциально нежелательные приложения (PUA) — это категория программного обеспечения, которое может привести к медленному запуску компьютера, показу неожиданных объявлений или в худшем случае установке другого программного обеспечения, которое может быть неожиданным или нежелательным. По умолчанию в Windows 10 (версия 2004 и более поздние версии) антивирус Microsoft Defender блокирует приложения, которые считаются PUA, для устройств Enterprise (E5).

Потенциально нежелательные приложения (PUA) не считаются вирусами, вредоносными программами или другими типами угроз, но могут выполнять действия в конечных точках, которые отрицательно влияют на производительность конечных точек или их использование. _PUA также_ может ссылаться на приложение, которое имеет плохую репутацию, как оценивает Microsoft Defender для конечной точки, из-за определенных видов нежелательного поведения.

Ниже приводятся примеры:

- **Рекламное** программное обеспечение, которое отображает рекламу или рекламные акции, в том числе программное обеспечение, которое вставляет рекламу на веб-страницы.
- **Комплектирование программного** обеспечения, которое предлагает установить другое программное обеспечение, которое не подписано одной и той же сущностью в цифровом формате. Кроме того, программное обеспечение, которое предлагает установить другое программное обеспечение, которое квалифицируется как PUA.
- **Программное обеспечение для уклонения,** которое активно пытается избежать обнаружения с помощью продуктов безопасности, в том числе программного обеспечения, которое ведет себя по-разному в присутствии продуктов безопасности.

> [!TIP]
> Дополнительные примеры и обсуждение критериев, которые мы используем для обозначения приложений для особого внимания со стороны функций безопасности, см. в примере, как Корпорация Майкрософт определяет вредоносные программы и потенциально [нежелательные приложения.](/windows/security/threat-protection/intelligence/criteria)

Потенциально нежелательные приложения могут повысить риск заражения сети фактическими вредоносными программами, усложнять выявление вредоносных программ или тратить ИТ-ресурсы на их очистку. Защита PUA поддерживается в Windows 10, Windows Server 2019 и Windows Server 2016.

## <a name="microsoft-edge"></a>Microsoft Edge

Новый [Microsoft Edge,](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea)основанный на хроме, блокирует потенциально нежелательные загрузки приложений и связанные URL-адреса ресурсов. Эта функция предоставляется с [помощью Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview).

### <a name="enable-pua-protection-in-chromium-based-microsoft-edge"></a>Включить защиту PUA в Microsoft Edge на основе хрома

Хотя потенциально нежелательная защита приложений в Microsoft Edge (на основе хрома, версия 80.0.361.50) отключена по умолчанию, ее можно легко включить из браузера.

1. Выберите эллипсы и выберите **Параметры**.
2. Выберите **конфиденциальность, поиск и службы.**
3. В разделе **Безопасность** включаем **блок потенциально нежелательных приложений.**

> [!TIP]
> Если вы работаете в Microsoft Edge (на основе хрома), вы можете безопасно изучить функцию защиты PUA, блокирующую URL-адрес, опробуя ее на одной из демонстрационных страниц [Microsoft Defender SmartScreen.](https://demo.smartscreen.msft.net/)

### <a name="blocking-urls-with-microsoft-defender-smartscreen"></a>Блокировка URL-адресов с помощью SmartScreen защитника Майкрософт

В Chromium-edge с включенной защитой PUA Microsoft Defender SmartScreen защищает вас от URL-адресов, связанных с PUA.

Администраторы безопасности могут настроить [совместное](/DeployEdge/configure-microsoft-edge) работу Microsoft Edge и Microsoft Defender SmartScreen для защиты групп пользователей от URL-адресов, связанных с PUA. Существует несколько [параметров групповой политики](/DeployEdge/microsoft-edge-policies#smartscreen-settings) для SmartScreen Microsoft Defender, в том числе для блокировки [PUA.](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled) Кроме того, администраторы могут настроить [Microsoft Defender SmartScreen](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) в целом, используя параметры групповой политики, чтобы включить или отключить Microsoft Defender SmartScreen.

Несмотря на то, что Microsoft Defender для конечной точки имеет свой собственный список блоков на основе набора данных, управляемых Корпорацией Майкрософт, этот список можно настроить на основе собственных сведений об угрозах. Если вы [создаете и управляете](/microsoft-365/security/defender-endpoint/manage-indicators) индикаторами на портале Microsoft Defender for Endpoint, Microsoft Defender SmartScreen уважает новые параметры.

## <a name="microsoft-defender-antivirus"></a>Антивирус Microsoft Defender

Функция защиты потенциально нежелательного приложения (PUA) в антивирусе Microsoft Defender может обнаруживать и блокировать puAs в конечных точках сети.

> [!NOTE]
> Эта функция доступна в Windows 10, Windows Server 2019 и Windows Server 2016.

Антивирус Microsoft Defender блокирует обнаруженные файлы PUA и любые попытки скачивания, перемещения, запуска или установки. Заблокированные файлы PUA затем перемещаются на карантин. При обнаружении файла PUA на конечной точке антивирус Microsoft Defender отправляет пользователю уведомление[(если](configure-notifications-microsoft-defender-antivirus.md)уведомления не отключены) в том же формате, что и другие обнаружения угроз. Уведомление предисловие, чтобы `PUA:` указать его содержимое.

Уведомление отображается в обычном списке [карантина в приложении Windows Security.](microsoft-defender-security-center-antivirus.md)

### <a name="configure-pua-protection-in-microsoft-defender-antivirus"></a>Настройка защиты PUA в антивирусе Microsoft Defender

Вы можете включить защиту PUA с [помощью Microsoft Intune,](/mem/intune/protect/device-protect) [Microsoft Endpoint Configuration Manager,](/mem/configmgr/protect/deploy-use/endpoint-protection)Групповой политики [или](/azure/active-directory-domain-services/manage-group-policy)с помощью [команды PowerShell.](/powershell/module/defender/?preserve-view=true&view=win10-ps)

Вы также можете использовать защиту PUA в режиме аудита для обнаружения потенциально нежелательных приложений, не блокируя их. Обнаружения запечатлены в журнале событий Windows.

> [!TIP]
> Посетите веб-сайт демонстрации Microsoft Defender для конечной точки [demo.wd.microsoft.com,](https://demo.wd.microsoft.com/Page/UrlRep) чтобы подтвердить, что функция работает, и увидеть ее в действии.

Защита PUA в режиме аудита полезна, если ваша компания проводит внутреннюю проверку соответствия требованиям безопасности программного обеспечения, и вы хотите избежать ложных срабатывай.

#### <a name="use-intune-to-configure-pua-protection"></a>Использование Intune для настройки защиты PUA

Дополнительные сведения см. в настройках параметров ограничения устройств [в Microsoft Intune](/intune/device-restrictions-configure) и [Microsoft Defender Antivirus device restriction settings for Windows 10 in Intune.](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)

#### <a name="use-configuration-manager-to-configure-pua-protection"></a>Настройка защиты PUA с помощью диспетчера конфигурации

Защита PUA включена по умолчанию в Microsoft Endpoint Manager (Current Branch).

Сведения о настройке Microsoft Endpoint Manager (Current Branch) см. в материале "Создание и развертывание политик противомалярийных [программ".](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings)

Дополнительные System Center 2012 настройки см. в приложении How [to Deploy Potentially Unwanted Application Protection Policy for Endpoint Protection in Configuration Manager.](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA)

> [!NOTE]
> События PUA, заблокированные антивирусом Microsoft Defender, сообщаются в Windows Event Viewer, а не в Microsoft Endpoint Configuration Manager.

#### <a name="use-group-policy-to-configure-pua-protection"></a>Настройка защиты PUA с помощью групповой политики

1. Загрузка и установка административных шаблонов [(.admx) для Обновления Windows 10 октября 2020 г. (20H2)](https://www.microsoft.com/download/details.aspx?id=102157)

2. На компьютере управления групповой политикой откройте консоль [управления групповой политикой.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))

3. Выберите объект групповой политики, который необходимо настроить, а затем выберите **Изменить**.

4. В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера** и выберите **административные шаблоны.**

5. Расширь дерево до **антивируса**  >  **Microsoft Defender компоненты Windows.**

6. Дважды **щелкните Настройка обнаружения для потенциально нежелательных приложений.**

7. Выберите **Включено,** чтобы включить защиту PUA.

8. В **Параметры** выберите **Блок** для блокировки потенциально  нежелательных приложений или выберите режим аудита, чтобы проверить, как работает параметр в вашей среде. Нажмите кнопку **ОК**.

9. Развертывание объекта групповой политики, как обычно.

#### <a name="use-powershell-cmdlets-to-configure-pua-protection"></a>Чтобы настроить защиту PUA, используйте cmdlets PowerShell

##### <a name="to-enable-pua-protection"></a>Чтобы включить защиту PUA

```PowerShell
Set-MpPreference -PUAProtection Enabled
```

Настройка значения для этого cmdlet включает `Enabled` функцию, если она отключена.

##### <a name="to-set-pua-protection-to-audit-mode"></a>Настройка режима аудита защиты PUA

```PowerShell
Set-MpPreference -PUAProtection AuditMode
```

Параметр `AuditMode` обнаруживает PUAs, не блокируя их.

##### <a name="to-disable-pua-protection"></a>Отключение защиты PUA

Рекомендуется поддерживать включенную защиту PUA. Однако вы можете отключить его с помощью следующего cmdlet:

```PowerShell
Set-MpPreference -PUAProtection Disabled
```

Настройка значения для этого комлета, чтобы `Disabled` отключить функцию, если она включена.

Дополнительные сведения о том, как использовать [PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md) с антивирусным вирусом Microsoft Defender и [Defender,](/powershell/module/defender/index) см. в этой ссылке.

## <a name="view-pua-events"></a>Просмотр событий PUA

События PUA сообщаются в Windows Event Viewer, но не в Microsoft Endpoint Manager или Intune. Кроме того, можно использовать `Get-MpThreat` этот кодлет для просмотра угроз, с помощью антивирусных программ Microsoft Defender. Пример:

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

Вы можете включить уведомления электронной почты для получения почты об обнаружении PUA.

Сведения [о просмотре антивирусных](troubleshoot-microsoft-defender-antivirus.md) событий Microsoft Defender см. в материале "Устранение неполадок". События PUA записывают в соответствии с ИД события **1160**.

## <a name="excluding-files"></a>Исключение файлов

Иногда файл ошибочно блокируется защитой PUA или для выполнения задачи требуется функция PUA. В этих случаях файл можно добавить в список исключений.

Дополнительные сведения см. в [материалах Configure and validate exclusions based on file extension and folder location.](configure-extension-file-exclusions-microsoft-defender-antivirus.md)

## <a name="see-also"></a>См. также

- [Защита нового поколения](microsoft-defender-antivirus-in-windows-10.md)
- [Настройка поведенческой, севристической и защиты в режиме реального времени](configure-protection-features-microsoft-defender-antivirus.md)