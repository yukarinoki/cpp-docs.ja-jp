---
title: Crowset::movefirst |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CRowset<TAccessor>::MoveFirst
- ATL::CRowset::MoveFirst
- CRowset<TAccessor>.MoveFirst
- CRowset::MoveFirst
- CRowset.MoveFirst
- ATL.CRowset.MoveFirst
- ATL.CRowset<TAccessor>.MoveFirst
- ATL::CRowset<TAccessor>::MoveFirst
dev_langs:
- C++
helpviewer_keywords:
- MoveFirst method
ms.assetid: a17c0799-ead9-4d85-9a1d-8b17188d01e3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 811e2cdc18711c85cbb2a43e555a273bf3f50d81
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33091785"
---
# <a name="crowsetmovefirst"></a>CRowset::MoveFirst
最初の位置にカーソルを移動し、最初の行を取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT MoveFirst() throw();  
  
```  
  
## <a name="return-value"></a>戻り値  
 標準の `HRESULT`。  
  
## <a name="remarks"></a>コメント  
 呼び出し[irowset::restartposition](https://msdn.microsoft.com/en-us/library/ms712877.aspx)を初期位置 (行セットの作成時に、次のフェッチ位置をした位置) に次のフェッチ位置の位置を変更して、最初の行を取得します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CRowset クラス](../../data/oledb/crowset-class.md)   
 [CRowset::MoveNext](../../data/oledb/crowset-movenext.md)   
 [CRowset::MoveToBookmark](../../data/oledb/crowset-movetobookmark.md)   
 [CRowset::MovePrev](../../data/oledb/crowset-moveprev.md)   
 [CRowset::MoveLast](../../data/oledb/crowset-movelast.md)   
 [IRowset::RestartPosition](https://msdn.microsoft.com/en-us/library/ms712877.aspx)