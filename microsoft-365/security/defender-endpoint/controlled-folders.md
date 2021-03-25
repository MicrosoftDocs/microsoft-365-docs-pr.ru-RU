---
title: Защита важных папок от программ-вымогателей от шифрования файлов с помощью управляемого доступа к папкам
description: Файлы в папках по умолчанию могут быть защищены от изменения вредоносными приложениями. Предотвращение шифрования файлов программ-вымогателей.
keywords: управляемый доступ к папкам, Windows 10, защитник Windows, вымогатели, защита, файлы, папки
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
audience: ITPro
ms.date: 02/03/2021
ms.reviewer: v-maave
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: b937dd41f0296f2cf4102f41f8ab10bd55e1c35d
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51200285"
---
# <a name="protect-important-folders-with-controlled-folder-access"></a>Защита важных папок с управляемым доступом к папкам

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-controlled-folder-access"></a>Что такое управляемый доступ к папкам?

Управляемый доступ к папкам помогает защитить ценные данные от вредоносных приложений и угроз, таких как вымогателей. Управляемый доступ к папкам защищает данные, проверяя приложения со списком известных надежных приложений. Поддерживаемый клиентами Windows Server 2019 и Windows 10, управляемый доступ к папкам можно включить с помощью приложения безопасности Windows, Microsoft Endpoint Configuration Manager или Intune (для управляемых устройств). 

> [!NOTE]
> Скрипты не доверяются, и вы не можете разрешить им доступ к управляемым защищенным папок.  Например, PowerShell не доверяется управляемым доступом к папкам, даже если вы позволяете с индикаторами сертификата [и файла](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/indicator-certificates). 

Управляемый доступ к папкам лучше всего работает с [Microsoft Defender для конечной](microsoft-defender-endpoint.md)точки, что позволяет подробно сообщать о событиях и блоках управляемого доступа к папкам в рамках обычных сценариев расследования оповещений. [](investigate-alerts.md)

> [!TIP]
> Блоки доступа к управляемым папкам не создают оповещений в [очереди Оповещения.](alerts-queue.md) Тем не менее, вы можете просматривать сведения о блоках доступа к контролируемым папкам в представлении временной шкалы [устройства,](investigate-machines.md)при использовании расширенных методов охоты [или](advanced-hunting-overview.md)с пользовательскими [правилами обнаружения.](custom-detection-rules.md)

## <a name="how-does-controlled-folder-access-work"></a>Как работает управляемый доступ к папкам?

Управляемый доступ к папкам работает, только позволяя доверенным приложениям получать доступ к защищенным папкам. Защищенные папки заданы при настройке управляемого доступа к папкам. Как правило, обычно используемые папки, например используемые для документов, фотографий, скачиваний и т. д., включаются в список управляемых папок. 

Управляемый доступ к папкам работает со списком доверенных приложений. Приложения, включенные в список доверенных программных продуктов, работают, как и ожидалось. Приложения, не включенные в список, не могут вносить изменения в файлы в защищенных папках. 

Приложения добавляются в список в зависимости от их распространенности и репутации. Приложения, которые широко распространены в вашей организации и никогда не отображали никаких действий, которые считаются вредоносными, считаются заслуживающими доверия. Эти приложения добавляются в список автоматически.

Приложения также можно добавлять вручную в доверенный список с помощью Configuration Manager или Intune. Дополнительные действия, например добавление [индикатора](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file) файла для приложения, можно выполнить из консоли Центра безопасности.

## <a name="why-controlled-folder-access-is-important"></a>Почему важен управляемый доступ к папкам

