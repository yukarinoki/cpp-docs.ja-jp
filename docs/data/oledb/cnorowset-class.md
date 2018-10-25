---
title: CNoRowset クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.CNoRowset
- ATL::CNoRowset<TAccessor>
- CNoRowset
- ATL.CNoRowset<TAccessor>
- ATL::CNoRowset
dev_langs:
- C++
helpviewer_keywords:
- CNoRowset class
ms.assetid: 55c6c7a4-9e3a-4775-a2dd-c8b333012fa6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f14ad79e1cbd2207b4eb1582cb80e0107d68ec39
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50064239"
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