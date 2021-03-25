---
title: Настройка управляемого доступа к папкам
description: Добавьте другие папки, которые должны быть защищены управляемым доступом к папкам, или разрешить приложениям, которые неправильно блокируют изменения важных файлов.
keywords: Управляемый доступ к папкам, Windows 10, защитник Windows, вымогатели, защита, файлы, папки, настройка, добавление папки, добавление приложения, разрешение, добавление исполняемого
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: jcedola, dbodorin, vladiso, nixanm, anvascon
manager: dansimp
ms.date: 01/06/2021
ms.technology: mde
ms.openlocfilehash: 64f96544361a672881c590716adea80f40777c6e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163343"
---
# <a name="customize-controlled-folder-access"></a>Настройка управляемого доступа к папкам

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)


Управляемый доступ к папкам помогает защитить ценные данные от вредоносных приложений и угроз, таких как вымогателей. Управляемый доступ к папкам поддерживается в клиентах Windows Server 2019 и Windows 10.

В этой статье описывается настройка возможностей доступа к управляемым папкам и содержатся следующие разделы:

- [Защита дополнительных папок](#protect-additional-folders)
- [Добавление приложений, которые должны быть разрешены для доступа к защищенным папок](#allow-specific-apps-to-make-changes-to-controlled-folders)
- [Разрешить подписанным исполняемым файлам доступ к защищенным папкам](#allow-signed-executable-files-to-access-protected-folders)
- [Настройка уведомления](#customize-the-notification)

> [!IMPORTANT]
> Контролируемый доступ к папкам отслеживает приложения для действий, которые обнаруживаются как вредоносные. Иногда законным приложениям блокируется внесение изменений в файлы. Если управляемый доступ к папкам влияет на производительность организации, можно рассмотреть возможность запуска этой функции в режиме аудита, чтобы полностью оценить последствия. [](audit-windows-defender.md)

## <a name="protect-additional-folders"></a>Защита дополнительных папок

Управляемый доступ к папкам применяется ко многим папкам системы и расположениям по умолчанию, включая такие папки, как **Documents,** **Pictures** и **Movies.** Вы можете добавить дополнительные папки, которые необходимо защитить, но вы не можете удалить папки по умолчанию в списке по умолчанию.

Добавление других папок к управляемому доступу к папкам может быть полезно для случаев, когда вы не сохраняете файлы в библиотеках Windows по умолчанию или вы изменили расположение библиотек по умолчанию.

Вы также можете указать сетевые акции и составить карту дисков. Поддерживаются переменные среды и подкарды. Сведения об использовании подмастерьев см. в материалах [Use wildcards in the file name and folder path or extension exclusion lists.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)

Для добавления и удаления дополнительных защищенных папок можно использовать приложение Windows Security, групповую политику, команды PowerShell или поставщики служб конфигурации управления мобильными устройствами.

### <a name="use-the-windows-security-app-to-protect-additional-folders"></a>Используйте приложение Windows Security для защиты дополнительных папок

1. Откройте приложение Безопасности Windows, выбрав значок щита в панели задач или нажав меню пусков для **безопасности.**

2. Выберите **защиту & вирусов,** а затем прокрутите его в раздел **Защита вымогателей.**

3. Выберите **Управление защитой вымогателей,** чтобы открыть области защиты вымогателей. 

4. В разделе **Управляемый доступ к папкам** выберите **защищенные папки.**

5. Выберите **Да** в **запросе Управления доступом пользователей.** Экраны **области защищенных** папок.

4. Выберите **Добавить защищенную папку** и следуйте подсказкам для добавления папок.

### <a name="use-group-policy-to-protect-additional-folders"></a>Использование групповой политики для защиты дополнительных папок

1. На компьютере управления групповой политикой откройте консоль управления групповой политикой [,](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)щелкните правой кнопкой мыши объект групповой политики, который необходимо настроить, а затем выберите **Изменить**.

2. В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера** и выберите **административные шаблоны.**

3. Расширь дерево до **компонентов**  >  **антивируса Microsoft Defender Защитник Windows**  >  **с**  >  управляемым доступом к папкам.

4. Дважды **щелкните Настроенные защищенные папки и** установите параметр **Включено**. Выберите **Показать и** ввести каждую папку.

### <a name="use-powershell-to-protect-additional-folders"></a>Использование PowerShell для защиты дополнительных папок

1. Введите **PowerShell** в меню Пуск, щелкните правой кнопкой мыши **Windows PowerShell** выберите **Выполнить в качестве администратора**

2. Введите следующий cmdlet:

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessProtectedFolders "<the folder to be protected>"
    ```
3. Повторите шаг 2, пока не добавите все папки, которые необходимо защитить. Добавленные папки видны в приложении Windows Security.

   ![Снимок экрана окна PowerShell с вступитым выше cmdlet](/microsoft-365/security/defender-endpoint/images/cfa-allow-folder-ps)

> [!IMPORTANT]
> Используйте `Add-MpPreference` для добавления или добавления приложений в список. С помощью `Set-MpPreference` этого комлета будет переописывать существующий список.

### <a name="use-mdm-csps-to-protect-additional-folders"></a>Использование CSPs MDM для защиты дополнительных папок

Используйте [поставщик служб конфигурации ./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) (CSP), чтобы разрешить приложениям вносить изменения в защищенные папки.

## <a name="allow-specific-apps-to-make-changes-to-controlled-folders"></a>Разрешить определенным приложениям вносить изменения в управляемые папки

Можно указать, считаются ли некоторые приложения безопасными, и предоставить доступ к файлам в защищенных папках. Разрешение приложений может быть полезным, если определенное приложение, которое вы знаете и доверяете, блокируется функцией доступа к управляемой папке.

> [!IMPORTANT]
> По умолчанию Windows добавляет приложения, которые считаются удобными для разрешенного списка. Такие приложения, которые добавляются автоматически, не записываются в список, показанный в приложении Безопасности Windows или с помощью связанных с ними cmdlets PowerShell. Не нужно добавлять большинство приложений. Добавляйте приложения только в том случае, если они заблокированы, и вы можете проверить их надежность.

При добавлении приложения необходимо указать расположение приложения. Только приложению в этом расположении будет разрешен доступ к защищенным папкам. Если приложение (с тем же именем) находится в другом расположении, оно не будет добавлено в список допустимых и может быть заблокировано управляемым доступом к папке.

Разрешенное приложение или служба имеет доступ к управляемой папке только после ее начала. Например, служба обновления будет продолжать запускать события после ее разрешения, пока она не будет остановлена и перезапущена.

### <a name="use-the-windows-defender-security-app-to-allow-specific-apps"></a>Используйте приложение Защитник Windows безопасности, чтобы разрешить определенные приложения

1. Откройте приложение Windows Security, ища меню пуск для **безопасности.**

2. Выберите **плитку защиты &** вирусов (или значок щита в левой панели меню), а затем выберите управление защитой **вымогателей.**

3. В разделе **Управляемый доступ к папке** выберите Разрешить приложение с помощью управляемого доступа **к папке**

4. Выберите **Добавление разрешенного приложения** и следуйте подсказкам для добавления приложений.

    ![Снимок экрана, как добавить разрешенную кнопку приложения](/microsoft-365/security/defender-endpoint/images/cfa-allow-app)

### <a name="use-group-policy-to-allow-specific-apps"></a>Использование групповой политики для допуска определенных приложений

1. На устройстве управления групповой политикой откройте консоль управления групповой политикой [правой](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)кнопкой мыши объект групповой политики, который необходимо настроить, и выберите **Изменить**.

2. В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера** и выберите **административные шаблоны.**

3. Расширь дерево до **компонентов**  >  **антивируса Microsoft Defender Защитник Windows**  >  **с**  >  управляемым доступом к папкам.

4. Дважды щелкните **параметр Настройка разрешенных приложений** и установите параметр **Включено.** Выберите **Показать** и ввести каждое приложение.

### <a name="use-powershell-to-allow-specific-apps"></a>Использование PowerShell для допуска определенных приложений

1. Введите **PowerShell** в меню Пуск, щелкните правой кнопкой мыши **Windows PowerShell** выберите **Выполнить в качестве администратора**
2. Введите следующий cmdlet:

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "<the app that should be allowed, including the path>"
    ```

    Например, чтобы добавить исполняемыйtest.exe, расположенный в папке *C:\apps,* этот комлет будет следующим образом: 

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "c:\apps\test.exe"
    ```

   Продолжайте использовать `Add-MpPreference -ControlledFolderAccessAllowedApplications` для добавления дополнительных приложений в список. Приложения, добавленные с помощью этого комлета, будут отображаться в приложении Безопасности Windows.

![Снимок экрана окна PowerShell с вписаным выше cmdlet](/microsoft-365/security/defender-endpoint/images/cfa-allow-app-ps)

> [!IMPORTANT]
> Используйте `Add-MpPreference` для добавления или добавления приложений в список. С помощью `Set-MpPreference` этого комлета будет переописывать существующий список.

### <a name="use-mdm-csps-to-allow-specific-apps"></a>Использование CSPs MDM для допуска определенных приложений

Используйте [поставщик услуг конфигурации ./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) (CSP), чтобы разрешить приложениям вносить изменения в защищенные папки.

## <a name="allow-signed-executable-files-to-access-protected-folders"></a>Разрешить подписанным исполняемым файлам доступ к защищенным папкам

Индикаторы сертификата и файлов Microsoft Defender для конечной точки могут разрешить подписанным исполняемым файлам доступ к защищенным папкам. Дополнительные сведения о реализации см. [в материале Create indicators based on certificates.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/indicator-certificates)

> [!Note]
> Это не относится к сценариям, включая Powershell

## <a name="customize-the-notification"></a>Настройка уведомления

Дополнительные сведения о настройке уведомления при запуске правила и блокировке приложения или файла см. в статью Настройка уведомлений оповещения в [Microsoft Defender для конечной точки.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-email-notifications)

## <a name="see-also"></a>См. также

- [Защита важных папок с управляемым доступом к папкам](controlled-folders.md)
- [Включить управляемый доступ к папкам](enable-controlled-folders.md)
- [Оценка правил уменьшения поверхности атаки](evaluate-attack-surface-reduction.md)
