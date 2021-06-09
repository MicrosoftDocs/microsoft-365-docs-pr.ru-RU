---
title: Планирование развертывания конечной точки в Microsoft Defender
description: Выберите лучшую стратегию развертывания Microsoft Defender для конечных точек для среды
keywords: развертывание, планирование, стратегия развертывания, локальное облако, управление по прему, оценке, бортовой, локальной, групповой политике, гп, менеджеру конечных точек, mem
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8cd670e72bbb4ec0abacd4ed053a9ea9af12608b
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163579"
---
# <a name="plan-your-microsoft-defender-for-endpoint-deployment"></a>Планирование развертывания конечной точки в Microsoft Defender 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-secopsdashboard-abovefoldlink) 


Запланируйте развертывание Microsoft Defender для конечной точки, чтобы максимально повысить возможности безопасности в пакете и лучше защитить свое предприятие от киберугроз.


Это решение содержит рекомендации по выявлению архитектуры среды, выбор типа средства развертывания, который наилучшим образом соответствует вашим потребностям, и инструкции по настройке возможностей.


![Изображение потока развертывания](images/deployment-guide-plan.png)


## <a name="step-1-identify-architecture"></a>Шаг 1. Определение архитектуры
Мы понимаем, что каждая корпоративная среда уникальна, поэтому мы предоставили несколько вариантов, чтобы предоставить вам гибкость при выборе способов развертывания службы.

В зависимости от среды некоторые средства лучше подходят для определенных архитектур. 

Используйте следующий материал, чтобы выбрать соответствующую архитектуру Defender для конечной точки, которая лучше всего подходит для вашей организации.

| Item | Описание |
|:-----|:-----|
|[![Изображение большого пальца для стратегии развертывания Defender для конечной точки](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)<br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) | Материалы по архитектуре помогут вам спланировать развертывание для следующих архитектур: <ul><li> Облачное развертывание </li><li> Совместное управление </li><li> Локальное развертывание</li><li>Оценка и локальное внедрение</li>



## <a name="step-2-select-deployment-method"></a>Шаг 2. Выбор метода развертывания
Defender for Endpoint поддерживает различные конечные точки, которые можно использовать на борту службы. 

В следующей таблице перечислены поддерживаемые конечные точки и соответствующий инструмент развертывания, который можно использовать для правильного планирования развертывания.

| Endpoint     | Средство развертывания                       |
|--------------|------------------------------------------|
| **Windows**  |  [Локальный скрипт (до 10 устройств)](configure-endpoints-script.md) <br>  [Групповая политика](configure-endpoints-gp.md) <br>  [Microsoft Endpoint Manager/ Диспетчер мобильных устройств](configure-endpoints-mdm.md) <br>   [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [Скрипты VDI](configure-endpoints-vdi.md)   |
| **macOS**    | [Локальный скрипт](mac-install-manually.md) <br> [Microsoft Endpoint Manager](mac-install-with-intune.md) <br> [JAMF Pro](mac-install-with-jamf.md) <br> [Управление мобильными устройствами](mac-install-with-other-mdm.md) |
| **Linux Server** | [Локальный скрипт](linux-install-manually.md) <br> [Puppet](linux-install-with-puppet.md) <br> [Ansible](linux-install-with-ansible.md)|
| **iOS**      | [На основе приложения](ios-install.md)                                |
| **Android**  | [Microsoft Endpoint Manager](android-intune.md)               | 



## <a name="step-3-configure-capabilities"></a>Шаг 3. Настройка возможностей
После использования конечных точек настройте возможности безопасности в Defender для конечной точки, чтобы можно было максимально повысить надежность защиты, доступную в наборе. Возможности включают в себя:

- Обнаружение и устранение угроз на конечных точках
- Защита нового поколения
- Сокращение направлений атак


  
## <a name="related-topics"></a>Статьи по теме
- [Этапы развертывания](deployment-phases.md)
