---
title: Cdataconnection::operator CSession * |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDataConnection.operatorCSession*
- CDataConnection::operatorCSession*
- operatorCSession*
- CSession*
dev_langs:
- C++
helpviewer_keywords:
- operator CSession*
- CSession* operator
ms.assetid: 0b0feede-5c3e-4835-be5b-03651597014d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 97219418f18220cde84c80cb9052f17552a3a45d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cdataconnectionoperator-csession"></a>CDataConnection::operator CSession*
格納されているポインターを返します`CSession`オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```cpp
operator const CSession*() throw();  
  
```  
  
## <a name="remarks"></a>コメント  
 この演算子が格納されているへのポインターを返します`CSession`を渡すことをすることにより、オブジェクト、`CDataConnection`オブジェクトを`CSession`ポインターが必要です。  
  
## <a name="example"></a>例  
 参照してください[演算子 CSession &](../../data/oledb/cdataconnection-operator-csession-amp.md)使用例についてはします。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CDataConnection クラス](../../data/oledb/cdataconnection-class.md)   
 [CDataConnection::operator CSession&](../../data/oledb/cdataconnection-operator-csession-amp.md)