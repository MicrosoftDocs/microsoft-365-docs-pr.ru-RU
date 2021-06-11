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
ms.date: 06/10/2021
ms.reviewer: v-maave
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: c60620d2a589c8473764b810d1fcb0e24f674451
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904060"
---
# <a name="protect-important-folders-with-controlled-folder-access"></a>Защита важных папок с управляемым доступом к папкам

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-controlled-folder-access"></a>Что такое управляемый доступ к папкам?

Управляемый доступ к папкам помогает защитить ценные данные от вредоносных приложений и угроз, таких как вымогателей. Управляемый доступ к папкам защищает данные, проверяя приложения со списком известных надежных приложений. Поддерживаемый Windows Server 2019 и Windows 10 клиенты, управляемый доступ к папкам можно включить с помощью Безопасность Windows App, Microsoft Endpoint Configuration Manager или Intune (для управляемых устройств). 

> [!NOTE]
> Скрипты не доверяются, и вы не можете разрешить им доступ к управляемым защищенным папок.  Например, PowerShell не доверяется управляемым доступом к папкам, даже если вы позволяете с индикаторами сертификата [и файла](/microsoft-365/security/defender-endpoint/indicator-certificates). 

Управляемый доступ к папкам лучше всего работает с [Microsoft Defender для конечной](microsoft-defender-endpoint.md)точки, что позволяет подробно сообщать о событиях и блоках управляемого доступа к папкам в рамках обычных сценариев расследования оповещений. [](investigate-alerts.md)

> [!TIP]
> Блоки доступа к управляемым папкам не создают оповещений в [очереди Оповещения.](alerts-queue.md) Тем не менее, вы можете просматривать сведения о блоках доступа к контролируемым папкам в представлении временной шкалы [устройства,](investigate-machines.md)при использовании расширенных методов охоты [или](advanced-hunting-overview.md)с пользовательскими [правилами обнаружения.](custom-detection-rules.md)

## <a name="how-does-controlled-folder-access-work"></a>Как работает управляемый доступ к папкам?

Управляемый доступ к папкам работает, только позволяя доверенным приложениям получать доступ к защищенным папкам. Защищенные папки заданы при настройке управляемого доступа к папкам. Как правило, обычно используемые папки, например используемые для документов, фотографий, скачиваний и т. д., включаются в список управляемых папок. 

Управляемый доступ к папкам работает со списком доверенных приложений. Приложения, включенные в список доверенных программных продуктов, работают, как и ожидалось. Приложения, не включенные в список, не могут вносить изменения в файлы в защищенных папках. 

Приложения добавляются в список в зависимости от их распространенности и репутации. Приложения, которые широко распространены в вашей организации и никогда не отображали никаких действий, которые считаются вредоносными, считаются заслуживающими доверия. Эти приложения добавляются в список автоматически.

Приложения также можно добавлять вручную в доверенный список с помощью Configuration Manager или Intune. Дополнительные действия, например добавление [индикатора](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file) файла для приложения, можно выполнить из консоли Центра безопасности.

## <a name="why-controlled-folder-access-is-important"></a>Почему важен управляемый доступ к папкам

