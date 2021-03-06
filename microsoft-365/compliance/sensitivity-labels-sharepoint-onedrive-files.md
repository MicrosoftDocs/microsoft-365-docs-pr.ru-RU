---
title: Включение меток конфиденциальности для файлов Office в SharePoint и OneDrive
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Администраторы могут включить поддержку меток конфиденциальности для файлов Word, Excel и PowerPoint в SharePoint и OneDrive.
ms.openlocfilehash: 61b6c366f76c25ab0b35df4314f63491be5ce5e6
ms.sourcegitcommit: 022d9d91263994c48efcebe08a84319573dc3a8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/12/2021
ms.locfileid: "53377233"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive"></a>Включение меток конфиденциальности для файлов Office в SharePoint и OneDrive

>*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Внесите встроенную маркировку для поддерживаемых Office файлов в SharePoint и OneDrive, чтобы [](sensitivity-labels.md) пользователи могли применять метки конфиденциальности в Office для Интернета. [](sensitivity-labels-office-apps.md#office-file-types-supported) Когда эта функция включена,  пользователи увидят кнопку "Чувствительность" на ленте, чтобы они могли применять метки, и увидеть любое примененное имя метки на панели состояния.

Включение этой функции также SharePoint и OneDrive возможность обработки содержимого Office файлов, зашифрованных с помощью метки конфиденциальности. Метка может применяться в Office для Интернета или Office настольных приложениях и загружаться или SharePoint и OneDrive. Пока эта функция не включается, эти службы не могут обрабатывать зашифрованные файлы, что означает, что совместное открытие, eDiscovery, предотвращение потери данных, поиск и другие функции совместной работы не будут работать для этих файлов.

После ввести метки конфиденциальности для Office файлов в SharePoint и OneDrive, для новых и измененных файлов с меткой чувствительности, применяемой шифрованием с облачным ключом (и не используемое шифрование [двойных](double-key-encryption.md)ключей):

- Для Word Excel и PowerPoint файлы SharePoint и OneDrive распознают метку и теперь могут обрабатывать содержимое зашифрованного файла.

- При загрузке или доступе к этим файлам из SharePoint или OneDrive, метка конфиденциальности и любые параметры шифрования с метки применяются и остаются с файлом, где бы он ни хранился. Убедитесь, что вы предоставляете пользователю рекомендации по использованию только меток для защиты документов. Дополнительные сведения см. в [меню Параметры управления правами на информацию (IRM) и метки конфиденциальности.](sensitivity-labels-office-apps.md#information-rights-management-irm-options-and-sensitivity-labels)

- Когда пользователи загружают помеченные и зашифрованные файлы в SharePoint или OneDrive, они должны иметь по крайней мере права просмотра этих файлов. Например, они могут открывать файлы за пределами SharePoint. Если они не имеют этого права на минимальное использование, загрузка успешно, но служба не распознает метку и не может обрабатывать содержимое файла.

- Используйте Office для Интернета (Word, Excel, PowerPoint) для открытия и редактирования Office с метами конфиденциальности, которые применяют шифрование. Разрешения, которые были назначены с помощью шифрования, применяются. Для этих документов также можно [использовать](apply-sensitivity-label-automatically.md) автометку.

- Внешние пользователи могут получать доступ к документам, помеченным шифрованием, с помощью учетных записей гостей. Дополнительные сведения см. в [материалах Support for external users and labeled content.](sensitivity-labels-office-apps.md#support-for-external-users-and-labeled-content)

- Office 365 eDiscovery поддерживает полнотексовое поиск этих файлов, а политики предотвращения потери данных (DLP) поддерживают контент в этих файлах.

> [!NOTE]
> Если шифрование было применено с помощью локального ключа (топология управления ключом, часто именуемая [](double-key-encryption.md)"удержание собственного ключа" или HYOK), или с помощью шифрования двойных ключей, поведение службы для обработки содержимого файла не меняется. Поэтому для этих файлов совместная работа, поиск, открытие электронных данных, предотвращение потери данных, поиск и другие функции совместной работы не будут работать.
>
> Поведение SharePoint и OneDrive также не меняется для существующих файлов в этих расположениях, помеченных шифрованием с помощью одного ключа на основе Azure. Чтобы эти файлы могли воспользоваться новыми возможностями после добавления меток конфиденциальности для Office файлов SharePoint и OneDrive, файлы должны быть загружены и загружены повторно или изменены.

После ввести метки конфиденциальности для Office файлов в SharePoint и OneDrive доступны [](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) три новых события аудита для мониторинга меток чувствительности, применяемых к документам в SharePoint и OneDrive:

- **Метка конфиденциальности применена к файлу**
- **Метка конфиденциальности, примененная к файлу, изменена**
- **Метка конфиденциальности, примененная к файлу, удалена**

Просмотрите следующее видео (без звука), чтобы увидеть новые возможности в действии:

> [!VIDEO https://www.microsoft.com/videoplayer/embed//RE4ornZ]

У вас всегда есть выбор, чтобы отключить метки конфиденциальности для Office файлов[](#how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out)в SharePoint и OneDrive (отказ) в любое время.

Если в настоящее время вы защищаете документы в SharePoint с помощью SharePoint управления правами на информацию (IRM), обязательно ознакомьтесь с разделом управления правами на SharePoint информации [(IRM)](#sharepoint-information-rights-management-irm-and-sensitivity-labels) и меток конфиденциальности на этой странице.

## <a name="requirements"></a>Требования

Эти новые возможности работают только с [метами конфиденциальности.](sensitivity-labels.md) Если в настоящее время у вас есть метки Azure Information Protection, сначала перенаселите их на метки конфиденциальности, чтобы включить эти функции для новых файлов, которые вы загружаете. Дополнительные сведения об этом процессе см. в статье [Перенос меток Azure Information Protection на платформу унифицированных меток конфиденциальности](/azure/information-protection/configure-policy-migrate-labels).

Используйте версию приложение синхронизации OneDrive 19.002.0121.0008 или более поздней версии Windows и версию 19.002.0107.0008 или более поздней версии на Mac. Обе эти версии были выпущены 28 января 2019 г. и в настоящее время выпущены для всех колец. Дополнительные сведения см. в [OneDrive заметки о выпуске.](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0) После включить метки конфиденциальности для Office файлов в SharePoint и OneDrive, пользователям, которые запускают более старую версию приложения синхронизации, будет предложено обновить его.

## <a name="limitations"></a>Ограничения

- SharePoint и OneDrive не могут обрабатывать некоторые файлы, помеченные и зашифрованные из Office настольных приложений, когда эти файлы содержат данные PowerQuery, данные, хранимые в настраиваемой надстройке, или настраиваемые XML-части, такие как Cover Page Properties, схемы типа контента, настраиваемая информационная панель документов и настраиваемая XSN. Это ограничение также применимо к файлам, в которые при отправке добавлен [iD](https://support.microsoft.com/office/enable-and-configure-unique-document-ids-ea7fee86-bd6f-4cc8-9365-8086e794c984) документа.

    Для этих файлов либо нанесите метку без шифрования, чтобы их можно было открыть в Office в Интернете, либо поручить пользователям открывать файлы в своих настольных приложениях. Файлы, помеченные и зашифрованные только в Office в Интернете, не затронуты.

- SharePoint и OneDrive автоматически не применяйте метки конфиденциальности к существующим файлам, которые вы уже зашифрованы с помощью меток Azure Information Protection. Вместо этого, чтобы функции работали после того, как вы включаете метки конфиденциальности для Office файлов в SharePoint и OneDrive, выполните эти задачи:

    1. Убедитесь, что метки [Azure Information Protection](/azure/information-protection/configure-policy-migrate-labels) перенесены [](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) на метки конфиденциальности и опубликованы из Центр соответствия требованиям Microsoft 365.
    2. Скачайте помеченные файлы и загрузите их в исходное расположение в SharePoint или OneDrive.

- SharePoint и OneDrive не могут обрабатывать зашифрованные файлы, если метка, которая применяла шифрование, имеет любую из следующих конфигураций [для шифрования:](encryption-sensitivity-labels.md#configure-encryption-settings)
  - **Разрешить пользователям назначать разрешения при применении метки** и если выбран флажок **предлагать пользователям указать разрешения в Word, PowerPoint и Excel**. Этот параметр иногда называют "пользовательскими разрешениями".
  - Для параметра **Срок действия доступа пользователей к содержимому истекает** установлено значение, отличное от **никогда**.
  - Выбрано: **Шифрование с двойным ключом**.

    Для меток с любой из этих конфигураций шифрования метки не отображаются пользователям в Office для Интернета. Кроме того, новые возможности нельзя использовать с помеченными документами, которые уже имеют эти параметры шифрования. Например, эти документы не будут возвращены в результатах поиска, даже если они обновлены.

- По причинам производительности при загрузке или сохранения документа для SharePoint и метка файла не применяется шифрование, столбец **Sensitivity** в библиотеке документов может отобразить имя метки. Фактор в этой задержке, если вы используете сценарии или автоматизации, которые зависят от имени метки в этом столбце.

- Если документ помечен во время его проверки в [SharePoint,](https://support.microsoft.com/office/check-out-check-in-or-discard-changes-to-files-in-a-library-7e2c12a9-a874-4393-9511-1378a700f6de)столбец **Sensitivity** в библиотеке документов не будет отображать имя метки до тех пор, пока документ не будет зарегистрирован и далее откроется в SharePoint.

- Если помеченный и зашифрованный документ загружается из SharePoint или OneDrive приложением или службой с основным именем службы, а затем снова загружается с меткой, которая применяет различные параметры шифрования, загрузка будет неудачной. В качестве примера можно Microsoft Cloud App Security метку конфиденциальности в файле с **Конфиденциальной** на высококонфиденциальную или с **Конфиденциальной** на  **общую.**
    
    Загрузка не сбой, если приложение или служба впервые запускает раздел [Unlock-SPOSensitivityLabelEncryptedFile,](/powershell/module/sharepoint-online/unlock-sposensitivitylabelencryptedFile) как поясняется в разделе [Удаление](#remove-encryption-for-a-labeled-document) шифрования для помеченного документа. Или перед отправкой исходный файл удаляется или меняется имя файла.

- Пользователи могут испытывать задержки с открытием зашифрованных документов в следующем сценарии Save As: Using a desktop version of Office, пользователь выбирает save As для документа с меткой конфиденциальности, применяемой шифрованием. Пользователь выбирает SharePoint или OneDrive для расположения, а затем немедленно пытается открыть этот документ в Office для Интернета. Если служба по-прежнему обрабатывает шифрование, пользователь видит сообщение о том, что документ должен быть открыт в своем настольном приложении. Если они попытаются повторить попытку через пару минут, документ успешно откроется в Office для Интернета.

- Для зашифрованных документов печать не поддерживается.

- Для зашифрованного документа, который предоставляет пользователю разрешения на редактирование, копирование не может быть заблокировано в веб-версиях Office приложений.

- По умолчанию Office и мобильные приложения не поддерживают совместное авторство файлов, помеченных шифрованием. Эти приложения продолжают открывать помеченные и зашифрованные файлы в эксклюзивном режиме редактирования.

    > [!NOTE]
    > Теперь совместное авторство поддерживается в предварительном просмотре. Дополнительные сведения см. в публикации [Enable co-authoring for files encrypted with sensitivity labels.](sensitivity-labels-coauthoring.md)

- Если администратор изменяет параметры опубликованных меток, которые уже применяются к файлам, скачамым для клиента синхронизации пользователей, пользователи не смогут сохранить изменения, внесенные в файл в папке OneDrive Sync. Этот сценарий применяется к файлам, помеченным шифрованием, а также при изменении метки с метки, которая не применяла шифрование к мете, применяемой шифрованием. Пользователи видят [красный круг с](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3)ошибкой с белым крестом и просят сохранить новые изменения в виде отдельной копии. Вместо этого они могут закрыть и открыть файл или использовать Office для Интернета.

- Пользователи могут испытывать проблемы с сохранением после отключения или в режиме сна, когда вместо Office для Интернета, они используют настольные и мобильные приложения для Word, Excel или PowerPoint. Для этих пользователей, когда они возобновляют сеанс Приложение Office и пытаются сохранить изменения, они видят сообщение о сбое отправки с возможностью сохранить копию вместо сохранения исходного файла.

- Документы, зашифрованные следующими способами, не могут быть открыты в Office для Интернета:
  - Шифрование с локальной клавишей ("удерживайте собственный ключ" или HYOK)
  - Шифрование, примененное с помощью [шифрования двойных ключей](double-key-encryption.md)
  - Шифрование, которое применялось независимо от метки, например, путем непосредственного применения шаблона защиты управления правами.

- Метки, настроенные для [других языков,](create-sensitivity-labels.md#additional-label-settings-with-security--compliance-center-powershell) не поддерживаются и отображают только исходный язык.

- Захваты экрана не могут быть предотвращены для зашифрованных документов. Дополнительные сведения см. в [статью Can Rights Management prevent screen captures?](/azure/information-protection/faqs-rms#can-rights-management-prevent-screen-captures)

- Если удалить метку, которая была применена к документу в SharePoint или OneDrive, а не удалить метку из применимой политики меток, документ при загрузке не будет помечен или зашифрован. Для сравнения, если помеченный документ хранится за пределами SharePoint или OneDrive, документ остается зашифрованным, если метка удалена. Обратите внимание, что хотя метки можно удалить на этапе тестирования, удаление метки в производственной среде очень редко.

## <a name="how-to-enable-sensitivity-labels-for-sharepoint-and-onedrive-opt-in"></a>Как включить метки конфиденциальности для SharePoint и OneDrive (в)

Новые возможности можно включить с помощью Центр соответствия требованиям Microsoft 365 или с помощью PowerShell. Как и во всех изменениях конфигурации на уровне клиента для SharePoint и OneDrive, для внесения изменений требуется около 15 минут.

### <a name="use-the-compliance-center-to-enable-support-for-sensitivity-labels"></a>Используйте центр соответствия требованиям, чтобы включить поддержку меток конфиденциальности

Этот параметр является самым простым способом включить метки конфиденциальности для SharePoint и OneDrive, но вы должны войти в качестве глобального администратора для клиента.

1. Войдите в [Центр соответствия требованиям Microsoft 365](https://compliance.microsoft.com/) глобального администратора и перейдите к **защите информации**  >  **решений**

    Если этот параметр не отображается сразу, сначала выберите пункт **Показать все**.

2. Если вы видите сообщение, которое включит возможность обработки контента в Office файлах, выберите **Включить сейчас:**

    ![Включаем кнопку теперь, чтобы включить метки конфиденциальности для Office Online](../media/sensitivity-labels-turn-on-banner.png)

    Команда запускается немедленно, и когда страница будет обновлена, сообщение или кнопку больше не будут видеть.

> [!NOTE]
> Если у вас Microsoft 365 multi-Geo, необходимо использовать PowerShell, чтобы включить эти возможности для всех географических местоположений. Подробнее см. в следующем разделе.

### <a name="use-powershell-to-enable-support-for-sensitivity-labels"></a>Использование PowerShell для поддержки меток конфиденциальности

В качестве альтернативы использованию центра соответствия требованиям можно включить поддержку меток конфиденциальности с помощью [комлета Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant) из SharePoint PowerShell.

Если у вас Microsoft 365-Geo, необходимо использовать PowerShell, чтобы включить эту поддержку для всех географических местоположений.

#### <a name="prepare-the-sharepoint-online-management-shell"></a>Подготовка SharePoint сетевой оболочки управления

Перед запуском команды PowerShell, чтобы включить метки конфиденциальности для Office файлов в SharePoint и OneDrive, убедитесь, что вы запустите SharePoint версии Online Management Shell 16.0.0.19418.12000 или более поздней версии. Если у вас уже есть последняя версия, можно перейти к [следующей процедуре](#run-the-powershell-command-to-enable-support-for-sensitivity-labels) для запуска команды PowerShell.

1. Если у вас установлена предыдущая версия командной консоли SharePoint Online из коллекции PowerShell, вы можете обновить модуль, выполнив следующий командлет.

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. Кроме того, если вы установили предыдущую версию SharePoint online Management Shell из Центра  загрузки Майкрософт, вы также можете перейти к добавлению или удалению программ и удалить SharePoint online Management Shell.

3. В веб-браузере перейдите на страницу Центра загрузки и [скачайте последнюю версию командной консоли SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkId=255251).

4. Выберите язык и нажмите кнопку **Скачать**.

5. Выберите разрядность файла MSI (x64 или x86). Скачайте файл x64, если вы запустите 64-битную версию Windows или файл x86 при запуске 32-битной версии. Если вы не знаете, см. в Windows версии операционной [системы?](https://support.microsoft.com/help/13443/windows-which-operating-system)

6. После скачивания файла запустите файл и выполните действия мастера настройки.

#### <a name="run-the-powershell-command-to-enable-support-for-sensitivity-labels"></a>Запустите команду PowerShell, чтобы включить поддержку меток конфиденциальности

Чтобы включить новые возможности, используйте комлет [Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant) с *параметром EnableAIPIntegration:*

1. С помощью учетной записи работы или учебного заведения с глобальными привилегиями администратора SharePoint администратора в Microsoft 365 подключите SharePoint. Сведения о том, как это сделать, см. в статье [Начало работы с командной консолью SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).

    > [!NOTE]
    > Если у вас Microsoft 365 multi-Geo, используйте параметр -URL с [Подключение-SPOService](/powershell/module/sharepoint-online/connect-sposervice)и укажите URL-адрес SharePoint Центра администрирования в Интернете для одного из ваших геолокационных местоположений.

2. Запустите следующую команду и нажмите **кнопку Y,** чтобы подтвердить:

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true
    ```
3. Для Microsoft 365 Multi-Geo: повторите шаги 1 и 2 для каждого из оставшихся геолокационных объектов.

## <a name="publishing-and-changing-sensitivity-labels"></a>Публикация и изменение меток конфиденциальности

При использовании меток конфиденциальности с SharePoint и OneDrive следует помнить, что необходимо разрешить время репликации при публикации новых меток чувствительности или обновлении существующих меток чувствительности. Это особенно важно для новых меток, которые применяют шифрование.

Например: вы создаете и публикуете новую метку конфиденциальности, которая применяет шифрование, и она очень быстро появляется в настольном приложении пользователя. Пользователь применяет эту метку к документу, а затем загружает его в SharePoint или OneDrive. Если репликация меток не завершена для службы, новые возможности не будут применены к этому документу при загрузке. В результате документ не возвращается в поиске или для поиска электронных документов, а в Office для Интернета.

Следующие изменения реплицируется в течение одного часа: новые и удаленные метки конфиденциальности, а также параметры политики меток чувствительности, которые включают в политику метки.

Следующие изменения реплицируется в течение 24 часов. Изменения параметров меток чувствительности для существующих меток.

Поскольку задержка репликации для новых меток конфиденциальности составляет всего один час, маловероятно, что в этом примере вы сможете запустить сценарий. Но в качестве гарантии рекомендуется сначала опубликовать новые метки нескольким пользователям тестирования, подождать час, а затем проверить поведение меток в SharePoint и OneDrive. В качестве последнего шага сделайте метку доступной для большего пользователей, добавив больше пользователей в существующую политику меток или добавьте метку в существующую политику меток для стандартных пользователей. На момент, когда стандартные пользователи видят метку, она уже синхронизирована с SharePoint и OneDrive.

## <a name="sharepoint-information-rights-management-irm-and-sensitivity-labels"></a>SharePoint Метки управления правами на информацию (IRM) и метки конфиденциальности

SharePoint управления правами на информацию [(IRM)](set-up-irm-in-sp-admin-center.md) — это более старая технология для защиты файлов на уровне списка и библиотеки путем применения шифрования и ограничений при загрузке файлов. Эта более старая технология защиты предназначена для предотвращения открытия файла несанкционированными пользователями во время его SharePoint.

Для сравнения, метки чувствительности помимо шифрования предоставляют параметры защиты визуальных разметок (заготки, подножки, водяные знаки). Параметры шифрования поддерживают полный [](/azure/information-protection/configure-usage-rights) диапазон прав на использование, чтобы ограничить то, что пользователи могут делать с содержимым, и для многих сценариев поддерживаются одинаковые [метки конфиденциальности.](get-started-with-sensitivity-labels.md#common-scenarios-for-sensitivity-labels) Использование того же метода защиты с согласованными настройками между рабочими нагрузками и приложениями приводит к последовательной стратегии защиты.

Тем не менее, вы можете использовать оба решения защиты вместе, и поведение будет следующим образом:

- Если вы загрузите файл с меткой конфиденциальности, которая применяет шифрование, SharePoint не сможет обрабатывать содержимое этих файлов, поэтому совместное, eDiscovery, DLP и поиск не поддерживаются для этих файлов.

- Если вы маркировали файл с Office для Интернета, применяются все параметры шифрования с метки. Для этих файлов поддерживаются совместное, электронное открытие, DLP и поиск.

- Если вы скачиваете файл, помеченный с помощью Office для Интернета, метка сохраняется, а все параметры шифрования из метки применяются, а не параметры ограничений IRM.

- Если вы скачиваете Office или PDF-файл, который не шифруется с меткой конфиденциальности, применяются параметры IRM.

- Если вы включили любой из дополнительных параметров библиотеки IRM, которые включают предотвращение отправки пользователями документов, не поддерживаюющих IRM, эти параметры применяются.

При таком поведении вы можете быть уверены, что все Office и PDF-файлы защищены от несанкционированного доступа, если они загружены, даже если они не помечены. Однако загруженные файлы с меткой не будут пользоваться преимуществами новых возможностей.


## <a name="search-for-documents-by-sensitivity-label"></a>Поиск документов с помощью метки конфиденциальности

Используйте управляемое свойство **InformationProtectionLabelId,** чтобы найти все документы в SharePoint или OneDrive с определенной меткой конфиденциальности. Используйте следующий синтаксис: `InformationProtectionLabelId:<GUID>`

Например, для поиска всех документов, помеченных как "Конфиденциальные", и эта метка имеет GUID "8faca7b8-8d20-48a3-8ea2-0f96310a848e", в поле поиска введите:

```
InformationProtectionLabelId:8faca7b8-8d20-48a3-8ea2-0f96310a848e
```

Поиск не будет находить помеченные документы в сжатом файле, например .zip файле.

Чтобы получить GUID-коды для меток конфиденциальности, используйте кодлет [Get-Label:](/powershell/module/exchange/get-label)

1. Сначала [подключитесь к PowerShell Центра безопасности и соответствия требованиям Office 365](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).

    Например, в сеансе PowerShell, который вы запускаете как администратор, войдите в систему с помощью учетной записи глобального администратора.

2. Затем запустите следующую команду:

    ```powershell
    Get-Label |ft Name, Guid
    ```

Дополнительные сведения об использовании управляемых свойств см. в [SharePoint.](/sharepoint/manage-search-schema)

## <a name="remove-encryption-for-a-labeled-document"></a>Удаление шифрования для помеченного документа

Могут быть редкие случаи, когда администратору SharePoint удалить шифрование из документа, хранимом в SharePoint. Любой пользователь, [](/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions) которому назначено право управления правами на экспорт или полный контроль для этого документа, может удалить шифрование, примененное службой управления правами Azure из Azure Information Protection. Например, пользователи с одним из этих прав на использование могут заменить метку, применяемую шифрование, меткой без шифрования. [Супер-пользователь](/azure/information-protection/configure-super-users) также может скачать файл и сохранить локализованную копию без шифрования.

В качестве альтернативы глобальный администратор или администратор SharePoint может запустить команды [Unlock-SPOSensitivityLabelEncryptedFile,](/powershell/module/sharepoint-online/unlock-sposensitivitylabelencryptedFile) которые удаляют метку конфиденциальности и шифрование. [](/sharepoint/sharepoint-admin-role) Этот комдлет выполняется, даже если у администратора нет разрешений на доступ к сайту или файлу, или если служба управления правами Azure недоступна.

Пример:

```powershell
Unlock-SPOSensitivityLabelEncryptedFile -FileUrl "https://contoso.com/sites/Marketing/Shared Documents/Doc1.docx" -JustificationText "Need to decrypt this file"
```

Требования:

- SharePoint Online Management Shell версии 16.0.20616.12000 или более поздней версии.

- Шифрование было применено меткой конфиденциальности с настройками шифрования, определенными администратором (параметры Присвоения разрешений теперь [помечены).](encryption-sensitivity-labels.md#assign-permissions-now) [Шифрование двойных](encryption-sensitivity-labels.md#double-key-encryption) ключей не поддерживается для этого комлета.

Текст обоснования добавляется [](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) в событие аудита метки Удаленная чувствительность из **файла,** а действие расшифровки также записываются в журнале использования защиты для Azure [Information Protection.](/azure/information-protection/log-analyze-usage)

## <a name="how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out"></a>Отключение меток конфиденциальности для SharePoint и OneDrive (отказ)

Если отключить эти новые возможности, файлы, загруженные после включения меток конфиденциальности для SharePoint и OneDrive, по-прежнему будут защищены меткой, так как параметры метки продолжают применяться. При применении меток конфиденциальности к новым файлам после отключения этих новых возможностей полный текст поиска, поиска электронных данных и совместной работы больше не будет.

Чтобы отключить эти новые возможности, необходимо использовать PowerShell. С помощью SharePoint online Management Shell и команды [Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant) укажите тот же параметр *EnableAIPIntegration,* как описано в разделе [Use PowerShell,](#use-powershell-to-enable-support-for-sensitivity-labels) чтобы включить поддержку меток конфиденциальности. Но на этот раз установите значение параметра false и нажмите **Y,** чтобы подтвердить:

```PowerShell
Set-SPOTenant -EnableAIPIntegration $false
```

Если у вас Microsoft 365 multi-Geo, необходимо выполнить эту команду для каждого из ваших геолокационных местоположений.

## <a name="next-steps"></a>Дальнейшие действия

После включения меток конфиденциальности для Office файлов в SharePoint и OneDrive, рассмотрите возможность автоматической маркировки этих файлов с помощью политик автоматической маркировки. Дополнительные сведения см. в [материалах Apply a sensitivity label to content automatically.](apply-sensitivity-label-automatically.md)

Требуется предоставить общий доступ к помеченным зашифрованным документам пользователям за пределами вашей организации?  См. раздел [Совместное использование зашифрованных документов с внешними пользователями](sensitivity-labels-office-apps.md#sharing-encrypted-documents-with-external-users).
