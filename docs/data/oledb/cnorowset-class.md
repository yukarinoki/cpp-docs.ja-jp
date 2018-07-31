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
ms.openlocfilehash: e92c9bfb49bbb64faca633f04bb87f40028b6e1e
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2018
ms.locfileid: "39339563"
---
# <a name="cnorowset-class"></a>CNoRowset クラス
テンプレート引数として使用できます (`TRowset`) の[CCommand](../../data/oledb/ccommand-class.md)または[CTable](../../data/oledb/ctable-class.md)します。  
  
## <a name="syntax"></a>構文

```cpp
template <class TAccessor = CAccessorBase>  
class CNoRowset  
```  
  
### <a name="parameters"></a>パラメーター  
 *TAccessor*  
 アクセサー クラス。 既定値は `CAccessorBase` です。  
  
## <a name="remarks"></a>Remarks  
 使用`CNoRowset`コマンドが行セットを返さない場合は、テンプレート引数として。  
  
 `CNoRowset` 次のスタブ メソッドは、それぞれのメソッドに対応するその他のアクセサー クラスを実装します。  
  
-   `BindFinished` -バインドが完了したことを示します (返します`S_OK`)。  
  
-   `Close` -行と、現在の IRowset インターフェイスを解放します。  
  
-   `GetIID` -接続ポイントのインターフェイス ID を取得します。  
  
-   `GetInterface` -インターフェイスを取得します。  
  
-   `GetInterfacePtr` -カプセル化されたインターフェイス ポインターを取得します。  
  
-   `SetAccessor` -アクセサーにポインターを設定します。  
  
-   `SetupOptionalRowsetInterfaces` -行セットの省略可能なインターフェイスを設定します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)