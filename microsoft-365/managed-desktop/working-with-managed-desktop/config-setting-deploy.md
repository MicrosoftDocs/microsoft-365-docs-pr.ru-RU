---
title: Развертывание настраиваемых параметров на компьютере, управляемом Майкрософт
description: Развертывание и отслеживание настраиваемых изменений параметров в компьютере, управляемом Майкрософт.
keywords: Компьютер под управлением Майкрософт, Microsoft 365, служба, документация, развертывание, поэтапное развертывание, настраиваемые параметры
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a24d0dc64e2262a8b208119c45a4a6bade701c10
ms.sourcegitcommit: adaedd1418a3bd6e4875b77fd9e008b47e0b2a51
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2020
ms.locfileid: "48104538"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a>Развертывание и отслеживание настраиваемых параметров — компьютеры, управляемые Майкрософт

После внесения изменений в категории параметров и стадии развертывания страница состояния развертывания позволяет начать развертывание параметров в группах. На этой странице показана сводка по каждому настраиваемому параметру. Открыв категорию параметров, можно развернуть параметры в группах и отслеживать ход развертывания.

## <a name="deployment-statuses"></a>Состояния развертывания 

Это состояния, которые вы увидите для каждого развертывания.

Status  | Объяснение 
--- | --- 
Развертывание | Изменения ожидают развертывания в этой группе.
В процессе выполнения | Изменение применяется к активным устройствам в этой группе. 
Завершение | Изменение выполнено на всех активных устройствах в этой группе. 
Не выполнено | Сбой изменения на 10 % активных устройств в группе, поэтому развертывание было остановлено.<br><br> Запрос в службу поддержки будет автоматически открыт с помощью операций microsoft Managed Desktop для устранения неполадок развертывания. 
Reverted | Изменение было отменено до последнего изменения, которое было успешно развернуто во всех группах развертывания.

## <a name="deploy-changes"></a>Развертывание изменений

В этих инструкциях мы откажемся от фонового рисунка рабочего стола. После поэтапного развертывания изменения развертываются со страницы состояния развертывания. 

**Развертывание изменений**

1. Войдите в [Microsoft Endpoint Manager и](https://endpoint.microsoft.com/) перейдите в меню **"Устройства"**
2. Наберем раздел "Рабочий стол, управляемый Майкрософт", выберите **"Параметры".**
3. В **рабочей области** состояния развертывания выберите параметр, который требуется развернуть, а затем выберите поэтапное развертывание для развертывания.
4. Выберите  "Развернуть", чтобы развернуть изменение в одной из групп развертывания.

> [!NOTE] 
> Оранжевый значок предупреждения указывает, что для развертывания доступна предыдущая группа, так как ее рекомендуется развертывать по порядку. 

<!-- Needs picture updated to show MEM ![Deployment status workspace. Trusted sites pane on the right. In the Deployment groups section are three columns: deployment groups, devices, and status. In the status column, "deploy" is highlighted.](../../media/1deployedit.png) -->

Рекомендуется развертывать развертывание в группах развертывания в таком порядке: Test, First, Fast, and then Broad. 

После завершения изменений в каждой группе состояние меняется на **"Завершено".**

<!-- Needs picture updated to show MEM ![Deployment status workspace with columns for date updated, version, test, first, fast, and broad. The Proxy row is expanded, showing a dated setting flagged as "complete" in each of the four deployment groups.](../../media/2completeedit.png) -->

## <a name="revert-deployment"></a>Отовращать развертывание

После развертывания изменения можно вернуться к статусу **развертывания.** При отращении изменения, которое находится **в** процессе выполнения или **завершения,** текущее развертывание останавливается. Этот параметр вернется к последней версии, развернутой для всех групп. 

В качестве примера мы покажем, как отменить изменение с помощью фонового рисунка рабочего стола. 

**Как отменить изменение**
1. Войдите в [Microsoft Endpoint Manager и](https://endpoint.microsoft.com/) перейдите в меню **"Устройства"**
2. Наберем раздел "Рабочий стол, управляемый Майкрософт", выберите **"Параметры".**
3. В **рабочей области состояния** развертывания выберите параметр, который требуется отовращать, а затем выберите поэтапное развертывание, для чего требуется вернуться.
4. Under **Need to revert this change?**, select **Revert deployment**.

<!-- Needs picture updated to show MEM ![Deployment status workspace. Browser start pages is selected, opening a pane on the right side with data about the submitted change and its status. At the bottom is the "need to revert this change" area where you can select "Revert deployment."](../../media/3revert.png) -->

## <a name="additional-resources"></a>Дополнительные ресурсы
- [Обзор настраиваемых параметров](config-setting-overview.md)
- [Справочник по настраиваемым параметрам](config-setting-ref.md) 
