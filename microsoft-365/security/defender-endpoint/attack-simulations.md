---
title: Опыт работы с ATP Защитника Майкрософт с помощью имитации атак
description: Запустите предоставленные имитации сценариев атак, чтобы узнать, как ATP Защитника Майкрософт может обнаруживать, исследовать и реагировать на нарушения.
keywords: wdatp, test, scenario, attack, simulation, simulated, diy, Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 11/20/2018
ms.technology: mde
ms.openlocfilehash: 25538e1866db8f4a7bff24ac336005bf2e1ce78b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073053"
---
# <a name="experience-microsoft-defender-for-endpoint-through-simulated-attacks"></a>Опыт Microsoft Defender для конечной точки с помощью имитации атак 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-attacksimulations-abovefoldlink)

>[!TIP]
>- Узнайте о последних улучшениях в ATP Защитника Microsoft: что нового в [Defender для конечной точки?.](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/).
>- Defender for Endpoint в недавней оценке MITRE продемонстрировал ведущие в отрасли возможности оптики и обнаружения. Read: [Insights from the MITRE ATT&CK-based assessment](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).

Может потребоваться испытать Defender для конечной точки, прежде чем вы на борту более нескольких устройств в службу. Для этого можно выполнить управляемые имитации атак на нескольких тестовых устройствах. После запуска смоделированных атак вы можете просмотреть, как Defender для конечной точки просматривает вредоносную активность и изучите, как она позволяет эффективно отвечать.

## <a name="before-you-begin"></a>Перед началом работы

Для запуска любого из предоставленных симуляций необходимо по крайней мере [одно бортовом устройстве.](onboard-configure.md) 

Ознакомьтесь с документом по погона, который содержит каждый сценарий атаки. Каждый документ содержит требования к ОС и приложениям, а также подробные инструкции, которые относятся к сценарию атаки.

## <a name="run-a-simulation"></a>Запуск моделирования

1. В   >  **справке & руководства**, выберите, какой из доступных сценариев атак вы хотите имитировать:

   - **Сценарий 1. Отбрасыватель** документа — имитирует доставку социально разработанного документа-приманки. В документе запускается специально созданный backdoor, который дает злоумышленникам контроль.

   - **Сценарий 2. Сценарий PowerShell** в без файловой атаке — имитирует без файловую атаку, которая опирается на PowerShell, демонстрацию уменьшения поверхности атаки и обнаружение вредоносных действий памяти на устройстве.
    
   - **Сценарий 3.** Автоматизированная реакция на инциденты — запускает автоматическое расследование, которое автоматически охотится за артефактами нарушений и устраняет их для масштабирования емкости реагирования на инциденты.

2. Скачайте и прочитайте соответствующий документ по погонам, предоставленный в выбранном сценарии.

3. Скачайте файл моделирования или скопируйте сценарий моделирования, перенавигав для **справки**&  >  **руководства.** Вы можете скачать файл или скрипт на тестовом устройстве, но это не является обязательным.

4. Запустите файл или сценарий моделирования на тестовом устройстве, как поручено в документе по поручению.

> [!NOTE]
> Файлы или сценарии моделирования имитируют действия атаки, но на самом деле являются доброкачественными и не наносят вреда тестовом устройству.
> 
> 
> Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-attacksimulations-belowfoldlink)


## <a name="related-topics"></a>Статьи по теме

- [Бортовых устройств](onboard-configure.md)
- [На борту устройств с Windows 10](configure-endpoints.md)
