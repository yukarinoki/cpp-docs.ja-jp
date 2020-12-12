---
description: '詳細情報: プロバイダーでサポートされていないデータの変換'
title: プロバイダーでサポートされないデータの変換
ms.date: 10/29/2018
helpviewer_keywords:
- OLE DB provider templates, unsupported data types
ms.assetid: f495e50f-530a-4fab-ab54-e0c359785845
ms.openlocfilehash: 9fb449247ff40118e89dbebee5f43a1208a1f181
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323367"
---
# <a name="converting-data-not-supported-by-the-provider"></a>プロバイダーでサポートされないデータの変換

コンシューマーがプロバイダーでサポートされていないデータ型を要求した場合、の OLE DB プロバイダーテンプレートコードは `IRowsetImpl::GetData` Msdadc.dll を呼び出して、データ型を変換します。

データ変換を必要とするのようなインターフェイスを実装する場合は `IRowsetChange` 、Msdaenum.dll を呼び出して変換を行うことができます。 `GetData`例として、atldb.h で定義されているを使用します。

## <a name="see-also"></a>関連項目

[OLE DB プロバイダーテンプレートの操作](../../data/oledb/working-with-ole-db-provider-templates.md)
