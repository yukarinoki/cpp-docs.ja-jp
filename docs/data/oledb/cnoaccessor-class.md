---
title: CNoAccessor クラス
ms.date: 11/04/2016
f1_keywords:
- ATL::CNoAccessor
- CNoAccessor
- ATL.CNoAccessor
helpviewer_keywords:
- CNoAccessor class
ms.assetid: eb669ae5-0a56-49a3-9646-c4ae6239da31
ms.openlocfilehash: d6eb5aaa9a66f46335b0a364e6c6e79abc297d64
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50647893"
---
# <a name="cnoaccessor-class"></a>CNoAccessor クラス

テンプレート引数として使用できます (`TAccessor`) のテンプレートのクラスなど`CCommand`と`CTable`、アクセサー クラスの引数を必要とします。

## <a name="syntax"></a>構文

```cpp
class CNoAccessor
```

## <a name="remarks"></a>Remarks

使用`CNoAccessor`パラメーターをサポートまたは列を出力するクラスしたくない場合は、テンプレート引数として。

`CNoAccessor` 次のスタブ メソッドは、それぞれのメソッドに対応するその他のアクセサー クラスを実装します。

- `BindColumns` -列は、アクセサーにバインドします。

- `BindParameters` -列に作成されたパラメーターをバインドします。

- `Bind` -バインドを作成します。

- `Close` -アクセサーを閉じます。

- `ReleaseAccessors` -クラスによって作成されたアクセサーを解放します。

- `FreeRecordMemory` -解放する必要がある現在のレコード内の列を解放します。

- `GetColumnInfo` -開かれた行セットから列情報を取得します。

- `GetNumAccessors` -クラスによって作成されたアクセサーの数を取得します。

- `IsAutoAccessor` 移動操作中に、アクセサーのデータが自動的に取得される場合に true を返します。

- `GetHAccessor` -指定されたアクセサーのアクセサーのハンドルを取得します。

- `GetBuffer` -ブックマーク バッファーへのポインターを取得します。

- `NoBindOnNullRowset` -空の行セットのデータ バインディングをできないようにします。

## <a name="requirements"></a>必要条件

**ヘッダー:** atldbcli.h

## <a name="see-also"></a>関連項目

[OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)