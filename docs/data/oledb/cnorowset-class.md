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
ms.openlocfilehash: 513e393bbc782d87b37dab108428f2970fbb92e8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50644458"
---
# <a name="cnorowset-class"></a>CNoRowset クラス

テンプレート引数として使用できます (`TRowset`) の[CCommand](../../data/oledb/ccommand-class.md)または[CTable](../../data/oledb/ctable-class.md)します。

## <a name="syntax"></a>構文

```cpp
template <class TAccessor = CAccessorBase>
class CNoRowset
```

### <a name="parameters"></a>パラメーター

*TAccessor*<br/>
アクセサー クラス。 既定値は `CAccessorBase` です。

## <a name="remarks"></a>Remarks

使用`CNoRowset`コマンドが行セットを返さない場合は、テンプレート引数として。

`CNoRowset` 次のスタブ メソッドは、それぞれのメソッドに対応するその他のアクセサー クラスを実装します。

- `BindFinished` -バインドが完了したことを示します (返します`S_OK`)。

- `Close` -行と、現在の IRowset インターフェイスを解放します。

- `GetIID` -接続ポイントのインターフェイス ID を取得します。

- `GetInterface` -インターフェイスを取得します。

- `GetInterfacePtr` -カプセル化されたインターフェイス ポインターを取得します。

- `SetAccessor` -アクセサーにポインターを設定します。

- `SetupOptionalRowsetInterfaces` -行セットの省略可能なインターフェイスを設定します。

## <a name="requirements"></a>必要条件

**ヘッダー:** atldbcli.h

## <a name="see-also"></a>関連項目

[OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)