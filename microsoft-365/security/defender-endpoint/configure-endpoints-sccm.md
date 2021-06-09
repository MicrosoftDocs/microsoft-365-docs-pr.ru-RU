---
title: Подключение устройств Windows 10 с помощью Configuration Manager
description: Используйте Диспетчер конфигурации для развертывания пакета конфигурации на устройствах, чтобы они были размещены в службе.
keywords: бортовые устройства с помощью sccm, управления устройствами, настройка Microsoft Defender для устройств endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 02/07/2020
ms.technology: mde
ms.openlocfilehash: d827fb89a082286b1b7b77ea0a14e588ce171161
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842198"
---
# <a name="onboard-windows-10-devices-using-configuration-manager"></a>Подключение устройств Windows 10 с помощью Configuration Manager

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**

- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Microsoft Endpoint Configuration Manager текущего филиала
- Диспетчер конфигураций System Center 2012 R2

>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointssccm-abovefoldlink)

## <a name="supported-client-operating-systems"></a>Поддерживаемые клиентские операционные системы

На основе версии диспетчера конфигурации можно использовать следующие клиентские операционные системы:

#### <a name="configuration-manager-version-1910-and-prior"></a>Configuration Manager version 1910 and prior

- Компьютеры клиентов, работающие Windows 10 

#### <a name="configuration-manager-version-2002-and-later"></a>Configuration Manager version 2002 and later

Начиная с версии Configuration Manager 2002, вы можете использовать следующие операционные системы:

- Windows 8.1
- Windows 10
- Windows Server 2012 R2
- Windows Server 2016
- Windows Server 2016 версии 1803 или более поздней версии
- Windows Server 2019

>[!NOTE]
>Дополнительные сведения о том, как Windows Server 2012 R2, Windows Server 2016 и Windows Server 2019, см. в Windows [серверов.](configure-server-endpoints.md)



### <a name="onboard-devices-using-system-center-configuration-manager"></a>Бортовых устройств с System Center Configuration Manager


[![Изображение PDF, показывающая различные пути развертывания](images/onboard-config-mgr.png)](images/onboard-config-mgr.png#lightbox)


Ознакомьтесь с [pdf или Visio,](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf) чтобы узнать о различных путях развертывания Microsoft Defender для конечной точки. [](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) 



1. Откройте пакет конфигурации Configuration Manager .zip файл *(WindowsDefenderATPOnboardingPackage.zip), загруженный* из мастера бортового обслуживания. Вы также можете получить пакет из [Центр безопасности в Microsoft Defender:](https://securitycenter.windows.com/)

    1. В области навигации выберите **Параметры**  >  **onboarding**.
    
    1. Выберите Windows 10 в качестве операционной системы.

    1. В поле **Метод развертывания** выберите System Center Configuration Manager **2012/2012 R2/1511/1602**.
    
    1. Выберите **пакет Загрузка** и сохраните .zip файл.

2. Извлечение содержимого файла .zip в общее расположение только для чтения, к которому могут получить доступ сетевые администраторы, которые будут развертывать пакет. У вас должен быть файл с именем *WindowsDefenderATPOnboardingScript.cmd.*

3. Развертывание пакета, следуя шагам в статье [Packages and Programs System Center R2 Configuration Manager 2012.](/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\))

    а. Выберите предопределяемую коллекцию устройств для развертывания пакета.

> [!NOTE]
> Защитник для конечной точки не поддерживает вовне на этапе [Out-Of-Box Experience (OOBE).](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) Убедитесь, что пользователи заполняют OOBE после Windows установки или обновления.

>[!TIP]
> После работы на устройстве можно выполнить тест обнаружения, чтобы убедиться, что устройство правильно вошел в службу. Дополнительные сведения см. в таблице [Run a detection test on a newly onboarded Defender for Endpoint device.](run-detection-test.md)
>
> Обратите внимание, что в приложении Configuration Manager можно создать правило обнаружения, чтобы постоянно проверять, было ли устройство на борту. Приложение — это другой тип объекта, чем пакет и программа.
> Если устройство еще не установлено (в связи с завершением OOBE или по какой-либо другой причине), диспетчер конфигурации будет повторно фиксироваться на борту устройства до тех пор, пока правило не обнаружит изменение состояния.
> 
> Это поведение может быть выполнено путем проверки правила обнаружения, если значение реестра "OnboardingState" (типа REG_DWORD) = 1.
> Это значение реестра расположено в статье "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status".
Дополнительные сведения см. в [руб. В System Center 2012 R2 Configuration Manager.](/previous-versions/system-center/system-center-2012-R2/gg682159\(v=technet.10\)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type)

### <a name="configure-sample-collection-settings"></a>Настройка параметров коллекции образцов

Для каждого устройства можно установить значение конфигурации, чтобы определить, можно ли собирать образцы с устройства при Центр безопасности в Microsoft Defender отправки файла для глубокого анализа.

>[!NOTE]
>Эти параметры конфигурации обычно делаются с помощью Configuration Manager. 

Вы можете установить правило соответствия требованиям для элемента конфигурации в диспетчере конфигурации, чтобы изменить пример параметров обмена данными на устройстве.

Это правило должно быть *элементом* настройки правил соответствия требованиям, который задает значение ключа реестра на целевых устройствах, чтобы убедиться, что они являются жалобами.

Конфигурация заданная с помощью следующей записи ключа реестра:

```console
Path: "HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection"
Name: "AllowSampleCollection"
Value: 0 or 1
```

Где:<br>
Тип ключа — это D-WORD. <br>
Возможные значения:
- 0 — не разрешает общий доступ к примеру с этого устройства
- 1 — позволяет обмениваться всеми типами файлов с этого устройства

Значение по умолчанию в случае, если ключ реестра не существует, составляет 1.

Дополнительные сведения о соблюдении System Center Configuration Manager см. в введении параметров соответствия требованиям [в System Center R2 Configuration Manager 2012.](/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\))


