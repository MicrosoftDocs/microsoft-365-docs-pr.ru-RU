---
title: Начало работы с расширением соответствия требованиям Майкрософт
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Подготовьтесь к использованию расширения соответствия требованиям Майкрософт и разверните его.
ms.openlocfilehash: a76a4b1ab5b92a1e237663f65002b99d792b13bb
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288375"
---
# <a name="get-started-with-microsoft-compliance-extension"></a>Начало работы с расширением соответствия требованиям Майкрософт

Используйте эти процедуры для развертывания расширения соответствия требованиям Майкрософт.

## <a name="before-you-begin"></a>Подготовка

Чтобы использовать расширение соответствия требованиям Майкрософт, устройство должно быть подключено к защите от потери данных в конечной точке. Просмотрите эти статьи, если вы незнакомы с защитой от потери данных (DLP) или DLP в конечной точке

- [Сведения о расширении соответствия требованиям Майкрософт](dlp-chrome-learn-about.md)
- [Сведения о защите от потери данных](dlp-learn-about-dlp.md)
- [Создание, тестирование и настройка политики защиты от потери данных](create-test-tune-dlp-policy.md)
- [Создание политики защиты от потери данных на основе шаблона](create-a-dlp-policy-from-a-template.md)
- [Сведения о защите от потери данных в конечной точке](endpoint-dlp-learn-about.md)
- [Начало работы с функцией защиты от потери данных в конечной точке](endpoint-dlp-getting-started.md)
- [Средства и методы подключения для устройств с Windows 10](dlp-configure-endpoints.md)
- [Настройка параметров прокси-сервера устройства и подключения к Интернету для защиты от потери данных в конечной точке](endpoint-dlp-configure-proxy.md)
- [Использование защиты от потери данных в конечной точке](endpoint-dlp-using.md)

### <a name="skusubscriptions-licensing"></a>Лицензирование SKU и подписок

Перед началом работы подтвердите [подписку Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) и любые дополнительные надстройки. Чтобы использовать функции защиты от потери данных в конечной точке, необходимо иметь одну из этих подписок или надстроек.

- Microsoft 365 E5
- Microsoft 365 A5 (для учебных заведений)
- Соответствие требованиям Microsoft 365 E5
- Соответствие требованиям Microsoft 365 A5
- Защита информации и управление данными в Microsoft 365 E5
- Защита информации и управление данными в Microsoft 365 A5

Подробные инструкции по лицензированию см. в статье [Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).

- У вашей организации должна быть лицензия на защиту от потери данных в конечной точке.
- Ваши устройства должны работать под управлением 64-разрядной версии Windows 10 сборки 1809 или более поздней.
- На устройстве должен быть установлен клиент защиты от вредоносных программ версии 4.18.2101.9 или более поздней. Проверьте свою текущую версию, открыв приложение **Безопасность Windows**, щелкнув значок **Параметры** и выбрав **О программе**.


### <a name="permissions"></a>Разрешения

Данные из службы защиты от потери данных в конечной точке доступны в [Обозревателе действий](data-classification-activity-explorer.md). Существует семь ролей, которые предоставляют разрешения обозревателю действий. Учетная запись, которую вы используете для доступа к данным, должна входить в любую из этих ролей.

- Глобальный администратор
- Администратор соответствия требованиям
- Администратор безопасности
- Администратор данных соответствия требованиям
- Глобальный читатель
- Читатель сведений о безопасности
- Читатель отчетов

### <a name="overall-installation-workflow"></a>Общий рабочий процесс установки

Развертывание расширения соответствия требованиям Майкрософт — это многоэтапный процесс. Вы можете выбрать установку на одном компьютере одновременно или использовать Microsoft Endpoint Manager или групповую политику для развертывания в пределах организации.

