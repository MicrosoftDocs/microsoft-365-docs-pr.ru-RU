---
title: Подключение устройств Windows 10 с помощью Configuration Manager
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Используйте Configuration Manager для развертывания пакета конфигурации на устройствах, чтобы они были вовсю в службе.
ms.openlocfilehash: ea1b0cba10dc3e7120192e0c0ee87e2e354f1cc2
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769475"
---
# <a name="onboard-windows-10-devices-using-configuration-manager"></a>Подключение устройств Windows 10 с помощью Configuration Manager

**Область применения:**

- [Предотвращение потери данных конечной точки Microsoft 365 (DLP)](/microsoft-365/compliance/endpoint-dlp-learn-about)
- Диспетчер конфигураций System Center 2012 R2

### <a name="onboard-devices-using-system-center-configuration-manager"></a>Ветвь устройств с помощью System Center Configuration Manager

1. Откройте ZIP-файл пакета конфигурации ** Configuration Manager (DeviceComplianceOnboardingPackage.zip), который вы скачали из мастера подбора службы. Вы также можете получить пакет из [Центра соответствия требованиям Майкрософт.](https://compliance.microsoft.com/)

2. В области навигации выберите **"Параметры** для входящего  >  **устройства".**  >  

3. В поле **"Метод развертывания"** выберите **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602.**
 
4. Выберите **пакет загрузки** и сохраните ZIP-файл.

5. Извлеките содержимое ZIP-файла в общую папку, доступную только для чтения, доступную администраторам сети, которые будут развертывать пакет. У вас должен быть файл *DeviceComplianceOnboardingScript.cmd.*

6. Развернем пакет, следуя шагам в статье "Пакеты и [программы System Center 2012 R2 Configuration Manager".](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\))

7. Выберите предопределную коллекцию устройств для развертывания пакета.

> [!NOTE]
> Microsoft 365 Endpoint data loss prevention doesn't support onboarding during the [Out-of-Box Experience (OOBE)](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) phase. Убедитесь, что после установки или обновления Windows пользователи завершат OOBE.

>[!TIP]
> После вбора устройства можно выполнить тест обнаружения, чтобы убедиться, что устройство правильно вложено в службу. Дополнительные сведения см. в тесте обнаружения на новом устройстве [ATP в Microsoft Defender.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
>
> Обратите внимание, что можно создать правило обнаружения в приложении Configuration Manager, чтобы постоянно проверять, было ли устройство в сети. Приложение — это объект другого типа, чем пакет и программа.
> Если устройство еще не установлено (из-за ожидающих завершения OOBE или по какой-либо другой причине), Configuration Manager будет повторно фиксировать устройство, пока правило не обнаружит изменение состояния.
> 
> Для этого можно создать проверку правила обнаружения, если значение реестра "OnboardingState" (типа REG_DWORD) = 1.
> Это значение реестра находится в "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status".
Дополнительные сведения [см. в подстроке Configure Detection Methods в System Center 2012 R2 Configuration Manager.](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682159\(v=technet.10\)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type)

### <a name="configure-sample-collection-settings"></a>Настройка параметров образца коллекции

Для каждого устройства можно установить значение конфигурации, чтобы определить, можно ли собирать образцы с устройства при отправке запроса через Центр безопасности Microsoft Defender на отправку файла для глубокого анализа.

>[!NOTE]
>Эти параметры конфигурации обычно настраиваются с помощью Configuration Manager. 

Вы можете настроить правило соответствия для элемента конфигурации в Configuration Manager, чтобы изменить пример параметра share на устройстве.

Это правило должно  быть исправлением элемента конфигурации правила соответствия, который задает значение ключа реестра на целевых устройствах, чтобы убедиться, что они жалуются.

Конфигурация заданная с помощью следующей записи реестра:

```
Path: “HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection”
Name: "AllowSampleCollection"
Value: 0 or 1
```
Где:<br>
Тип ключа — D-WORD. <br>
Возможные значения:
- 0 — не разрешает общий доступ к примерам с этого устройства
- 1 — разрешает общий доступ к файлам всех типов с этого устройства

Значение по умолчанию, если не существует ключа реестра, — 1.

Дополнительные сведения о соответствии требованиям System Center Configuration Manager см. в введении параметров соответствия [в System Center 2012 R2 Configuration Manager.](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\))


## <a name="other-recommended-configuration-settings"></a>Другие рекомендуемые параметры конфигурации
После включения устройств в службу важно воспользоваться преимуществами включенных возможностей защиты от угроз, включив для них следующие рекомендуемые параметры конфигурации.

### <a name="device-collection-configuration"></a>Конфигурация коллекции устройств
Если вы используете Endpoint Configuration Manager версии 2002 или более поздней, вы можете расширить развертывание, включив серверы или клиенты более поздней версии.


### <a name="next-generation-protection-configuration"></a>Конфигурация защиты нового поколения

Рекомендуется использовать следующие параметры конфигурации:

**Сканирование**

- Проверка съемных устройств хранения, таких как USB-накопители: да

**Защита в режиме реального времени**

- Включить мониторинг поведения: да
- Включить защиту от потенциально нежелательных приложений при загрузке и перед установкой: да

**Облачная служба защиты**

- Тип членства в облачной службе защиты: расширенные членство

**Уменьшение поверхности атаки** Настройте все доступные правила для аудита.

>[!NOTE]
> Блокировка этих действий может прервать законные бизнес-процессы. Лучший способ — установить все для аудита, определить, какие из них безопасно включить, а затем включить эти параметры на конечных точках, которые не имеют обнаружений ложных срабатывающих результатов.

**Защита сети**

