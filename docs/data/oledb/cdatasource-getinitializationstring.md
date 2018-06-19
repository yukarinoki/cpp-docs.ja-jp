---
title: Cdatasource::getinitializationstring |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CDataSource::GetInitializationString
- CDataSource.GetInitializationString
- GetInitializationString
- CDataSource::GetInitializationString
- ATL.CDataSource.GetInitializationString
dev_langs:
- C++
helpviewer_keywords:
- GetInitializationString method
ms.assetid: 97134723-6e99-4004-a56d-ec57543dbf3b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c2cc4652dcb7450217fd99969089bdbeb41c3a3f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33094053"
---
# <a name="cdatasourcegetinitializationstring"></a>CDataSource::GetInitializationString
現在開かれているデータ ソースの初期化文字列を取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetInitializationString(BSTR* pInitializationString,   
   bool bIncludePassword = false) throw();  
```  
  
#### <a name="parameters"></a>パラメーター  
 *pInitializationString*  
 [out]初期化文字列へのポインター。  
  
 *bIncludePassword*  
 [in]**true**文字列にパスワードが含まれている場合は、それ以外の場合**false**です。  
  
## <a name="return-value"></a>戻り値  
 標準の `HRESULT`。  
  
## <a name="remarks"></a>コメント  
 結果として得られる初期化文字列を使用して、後でこのデータ ソース接続を再び開くことができます。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CDataSource クラス](../../data/oledb/cdatasource-class.md)