---
title: Изображения устройства
description: Требования к изображению при заказе новых устройств или повторном их повторном
keywords: Компьютеры, управляемые Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: fb3646e2ff339115d3fe6043ed45ea8f2140105a
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2021
ms.locfileid: "53419515"
---
# <a name="device-images"></a>Изображения устройства


Если вы заказывать новые [](#existing-devices) [устройства](#new-devices) или повторно использовать существующие устройства, у вас есть несколько вариантов для обеспечения того, чтобы изображение на устройстве соответствовало требованиям [нашего устройства.](device-requirements.md#check-hardware-requirements)

## <a name="new-devices"></a>новых устройств;
При заказе нового устройства [](device-requirements.md#minimum-requirements)от утвержденного производителя выполните следующие действия, чтобы убедиться, что они отгрузят устройства с нужным компьютеры, управляемые Майкрософт изображения и конфигурации программного обеспечения. При первом планировании регистрации определенной модели устройства в службе необходимо проверить пример, чтобы убедиться, что она обеспечит ожидающееся пользователем впечатление. Дополнительные сведения см. в [дополнительных сведениях о проверке новых устройств.](/microsoft-365/managed-desktop/get-started/validate-device)

### <a name="dell"></a>Dell
Работайте непосредственно с представителем по продажам Dell, который будет убедиться, что изображение, утвержденное компьютеры, управляемые Майкрософт, будет применено к устройствам для вашего заказа. Дополнительные вопросы по устройствам Dell, изображению и процессу заказа можно задать в MMD_at_dell@dell.com.

### <a name="hp"></a>HP 
При заказе новых устройств в HP обязательно используйте определенный SKU, указанный в разделе Дополнительные требования для каждой модели, найденной на сайте бизнес-устройств Магазина [Windows 10 Pro](https://www.microsoft.com/windowsforbusiness/view-all-devices#view-all-filter) (фильтр представления для демонстрации компьютеры, управляемые Майкрософт устройств).

Если вы заказывать устройство от HP, которое было [](customizing.md) утверждено в качестве исключения, но в настоящее время не перечислены на странице Список устройств, обязательно запросить SKU, который будет использоваться для вашей модели. Мы будем работать с HP, чтобы получить эту информацию с помощью вашего запроса на исключение. Вы также можете связаться с HP напрямую для любых вопросов о устройствах и инструкции по заказу устройств с помощью этих адресов:
 
- Америка: mmd-americas@hp.com
- Европа/Ближний Восток/Африка: mmd-emea@hp.com
- Азиатско-Тихоокеанский регион/Япония: mmd-apj@hp.com
- Глобальный: mmd@hp.com

### <a name="lenovo"></a>Lenovo
При заказе устройств из Lenovo для компьютеры, управляемые Майкрософт в компьютеры, управляемые Майкрософт необходимо указать определенный номер части, включенный в состав заказа. Свяжитесь с вашим представителем по продажам Lenovo илипартнером канала Lenovo и попросите их создать "специальную модель ставок" с системой, которая соответствует требованиям [нашего устройства.](device-requirements.md#minimum-requirements) Чтобы включить предварительно загруженное изображение, совместимое с компьютеры, управляемые Майкрософт, попросите представителя по продажам со ссылкой на номер части блока систем *SBB0Q94938 — MMD Enablement*." Работайте с вашим представителем по продажам Lenovo или партнером канала Lenovo для рекомендуемых служб, служб поддержки и изображений.

### <a name="microsoft"></a>Корпорация Майкрософт
Все устройства Майкрософт, которые соответствуют требованиям к устройству, оснащены изображением, которое работает с компьютеры, управляемые Майкрософт. Другие действия не требуются.

Чтобы получить последнее изображение, доступное на заводе на устройстве Майкрософт, работайте со специалистом Surface, чтобы использовать процесс Surface "Pegged PO".

## <a name="existing-devices"></a>Существующие устройства

Вы можете повторно использовать существующие устройства [](device-requirements.md#minimum-requirements) до тех пор, пока они соответствуют требованиям устройства и требованиям [программного обеспечения.](device-requirements.md#installed-software) Следуйте шагам, соответствующим вашему производителю.

Вы можете переиметь устройства либо с изображением от производителя, либо с помощью компьютеры, управляемые Майкрософт "универсального изображения". Чтобы получить соответствующее изображение производителя, можно [](#new-devices) заказать по крайней мере одно новое устройство модели, которое вы повторно. Затем вы можете получить изображение с этого устройства и применить его на других устройствах той же модели.

> [!NOTE]
> Вы несете ответственность за создание, тестирование и развертывание изображений. Кроме того, рекомендуется использовать соответствующие изображения, предоставляемые производителем по возможности, а не пользовательские изображения, включая "универсальное изображение".

### <a name="hp"></a>HP

Коммерческие КОМПЬЮТЕРы HP, отправленные с корпоративным готовым изображением HP, включают в себя . WIM-файл для восстановления. Это изображение можно использовать для применения образа восстановления фабрики к другим устройствам той же модели.

Эти действия удаляют все данные на устройстве, поэтому перед запуском необходимо сохранить все данные, которые необходимо сохранить.

1. [Создайте usb-накопитель с возможностью загрузки](/windows-hardware/manufacture/desktop/winpe-create-usb-bootable-drive) с помощью WinPE.
2. Скопируйте эти файлы из C: \\ SOURCES на USB-накопитель:
    - Файл WIM восстановления фабрики (например, HP \_ EliteBook \_ 840 \_ G7 \_ Notebook PC CR \_ \_ \_ 2004.wim)
    - РАЗВЕРТЫВАНИЕ. CMD
    - ReCreatePartitions.txt
3. [Загрузка устройства в WinPE](https://store.hp.com/us/en/tech-takes/how-to-boot-from-usb-drive-on-windows-10-pcs) USB-накопитель.
4. В командной подсказке запустите [Diskpart.exe](/windows-server/administration/windows-commands/diskpart#additional-references).
5. В Diskpart запустите, а затем обратите внимание на основной номер диска хранилища `list disk` (как правило, диск 0).
6. Exit Diskpart путем ввода `exit` .
7. В командной подсказке `deploy.cmd <sys_disk> <recovery_wim>` *запустите , sys_disk* это номер диска основного  диска хранения, который вы только что определили, и recovery_wim имя файла . Файл WIM, который вы скопировали ранее.
8. Удалите USB-накопитель и перезапустите устройство.

### <a name="microsoft"></a>Корпорация Майкрософт 

Устройства Microsoft Surface включают изображения "восстановления голого [металла",](https://support.microsoft.com/en-us/surfacerecoveryimage) которые являются специфическими для каждой модели. Эти изображения можно использовать для повторного использования устройств.

На этих изображениях используется среда Windows восстановления (WinRE), и это ручной процесс (не автоматизированный). Выполните действия по [созданию и использованию usb-накопителя восстановления для Surface.](https://support.microsoft.com/surface/creating-and-using-a-usb-recovery-drive-for-surface-677852e2-ed34-45cb-40ef-398fc7d62c07)


### <a name="universal-image"></a>Универсальный образ
компьютеры, управляемые Майкрософт создал изображение, содержащее Windows 10 Pro и Приложения Microsoft 365 для Enterprise, которое можно использовать с компьютеры, управляемые Майкрософт. Однако лучше использовать изображения, подходящие для компьютеры, управляемые Майкрософт, предоставляемых производителем, даже если это означает более старую версию Windows, которую необходимо обновить после того, как пользователь войт. Использование компьютеры, управляемые Майкрософт универсального изображения должно быть окончательным вариантом.

- Мы обновляем изображение с Windows ежемесячного обновления качества каждые 30-60 дней и Приложения Microsoft 365 для Enterprise обновлений по крайней мере два раза в год.
- Изображение содержит пакет подготовка восстановления, чтобы обеспечить восстановление Приложения Microsoft 365 для Enterprise после Windows восстановления.
- Вы можете развернуть изображение с помощью USB-дисков. Он содержит скриптируемый процесс вставки драйверов (описанный в документации, включенной в изображение).
- Вы можете изменять включенные скрипты и папки для использования с другими настройками, такими как добавление определенных накопительных обновлений, код копирования файлов или выполнение других проверок.
- Драйверы и обновления качества добавляются в Windows во время развертывания с USB-накопителя.

> [!NOTE]
> Вы несете ответственность за добавление всех необходимых драйверов, выполнение всех тестов и отсутствие проблем с окончательным развернутым изображением. Мы предоставляем универсальное изображение "as-is", но предоставляем техническое руководство и ответим на вопросы. Свяжитесь с MMDImage@microsoft.com.

Отправка запросов на контент и документацию универсального изображения путем создания запроса на изменение на [портале Admin.](../get-started/access-admin-portal.md)


