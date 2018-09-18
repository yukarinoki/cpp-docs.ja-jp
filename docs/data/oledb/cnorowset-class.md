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
ms.openlocfilehash: a838bc904a4f09f72962ce7c991bab8e5ac8fcbf
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46074839"
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
  
## <a name="requirements"></a>要件  

**ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  

[OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)