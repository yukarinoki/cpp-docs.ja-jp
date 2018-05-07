---
title: Cdynamicaccessor::getlength |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDynamicAccessor.GetLength
- ATL.CDynamicAccessor.GetLength
- CDynamicAccessor::GetLength
- ATL::CDynamicAccessor::GetLength
dev_langs:
- C++
helpviewer_keywords:
- GetLength method
ms.assetid: 3ae8983b-b267-4cf9-bfc0-3e191f79e646
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: cc7203f030fc3a9ca00839bc9955c85eaa770935
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cdynamicaccessorgetlength"></a>CDynamicAccessor::GetLength
指定された列の長さを取得します。  
  
## <a name="syntax"></a>構文  
  
```
bool GetLength(DBORDINAL nColumn,   
  DBLENGTH* pLength) const throw();  

bool GetLength(const CHAR* pColumnName,   
   DBLENGTH* pLength) const throw();  

bool GetLength(const WCHAR* pColumnName,   
   DBLENGTH* pLength) const throw();  
```  
  
#### <a name="parameters"></a>パラメーター  
 `nColumn`  
 [in]列番号。 列番号は、1 から始まります。 値 0 は、存在する場合に、ブックマーク列を参照します。  
  
 `pColumnName`  
 [in]列名を含む文字列へのポインター。  
  
 `pLength`  
 [out]列の長さ (バイト単位) を含む整数へのポインター。  
  
## <a name="return-value"></a>戻り値  
 返します**true**指定された列が検出された場合。 この関数を返しますそれ以外の場合、 **false**です。  
  
## <a name="remarks"></a>コメント  
 最初のオーバーライドは、列番号を受け取り、2 番目と 3 番目の上書き列名を ANSI または Unicode の形式でそれぞれ行います。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CDynamicAccessor クラス](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicAccessor::SetLength](../../data/oledb/cdynamicaccessor-setlength.md)