Управляемый доступ к папкам особенно полезен для защиты документов и сведений от [программ-вымогателей.](https://www.microsoft.com/wdsi/threats/ransomware) При атаке вымогателей ваши файлы могут быть зашифрованы и взяты в заложники. С управляемым доступом к папке на компьютере появляется уведомление, в котором приложение пыталось внести изменения в файл в защищенной папке. Вы можете [настроить уведомление](customize-attack-surface-reduction.md#customize-the-notification), указав сведения о вашей организации и контактные данные. Вы также можете включить правила по отдельности, чтобы настроить, какие методы отслеживает функция.

Защищенные [папки включают общие](#review-controlled-folder-access-events-in-windows-event-viewer) системные папки (включая сектора загрузки), и вы можете [добавить больше папок.](customize-controlled-folders.md#protect-additional-folders) Вы также [можете разрешить приложениям](customize-controlled-folders.md#allow-specific-apps-to-make-changes-to-controlled-folders) предоставить им доступ к защищенным папкам.

Вы можете использовать [режим аудита,](audit-windows-defender.md) чтобы оценить, как управляемый доступ к папкам повлияет на организацию, если она включена. Вы также можете посетить веб-сайт [](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) Защитник Windows test ground в demo.wd.microsoft.com, чтобы подтвердить, что функция работает, и посмотреть, как она работает.

Управляемый доступ к папке поддерживается в следующих версиях Windows:
- [Windows 10 версии 1709](/windows/whats-new/whats-new-windows-10-version-1709) и более поздней версии
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

## <a name="windows-system-folders-are-protected-by-default"></a>Windows системные папки защищены по умолчанию

Windows по умолчанию защищены по умолчанию, а также несколько других папок: 

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
> Можно настроить дополнительные папки в качестве защищенных, но нельзя удалить Windows системные папки, защищенные по умолчанию.

## <a name="requirements-for-controlled-folder-access"></a>Требования к управляемому доступу к папкам

Доступ к управляемой папке требует включения антивирусная программа в Microsoft Defender защиты в [режиме реального времени.](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)

## <a name="review-controlled-folder-access-events-in-the-microsoft-365-defender-portal"></a>Просмотр событий управляемого доступа к папкам на портале Microsoft 365 Defender

Defender for Endpoint предоставляет подробные отчеты [](investigate-alerts.md) о событиях и блоках в рамках сценариев расследования предупреждений на портале Microsoft 365 Defender. [(См. microsoft Defender для конечной точки в Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).)

Вы можете запрашивать данные Microsoft Defender для конечных точек с помощью [расширенных методов охоты.](/microsoft-365/security/defender-endpoint/advanced-hunting-windows-defender-advanced-threat-protection) Если используется режим аудита, можно [](advanced-hunting-overview.md) использовать расширенный режим охоты, чтобы узнать, как параметры управляемого доступа к папкам влияют на среду, если они включены. [](audit-windows-defender.md)

Пример запроса

```PowerShell
DeviceEvents
| where ActionType in ('ControlledFolderAccessViolationAudited','ControlledFolderAccessViolationBlocked')
```

## <a name="review-controlled-folder-access-events-in-windows-event-viewer"></a>Просмотр событий управляемого доступа к папкам в Windows просмотра событий

Вы можете просмотреть журнал Windows событий, чтобы просмотреть события, созданные при блоке управляемого доступа к папке (или аудите) приложения:

1. Скачайте [пакет оценки](https://aka.ms/mp7z2w) и извлеките *файл* cfa-events.xmlв доступное расположение на устройстве.
2. Введите **viewer события** в меню Пуск, чтобы открыть Windows просмотра событий.
3. На левой панели в статье **Действия** выберите импорт **настраиваемого представления...**.
4. Перейдите к месту, где *cfa-events.xml* и выберите его. Кроме того, [скопируйте XML напрямую.](event-views.md)
5. Нажмите **ОК**.

В следующей таблице показаны события, связанные с доступом к управляемой папке:

|Идентификатор события | Описание |
|:---|:---|
|5007 | Событие при смене параметров |
|1124 | Событие доступа к контролируемой управляемой папке | 
|1123 | Событие доступа к заблокированной управляемой папке |

## <a name="view-or-change-the-list-of-protected-folders"></a>Просмотр или изменение списка защищенных папок

Вы можете использовать Безопасность Windows для просмотра списка папок, защищенных управляемым доступом к папкам. 

1. На Windows 10 откройте приложение Безопасность Windows.
2. Выберите **Защита от вирусов и угроз**.
3. Под **защитой вымогателей** выберите **Управление защитой вымогателей.**
4. Если доступ к управляемой папке отключен, его необходимо включить. Выберите **защищенные папки.**
5. Выполните одно из следующих действий:
   - Чтобы добавить папку, выберите **+ Добавить защищенную папку.**
   - Чтобы удалить папку, выберите ее, а затем выберите **Удалить**. 

> [!NOTE]
> [Windows по](#windows-system-folders-are-protected-by-default) умолчанию защищены системные папки, и удалить их из списка невозможно.