1. [Подготовка устройств](#prepare-your-devices).
2. [Базовая настройка Selfhost на одном компьютере](#basic-setup-single-machine-selfhost)
3. [Развертывание с помощью Microsoft Endpoint Manager](#deploy-using-microsoft-endpoint-manager)
4. [Развертывание с помощью групповой политики](#deploy-using-group-policy)
5. [Тестирование расширения](#test-the-extension)
6. [Просмотр оповещений защиты от потери данных Chrome с помощью панели управления оповещениями](#use-the-alerts-management-dashboard-to-viewing-chrome-dlp-alerts)
7. [Просмотр данных защиты от потери данных Chrome с помощью обозревателя действий](#viewing-chrome-dlp-data-in-activity-explorer)

### <a name="prepare-infrastructure"></a>Подготовка инфраструктуры

Если вы разворачиваете расширение соответствия требованиям Майкрософт на всех отслеживаемых устройствах с Windows 10, удалите Google Chrome из списка запрещенных приложений или запрещенных браузеров. Дополнительные сведения см. в разделе [Запрещенные браузеры](endpoint-dlp-using.md#unallowed-browsers). Если вы разворачиваете его только на нескольких устройствах, вы можете оставить Chrome в списке запрещенных браузеров или запрещенных приложений. Расширение соответствия требованиям Майкрософт обойдет ограничения обоих списков для компьютеров, на которых оно устанавливается.

### <a name="prepare-your-devices"></a>Подготовка устройств

1. Используйте процедуры из следующих статей, чтобы подключить свои устройства.
    1. [Начало работы с функцией защиты от потери данных в конечной точке](endpoint-dlp-getting-started.md)
    1. [Средства и методы подключения для устройств с Windows 10](dlp-configure-endpoints.md)
    1. [Настройка параметров прокси-сервера устройства и подключения к Интернету для защиты от потери данных в конечной точке](endpoint-dlp-configure-proxy.md)

### <a name="basic-setup-single-machine-selfhost"></a>Базовая настройка Selfhost на одном компьютере

Это рекомендуемый метод.

1. Войдите на компьютер с Windows 10, где нужно установить расширение соответствия требованиям Майкрософт, и запустите этот сценарий PowerShell в качестве администратора.

   ```powershell
   Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
   ```

2. Перейдите на страницу [Расширение соответствия требованиям Майкрософт — интернет-магазин Chrome (google.com)](https://chrome.google.com/webstore/detail/microsoft-compliance-exte/echcggldkblhodogklpincgchnpgcdco).

3. Установите расширение с помощью инструкций на странице интернет-магазина Chrome.

### <a name="deploy-using-microsoft-endpoint-manager"></a>Развертывание с помощью Microsoft Endpoint Manager

Используйте этот метод установки для развертывания в пределах организации

##### <a name="enabling-required-registry-key-via-microsoft-endpoint-manager"></a>Включение обязательного ключа реестра с помощью Microsoft Endpoint Manager

1. Создайте сценарий PowerShell со следующим содержимым:

    ```powershell
    Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
    ```

2. Войдите в [Центр администрирования Microsoft Endpoint Manager](https://endpoint.microsoft.com).

3. Выберите **Устройства** > **Сценарии** и нажмите **Добавить**.

4. Перейдите к расположению сценария, созданного при запросе.

5. Выберите следующие параметры:
    1. Запускать сценарий по учетным данным входа: ДА
    1. Принудительно проверить подпись сценария: НЕТ
    1. Запуск сценария в 64-разрядном узле PowerShell: ДА

6. Выберите подходящие группы устройств и примените политику.

#### <a name="microsoft-endpoint-manager-force-install-steps"></a>Этапы принудительной установки Microsoft Endpoint Manager

Перед добавлением расширения соответствия требованиям Майкрософт в список принудительно устанавливаемых расширений важно внедрить ADMX Chrome. Этапы этого процесса в Microsoft Endpoint Manager описаны корпорацией Google: [Как управлять браузером Chrome с помощью Microsoft Intune — корпоративная справка Google Chrome](https://support.google.com/chrome/a/answer/9102677?hl=en#zippy=%2Cstep-ingest-the-chrome-admx-file-into-intune).

 После внедрения ADMX можно с помощью инструкций ниже создать профиль конфигурации для этого расширения.

1. Войдите в Центр администрирования Microsoft Endpoint Manager (https://endpoint.microsoft.com).

2. Перейдите к профилям конфигурации.

3. Нажмите **Создать профиль**.

4. Выберите **Windows 10** в качестве платформы.

5. Выберите **Пользовательский** в качестве типа профиля.

6. Выберите вкладку **Параметры**.

7. Нажмите **Добавить**.

8. Введите следующие сведения о политике.

    OMA-URI: `./Device/Vendor/MSFT/Policy/Config/Chrome~Policy~googlechrome~Extensions/ExtensionInstallForcelist`<br/>
    Тип данных: `String`<br/>
    Значение: `<enabled/><data id="ExtensionInstallForcelistDesc" value="1&#xF000; echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx"/>`

9. Нажмите "Создать".

### <a name="deploy-using-group-policy"></a>Развертывание с помощью групповой политики

Если вы не хотите использовать Microsoft Endpoint Manager, можно применить групповые политики для развертывания расширения соответствия требованиям Майкрософт в организации

1. Ваши устройства должны быть управляемыми с помощью групповой политики, и необходимо импортировать все ADMX Chrome в центральное хранилище групповой политики. Дополнительные сведения см. в статье [Как создать центральное хранилище для административных шаблонов групповой политики в Windows и управлять им](/troubleshoot/windows-client/group-policy/create-and-manage-central-store).

2. Создайте сценарий PowerShell с помощью команды PowerShell:

    ```powershell
    Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
    ```

3. Откройте **консоль управления групповой политикой** и перейдите в свое подразделение.

4. Щелкните правой кнопкой мыши и выберите **Создать GPO в этом домене и связать его**. При запросе назначьте понятное имя этому объекту групповой политики (GPO) и завершите его создание.

5. Щелкните правой кнопкой мыши GPO и нажмите **Изменить**.

6. Перейдите в раздел **Конфигурация компьютера** > **Настройки** > **Настройки панели управления** > **Запланированные задачи**.

7. Создайте новую задачу для немедленного запуска, щелкнув правой кнопкой мыши и выбрав **Создать** > **Немедленная задача (Windows 7 и выше)**.

8. Добавьте имя и описание задачи.

9. Выберите соответствующую учетную запись для запуска немедленной задачи, например NT Authority.

10. Выберите **Выполнить с наивысшими правами**.

11. Настройте политику для Windows 10.

12. На вкладке **Действия** выберите действие **Запуск программы**.

13. Введите путь к программе или сценарию, созданному на шаге 1.

14. Нажмите **Применить**.

#### <a name="adding-the-chrome-extension-to-the-forceinstall-list"></a>Добавление расширения Chrome в список ForceInstall

1. В редакторе управления групповыми политиками перейдите к своему подразделению.

2. Разверните следующий путь: **Конфигурация компьютера или пользователя** > **Политики** > **Административные шаблоны** > **Классические административные шаблоны** > **Google** > **Google Chrome** > **Расширения**. Этот путь может отличаться в зависимости от вашей конфигурации.

3. Выберите **Настроить список принудительно устанавливаемых расширений**.

4. Щелкните правой кнопкой мыши и выберите **Изменить**.

5. Щелкните **Включено**.

6. Выберите **Показать**.

7. В разделе **Значение** добавьте следующую запись: `echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx`

8. Нажмите **ОК** и **Применить**.

### <a name="test-the-extension"></a>Тестирование расширения

#### <a name="upload-to-cloud-service-or-access-by-unallowed-browsers-cloud-egress"></a>Отправка в облачную службу или доступ путем выхода в облако запрещенными браузерами

1. Создайте или получите конфиденциальный элемент и попробуйте отправить файл в один из запрещенных доменов службы вашей организации. Конфиденциальные данные должны соответствовать одному из наших встроенных [типов конфиденциальной информации](sensitive-information-type-entity-definitions.md) или одному из типов конфиденциальной информации вашей организации. На тестируемом устройстве должно появиться всплывающее уведомление защиты от потери данных о том, что это действие запрещено при открытом файле.

#### <a name="testing-other-dlp-scenarios-in-chrome"></a>Тестирование других сценариев защиты от потери данных в Chrome

Теперь, когда вы удалили Chrome из списка запрещенных браузеров или приложений, вы можете протестировать сценарии, указанные ниже, чтобы подтвердить, что действие соответствует требованиям вашей организации.

- Копирование данных из конфиденциального элемента в другой документ с помощью буфера обмена
  - Для проверки откройте в браузере Chrome файл, защищенный от копирования в буфер обмена, и попытайтесь скопировать данные из файла.
  - Ожидаемый результат: всплывающее уведомление защиты от потери данных о том, что это действие запрещено при открытом файле.
- Печать документа
  - Для проверки откройте в браузере Chrome файл, защищенный от печати, и попытайтесь распечатать файл.
  - Ожидаемый результат: всплывающее уведомление защиты от потери данных о том, что это действие запрещено при открытом файле.
- Копирование на съемный USB-носитель
  - Для проверки попробуйте сохранить файл на съемном носителе.
  - Ожидаемый результат: всплывающее уведомление защиты от потери данных о том, что это действие запрещено при открытом файле.
- Копирование в сетевую папку
  - Для проверки попробуйте сохранить файл в сетевой папке.
  - Ожидаемый результат: всплывающее уведомление защиты от потери данных о том, что это действие запрещено при открытом файле.

### <a name="use-the-alerts-management-dashboard-to-viewing-chrome-dlp-alerts"></a>Просмотр оповещений защиты от потери данных Chrome с помощью панели управления оповещениями

1. Откройте страницу **Защита от потери данных** в [Центре соответствия требованиям Microsoft 365](https://compliance.microsoft.com) и выберите **Оповещения**.

2. Используйте процедуры из статьи [Настройка и просмотр оповещений для политик защиты от потери данных](dlp-configure-view-alerts-policies.md), чтобы просмотреть оповещения для своих политик защиты от потери данных в конечной точке.

### <a name="viewing-chrome-dlp-data-in-activity-explorer"></a>Просмотр данных защиты от потери данных Chrome с помощью обозревателя действий

1. Откройте страницу [Классификация данных](https://compliance.microsoft.com/dataclassification?viewid=overview) для своего домена в Центре соответствия требованиям Microsoft 365 и выберите **Обозреватель действий**.

2. Выполните действия, описанные в статье [Начало работы с обозревателем действий](data-classification-activity-explorer.md), чтобы получить доступ к данным и отфильтровать их на своих устройствах конечной точки.

   > [!div class="mx-imgBorder"]
   > ![фильтр обозревателя действий для устройств конечных точек](../media/endpoint-dlp-4-getting-started-activity-explorer.png)

### <a name="known-issues-and-limitations"></a>Известные проблемы и ограничения

1. Не поддерживается блокировка переопределения для выхода в облако.
2. Режим инкогнито не поддерживается и должен быть отключен.

## <a name="next-steps"></a>Следующие шаги

После того, как вы подключили устройства, вы можете просмотреть данные об активности в обозревателе действий и перейти к этапу создания политик защиты от потери данных для конфиденциальных элементов.

- [Использование Защиты от потери данных в конечной точке](endpoint-dlp-using.md)

## <a name="see-also"></a>См. также

- [Сведения о защите от потери данных в конечной точке](endpoint-dlp-learn-about.md)
- [Использование защиты от потери данных в конечной точке](endpoint-dlp-using.md)
- [Сведения о защите от потери данных](dlp-learn-about-dlp.md)
- [Создание, тестирование и настройка политики защиты от потери данных](create-test-tune-dlp-policy.md)
- [Начало работы с обозревателем действий](data-classification-activity-explorer.md)
- [Microsoft Defender для конечной точки](/windows/security/threat-protection/)
- [Средства и методы подключения для компьютеров с Windows 10](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [Подписка на Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [Устройства, подключенные к Azure AD](/azure/active-directory/devices/concept-azure-ad-join)
- [Загрузка нового браузера Microsoft Edge на основе Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
