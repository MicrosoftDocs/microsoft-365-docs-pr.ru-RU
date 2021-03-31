---
title: Минимальные требования к Microsoft Defender для конечной точки
description: Понимание требований и требований лицензирования для бортовых устройств к службе
keywords: минимальные требования, лицензирование, таблица сравнения
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 1b203a29083aaa4a1f86abcd7e2c7b24bd63f186
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445748"
---
# <a name="minimum-requirements-for-microsoft-defender-for-endpoint"></a>Минимальные требования к Microsoft Defender для конечной точки

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-minreqs-abovefoldlink)


Для бортовых устройств к службе существует несколько минимальных требований. Узнайте о требованиях к лицензированию, оборудованию и программному обеспечению и других параметрах конфигурации для бортовых устройств службы.

> [!TIP]
> - Узнайте о последних усовершенствованиях в сообществе Защитник для конечной точки: [Защитник для конечной точки.](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced)
> - Defender for Endpoint в недавней оценке MITRE продемонстрировал ведущие в отрасли возможности оптики и обнаружения. Read: [Insights from the MITRE ATT&CK-based assessment](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).

## <a name="licensing-requirements"></a>Требования к лицензированию
Microsoft Defender для конечной точки требует одно из следующих предложений по лицензированию томов Корпорации Майкрософт:

- Windows 10 Корпоративная E5
- Windows 10 для образовательных учреждений A5
- Microsoft 365 E5 (M365 E5), которая включает Windows 10 Enterprise E5
- Microsoft 365 A5 (M365 A5)
- Безопасность Microsoft 365 E5
- Microsoft 365 A5 Security
- Microsoft Defender для конечной точки

> [!NOTE]
> Лицензированные пользователи могут использовать Microsoft Defender для конечной точки на пяти одновременном устройстве.
> Microsoft Defender для конечной точки также доступен для покупки у поставщика облачных решений (CSP).
> Для VMs RDSH не требуется отдельная лицензия Defender для конечной точки.

Microsoft Defender для конечной точки для серверов требует одного из следующих вариантов лицензирования:

