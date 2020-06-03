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
ms.openlocfilehash: c82d756690c6c2a719cb03f458c471aa44e3d5b5
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80211732"
---
# <a name="cnoaccessor-class"></a>CNoAccessor クラス

は、アクセサークラスの引数を必要とする `CCommand` や `CTable`などのテンプレートクラスのテンプレート引数 (`TAccessor`) として使用できます。

## <a name="syntax"></a>構文

```cpp
class CNoAccessor
```

## <a name="remarks"></a>解説

クラスでパラメーターまたは出力列がサポートされないようにする場合は、テンプレート引数として `CNoAccessor` を使用します。

`CNoAccessor` は、次のスタブメソッドを実装します。これらはそれぞれ、他のアクセサークラスのメソッドに対応します。

- `BindColumns`-列をアクセサーにバインドします。

- `BindParameters`-作成されたパラメーターを列にバインドします。

- `Bind`-バインドを作成します。

- `Close`-アクセサーを閉じます。

- `ReleaseAccessors`-クラスによって作成されたアクセサーを解放します。

- `FreeRecordMemory`-解放する必要がある現在のレコード内のすべての列を解放します。

- `GetColumnInfo`-開かれた行セットから列情報を取得します。

- `GetNumAccessors`-クラスによって作成されたアクセサーの数を取得します。

- `IsAutoAccessor`-移動操作中にアクセサーに対してデータが自動的に取得される場合に true を返します。

- `GetHAccessor`-指定されたアクセサーのアクセサーハンドルを取得します。

- `GetBuffer`-ブックマークバッファーへのポインターを取得します。

- `NoBindOnNullRowset`-空の行セットでのデータバインディングを防止します。

## <a name="requirements"></a>必要条件

**ヘッダー:** atldbcli.h

## <a name="see-also"></a>参照

[OLE DB コンシューマー テンプレートに関するページ](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)
