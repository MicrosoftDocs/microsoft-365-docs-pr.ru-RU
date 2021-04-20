---
title: Подключение устройств Windows 10 с помощью Configuration Manager
description: Используйте Диспетчер конфигурации для развертывания пакета конфигурации на устройствах, чтобы они были размещены в службе.
keywords: на борту устройств с помощью sccm, управления устройствами, настройки устройств ATP Windows, настройки Microsoft Defender для устройств конечных точек
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
ms.openlocfilehash: 3550bec28945ab888efbe2ca46f12ca7f96aab4a
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2021
ms.locfileid: "51892867"
---
# <a name="onboard-windows-10-devices-using-configuration-manager"></a>Подключение устройств Windows 10 с помощью Configuration Manager

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**

- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Текущий филиал Microsoft Endpoint Configuration Manager
- Диспетчер конфигураций System Center 2012 R2

>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointssccm-abovefoldlink)

## <a name="supported-client-operating-systems"></a>Поддерживаемые клиентские операционные системы

На основе версии диспетчера конфигурации можно использовать следующие клиентские операционные системы:

#### <a name="configuration-manager-version-1910-and-prior"></a>Configuration Manager version 1910 and prior

- Клиенты компьютеров с Windows 10 

#### <a name="configuration-manager-version-2002-and-later"></a>Configuration Manager version 2002 and later

Начиная с версии Configuration Manager 2002, вы можете использовать следующие операционные системы:

- Windows 8.1
- Windows 10
- Windows Server 2012 R2
- Windows Server 2016
- Windows Server 2016, версия 1803 или более поздней версии
- Windows Server 2019

>[!NOTE]
>Дополнительные сведения о том, как на борту Windows Server 2012 R2, Windows Server 2016 и Windows Server 2019 см. в таблице [Onboard Windows servers.](configure-server-endpoints.md)



### <a name="onboard-devices-using-system-center-configuration-manager"></a>Onboard devices using System Center Configuration Manager


