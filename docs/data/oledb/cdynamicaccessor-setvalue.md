---
title: Cdynamicaccessor::setvalue |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.CDynamicAccessor.SetValue
- ATL::CDynamicAccessor::SetValue
- ATL::CDynamicAccessor::SetValue<ctype>
- CDynamicAccessor.SetValue
- ATL.CDynamicAccessor.SetValue<ctype>
- CDynamicAccessor::SetValue
- CDynamicAccessor::SetValue<ctype>
dev_langs:
- C++
helpviewer_keywords:
- SetValue method
ms.assetid: ecc18850-96e5-4845-abe5-ab34ad467238
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9322394f2b72b49afe988c371858d9ee580825ab
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33095678"
---
# <a name="cdynamicaccessorsetvalue"></a>CDynamicAccessor::SetValue
指定された列にデータを格納します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
template <class ctype>
bool SetValue(   
   DBORDINAL nColumn,   
   constctype& data) throw( );  

template <class ctype>    
bool SetValue(   
   const CHAR * pColumnName,   
   const ctype& data) throw( );  

template <class ctype>   
bool SetValue(  
   const WCHAR *pColumnName,  
   const ctype& data) throw( );  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ctype`  
 [in]文字列型を除く任意のデータ型を処理するテンプレート パラメーター (**CHAR\***、 **WCHAR\***)、特別な処理を必要とします。 `GetValue` ここでの指定に基づいて適切なデータ型を使用します。  
  
 `pColumnName`  
 [in]列名を含む文字列へのポインター。  
  
 `data`  
 [in]データを含むメモリへのポインター。  
  
 `nColumn`  
 [in]列番号。 列番号は、1 から始まります。 値 0 は、存在する場合に、ブックマーク列を参照します。  
  
## <a name="return-value"></a>戻り値  
 文字列データを設定する場合は、template 宣言されていないバージョンを使用して`GetValue`です。 このメソッドの template 宣言されていないバージョンを返す**void\***、指定された列のデータを格納しているバッファーの一部を指しています。 返します**NULL**列が見つからない場合。  
  
 その他のすべてのデータ型は、テンプレート化されたバージョンを使用する方が簡単`GetValue`です。 テンプレート化されたバージョンを返す**true**成功した場合または**false**エラー発生時にします。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CDynamicAccessor クラス](../../data/oledb/cdynamicaccessor-class.md)