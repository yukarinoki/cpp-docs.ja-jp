---
description: '詳細情報: CNoRowset クラス'
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
ms.openlocfilehash: 4cdb4631b63ec1f013183713900ffd9574d90fc3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97307562"
---
# <a name="cnorowset-class"></a>CNoRowset クラス

は、 `TRowset` [CCommand](../../data/oledb/ccommand-class.md) または [CTable](../../data/oledb/ctable-class.md)のテンプレート引数 () として使用できます。

## <a name="syntax"></a>構文

```cpp
template <class TAccessor = CAccessorBase>
class CNoRowset
```

### <a name="parameters"></a>パラメーター

*TAccessor*<br/>
アクセサークラス。 既定値は、`CAccessorBase` です。

## <a name="remarks"></a>Remarks

`CNoRowset`コマンドが行セットを返さない場合は、テンプレート引数としてを使用します。

`CNoRowset` では、次のスタブメソッドが実装されています。これらはそれぞれ、他のアクセサークラスのメソッドに対応しています。

- `BindFinished` -バインドが完了したことを示します (を返し `S_OK` ます)。

- `Close` -行と現在の IRowset インターフェイスを解放します。

- `GetIID` -接続ポイントのインターフェイス ID を取得します。

- `GetInterface` -インターフェイスを取得します。

- `GetInterfacePtr` -カプセル化されたインターフェイスポインターを取得します。

- `SetAccessor` -アクセサーへのポインターを設定します。

- `SetupOptionalRowsetInterfaces` -行セットのオプションのインターフェイスを設定します。

## <a name="requirements"></a>要件

**ヘッダー:** atldbcli.h

## <a name="see-also"></a>関連項目

[OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB コンシューマーテンプレートリファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)
