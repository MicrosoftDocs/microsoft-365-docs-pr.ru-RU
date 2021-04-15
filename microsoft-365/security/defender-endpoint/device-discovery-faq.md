---
title: Обнаружение устройств часто задают вопросы
description: Поиск ответов на часто задаваемые вопросы (ВОПРОСЫ) об обнаружении устройства
keywords: обнаружение, обнаружение, пассивная, проактивность, сеть, видимость, сервер, рабочие станции, бортовых, неустановимых устройств
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: b3fef3479fa2d36806e6657b31f5152c54b9251f
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765003"
---
# <a name="device-discovery-frequently-asked-questions"></a>Обнаружение устройств часто задают вопросы

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

Найдите ответы на часто задаваемые вопросы (часто задаваемые вопросы) об обнаружении устройства.

## <a name="what-is-basic-discovery-mode"></a>Что такое базовый режим обнаружения?
Этот режим позволяет каждому устройству Microsoft Defender для конечной точки собирать сетевые данные и открывать соседние устройства. Onboarded endpoints passively collect events in the network and extract device information from them. Не будет инициирован сетевой трафик. Onboarded endpoints will simply extract data from every network traffic that is seen by an onboarded device. Эти данные используются для списка неугодных устройств в сети.

## <a name="can-i-disable-basic-discovery"></a>Можно ли отключить открытие Basic?
У вас есть возможность отключить обнаружение устройств на странице [Расширенные функции.](advanced-features.md) Однако вы потеряете видимость на неугодных устройствах в сети. 

## <a name="what-is-standard-discovery-mode"></a>Что такое стандартный режим обнаружения?
 В этом режиме конечные точки, на борту в Microsoft Defender для конечной точки, могут активно зондировать наблюдаемые устройства в сети для обогащения собранных данных (с незначительным количеством сетевого трафика). Этот режим настоятельно рекомендуется для создания надежного и согласованного инвентаризации устройств. Если вы решите отключить этот режим и выбрать базовый режим обнаружения, вы, скорее всего, получите ограниченную видимость неугомонных конечных точек в сети.

## <a name="can-i-control-which-devices-perform-standard-discovery"></a>Могу ли я управлять, какие устройства выполняют стандартные открытия?
 Вы можете настроить список устройств, используемых для выполнения стандартных открытий. Вы можете включить обнаружение Standard на всех бортовых устройствах, которые также поддерживают эту возможность (в настоящее время только для устройств с Windows 10), либо выбрать подмножество или подмножество устройств, указав их теги устройств. В этом случае все остальные устройства будут настроены только для запуска базового обнаружения. Конфигурация доступна на странице параметры обнаружения устройства.

## <a name="which-onboarded-devices-can-perform-discovery"></a>Какие бортовых устройства могут выполнять обнаружение?
 Onboarded devices running on Windows 10 version 1809 or later can perform discovery.

## <a name="what-happens-if-my-onboarded-devices-is-connected-to-my-home-network-or-to-public-access-point"></a>Что произойдет, если мои подключенные устройства подключены к домашней сети или к точке общего доступа?
 Механизм обнаружения различает сетевые события, полученные в корпоративной сети, и вне корпоративной сети. Сопоставляет сетевые идентификаторы всех клиентов клиента, события различаются между событиями, полученными из частных сетей и корпоративных сетей. Частные сетевые устройства не будут перечислены в инвентаре и не будут активно зондироваться.

## <a name="what-protocols-are-you-capturing-and-analyzing"></a>Какие протоколы вы захватываете и анализируете?
 По умолчанию все бортовые устройства, работающие в Windows 10 версии 1809 или более поздней версии, схватив и анализируя следующие протоколы: ARP, CDP, DHCP, DHCPv6, IP (headers), LLDP, LLMNR, mDNS, MNDP, NBNS, SSDP, TCP (headers), UDP (headers), WSD

## <a name="which-protocols-do-you-use-for-active-probing-in-standard-discovery"></a>Какие протоколы вы используете для активного прорабтки в стандартном открытии?
 Если устройство настроено для запуска стандартных открытий, подвергаются проверке службы с помощью следующих протоколов: ARP, FTP, HTTP, ICMP, LLMNR, NBNS, RDP, SIP, SMTP, SNMP, SNMP, Telnet, UPNP, WSD, SMB, NBSS, IPP, PJL

## <a name="how-can-i-exclude-targets-from-being-probed-with-standard-discovery"></a>Как исключить возможность проверки целей с помощью стандартного обнаружения?
 Если в сети есть устройства, которые не следует активно проверять, можно также определить список исключений, чтобы предотвратить их сканирование. Конфигурация доступна на странице параметры обнаружения устройства.

## <a name="can-i-exclude-devices-from-being-discovered"></a>Можно ли исключить обнаружение устройств?
 Поскольку при обнаружении устройств в сети используются пассивные методы обнаружения устройств, любое устройство, которое взаимодействует с вашими бортовых устройствами в корпоративной сети, может быть обнаружено и перечислено в инвентаре. Вы можете исключить устройства только из активного прорабаты.

## <a name="how-frequent-is-the-active-probing"></a>Как часто активное прорабывение?
 Устройства будут активно зондироваться при наблюдении за изменениями в характеристиках устройств (каждые 1-3 недели), чтобы убедиться, что существующая информация является необходимой.

## <a name="my-security-tool-raised-alert-on-unicastscannerps1-or-port-scanning-activity-initiated-by-it-what-should-i-do"></a>Мой инструмент безопасности поднял оповещение о UnicastScanner.ps1 или при проверке порта, инициированной этим инструментом, что мне делать?
 Сценарии активного прорабаки подписывались Корпорацией Майкрософт и являются безопасными. В список исключений можно добавить следующий путь: `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\*.ps`


## <a name="what-is-the-amount-of-traffic-being-generated-by-the-standard-discovery-active-probe"></a>Какой объем трафика создает активный зонд Standard discovery?
 Активное зондировать может генерировать до 5K трафика между бортового устройства и зондировали устройство, каждая попытка зондировать

## <a name="why-is-there-a-discrepancy-between-can-be-onboarded-devices-in-the-device-inventory-and-the-number-of-devices-to-onboard-in-the-dashboard-tile"></a>Почему в инвентаризации устройств существует несоответствие между "могут быть бортовых" устройств и числом "устройств на борту" в плитке панели мониторинга?
Вы можете заметить различия между числом перечисленных устройств в списке "может быть включено" в инвентаре устройства, "на борту в Microsoft Defender для конечной точки" рекомендации по безопасности и "устройства для бортовой панели" виджет панели мониторинга.

 Рекомендации по безопасности и виджет панели мониторинга для устройств, стабильных в сети; за исключением эфемерных устройств, гостевых устройств и других. Идея заключается в том, чтобы рекомендовать на стойких устройствах, которые также подразумевают общую оценку безопасности организации.

## <a name="can-i-onboard-unmanaged-devices-that-were-found"></a>Могу ли я использовать найденные неугодные устройства?
 Да. Неугомонные конечные точки в сети вводят в сеть уязвимости и риски. Их в службу может повысить видимость безопасности на них. 