## <a name="other-recommended-configuration-settings"></a>Другие рекомендуемые параметры конфигурации
После включения устройств в службу важно воспользоваться включенными возможностями защиты от угроз, включив их в следующие рекомендуемые параметры конфигурации.

### <a name="device-collection-configuration"></a>Конфигурация коллекции устройств
Если используется диспетчер конфигурации конечной точки версии 2002 или более поздней версии, можно расширить развертывание, включив серверы или клиенты на более позднем уровне.


### <a name="next-generation-protection-configuration"></a>Конфигурация защиты следующего поколения
Рекомендуется использовать следующие параметры конфигурации:

**Сканирование** <br>
- Сканирование съемных устройств хранения, таких как USB-накопители: Да

**Защита в режиме реального времени** <br>
- Включить поведенческий мониторинг: Да
- Включить защиту от потенциально нежелательных приложений при загрузке и до установки: Да

**Служба облачной защиты**
- Тип членства в службе облачной защиты: расширенный членский состав

**Уменьшение поверхности атаки** Настройка всех доступных правил для аудита.

>[!NOTE]
> Блокировка этих действий может прервать законные бизнес-процессы. Оптимальный подход — настройка всех параметров аудита, определение безопасных для включения и включение параметров конечных точек, не обнаруживающих ложных срабатывающих объектов.


**Защита сети** <br>
Перед включением сетевой защиты в режиме аудита или блокировки убедитесь, что вы установили обновление платформы антивирусных программ, которое можно получить на странице [поддержки.](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing)


**Контролируемый доступ к папкам**<br>
Включить функцию в режиме аудита не менее 30 дней. После этого периода просмотрите обнаружения и создайте список приложений, которые могут записываться в защищенные каталоги.

Дополнительные сведения см. в [дополнительных сведениях о доступе к управляемым папкам.](evaluate-controlled-folder-access.md)


## <a name="offboard-devices-using-configuration-manager"></a>Offboard devices using Configuration Manager

По соображениям безопасности срок действия пакета, используемой для устройств Offboard, истекает через 30 дней после даты его загрузки. Просроченные пакеты offboarding, отправленные на устройство, будут отклонены. При загрузке пакета offboarding вы будете уведомлены о дате истечения срока действия пакетов и он также будет включен в имя пакета.

> [!NOTE]
> На одном устройстве одновременно не следует развертывать политики бортового и оффбординга, в противном случае это приведет к непредсказуемым столкновениям.

### <a name="offboard-devices-using-microsoft-endpoint-manager-current-branch"></a>Offboard devices using Microsoft Endpoint Manager current branch

