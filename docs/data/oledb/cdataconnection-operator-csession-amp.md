---
title: Cdataconnection::operator CSession&amp; |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CSession&
- CDataConnection::operatorCSession&
- CDataConnection.operatorCSession&
- operatorCSession&
dev_langs:
- C++
helpviewer_keywords:
- operator CSession&
- CSession& operator
ms.assetid: fba1e498-e482-4dda-8e0f-2542163bf627
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7d46aeb352016c41dddaee972d438be8c28e22a9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33095422"
---
# <a name="cdataconnectionoperator-csessionamp"></a>Cdataconnection::operator CSession&amp;
格納されている参照を返します`CSession`オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```cpp
operator const CSession&();  
  
```  
  
## <a name="remarks"></a>コメント  
 この演算子は、包含への参照を返します`CSession`オブジェクトを渡して、`CDataConnection`オブジェクトを`CSession`参照を必要とします。  
  
## <a name="example"></a>例  
 関数がある場合 (など`func`下) を受け取る、`CSession`参照を行うこともできます**CSession &** に渡す、`CDataConnection`オブジェクトの代わりにします。  
  
 [!code-cpp[NVC_OLEDB_Consumer#5](../../data/oledb/codesnippet/cpp/cdataconnection-operator-csession-amp_1.cpp)]  
  
 [!code-cpp[NVC_OLEDB_Consumer#6](../../data/oledb/codesnippet/cpp/cdataconnection-operator-csession-amp_2.cpp)]  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CDataConnection クラス](../../data/oledb/cdataconnection-class.md)   
 [CDataConnection::operator CSession*](../../data/oledb/cdataconnection-operator-csession-star.md)