[![Изображение PDF, показывающая различные пути развертывания](images/onboard-config-mgr.png)](images/onboard-config-mgr.png#lightbox)


Ознакомьтесь с [PDF или](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  [Visio,](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) чтобы увидеть различные пути развертывания Microsoft Defender для конечной точки. 



1. Откройте пакет конфигурации Configuration Manager .zip file *(WindowsDefenderATPOnboardingPackage.zip), который* вы скачали из мастера бортового обслуживания. Вы также можете получить пакет из [Центра безопасности Защитника Майкрософт:](https://securitycenter.windows.com/)

    1. В области навигации выберите **параметры**  >  **onboarding**.
    
    1. Выберите Windows 10 в качестве операционной системы.

    1. В поле **Метод развертывания** выберите System Center Configuration **Manager 2012/2012 R2/1511/1602**.
    
    1. Выберите **пакет Загрузка** и сохраните файл .zip.

2. Извлеките содержимое файла .zip в общее расположение только для чтения, к которому можно получить доступ администраторов сети, которые будут развертывать пакет. У вас должен быть файл с именем *WindowsDefenderATPOnboardingScript.cmd.*

3. Развертывание пакета, следуя шагам в статье [Packages and Programs System Center 2012 R2 Configuration Manager.](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\))

    а. Выберите предопределяемую коллекцию устройств для развертывания пакета.

> [!NOTE]
> Защитник для конечной точки не поддерживает вовне на этапе [Out-Of-Box Experience (OOBE).](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) Убедитесь, что пользователи заполняют OOBE после установки Или обновления Windows.

>[!TIP]
> После работы на устройстве можно выполнить тест обнаружения, чтобы убедиться, что устройство правильно вошел в службу. Дополнительные сведения см. в таблице [Run a detection test on a newly onboarded Defender for Endpoint device.](run-detection-test.md)
>
> Обратите внимание, что в приложении Configuration Manager можно создать правило обнаружения, чтобы постоянно проверять, было ли устройство на борту. Приложение — это другой тип объекта, чем пакет и программа.
> Если устройство еще не установлено (в связи с завершением OOBE или по какой-либо другой причине), диспетчер конфигурации будет повторно фиксироваться на борту устройства до тех пор, пока правило не обнаружит изменение состояния.
> 
> Это поведение может быть выполнено путем проверки правила обнаружения, если значение реестра "OnboardingState" (типа REG_DWORD) = 1.
> Это значение реестра расположено в статье "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status".
Дополнительные сведения см. в дополнительных сведениях [в настройках методов обнаружения в System Center 2012 R2 Configuration Manager.](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682159\(v=technet.10\)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type)

### <a name="configure-sample-collection-settings"></a>Настройка параметров коллекции образцов

Для каждого устройства можно установить значение конфигурации, чтобы определить, можно ли собирать образцы с устройства при запросе через Центр безопасности Защитника Майкрософт для отправки файла для глубокого анализа.

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

Дополнительные сведения о соответствии требованиям диспетчера конфигурации центра системы см. в введении параметров соответствия требованиям [в System Center 2012 R2 Configuration Manager.](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\))


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

Если вы используете текущую ветвь Microsoft Endpoint Manager, см. в таблице Создание файла конфигурации [offboarding.](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file)

### <a name="offboard-devices-using-system-center-2012-r2-configuration-manager"></a>Offboard devices using System Center 2012 R2 Configuration Manager

1. Получите пакет offboarding из [Центра безопасности Защитника Майкрософт:](https://securitycenter.windows.com/)

    1. В области навигации выберите **Параметры**  >   **Offboarding**.

    1. Выберите Windows 10 в качестве операционной системы.

    1. В поле **Метод развертывания** выберите System Center Configuration **Manager 2012/2012 R2/1511/1602**.
    
    1. Выберите **пакет Загрузка** и сохраните файл .zip.

2. Извлеките содержимое файла .zip в общее расположение только для чтения, к которому можно получить доступ администраторов сети, которые будут развертывать пакет. У вас должен быть *файл с именем WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*.

3. Развертывание пакета, следуя шагам в статье [Packages and Programs System Center 2012 R2 Configuration Manager.](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\))

    а. Выберите предопределяемую коллекцию устройств для развертывания пакета.

> [!IMPORTANT]
> Отключение приводит к тому, что устройство перестает отправлять данные датчиков на портал, но данные с устройства, включая ссылки на все оповещения, которые у него были, будут храниться до 6 месяцев.


## <a name="monitor-device-configuration"></a>Мониторинг конфигурации устройства

Если вы используете текущую ветвь Microsoft Endpoint Manager, используйте встроенную панель мониторинга Defender для конечной точки в консоли Configuration Manager. Дополнительные сведения см. в [дополнительных сведениях Defender for Endpoint - Monitor.](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor)

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

Вы можете установить правило соответствия требованиям для элемента конфигурации в System Center 2012 R2 Configuration Manager для мониторинга развертывания.

Это правило должно быть *элементом* конфигурации правил соответствия требованиям, который отслеживает значение ключа реестра на целевых устройствах.

Мониторинг следующей записи ключа реестра:

```console
Path: "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status"
Name: "OnboardingState"
Value: "1"
```

Дополнительные сведения см. в введении параметров соответствия требованиям [в System Center 2012 R2 Configuration Manager.](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\))

## <a name="related-topics"></a>Похожие темы
- [На борту устройств Windows 10 с использованием групповой политики](configure-endpoints-gp.md)
- [Подключение устройств Windows 10 с помощью средств управления мобильными устройствами](configure-endpoints-mdm.md)
- [Подключение устройств Windows 10 с помощью локального сценария](configure-endpoints-script.md)
- [Подключение временных устройств инфраструктуры виртуальных рабочих столов (VDI)](configure-endpoints-vdi.md)
- [Запустите тест обнаружения на недавно созданном устройстве Microsoft Defender для конечных точек](run-detection-test.md)
- [Устранение неполадок в Microsoft Defender для проблем с бортовой точкой конечной точки](troubleshoot-onboarding.md)
