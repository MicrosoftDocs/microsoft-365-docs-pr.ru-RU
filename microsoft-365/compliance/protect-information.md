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
ms.collection:
- m365solution-mip
- m365initiative-compliance
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: Реализуйте возможности Microsoft Information Protection (МИП) с помощью соответствия требованиям Microsoft 365, которые помогают находить, классифицировать и защищать конфиденциальную информацию везде, где она живет или передается.
ms.openlocfilehash: 78aadbba5442d7ec3cdc1beeac6d290a11325861
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/09/2020
ms.locfileid: "48399048"
---
# <a name="microsoft-information-protection-in-microsoft-365"></a>Защита информации Майкрософт в Microsoft 365

>*[Лицензирование Microsoft 365 Security & соответствие требованиям](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

Используйте Microsoft Information Protection (МИП), чтобы помочь вам находить, классифицировать и защищать конфиденциальную информацию везде, где она живет или передается.

Возможности МИП включены в соответствие требованиям Microsoft 365 и предоставляют средства для работы с [данными](#know-your-data), [защиты данных](#protect-your-data)и [предотвращения потери данных](#prevent-data-loss).

![Сведения о ваших данных, защите данных, предотвращении потери данных, управлении данными](../media/powered-by-intelligent-platform.png)

Сведения об управлении данными можно найти в статье Microsoft [Information управление в microsoft 365](manage-Information-governance.md).

## <a name="know-your-data"></a>Изучение данных

Чтобы понять вашу ориентацию данных и определить важные данные в гибридной среде, используйте следующие возможности:
 
|Возможность|Какие проблемы она решает?|Начало работы|
|:------|:------------|:--------------------|:-----------------------------|
|[Типы конфиденциальной информации](sensitive-information-type-entity-definitions.md)| Определяет конфиденциальные данные с помощью встроенных или настраиваемых регулярных выражений или функции вместе с свидетельством подкрепляющее, включающим ключевые слова, уровни вероятности и сходства.| [Настройка встроенных типов конфиденциальных данных](customize-a-built-in-sensitive-information-type.md)|
|[Выученные классификаторы (Предварительная версия)](classifier-learn-about.md)| Классификация данных для вас с помощью одного из встроенных классификаторов или обучение классификатора с собственным контентом | [Начало работы с обучаемыми классификаторами (предварительная версия)](classifier-get-started-with.md) |
|[Классификация данных](data-classification-overview.md) | Определяет элементы, которые имеют метку конфиденциальности, метку хранения или классифицируются как тип конфиденциальной информации в Организации и действия, которые используются пользователями.  | [Начало работы с обозревателем контента](data-classification-content-explorer.md)<br /><br /> [Приступая к работе с обозревателем действий](data-classification-activity-explorer.md) |

## <a name="protect-your-data"></a>Защита данных

Для применения гибких действий защиты, включающих шифрование, ограничения доступа и визуальные метки, используйте следующие возможности:

|Возможность|Какие проблемы она решает?|Начало работы|
|:------|:------------|---------------------|:----------------------------|
|[Метки конфиденциальности](sensitivity-labels.md)| Единое решение для нескольких приложений, служб и устройств для подписи и защиты данных при их пересылке внутри и за пределами Организации <br /><br />Пример сценария: [применение и Просмотр меток конфиденциальности в Power BI и защита данных при экспорте](https://docs.microsoft.com/power-bi/admin/service-security-apply-data-sensitivity-labels)|[ Начало работы с метками конфиденциальности](get-started-with-sensitivity-labels.md) |
|[Клиент единой метки Azure Information Protection](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2)| Для компьютеров под управлением Windows дополнительные функции и функции, включающие метки и защиту всех типов файлов из проводника и PowerShell, расширяются метками конфиденциальности.<br /><br /> Примеры дополнительных функций: [настраиваемые конфигурации для клиента единой метки Azure Information Protection](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)| [Руководство по администратору клиентов единой метки Azure Information Protection](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide)|
|[Шифрование с двойным ключом](double-key-encryption.md)| Во всех обстоятельствах только вы можете расшифровывать защищенный контент или требования законодательства, которые необходимо удерживать в пределах географической границы | [Развертывание двойного шифрования ключей](double-key-encryption.md#deploy-dke)|
|[Шифрование сообщений в Office 365](ome.md) (OME)| Шифрует сообщения электронной почты и вложенные документы, которые отправляются любому пользователю на любом устройстве, поэтому только авторизованные получатели могут читать электронную информацию.  <br /><br />Пример сценария: [отзыв электронной почты, зашифрованной с помощью расширенного шифрования сообщений](revoke-ome-encrypted-mail.md) | [Настройка новых возможностей шифрования сообщений](set-up-new-message-encryption-capabilities.md)|
|[Шифрование службы с помощью ключа клиента](customer-key-overview.md) | Обеспечивает защиту от просмотра данных неавторизованными системами или персоналом и дополняет шифрование диска BitLocker в центрах обработки данных Майкрософт. | [Настройка ключа клиента для Office 365](customer-key-set-up.md)|
|[Управление правами на доступ к данным SharePoint (IRM)](set-up-irm-in-sp-admin-center.md#irm-enable-sharepoint-document-libraries-and-lists)|Защищает списки и библиотеки SharePoint таким образом, чтобы когда пользователь извлекает документ, скачанный файл защищен, чтобы только авторизованные пользователи могли просматривать и использовать файл в соответствии с указанными политиками. | [Set up Information Rights Management (IRM) in SharePoint admin center](set-up-irm-in-sp-admin-center.md)|
[Соединитель управления правами](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector) |Только Защита для существующих локальных развертываний, использующих Exchange или SharePoint Server, а также файловых серверов, на которых выполняется Windows Server и инфраструктура классификации файлов (FCI) | [Действия по развертыванию соединителя службы управления правами](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector#steps-to-deploy-the-rms-connector)
|[Сканер единой метки Azure Information Protection](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)| Обнаружение, метки и защита конфиденциальной информации, расположенной в локальных хранилищах данных | [Настройка и установка сканера единой метки Azure Information Protection](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner-configure-install)|
|[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)| Обнаружение, метки и защита конфиденциальной информации, которая находится в хранилищах данных в облаке | [Обнаружение, классификация, применение меток и защита регламентированных и конфиденциальных данных, хранящихся в облаке](https://docs.microsoft.com/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|[SDK защиты информации (Майкрософт)](https://docs.microsoft.com/information-protection/develop/overview#microsoft-information-protection-sdk)|Расширение меток конфиденциальности для сторонних приложений и служб  <br /><br /> Пример сценария: [Set и получение метки конфиденциальности (C++)](https://docs.microsoft.com/information-protection/develop/quick-file-set-get-label-cpp) |[Настройка пакета SDK для Microsoft Information Protection (MIP)](https://docs.microsoft.com/information-protection/develop/setup-configure-mip)|

## <a name="prevent-data-loss"></a>Защита от потери данных

Чтобы предотвратить случайный общий доступ к конфиденциальным сведениям, используйте следующие возможности:


|Возможность|Какие проблемы она решает?|Начало работы|
|:------|:------------|:---------------------|:-----------------------------|
|[Защита от потери данных](data-loss-prevention-policies.md) (DLP)| Помогает предотвратить непреднамеренное совместное использование конфиденциальных элементов <br /><br />Пример сценария: [Защита конфиденциальной информации в Microsoft Teams Chat и сообщений канала](dlp-microsoft-teams.md) | [Начало работы со стандартной политикой защиты от потери данных](get-started-with-the-default-dlp-policy.md)|
|[Защита от потери данных конечной точки (Предварительная версия)](endpoint-dlp-learn-about.md)| Расширяет возможности защиты от потери данных для элементов, используемых и совместно используемых на компьютерах с Windows 10 | [Начало работы с функцией защиты от потери данных в конечной точке (предварительная версия)](endpoint-dlp-getting-started.md)|
