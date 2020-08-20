---
title: Защита информации Майкрософт в Microsoft 365
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: High
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: Реализация возможностей Microsoft Information Protection (MIP) с помощью средства защиты от Microsoft 365, которые помогут вам обнаруживать, классифицировать и защищать конфиденциальную информацию в любое время.
ms.openlocfilehash: 96082bc70b093e763be00c847bb6a68ce302c8a9
ms.sourcegitcommit: 22fd8517707ed3ab6ef996247ad2aa372535ee56
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2020
ms.locfileid: "46815210"
---
# <a name="microsoft-information-protection-in-microsoft-365"></a>Защита информации Майкрософт в Microsoft 365

>*[Лицензирование для соответствия требованиям безопасности & Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

Служба защиты информации Майкрософт (MIP) позволяет обнаруживать, классифицировать и защищать конфиденциальную информацию влюбое время, где бы она ни находилась и проходит по-другому.

Возможности MIP включены в соответствие с Microsoft 365 и предоставляют вам средства [для](#know-your-data)избранности [данных,](#protect-your-data)защиты данных и [предотвращения их потери.](#prevent-data-loss)

![изглядение данных, защита данных, предотвращение потери данных, управление данными](../media/powered-by-intelligent-platform.png)

Сведения об управлении данными см. в статье [Об управлении информацией (Майкрософт) в Microsoft 365.](manage-Information-governance.md)

## <a name="know-your-data"></a>Изучение данных

Для понимания среды данных и определения важных данных в гибридной среде используйте следующие возможности:
 
|Возможность|Какие проблемы решает?|Начало работы|
|:------|:------------|:--------------------|:-----------------------------|
|[Типы конфиденциальной информации](sensitive-information-type-entity-definitions.md)| Идентифицирует конфиденциальные данные с помощью встроенных или настраиваемых регулярных выражений или функции, а также подтверждающих склонений, включающих ключевые слова, уровни вероятности и близость.| [Настройка встроенных типов конфиденциальных данных](customize-a-built-in-sensitive-information-type.md)|
|[Обучаемые классификаторы (предварительная версия)](classifier-getting-started-with.md)| Классифицирует данные с помощью одного из встроенных классификаторов или классификатора собственным контентом | [Создание обучаемого классификатора (предварительная версия)](classifier-creating-a-trainable-classifier.md) |
|[Классификация данных](data-classification-overview.md) | Определяет элементы с меткой конфиденциальности, меткой хранения или испорченными, классифицированными как тип конфиденциальной информации в организации, и действия, с которыми они выполняют пользователи  | [Начало работы с обозревателем контента](data-classification-content-explorer.md)<br /><br /> [Начало работы с обозревателем действий](data-classification-activity-explorer.md) |

## <a name="protect-your-data"></a>Защита данных

Чтобы применить гибкие действия защиты, в том том том, что шифрование, ограничения доступа и визуальные маркировки, используйте следующие возможности:

|Возможность|Какие проблемы решает?|Начало работы|
|:------|:------------|---------------------|:----------------------------|
|[Метки конфиденциальности](sensitivity-labels.md)| Единое решение для разных приложений, служб и устройств для маркировки и защиты данных при ее дробном и за пределах организации <br /><br />Пример сценария: [применение и просмотр меток конфиденциальности](https://docs.microsoft.com/power-bi/admin/service-security-data-protection-overview) в Power BI и защита данных при экспорте|[ Начало работы с метками конфиденциальности](get-started-with-sensitivity-labels.md) |
|[Клиент унифицированных меток Azure Information Protection](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2)| Для компьютеров с Windows расширяются метки конфиденциальности для дополнительных функций, включающих метки и защиту всех типов файлов в проводнике и PowerShell<br /><br /> Пример дополнительных функций. [Настраиваемые конфигурации для клиента унифицированных меток Azure Information Protection](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)| [Руководство администратора клиента для унифицированных меток Azure Information Protection](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide)|
|[Шифрование с двойным ключом](double-key-encryption.md)| При всех обстоятельствах можно никогда расшифровывать защищенный контент или нормативные требования, если ключи шифрования необходимо хранить в пределах географической границы. | [Развертывание шифрования двойным ключом](double-key-encryption.md#deploy-double-key-encryption)|
|[Шифрование сообщений Office 365](ome.md) (OME)| Шифрует сообщения электронной почты и вложенные документы, отправляемые любому пользователю на любом устройстве, чтобы только авторизованные получатели могли читать информацию, отправленную по электронной почте.  <br /><br />Пример сценария. Отзыв [электронных писем, зашифрованных с помощью расширенного шифрования сообщений](revoke-ome-encrypted-mail.md) | [Начало работы с шифрованием сообщений Office 365](set-up-new-message-encryption-capabilities.md)|
|[Шифрование службы с помощью ключа клиента](customer-key-overview.md) | Защищает от просмотра данных несанкционированными системами или сотрудниками, а также дополняет шифрование дисков BitLocker в центрах обработки данных Майкрософт. | [Настройка ключа клиента для Office 365](customer-key-set-up.md)|
|[Управление правами на доступ к данным SharePoint (IRM)](set-up-irm-in-sp-admin-center.md#irm-enable-sharepoint-document-libraries-and-lists)|Защищает списки и библиотеки SharePoint. Это позволяет защитить загруженный файл, чтобы только авторизованные пользователи могли просматривать и использовать его в соответствии с заданным вами политиками. | [Set up Information Rights Management (IRM) in SharePoint admin center](set-up-irm-in-sp-admin-center.md)|
[Соединитель Rights Management](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector) |Только защита для существующих локальных развертываний, использующих Exchange или SharePoint Server, или файловых серверов под управлением Windows Server и инфраструктуры классификации файлов (FCI) | [Действия по развертыванию соединителя RMS](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector#steps-to-deploy-the-rms-connector)
|[Средство проверки унифицированных меток Azure Information Protection](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)| Обнаруживает, метафировки и защищает конфиденциальную информацию, хранящуюся в локальных хранилищах данных. | [Настройка и установка унифицированного сканера присвоения меток Azure Information Protection](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner-configure-install)|
|[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)| Обнаруживать, метафировые и защищает конфиденциальную информацию, хранящуюся в хранилищах данных в облаке | [Обнаружение, классификация, применение меток и защита регламентированных и конфиденциальных данных, хранящихся в облаке](https://docs.microsoft.com/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|[SDK защиты информации (Майкрософт)](https://docs.microsoft.com/information-protection/develop/overview#microsoft-information-protection-sdk)|Расширение меток конфиденциальности для сторонних приложений и служб  <br /><br /> Пример [сценария: установка и получение метки конфиденциальности (C++)](https://docs.microsoft.com/information-protection/develop/quick-file-set-get-label-cpp) |[Настройка и настройка пакета SDK Microsoft Information Protection (MIP)](https://docs.microsoft.com/information-protection/develop/setup-configure-mip)|

## <a name="prevent-data-loss"></a>Защита от потери данных

Чтобы предотвратить непредназначение, общего доступа к конфиденциальным данным, воспользуйтесь следующими возможностями:


|Возможность|Какие проблемы решает?|Начало работы|
|:------|:------------|:---------------------|:-----------------------------|
|[Защита от потери данных](data-loss-prevention-policies.md) (DLP)| помогает предотвратить непреднамеренное предоставление общего доступа к конфиденциальным элементам; <br /><br />Пример сценария. [Защита конфиденциальной информации в чатах и сообщениях каналов Microsoft Teams](dlp-microsoft-teams.md) | [Начало работы со стандартной политикой защиты от потери данных](get-started-with-the-default-dlp-policy.md)|
|[Защита от потери данных в конечной точке (предварительная версия)](endpoint-dlp-learn-about.md)| Расширяет возможности DLP для элементов, используемых и совместно используемых на компьютерах с Windows 10 | [Начало работы с функцией защиты от потери данных в конечной точке (предварительная версия)](endpoint-dlp-getting-started.md)|
