---
title: Cdynamicstringaccessor::setstring |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDynamicStringAccessor::SetString
- CDynamicStringAccessor.SetString
dev_langs:
- C++
helpviewer_keywords:
- SetString method
ms.assetid: 94846d8b-4c1b-47fe-acdc-1752981cee25
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f5f4b7f9354de7f6c6ad10ba472bfd31873a0355
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cdynamicstringaccessorsetstring"></a>CDynamicStringAccessor::SetString
文字列として指定された列のデータを設定します。  
  
## <a name="syntax"></a>構文  
  
```
HRESULT SetString(DBORDINAL nColumn,  
  BaseType* data) throw();  


HRESULT SetString(const CHAR* pColumnName,  
   BaseType* data) throw();  


HRESULT SetString(const WCHAR* pColumnName,  
   BaseType* data) throw();  
```  
  
#### <a name="parameters"></a>パラメーター  
 `nColumn`  
 [in]列番号。 列番号は、1 から始まります。 0 の特殊な値は、存在する場合に、ブックマーク列を参照します。  
  
 `pColumnName`  
 [in]列の名前を表す文字列へのポインター。  
  
 `data`  
 [in]指定された列に書き込まれる、文字列データへのポインター。  
  
## <a name="return-value"></a>戻り値  
 指定された列を設定する文字列値へのポインター。 値の型は`BaseType`、されます`CHAR`または`WCHAR`かどうかに応じて`_UNICODE`かが定義されています。  
  
## <a name="remarks"></a>コメント  
 オーバーライド フォームは ANSI 文字列として列名を 2 番目と 3 番目のオーバーライド フォームは Unicode 文字列として列名。  
  
 場合`_SECURE_ATL`が定義されている場合、0 以外の値を表示するには、ランタイムのアサーション エラーが生成されます入力`data`文字列は、参照先のデータ列の最大の長さを超えています。 それ以外の場合は許容最大長より長い場合、入力文字列は切り捨てられます。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CDynamicStringAccessor クラス](../../data/oledb/cdynamicstringaccessor-class.md)