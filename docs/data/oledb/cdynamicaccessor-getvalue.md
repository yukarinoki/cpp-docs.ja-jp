---
title: Cdynamicaccessor::getvalue |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- GetValue
- CDynamicAccessor::GetValue<ctype>
- ATL.CDynamicAccessor.GetValue<ctype>
- CDynamicAccessor.GetValue
- CDynamicAccessor::GetValue
- ATL.CDynamicAccessor.GetValue
- ATL::CDynamicAccessor::GetValue
- ATL::CDynamicAccessor::GetValue<ctype>
dev_langs:
- C++
helpviewer_keywords:
- GetValue method
ms.assetid: 553f44af-68bc-4cb6-8774-e0940003fa90
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7e43707d4697fbbeece5475f71b7e2f93e731772
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33096419"
---
# <a name="cdynamicaccessorgetvalue"></a>CDynamicAccessor::GetValue
指定された列のデータを取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp
void* GetValue(DBORDINAL nColumn) const throw();  

void* GetValue(const CHAR* pColumnName) const throw();  

void* GetValue(const WCHAR* pColumnName) const throw();  

template < class ctype >
bool GetValue(DBORDINAL nColumn, ctype* pData) const throw();  

template < class ctype >  
bool GetValue(const CHAR* pColumnName, ctype* pData) const throw();  

template < class ctype >  
bool GetValue(const WCHAR* pColumnName, ctype* pData) const throw();  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ctype`  
 [in]文字列型を除く任意のデータ型を処理するテンプレート パラメーター (**CHAR\***、 **WCHAR\***)、特別な処理を必要とします。 `GetValue` ここでの指定に基づいて適切なデータ型を使用します。  
  
 `nColumn`  
 [in]列番号。 列番号は、1 から始まります。 値 0 は、存在する場合に、ブックマーク列を参照します。  
  
 `pColumnName`  
 [in]列の名前。  
  
 `pData`  
 [out]指定された列の内容へのポインター。  
  
## <a name="return-value"></a>戻り値  
 文字列データを渡す場合は、template 宣言されていないバージョンを使用して`GetValue`です。 このメソッドの template 宣言されていないバージョンを返す**void\***、指定された列のデータを格納しているバッファーの一部を指しています。 返します**NULL**列が見つからない場合。  
  
 その他のすべてのデータ型は、テンプレート化されたバージョンを使用する方が簡単`GetValue`です。 テンプレート化されたバージョンを返す**true**成功した場合または**false**エラー発生時にします。  
  
## <a name="remarks"></a>コメント  
 Template 宣言されていないバージョンを使用して、文字列およびその他のデータ型を含む列のテンプレート化されたバージョンを含む列を返します。  
  
 デバッグ モードで表示されるアサーション場合のサイズ`pData`が指している列のサイズと等しくないです。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CDynamicAccessor クラス](../../data/oledb/cdynamicaccessor-class.md)