---
title: Развертывание Microsoft Defender для конечной точки в кольцах
description: Узнайте, как развернуть Microsoft Defender для конечной точки в кольцах
keywords: развертывание, кольца, оценка, пилот, инсайдерская быстро, инсайдерская медленная, установка, бортовая, фаза, развертывание, развертывание, развертывание, принятие, настройка
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-overview
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8123bdf610b30407e5d262296f9c3639bc21b12f
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893489"
---
# <a name="deploy-microsoft-defender-for-endpoint-in-rings"></a>Развертывание Microsoft Defender для конечной точки в кольцах

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Развертывание Microsoft Defender для конечной точки можно сделать с помощью подхода к развертыванию на основе кольца. 

Кольца развертывания можно применить в следующих сценариях:
- [Новые развертывания](#new-deployments)
- [Существующие развертывания](#existing-deployments)

## <a name="new-deployments"></a>Новые развертывания

![Изображение колец развертывания](images/deployment-rings.png)


Метод на основе кольца — это метод определения набора конечных точек для бортового устройства и проверки соответствия определенным критериям перед началом развертывания службы на более широком наборе устройств. Вы можете определить критерии выхода для каждого кольца и убедиться, что они удовлетворены перед переходом на следующее кольцо.

Внедрение развертывания на основе кольца помогает уменьшить возможные проблемы, которые могут возникнуть при развертывании службы. Сначала с помощью пилотного пилотирования определенного числа устройств можно определить потенциальные проблемы и снизить возможные риски, которые могут возникнуть. 


В таблице 1 приводится пример колец развертывания, которые можно использовать. 

**Таблица 1**

|**Кольцо развертывания**|**Описание**|
|:-----|:-----|
Оценка | Кольцо 1. Определение 50 систем для пилотного тестирования 
Пилотное развертывание | Кольцо 2. Определение следующих конечных точек 50-100 в производственной среде <br>  
Полное развертывание | Кольцо 3. Выкатка службы для остальной среды с большими приращениями



### <a name="exit-criteria"></a>Критерии выхода
Пример набора критериев выхода для этих колец может включать в себя:
- Устройства показываются в списке инвентаризации устройств
- Оповещения отображаются на панели мониторинга
- [Выполнить тест обнаружения](run-detection-test.md)
- [Запуск смоделированной атаки на устройство](attack-simulations.md)

### <a name="evaluate"></a>Оценка
Определите небольшое количество тестовых машин в вашей среде, чтобы они были на борту службы. В идеале эти машины будут иметь менее 50 конечных точек. 


### <a name="pilot"></a>Пилотное развертывание
Microsoft Defender для конечной точки поддерживает различные конечные точки, которые можно использовать в службе. В этом кольце определите несколько устройств на борту и на основе определяемого вами критерия выхода решите перейти к следующему кольцу развертывания.

В следующей таблице показаны поддерживаемые конечные точки и соответствующий инструмент, который можно использовать на бортовых устройствах службы. 

| Endpoint     | Средство развертывания                       |
|--------------|------------------------------------------|
| **Windows**  |  [Локальный скрипт (до 10 устройств)](configure-endpoints-script.md) <br> ПРИМЕЧАНИЕ. Если вы хотите развернуть более 10 устройств в рабочей среде, используйте метод групповой политики или другие поддерживаемые ниже средства.<br>  [Групповая политика](configure-endpoints-gp.md) <br>  [Microsoft Endpoint Manager/ Mobile Device Manager](configure-endpoints-mdm.md) <br>   [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [Скрипты VDI](configure-endpoints-vdi.md)   |
| **macOS**    | [Локальный скрипт](mac-install-manually.md) <br> [Менеджер конечных точек Майкрософт](mac-install-with-intune.md) <br> [JAMF Pro](mac-install-with-jamf.md) <br> [Управление мобильными устройствами](mac-install-with-other-mdm.md) |
| **Linux Server** | [Локальный скрипт](linux-install-manually.md) <br> [Puppet](linux-install-with-puppet.md) <br> [Ansible](linux-install-with-ansible.md)|
| **iOS**      | [На основе приложения](ios-install.md)                                |
| **Android**  | [Менеджер конечных точек Майкрософт](android-intune.md)               | 




### <a name="full-deployment"></a>Полное развертывание
На данном этапе вы можете использовать материал [развертывания Plan](deployment-strategy.md) для планирования развертывания. 


Используйте следующий материал, чтобы выбрать соответствующую архитектуру Microsoft Defender для конечной точки, которая лучше всего подходит для вашей организации.

|**Item**|**Описание**|
|:-----|:-----|
|[![Изображение большого пальца для стратегии развертывания Конечных точек Microsoft Defender для конечной точки](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)<br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) | Материалы по архитектуре помогут вам спланировать развертывание для следующих архитектур: <ul><li> Облачное развертывание </li><li> Совместное управление </li><li> Локальное развертывание</li><li>Оценка и локальное внедрение</li>




## <a name="existing-deployments"></a>Существующие развертывания

### <a name="windows-endpoints"></a>Конечные точки Windows
Для Windows и/или Windows Servers вы выбираете несколько машин для досрочного тестирования (перед обновлением во вторник) с помощью программы проверки обновления безопасности **(SUVP).**

Дополнительные сведения см. в указанных ниже статьях.
- [Что такое программа проверки обновления безопасности](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/what-is-the-security-update-validation-program/ba-p/275767)
- [Программа проверки обновления программного обеспечения и Центр Майкрософт по защите от вредоносных программ создания — TwC Interactive Timeline Part 4](https://www.microsoft.com/security/blog/2012/03/28/software-update-validation-program-and-microsoft-malware-protection-center-establishment-twc-interactive-timeline-part-4/)


### <a name="non-windows-endpoints"></a>Конечные точки, не в Windows
С помощью macOS и Linux можно воспользоваться несколькими системами и запустить их в канале InsidersFast.

>[!NOTE]
>В идеале не менее одного администратора безопасности и одного разработчика, чтобы вы могли находить проблемы с совместимостью, производительностью и надежностью до того, как сборка будет перенастройка в канал "Production".

Выбор канала определяет тип и частоту обновлений, предлагаемых вашему устройству. Устройства в инсайдерской быстрой являются первыми, которые получают обновления и новые функции, а затем инсайдеры медленно и, наконец, prod.

![Изображение инсайдерской колец](images/insider-rings.png)

Для предварительного просмотра новых функций и обеспечения ранней обратной связи рекомендуется настроить некоторые устройства в вашем предприятии, чтобы использовать как инсайдеры-быстрые, так и инсайдеры-медленные.

>[!WARNING]
>Переключение канала после начальной установки требует повторной установки продукта. Чтобы переключить канал продукта: удалить существующий пакет, перенастройте устройство для использования нового канала и выполните действия в этом документе, чтобы установить пакет из нового расположения.
