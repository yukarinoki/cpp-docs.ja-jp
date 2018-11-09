---
title: プロバイダーでサポートされないデータの変換
ms.date: 10/29/2018
helpviewer_keywords:
- OLE DB provider templates, unsupported data types
ms.assetid: f495e50f-530a-4fab-ab54-e0c359785845
ms.openlocfilehash: 44cdde2bad24d21adbc728c90ecd173717c02b04
ms.sourcegitcommit: 943c792fdabf01c98c31465f23949a829eab9aad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2018
ms.locfileid: "51265192"
---
# <a name="converting-data-not-supported-by-the-provider"></a>プロバイダーでサポートされないデータの変換

コンシューマーがプロバイダーによってサポートされていないデータ型を要求すると、OLE DB プロバイダー テンプレートのコードを`IRowsetImpl::GetData`データ型に変換する Msdadc.dll を呼び出します。

ようなインターフェイスを実装する場合`IRowsetChange`データ変換が必要ですが、変換を行う Msdaenum.dll を呼び出すことができます。 使用`GetData`、例として、Atldb.h で定義されています。

## <a name="see-also"></a>関連項目

[OLE DB プロバイダー テンプレートの操作](../../data/oledb/working-with-ole-db-provider-templates.md)