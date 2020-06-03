---
title: CNoRowset クラス
ms.date: 11/04/2016
f1_keywords:
- ATL.CNoRowset
- ATL::CNoRowset<TAccessor>
- CNoRowset
- ATL.CNoRowset<TAccessor>
- ATL::CNoRowset
helpviewer_keywords:
- CNoRowset class
ms.assetid: 55c6c7a4-9e3a-4775-a2dd-c8b333012fa6
ms.openlocfilehash: 19a1e01fd29c74cf1c44081c24bf384704cf2acd
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80211473"
---
# <a name="cnorowset-class"></a>CNoRowset クラス

は、 [CCommand](../../data/oledb/ccommand-class.md)または[CTable](../../data/oledb/ctable-class.md)のテンプレート引数 (`TRowset`) として使用できます。

## <a name="syntax"></a>構文

```cpp
template <class TAccessor = CAccessorBase>
class CNoRowset
```

### <a name="parameters"></a>パラメーター

*TAccessor*<br/>
アクセサークラス。 既定では、 `CAccessorBase`です。

## <a name="remarks"></a>解説

コマンドが行セットを返さない場合は、テンプレート引数として `CNoRowset` を使用します。

`CNoRowset` は、次のスタブメソッドを実装します。これらはそれぞれ、他のアクセサークラスのメソッドに対応します。

- `BindFinished`-バインドが完了したことを示します (`S_OK`を返します)。

- `Close`-行と現在の IRowset インターフェイスを解放します。

- `GetIID`-接続ポイントのインターフェイス ID を取得します。

- `GetInterface`-インターフェイスを取得します。

- `GetInterfacePtr`-カプセル化されたインターフェイスポインターを取得します。

- `SetAccessor`-アクセサーへのポインターを設定します。

- `SetupOptionalRowsetInterfaces`-行セットのオプションのインターフェイスを設定します。

## <a name="requirements"></a>必要条件

**ヘッダー:** atldbcli.h

## <a name="see-also"></a>参照

[OLE DB コンシューマー テンプレートに関するページ](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)