Управляемый доступ к папкам особенно полезен для защиты документов и сведений от [программ-вымогателей.](https://www.microsoft.com/wdsi/threats/ransomware) При атаке вымогателей ваши файлы могут быть зашифрованы и взяты в заложники. С управляемым доступом к папке на компьютере появляется уведомление, в котором приложение пыталось внести изменения в файл в защищенной папке. Уведомление можно [настроить с](customize-attack-surface-reduction.md#customize-the-notification) помощью сведений о компании и контактных данных. Вы также можете включить правила по отдельности, чтобы настроить методы, которые отслеживает функция.

Защищенные [папки включают общие](#review-controlled-folder-access-events-in-windows-event-viewer) системные папки (включая сектора загрузки), и вы можете [добавить больше папок.](customize-controlled-folders.md#protect-additional-folders) Вы также [можете разрешить приложениям](customize-controlled-folders.md#allow-specific-apps-to-make-changes-to-controlled-folders) предоставить им доступ к защищенным папкам.

Вы можете использовать [режим аудита,](audit-windows-defender.md) чтобы оценить, как управляемый доступ к папкам повлияет на организацию, если она включена. Вы также можете посетить веб-сайт [](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) Защитник Windows test ground в demo.wd.microsoft.com, чтобы подтвердить, что функция работает, и посмотреть, как она работает.

Управляемый доступ к папкам поддерживается в следующих версиях Windows:
- [Windows 10, версия 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) и более поздние версии
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

## <a name="windows-system-folders-are-protected-by-default"></a>Папки системы Windows защищены по умолчанию

По умолчанию по умолчанию защищены папки системы Windows, а также несколько других папок: 

- `c:\Users\<username>\Documents`
- `c:\Users\Public\Documents`
- `c:\Users\<username>\Pictures`
- `c:\Users\Public\Pictures`
- `c:\Users\Public\Videos`
- `c:\Users\<username>\Videos`
- `c:\Users\<username>\Music`
- `c:\Users\Public\Music`
- `c:\Users\<username>\Favorites`

> [!NOTE]
> Дополнительные папки можно настроить как защищенные, но нельзя удалить папки системы Windows, защищенные по умолчанию.

## <a name="requirements-for-controlled-folder-access"></a>Требования к управляемому доступу к папкам

Для управляемого доступа к папкам требуется включение [антивируса Microsoft Defender в режиме реального времени.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)

## <a name="review-controlled-folder-access-events-in-the-microsoft-defender-security-center"></a>Просмотр событий доступа к контролируемым папкам в Центре безопасности Защитника Майкрософт

Defender for Endpoint предоставляет подробные отчеты о событиях и блоках в рамках сценариев расследования [оповещений.](investigate-alerts.md)

Вы можете запрашивать данные Microsoft Defender для конечных точек с помощью [расширенных методов охоты.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/advanced-hunting-windows-defender-advanced-threat-protection) Если используется режим аудита, можно [](advanced-hunting-overview.md) использовать расширенный режим охоты, чтобы узнать, как параметры управляемого доступа к папкам влияют на среду, если они включены. [](audit-windows-defender.md)

Пример запроса

```PowerShell
DeviceEvents
| where ActionType in ('ControlledFolderAccessViolationAudited','ControlledFolderAccessViolationBlocked')
```

## <a name="review-controlled-folder-access-events-in-windows-event-viewer"></a>Просмотр событий управляемого доступа к папкам в Windows Event Viewer

Вы можете просмотреть журнал событий Windows, чтобы просмотреть события, созданные при блоке управляемого доступа к папкам (или аудите) приложения:

1. Скачайте [пакет оценки](https://aka.ms/mp7z2w) и извлеките *файл* cfa-events.xmlв доступное расположение на устройстве.
2. Введите **для просмотра событий в** меню Пуск, чтобы открыть viewer событий Windows.
3. На левой панели в статье **Действия** выберите импорт **настраиваемого представления...**.
4. Перейдите к месту, где *cfa-events.xml* и выберите его. Кроме того, [скопируйте XML напрямую.](event-views.md)
5. Нажмите кнопку **ОК**.

В следующей таблице показаны события, связанные с доступом к управляемой папке:

|Идентификатор события | Описание |
|:---|:---|
|5007 | Событие при смене параметров |
|1124 | Событие доступа к контролируемой управляемой папке | 
|1123 | Событие доступа к заблокированной управляемой папке |

## <a name="view-or-change-the-list-of-protected-folders"></a>Просмотр или изменение списка защищенных папок

Вы можете использовать приложение Windows Security для просмотра списка папок, защищенных управляемым доступом к папкам. 

1. На устройстве Windows 10 откройте приложение Windows Security.
2. Выберите **защиту & вирусов.**
3. Под **защитой вымогателей** выберите **Управление защитой вымогателей.**
4. Если доступ к управляемой папке отключен, его необходимо включить. Выберите **защищенные папки.**
5. Выполните одно из следующих действий:
   - Чтобы добавить папку, выберите **+ Добавить защищенную папку.**
   - Чтобы удалить папку, выберите ее, а затем выберите **Удалить**. 

> [!NOTE]
> [Папки системы Windows](#windows-system-folders-are-protected-by-default) защищены по умолчанию, и удалить их из списка невозможно.

## <a name="see-also"></a>См. также

- [Оценка доступа к управляемой папке](evaluate-controlled-folder-access.md)
- [Настройка управляемого доступа к папкам](customize-controlled-folders.md)
- [Защита дополнительных папок](customize-controlled-folders.md#protect-additional-folders)
