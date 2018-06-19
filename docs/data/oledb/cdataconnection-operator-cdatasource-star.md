---
title: Cdataconnection::operator CDataSource * |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDataSource*
- CDataConnection::operatorCDataSource*
- CDataConnection.operatorCDataSource*
- operatorCDataSource*
dev_langs:
- C++
helpviewer_keywords:
- CDataSource* operator
- operator * (CDataSource)
ms.assetid: 9118e324-e68d-45c5-a791-03f041d420ed
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: bade9d813fb9804ae353f7c5139f063f278da225
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33095340"
---
# <a name="cdataconnectionoperator-cdatasource"></a>CDataConnection::operator CDataSource*
格納されているポインターを返します`CDataSource`オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```cpp
operator const CDataSource*() throw();  
  
```  
  
## <a name="remarks"></a>コメント  
 この演算子が格納されているへのポインターを返します`CDataSource`を渡すことをすることにより、オブジェクト、`CDataConnection`オブジェクトを`CDataSource`ポインターが必要です。  
  
 参照してください[演算子 CDataSource &](../../data/oledb/cdataconnection-operator-cdatasource-amp.md)使用例についてはします。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CDataConnection クラス](../../data/oledb/cdataconnection-class.md)   
 [CDataConnection::operator CDataSource&](../../data/oledb/cdataconnection-operator-cdatasource-amp.md)