Перед включением защиты сети в режиме аудита или блокировки убедитесь, что установлено обновление антивластиальной платформы, которое можно получить на странице [поддержки.](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing)


**Управляемый доступ к папок**

Включить функцию в режиме аудита не менее 30 дней. После этого просмотрите обнаружения и создайте список приложений, которые могут записывать в защищенные каталоги.

Дополнительные сведения см. в под [управлением оценки доступа к папок.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/evaluate-controlled-folder-access)


## <a name="offboard-devices-using-configuration-manager"></a>Отключение устройств с помощью Configuration Manager

Из соображений безопасности срок действия пакета, используемой для отключенных устройств, истекает через 30 дней после даты его загрузки. Пакеты отключения с истекшим сроком действия, отправленные на устройство, будут отклонены. При скачии пакета отключения вы будете уведомлены о дате окончания срока действия пакетов, и он также будет включен в имя пакета.

> [!NOTE]
> Политики в отношении подключения и отключения не должны развертываться одновременно на одном устройстве, в противном случае это приведет к непредсказуемым столкновениям.

### <a name="offboard-devices-using-microsoft-endpoint-configuration-manager-current-branch"></a>Отключение устройств с помощью текущей ветви Microsoft Endpoint Configuration Manager

Если вы используете текущую ветвь Microsoft Endpoint Configuration Manager, см. статью "Создание файла конфигурации [отключения".](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file)

### <a name="offboard-devices-using-system-center-2012-r2-configuration-manager"></a>Отключение устройств с System Center 2012 R2 Configuration Manager

1. Получите пакет отключения из Центра [соответствия требованиям Майкрософт:](https://compliance.microsoft.com/)

2. В области навигации выберите **параметры** отключения устройства.  >    >  

3. Выберите Windows 10 в качестве операционной системы.

4. В поле **"Метод развертывания"** выберите **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602.**
    
5. Выберите **пакет загрузки** и сохраните ZIP-файл.

6. Извлеките содержимое ZIP-файла в общую папку, доступную только для чтения, доступную администраторам сети, которые будут развертывать пакет. У вас должен быть файл *с именем DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd.*

7. Развернем пакет, следуя шагам в статье "Пакеты и [программы System Center 2012 R2 Configuration Manager".](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\))

8. Выберите предопределную коллекцию устройств для развертывания пакета.

> [!IMPORTANT]
> Отключение приводит к тому, что устройство перестает отправлять данные датчиков на портал, но данные с устройства, включая ссылки на все оповещения, которые у него есть, будут храниться до 6 месяцев.


## <a name="monitor-device-configuration"></a>Отслеживание конфигурации устройства

Если вы используете текущую ветвь Microsoft Endpoint Configuration Manager, используйте встроенную панель мониторинга ATP в Microsoft Defender в консоли Configuration Manager. Дополнительные сведения см. в [записи "Advanced Threat Protection в Microsoft Defender - Monitor".](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor)

Если вы используете System Center 2012 R2 Configuration Manager, мониторинг состоит из двух частей:

1. Подтверждение правильного развертывания пакета конфигурации и его работы (или успешного запуска) на устройствах в сети.

2. Проверка того, что устройства соответствуют требованиям службы защиты от потери данных конечной точки Microsoft 365 (это гарантирует, что устройство сможет завершить процесс регистрации и продолжит передачу данных в службу).

### <a name="confirm-the-configuration-package-has-been-correctly-deployed"></a>Подтверждение правильного развертывания пакета конфигурации

1. В консоли Configuration Manager щелкните **"Мониторинг"** в нижней части области навигации.

2. Выберите **"Обзор",** а затем **"Развертывания".**

3. Выберите развертывание с именем пакета.

4. Просмотрите индикаторы состояния в **статье "Статистика завершения** и **состояние содержимого".**

    В случае сбойных развертывание (устройств с состоянием "Ошибка", "Требования не выполнены" или "Сбой") может потребоваться устранить неполадки.  Дополнительные сведения см. в подсети "Устранение неполадок с подмавлением [Advanced Threat Protection в Microsoft Defender".](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)

    ![Configuration Manager с отображением успешного развертывания без ошибок](../media/sccm-deployment.png)

### <a name="check-that-the-devices-are-compliant-with-the-microsoft-365-endpoint-data-loss-prevention-service"></a>Убедитесь, что устройства соответствуют требованиям службы защиты от потери данных Конечной точки Microsoft 365

Вы можете настроить правило соответствия для элемента конфигурации в System Center 2012 R2 Configuration Manager для отслеживания развертывания.

> [!NOTE]
> Эта процедура и запись реестра применимы к DLP конечной точки, а также Advanced Threat Protection.

Это правило должно быть *элементом* конфигурации правила соответствия, который отслеживает значение ключа реестра на целевых устройствах.

Отслеживайте следующую запись реестра:
```
Path: “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status”
Name: “OnboardingState”
Value: “1”
```
Дополнительные сведения см. [в введении параметров соответствия требованиям в System Center 2012 R2 Configuration Manager.](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\))

## <a name="related-topics"></a>Связанные статьи
- [Ветвь устройств с Windows 10 с помощью групповой политики](dlp-configure-endpoints-gp.md)
- [Подключение устройств Windows 10 с помощью средств управления мобильными устройствами](dlp-configure-endpoints-mdm.md)
- [Подключение устройств Windows 10 с помощью локального сценария](dlp-configure-endpoints-script.md)
- [Подключение временных устройств инфраструктуры виртуальных рабочих столов (VDI)](dlp-configure-endpoints-vdi.md)
- [Запуск теста обнаружения на новом устройстве ATP в Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Устранение неполадок с подсетями Advanced Threat Protection в Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
