---
title: Cdatasource::getproperty |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CDataSource::GetProperty
- ATL.CDataSource.GetProperty
- CDataSource.GetProperty
- CDataSource::GetProperty
dev_langs:
- C++
helpviewer_keywords:
- GetProperty method
ms.assetid: 6531147c-b164-4ab5-a4a7-509634b85b4d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: afe21f6f41491a4f62eda09e2df43aa470417e20
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cdatasourcegetproperty"></a>CDataSource::GetProperty
接続されているデータ ソース オブジェクトに対して指定されたプロパティの値を返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetProperty(const GUID& guid,   
   DBPROPID propid,   
   VARIANT* pVariant) const throw();  
```  
  
#### <a name="parameters"></a>パラメーター  
 `guid`  
 [in]プロパティを取得する対象のプロパティの設定を識別する GUID。  
  
 `propid`  
 [in]プロパティを返すには、プロパティの ID。  
  
 *pVariant*  
 [out]バリアントを指すポインターを**GetProperty**プロパティの値を返します。  
  
## <a name="return-value"></a>戻り値  
 標準の `HRESULT`。  
  
## <a name="remarks"></a>コメント  
 複数のプロパティを取得する[GetProperties](../../data/oledb/cdatasource-getproperties.md)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CDataSource クラス](../../data/oledb/cdatasource-class.md)