Если вы используете Microsoft Endpoint Manager текущую ветвь, см. в статью Создание файла конфигурации [offboarding.](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file)

### <a name="offboard-devices-using-system-center-2012-r2-configuration-manager"></a>Offboard devices using System Center R2 Configuration Manager 2012

1. Получите пакет offboarding из [Центр безопасности в Microsoft Defender:](https://securitycenter.windows.com/)

    1. В области навигации выберите **Параметры**  >   **Offboarding**.

    1. Выберите Windows 10 в качестве операционной системы.

    1. В поле **Метод развертывания** выберите System Center Configuration Manager **2012/2012 R2/1511/1602**.
    
    1. Выберите **пакет Загрузка** и сохраните .zip файл.

2. Извлечение содержимого файла .zip в общее расположение только для чтения, к которому могут получить доступ сетевые администраторы, которые будут развертывать пакет. У вас должен быть *файл с именем WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*.

3. Развертывание пакета, следуя шагам в статье [Packages and Programs System Center R2 Configuration Manager 2012.](/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\))

    а. Выберите предопределяемую коллекцию устройств для развертывания пакета.

> [!IMPORTANT]
> Отключение приводит к тому, что устройство перестает отправлять данные датчиков на портал, но данные с устройства, включая ссылки на все оповещения, которые у него были, будут храниться до 6 месяцев.


## <a name="monitor-device-configuration"></a>Мониторинг конфигурации устройства

Если вы используете текущую Microsoft Endpoint Manager, используйте встроенную панель мониторинга Defender для конечной точки в консоли Configuration Manager. Дополнительные сведения см. в [дополнительных сведениях Defender for Endpoint - Monitor.](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor)

Если вы используете System Center 2012 R2 Configuration Manager, мониторинг состоит из двух частей:

1. Подтверждение правильного развертывания пакета конфигурации и успешного запуска (или успешного запуска) на устройствах в сети.

2. Проверка того, что устройства соответствуют службе Defender для конечной точки (это гарантирует, что устройство может завершить процесс бортовой обработки и может продолжать сообщать данные в службу).

### <a name="confirm-the-configuration-package-has-been-correctly-deployed"></a>Подтверждение правильного развертывания пакета конфигурации

1. В консоли Configuration Manager щелкните **Мониторинг** в нижней части панели навигации.

2. Выберите **Обзор** и **развертывание.**

3. Выберите развертывание с именем пакета.

4. Просмотрите индикаторы состояния в **статье Статистика завершения** и состояние **контента.**

    При сбойных развертываниях (устройствах с ошибками, невыполнением требований или сбойных состояниях) может потребоваться устранение неполадок устройств. Дополнительные сведения см. в выпуске [Устранение неполадок в microsoft Defender для конечной](troubleshoot-onboarding.md)точки.

    ![Диспетчер конфигурации, показывающий успешное развертывание без ошибок](images/sccm-deployment.png)

### <a name="check-that-the-devices-are-compliant-with-the-microsoft-defender-for-endpoint-service"></a>Убедитесь, что устройства соответствуют службе Microsoft Defender для конечных точек.

Вы можете установить правило соответствия требованиям для элемента конфигурации System Center 2012 R2 Configuration Manager для мониторинга развертывания.

Это правило должно быть *элементом* конфигурации правил соответствия требованиям, который отслеживает значение ключа реестра на целевых устройствах.

Мониторинг следующей записи ключа реестра:

```console
Path: "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status"
Name: "OnboardingState"
Value: "1"
```

Дополнительные сведения см. в введении параметров соответствия требованиям [в System Center R2 Configuration Manager 2012.](/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\))

## <a name="related-topics"></a>Статьи по теме
- [Onboard Windows 10 с помощью групповой политики](configure-endpoints-gp.md)
- [Подключение устройств Windows 10 с помощью средств управления мобильными устройствами](configure-endpoints-mdm.md)
- [Подключение устройств Windows 10 с помощью локального сценария](configure-endpoints-script.md)
- [Подключение временных устройств инфраструктуры виртуальных рабочих столов (VDI)](configure-endpoints-vdi.md)
- [Запустите тест обнаружения на недавно созданном устройстве Microsoft Defender для конечных точек](run-detection-test.md)
- [Устранение неполадок в Microsoft Defender для проблем с бортовой точкой конечной точки](troubleshoot-onboarding.md)
