---
title: プロバイダーでサポートされないデータの変換
ms.date: 11/04/2016
helpviewer_keywords:
- OLE DB provider templates, unsupported data types
ms.assetid: f495e50f-530a-4fab-ab54-e0c359785845
ms.openlocfilehash: a53781f71a55dfb07dc996e5e25644d9337e4c63
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50473440"
---
# <a name="converting-data-not-supported-by-the-provider"></a>プロバイダーでサポートされないデータの変換

コンシューマーがプロバイダーによってサポートされていないデータ型を要求すると、OLE DB プロバイダー テンプレートのコードを`IRowsetImpl::GetData`データ型に変換する Msdadc.dll を呼び出します。

ようなインターフェイスを実装する場合`IRowsetChange`データ変換が必要ですが、変換を行う Msdaenum.dll を呼び出すことができます。 使用`GetData`、例として、Atldb.h で定義されています。

## <a name="see-also"></a>関連項目

[OLE DB プロバイダー テンプレートの操作](../../data/oledb/working-with-ole-db-provider-templates.md)