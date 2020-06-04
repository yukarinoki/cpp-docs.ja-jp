---
title: プロバイダーでサポートされないデータの変換
ms.date: 10/29/2018
helpviewer_keywords:
- OLE DB provider templates, unsupported data types
ms.assetid: f495e50f-530a-4fab-ab54-e0c359785845
ms.openlocfilehash: e87aebc4d6f23343af9a2f966d2c522e95b304ea
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80211498"
---
# <a name="converting-data-not-supported-by-the-provider"></a>プロバイダーでサポートされないデータの変換

コンシューマーがプロバイダーでサポートされていないデータ型を要求した場合、`IRowsetImpl::GetData` の OLE DB プロバイダーテンプレートコードは Msdadc を呼び出してデータ型を変換します。

データ変換を必要とする `IRowsetChange` のようなインターフェイスを実装する場合は、Msdaenum を呼び出して変換を行うことができます。 例として、Atldb.h で定義されている `GetData`を使用します。

## <a name="see-also"></a>参照

[OLE DB プロバイダー テンプレートの操作](../../data/oledb/working-with-ole-db-provider-templates.md)
