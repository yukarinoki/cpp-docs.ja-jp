---
title: Cdynamicaccessor::setstatus |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDynamicAccessor::SetStatus
- ATL::CDynamicAccessor::SetStatus
- CDynamicAccessor.SetStatus
- ATL.CDynamicAccessor.SetStatus
dev_langs:
- C++
helpviewer_keywords:
- SetStatus method
ms.assetid: 6db82694-e87d-4bf8-a7e3-5765cf6abff9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7bf0fd390699d83261cf52651a3dc16613fa70d2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33098421"
---
# <a name="cdynamicaccessorsetstatus"></a>CDynamicAccessor::SetStatus
指定された列の状態を設定します。  
  
## <a name="syntax"></a>構文  
  
```
bool SetStatus(DBORDINAL nColumn,   
   DBSTATUS status)throw();  

bool SetStatus(const CHAR* pColumnName,   
   DBSTATUS status) throw();  

bool SetStatus(const WCHAR* pColumnName,   
   DBSTATUS status) throw();  
```  
  
#### <a name="parameters"></a>パラメーター  
 `nColumn`  
 [in]列番号。 列番号は、1 から始まります。 値 0 は、存在する場合に、ブックマーク列を参照します。  
  
 *status*  
 [in]列の状態。 参照してください[DBSTATUS](https://msdn.microsoft.com/en-us/library/ms722617.aspx)で、 *OLE DB プログラマーズ リファレンス*詳細についてはします。  
  
 `pColumnName`  
 [in]列名を含む文字列へのポインター。  
  
## <a name="return-value"></a>戻り値  
 返します**true**指定された列の状態が正常に設定されている場合。 この関数を返しますそれ以外の場合、 **false**です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CDynamicAccessor クラス](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicAccessor::GetStatus](../../data/oledb/cdynamicaccessor-getstatus.md)