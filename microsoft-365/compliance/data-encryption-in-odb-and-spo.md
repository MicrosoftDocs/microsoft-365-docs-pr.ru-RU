---
title: Шифрование данных в OneDrive для бизнеса и SharePoint Online
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 6501b5ef-6bf7-43df-b60d-f65781847d6c
ms.collection:
- M365-security-compliance
- SPO_Content
description: Понимание основных элементов шифрования данных для обеспечения их защиты в OneDrive для бизнеса и SharePoint Online.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f0c78a9ca6e6bad1e4aea707f8be5dec818b7a27
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817928"
---
# <a name="data-encryption-in-onedrive-for-business-and-sharepoint-online"></a>Шифрование данных в OneDrive для бизнеса и SharePoint Online

Понимание основных элементов шифрования данных для обеспечения их защиты в OneDrive для бизнеса и SharePoint Online.
  
## <a name="security-and-data-encryption-in-office-365"></a>Безопасность и шифрование данных в Office 365

Microsoft 365 — это строго безопасная среда, которая обеспечивает расширенную защиту нескольких уровней: физическая безопасность центра обработки данных, безопасность сети, безопасность доступа, безопасность приложений и безопасность данных. Данная статья посвящена вопросам защиты данных, которые хранятся и передаются, благодаря их шифрованию для OneDrive для бизнеса и SharePoint Online.
  
Посмотрите видео о принципах шифрования данных.
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/dea0dec4-4077-4095-9a32-19b94ea2da4b?autoplay=false]
  
## <a name="encryption-of-data-in-transit"></a>Шифрование транзитных данных

В OneDrive для бизнеса и SharePoint Online используются два сценария для входящих и исходящих данных в центрах данных.
  
- **Client communication with the server** Communication to OneDrive for Business across the Internet uses SSL/TLS connections. All SSL connections are established using 2048-bit keys.

- **Data movement between datacenters** The primary reason to move data between datacenters is for geo-replication to enable disaster recovery. For instance, SQL Server transaction logs and blob storage deltas travel along this pipe. While this data is already transmitted by using a private network, it is further protected with best-in-class encryption. 

## <a name="encryption-of-data-at-rest"></a>Шифрование статических данных

Шифрование статических включает два компонента: шифрование BitLocker на уровне диска и пофайловое шифрование клиентского контента.
  
Развертывание BitLocker выполняется для OneDrive для бизнеса и SharePoint Online в службе. Шифрование на основе файлов также находится в OneDrive для бизнеса и SharePoint Online в Microsoft 365 с несколькими клиентами и новыми выделенными средами, созданными для технологии с несколькими клиентами.
  
While BitLocker encrypts all data on a disk, per-file encryption goes even further by including a unique encryption key for each file. Further, every update to every file is encrypted using its own encryption key. Before they're stored, the keys to the encrypted content are stored in a physically separate location from the content. Every step of this encryption uses Advanced Encryption Standard (AES) with 256-bit keys and is Federal Information Processing Standard (FIPS) 140-2 compliant. The encrypted content is distributed across a number of containers throughout the datacenter, and each container has unique credentials. These credentials are stored in a separate physical location from either the content or the content keys.
  
Дополнительные сведения о соответствии требованиям FIPS 140-2 приведены в статье [соответствие требованиям стандарта fips 140-2](https://go.microsoft.com/fwlink/?LinkId=517625).
  
File-level encryption at rest takes advantage of blob storage to provide for virtually unlimited storage growth and to enable unprecedented protection. All customer content in OneDrive for Business and SharePoint Online will be migrated to blob storage. Here's how that data is secured:
  
1. All content is encrypted, potentially with multiple keys, and distributed across the datacenter. Each file to be stored is broken into one or more chunks, depending its size. Then, each chunk is encrypted using its own unique key. Updates are handled similarly: the set of changes, or deltas, submitted by a user is broken into chunks, and each is encrypted with its own key.

2. All of these chunks—files, pieces of files, and update deltas—are stored as blobs in our blob store. They also are randomly distributed across multiple blob containers.

3. "Карта", используемая для повторной сборки файла из компонентов, хранится в базе данных контента.

4. Each blob container has its own unique credentials per access type (read, write, enumerate, and delete). Each set of credentials is held in the secure Key Store and is regularly refreshed.

Другими словами, в пофайловом статическом шифровании задействованы три различных типа хранилищ, каждое со своими определенными функциями:
  
- Content is stored as encrypted blobs in the blob store. The key to each chunk of content is encrypted and stored separately in the content database. The content itself holds no clue as to how it can be decrypted.

- The Content Database is a SQL Server database. It holds the map required to locate and reassemble all of the content blobs held in the blob store as well as the keys needed to decrypt those blobs.

Each of these three storage components—the blob store, the Content Database, and the Key Store—is physically separate. The information held in any one of the components is unusable on its own. This provides an unprecedented level of security. Without access to all three it is impossible to retrieve the keys to the chunks, decrypt the keys to make them usable, associate the keys with their corresponding chunks, decrypt any chunk, or reconstruct a document from its constituent chunks.