- [Центр безопасности Azure с включенной службой Защитник Azure](https://docs.microsoft.com/azure/security-center/security-center-pricing)
- Microsoft Defender для конечной точки для сервера (по одной на закрытый сервер)

> [!NOTE]
> Клиенты могут приобретать лицензии на серверы (по одной на крытую среду операционной системы сервера)для Microsoft Defender для конечной точки для серверов, если у них есть совокупный минимум 50 лицензий для одной или более из следующих лицензий пользователей:
>
> * Microsoft Defender для конечной точки
> * Windows E5/A5
> * Microsoft 365 E5/A5
> * Безопасность Microsoft 365 E5/A5

Подробные сведения о лицензировании см. на [сайте Условия](https://www.microsoft.com/licensing/terms/) продукта и поработать с командой учетных записей, чтобы узнать больше об условиях и условиях.

Дополнительные сведения о массиве функций в выпусках Windows 10 см. в выпуске [Compare Windows 10.](https://www.microsoft.com/windowsforbusiness/compare)

Подробную таблицу сравнения сравнения коммерческих выпусков Windows 10 см. в сопоставлении [PDF.](https://wfbdevicemanagementprod.blob.core.windows.net/windowsforbusiness/Windows10_CommercialEdition_Comparison.pdf)

## <a name="browser-requirements"></a>Требования к браузеру
Доступ к Защитнику для конечной точки делается через браузер, поддерживая следующие браузеры:

- Microsoft Edge
- Google Chrome

> [!NOTE]
> Хотя другие браузеры могут работать, указанные браузеры поддерживаются.


## <a name="hardware-and-software-requirements"></a>Требования к оборудованию и программному обеспечению

### <a name="supported-windows-versions"></a>Поддерживаемые версии Windows
- Windows 7 SP1 Enterprise[(требуется ESU для поддержки.)](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq)
- Windows 7 SP1 Pro[(требуется ESU для поддержки.)](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq)
- Windows 8.1 Корпоративная
- Windows 8.1 Pro
- Windows 10 Корпоративная
- [Windows 10 Enterprise LTSC](https://docs.microsoft.com/windows/whats-new/ltsc/)
- Windows 10 для образовательных учреждений
- Windows 10 Pro
- Windows 10 Pro Education
- Сервер Windows
  - Windows Server 2008 R2 с пакетом обновления 1 (SP1)
  - Windows Server 2012 R2
  - Windows Server 2016
  - Windows Server, версия 1803 или более поздней версии
  - Windows Server 2019
- Виртуальный рабочий стол Windows

Устройства в сети должны запускать одно из этих выпусков.

Требования к оборудованию для Defender для конечной точки на устройствах одинаковы для поддерживаемых выпусков.

> [!NOTE]
> Машины с мобильными версиями Windows (например, Windows CE Windows 10 Mobile) не поддерживаются.
>
> Виртуальные машины под управлением Windows 10 Enterprise 2016 LTSB могут столкнуться с проблемой производительности при работе на платформах виртуализации, не в microsoft.
>
> В виртуальных средах рекомендуется использовать Windows 10 Enterprise LTSC 2019 или более поздней версии.


### <a name="other-supported-operating-systems"></a>Другие поддерживаемые операционные системы
- Android
- iOS
- Linux
- macOS

> [!NOTE]
> Вам потребуется подтвердить дистрибутивы Linux и версии Android, iOS и macOS, совместимые с Defender для конечной точки для работы интеграции.



### <a name="network-and-data-storage-and-configuration-requirements"></a>Требования к сетевому хранению и хранению данных и конфигурации
При первом запуске мастера бортовой связи необходимо выбрать, где хранятся данные Microsoft Defender для конечных точек: в Европейском союзе, Соединенном Королевстве или центрах обработки данных в США.

> [!NOTE]
> - Невозможно изменить расположение хранилища данных после первой установки.
> - Дополнительные сведения о том, где и как Майкрософт хранит данные, просмотрите в [Microsoft Defender для](data-storage-privacy.md) хранения данных конечной точки и конфиденциальности.


### <a name="diagnostic-data-settings"></a>Параметры диагностических данных

> [!NOTE]
> Microsoft Defender для конечной точки не требует определенного уровня диагностики до тех пор, пока он включен.

Убедитесь, что служба диагностических данных включена на всех устройствах организации.
По умолчанию эта служба включена. Это хорошая практика, чтобы проверить, чтобы убедиться, что вы получите данные датчика от них.

**Используйте командную строку, чтобы проверить тип** запуска службы диагностических данных Windows 10:

1. Откройте на устройстве повышенную командную строку:

   1.  В меню **Пуск** введите **cmd**.

   1.  Щелкните правой кнопкой мыши пункт **Командная строка** и выберите команду **Запуск от имени администратора**.

2. Введите следующую команду и нажмите **кнопку Ввод:**

   ```console
   sc qc diagtrack
   ```

   Если служба включена, результат должен выглядеть следующим образом:

   ![Результат команды sc-запроса для diagtrack](images/windefatp-sc-qc-diagtrack.png)


Необходимо настроить службу для автоматического запуска,  если START_TYPE не установлено AUTO_START **.**


**Чтобы автоматически запустить службу диагностических данных Windows 10, используйте командную строку:**

1.  Откройте повышенную командную строку в конечной точке:

    1. В меню **Пуск** введите **cmd**.

    1. Щелкните правой кнопкой мыши пункт **Командная строка** и выберите команду **Запуск от имени администратора**.

2.  Введите следующую команду и нажмите **кнопку Ввод:**

    ```console
    sc config diagtrack start=auto
    ```

3.  Отображается сообщение об успехе. Проверьте изменение, введите следующую команду и нажмите **кнопку Ввод:**

    ```console
    sc qc diagtrack
    ```


#### <a name="internet-connectivity"></a>Подключение к Интернету.
Подключение к Интернету на устройствах требуется напрямую или через прокси.

Датчик Defender для конечной точки может использовать среднюю пропускную способность 5 МБ для связи с облачной службой Defender для конечной точки и отчета о кибер-данных. Разовая деятельность, например загрузка файлов и коллекция пакетов расследований, не включаются в эту среднюю пропускную способность.

Дополнительные сведения о дополнительных параметрах конфигурации прокси см. в перенастройке прокси-сервера устройства и параметров [подключения к Интернету.](configure-proxy-internet.md)

Перед устройством необходимо включить службу диагностических данных. Служба включена по умолчанию в Windows 10.


## <a name="microsoft-defender-antivirus-configuration-requirement"></a>Требование конфигурации антивируса Microsoft Defender
Агент Defender для конечной точки зависит от способности антивируса Microsoft Defender сканировать файлы и предоставлять сведения о них.

Настройте обновления аналитики безопасности на устройствах Defender для конечных точек независимо от того, является ли антивирус Microsoft Defender активным антивирусом или нет. Дополнительные сведения см. в [веб-сайте Управление обновлениями антивирусного](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus)антивируса Microsoft Defender и применение базовых данных.

Если антивирус Microsoft Defender не является активным антивирусом в организации и вы используете службу Defender для конечных точек, антивирус Microsoft Defender переходит в пассивный режим.

Если ваша организация отключил антивирус Microsoft Defender с помощью групповой политики или других методов, устройства, которые находятся на борту, должны быть исключены из этой групповой политики.

Если вы на бортовых серверах, а антивирус Microsoft Defender не является активным антивирусным обеспечением на серверах, антивирус Microsoft Defender необходимо настроить, чтобы перейти в пассивный режим или отсеять. Конфигурация зависит от версии сервера. Дополнительные сведения см. в [веб-сайте Совместимость антивирусных программ Microsoft Defender.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus-compatibility.md)

> [!NOTE]
> Обычная политика группы не применяется к защите от тамперов, и изменения параметров антивируса Microsoft Defender будут игнорироваться при внесения в нее защиты.


## <a name="microsoft-defender-antivirus-early-launch-antimalware-elam-driver-is-enabled"></a>Включен драйвер антивируса Microsoft Defender Early Launch Antimalware (ELAM)
Если антивирус Microsoft Defender запущен в качестве основного антивирусного продукта на устройствах, агент Defender для конечных точек успешно будет на борту.

Если вы работаете с сторонним клиентом антивирусных программ и используете решения для управления мобильными устройствами или Microsoft Endpoint Manager (текущая ветвь), необходимо убедиться, что драйвер ELAM антивируса Microsoft Defender включен. Дополнительные сведения см. в [веб-сайте Убедитесь,](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)что антивирус Microsoft Defender не отключен политикой.


## <a name="related-topics"></a>Статьи по теме
- [Настройка microsoft Defender для развертывания конечных точек](production-deployment.md)
- [Бортовых устройств](onboard-configure.md)
