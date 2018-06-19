---
title: CAccessorRowset クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CAccessorRowset
- ATL.CAccessorRowset
- ATL::CAccessorRowset
dev_langs:
- C++
helpviewer_keywords:
- CAccessorRowset class
ms.assetid: bd4f58ed-cebf-4d43-8985-1e5fcbf06953
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 27d2153c6f600c3a5c75c1218e8751baaabcf030
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33090971"
---
# <a name="caccessorrowset-class"></a>CAccessorRowset クラス
行セットと 1 つのクラスに関連付けられているそのアクセサーをカプセル化します。  
  
## <a name="syntax"></a>構文

```cpp
template <class TAccessor = CNoAccessor, 
          template <typename T> class TRowset = CRowset>  
class CAccessorRowset : public TAccessor, public TRowset<TAccessor>  
```  
  
#### <a name="parameters"></a>パラメーター  
 `TAccessor`  
 アクセサー クラス。  
  
 `TRowset`  
 行セット クラスです。  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[バインド](../../data/oledb/caccessorrowset-bind.md)|バインディングが作成 (際に使用される**bBind**で false として指定された[ccommand::open](../../data/oledb/ccommand-open.md))。|  
|[CAccessorRowset](../../data/oledb/caccessorrowset-caccessorrowset.md)|コンストラクターです。|  
|[閉じる](../../data/oledb/caccessorrowset-close.md)|行セットとすべてのアクセサーを閉じます。|  
|[FreeRecordMemory](../../data/oledb/caccessorrowset-freerecordmemory.md)|現在のレコードを解放する必要があるすべての列を解放します。|  
|[GetColumnInfo](../../data/oledb/caccessorrowset-getcolumninfo.md)|実装して[icolumnsinfo::getcolumninfo](https://msdn.microsoft.com/en-us/library/ms722704.aspx)です。|  
  
## <a name="remarks"></a>コメント  
 クラス`TAccessor`アクセサーを管理します。 クラス*TRowset*行セットを管理します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)