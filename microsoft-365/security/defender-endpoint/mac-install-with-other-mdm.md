---
title: Развертывание с другой системой управления мобильными устройствами (MDM) для Microsoft Defender для конечной точки для Mac
description: Установите Microsoft Defender для конечной точки для Mac на другие решения управления.
keywords: Microsoft, defender, atp, mac, installation, deploy, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: mavel
author: maximvelichko
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: e929c17ada761a334700f6e66d2921483686834b
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861567"
---
# <a name="deployment-with-a-different-mobile-device-management-mdm-system-for-microsoft-defender-for-endpoint-on-macos"></a>Развертывание с другой системой управления мобильными устройствами (MDM) для Microsoft Defender для конечной точки на macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)
 
## <a name="prerequisites-and-system-requirements"></a>Необходимые условия и требования к системе

Перед началом работы см. в главной странице [Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md) на странице macOS описание необходимых условий и системных требований к текущей версии программного обеспечения.


## <a name="approach"></a>Способ

> [!CAUTION]

> В настоящее время Корпорация Майкрософт официально поддерживает только Intune и JAMF для развертывания и управления Microsoft Defender для конечной точки на macOS. Корпорация Майкрософт не предоставляет никаких гарантий, экспресс-или подразумеваемых, в отношении сведений, предоставленных ниже.

Если в организации используется решение управления мобильными устройствами (MDM), которое не поддерживается официально, это не означает, что вы не можете развернуть или запустить Microsoft Defender для конечной точки на macOS.

Microsoft Defender для конечной точки на macOS не зависит от каких-либо компонентов, определенных для поставщика. Его можно использовать с любым решением MDM, которое поддерживает следующие функции:

- Развертывание macOS .pkg на управляемых устройствах.
- Развертывание профилей конфигурации системы macOS на управляемых устройствах.
- Запустите произвольный настраиваемый администратором инструмент или скрипт на управляемых устройствах.

Большинство современных решений MDM включают эти функции, однако они могут называть их по-другому.

Однако можно развернуть Defender без последнего требования из предыдущего списка:

- Вы не сможете централизованно собирать состояние
- Если вы решите удалить Defender, вам потребуется войти на клиентские устройства локально в качестве администратора

## <a name="deployment"></a>Развертывание

Большинство решений MDM используют ту же модель для управления устройствами macOS с аналогичной терминологией. Используйте [развертывание на основе JAMF в](mac-install-with-jamf.md) качестве шаблона.

### <a name="package"></a>Пакет

Настройка развертывания [необходимого](mac-install-with-jamf.md)пакета приложений с пакетом установки (wdav.pkg), загруженным из Центра безопасности [Microsoft Defender.](mac-install-with-jamf.md)

Чтобы развернуть пакет на предприятии, используйте инструкции, связанные с решением MDM.

### <a name="license-settings"></a>Параметры лицензии

Настройка [профиля конфигурации системы.](mac-install-with-jamf.md) 

Решение MDM может называться как "Пользовательский профиль параметров", так как Microsoft Defender для конечной точки на macOS не является частью macOS.

Используйте список свойств jamf/WindowsDefenderATPOnboarding.plist, который можно извлечь из бортового пакета, загруженного из Центра безопасности [Microsoft Defender.](mac-install-with-jamf.md)
Система может поддерживать произвольный список свойств в формате XML. В этом случае можно загрузить файл jamf/WindowsDefenderATPOnboarding.plist.
Кроме того, может потребоваться сначала преобразовать список свойств в другой формат.

Как правило, пользовательский профиль имеет атрибут ID, name или domain. Для этого значения необходимо использовать именно "com.microsoft.wdav.atp".
MDM использует его для развертывания файла параметров **в /Library/Managed Preferences/com.microsoft.wdav.atp.plist** на клиентском устройстве, а Defender использует этот файл для загрузки данных на борту.

### <a name="kernel-extension-policy"></a>Политика расширения ядра

Настройка политики расширения KEXT или ядра. Используйте идентификатор **группы UBF8T346G9,** чтобы разрешить расширения ядра, предоставляемые Корпорацией Майкрософт.

> [!CAUTION]
> Если среда состоит из устройств Apple Silicon (M1), эти машины не должны получать профили конфигурации с политиками KEXT.
> Apple не поддерживает KEXT на этих машинах, развертывание такого профиля может быть неудачным на машинах M1.

### <a name="system-extension-policy"></a>Политика расширения системы

Настройка политики расширения системы. Используйте идентификатор **группы UBF8T346G9** и утвердите следующие идентификаторы пакета:

- com.microsoft.wdav.epsext
- com.microsoft.wdav.netext

### <a name="full-disk-access-policy"></a>Политика полного доступа к дискам

Предоставление полного доступа на диск к следующим компонентам:

- Microsoft Defender для конечной точки
    - Идентификатор: `com.microsoft.wdav`
    - Тип идентификатора: идентификатор пакета
    - Требование кода: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`

- Microsoft Defender для расширения безопасности конечных точек
    - Идентификатор: `com.microsoft.wdav.epsext`
    - Тип идентификатора: идентификатор пакета
    - Требование кода: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`

### <a name="network-extension-policy"></a>Политика расширения сети

В рамках возможностей обнаружения конечных точек и ответов Microsoft Defender for Endpoint на macOS проверяет трафик розетки и передает эти сведения на портал Центра безопасности Microsoft Defender. Следующая политика позволяет сетевому расширению выполнять эту функцию.

- Тип фильтра: плагин
- Идентификатор пакета плагинов: `com.microsoft.wdav`
- Идентификатор пакета поставщиков данных фильтрации: `com.microsoft.wdav.netext`
- Требование поставщика фильтрации данных: `identifier "com.microsoft.wdav.tunnelext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`
- Фильтровать розетки: `true`

## <a name="check-installation-status"></a>Проверка состояния установки

Запустите [Microsoft Defender для конечной точки](mac-install-with-jamf.md) на клиентских устройствах, чтобы проверить состояние бортового устройства.
