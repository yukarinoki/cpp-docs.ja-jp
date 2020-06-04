---
title: 手動アクセサーの使用
ms.date: 10/24/2018
helpviewer_keywords:
- command handling, OLE DB Templates
- manual accessors
- accessors [C++], manual
ms.assetid: 29f00a89-0240-482b-8413-4120b9644672
ms.openlocfilehash: a6c0e5236702229a61a828344ba5d0d288898aee
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209327"
---
# <a name="using-manual-accessors"></a>手動アクセサーの使用

不明なコマンドを処理する場合は、次の4つの操作を実行します。

- パラメーターを決定する

- コマンドを実行します。

- 出力列を決定する

- 複数のリターン行セットがあるかどうかを確認する

OLE DB コンシューマーテンプレートでこれらの操作を行うには、`CManualAccessor` クラスを使用して次の手順を実行します。

1. `CManualAccessor` をテンプレートパラメーターとして `CCommand` オブジェクトを開きます。

    ```cpp
    CCommand<CManualAccessor, CRowset, CMultipleResults> rs;
    ```

1. `IDBSchemaRowset` インターフェイスのセッションに対してクエリを実行し、プロシージャパラメーターの行セットを使用します。 `IDBSchemaRowset` インターフェイスが使用できない場合は、`ICommandWithParameters` インターフェイスを照会します。 詳細については、`GetParameterInfo` を呼び出してください。 どちらのインターフェイスも使用できない場合は、パラメーターがないと見なすことができます。

1. 各パラメーターに対して `AddParameterEntry` を呼び出して、パラメーターを追加し、設定します。

1. 行セットを開きますが、bind パラメーターを**false**に設定します。

1. `GetColumnInfo` を呼び出して、出力列を取得します。 `AddBindEntry` を使用して、出力列をバインドに追加します。

1. `GetNextResult` を呼び出して、使用可能な行セットがあるかどうかを確認します。 手順 2. ~ 5. を繰り返します。

手動アクセサーの例については、 [DBVIEWER](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Consumer)サンプルの「`CDBListView::CallProcedure`」を参照してください。

## <a name="see-also"></a>参照

[アクセサーの使用](../../data/oledb/using-accessors.md)
