---
description: '詳細情報: CNoAccessor クラス'
title: CNoAccessor クラス
ms.date: 11/04/2016
f1_keywords:
- ATL::CNoAccessor
- CNoAccessor
- ATL.CNoAccessor
helpviewer_keywords:
- CNoAccessor class
ms.assetid: eb669ae5-0a56-49a3-9646-c4ae6239da31
ms.openlocfilehash: 624c72c841280ec56bacf0edd29efeb4b1005988
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97170387"
---
# <a name="cnoaccessor-class"></a>CNoAccessor クラス

は、 `TAccessor` `CCommand` アクセサークラスの引数を必要とするやなどのテンプレートクラスのテンプレート引数 () として使用でき `CTable` ます。

## <a name="syntax"></a>構文

```cpp
class CNoAccessor
```

## <a name="remarks"></a>解説

`CNoAccessor`クラスがパラメーターまたは出力列をサポートしないようにする場合は、テンプレート引数としてを使用します。

`CNoAccessor` では、次のスタブメソッドが実装されています。これらはそれぞれ、他のアクセサークラスのメソッドに対応しています。

- `BindColumns` -列をアクセサーにバインドします。

- `BindParameters` -作成されたパラメーターを列にバインドします。

- `Bind` -バインドを作成します。

- `Close` -アクセサーを閉じます。

- `ReleaseAccessors` -クラスによって作成されたアクセサーを解放します。

- `FreeRecordMemory` -解放する必要がある現在のレコード内のすべての列を解放します。

- `GetColumnInfo` -開かれた行セットから列情報を取得します。

- `GetNumAccessors` -クラスによって作成されたアクセサーの数を取得します。

- `IsAutoAccessor` -移動操作中にアクセサーに対してデータが自動的に取得される場合は true を返します。

- `GetHAccessor` -指定されたアクセサーのアクセサーハンドルを取得します。

- `GetBuffer` -ブックマークバッファーへのポインターを取得します。

- `NoBindOnNullRowset` -空の行セットでのデータバインディングを防止します。

## <a name="requirements"></a>要件

**ヘッダー:** atldbcli.h

## <a name="see-also"></a>関連項目

[OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB コンシューマーテンプレートリファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)
