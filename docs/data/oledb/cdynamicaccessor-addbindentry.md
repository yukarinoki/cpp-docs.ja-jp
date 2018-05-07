---
title: Cdynamicaccessor::addbindentry |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CDynamicAccessor::AddBindEntry
- AddBindEntry
- CDynamicAccessor.AddBindEntry
- CDynamicAccessor::AddBindEntry
- ATL.CDynamicAccessor.AddBindEntry
dev_langs:
- C++
helpviewer_keywords:
- AddBindEntry method
ms.assetid: 8f139376-7db3-4193-ba3b-63fe938ffa79
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b49af256ea5f2f4fcc87474019c184e4c5babc58
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cdynamicaccessoraddbindentry"></a>CDynamicAccessor::AddBindEntry
出力列にバインド エントリを追加します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT AddBindEntry(const DBCOLUMNINFO& info) throw();  
```  
  
#### <a name="parameters"></a>パラメーター  
 `info`  
 [in]A **DBCOLUMNINFO**列情報を含む構造体。 「DBCOLUMNINFO 構造体」を参照してください[icolumnsinfo::getcolumninfo](https://msdn.microsoft.com/en-us/library/ms722704.aspx)で、 *OLE DB プログラマーズ リファレンス*です。  
  
## <a name="return-value"></a>戻り値  
 標準の`HRESULT`値。  
  
## <a name="remarks"></a>コメント  
 作成された既定のアクセサーをオーバーライドする場合は、このメソッドを使用して`CDynamicAccessor`(を参照してください[データのフェッチ操作方法?](../../data/oledb/fetching-data.md))。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CDynamicAccessor クラス](../../data/oledb/cdynamicaccessor-class.md)