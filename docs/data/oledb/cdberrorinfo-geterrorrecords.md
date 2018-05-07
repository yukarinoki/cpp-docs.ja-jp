---
title: Cdberrorinfo::geterrorrecords |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDBErrorInfo.GetErrorRecords
- ATL.CDBErrorInfo.GetErrorRecords
- ATL::CDBErrorInfo::GetErrorRecords
- GetErrorRecords
- CDBErrorInfo::GetErrorRecords
dev_langs:
- C++
helpviewer_keywords:
- GetErrorRecords method
ms.assetid: 07746774-bcca-4833-8f55-a619e9777c17
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 33e0ab54bc3da570aecba0df347e14a511b0a833
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cdberrorinfogeterrorrecords"></a>CDBErrorInfo::GetErrorRecords
指定したオブジェクトのエラー レコードを取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetErrorRecords(IUnknown* pUnk,   
   const IID& iid,   
   ULONG* pcRecords) throw();  


HRESULT GetErrorRecords(ULONG* pcRecords) throw();  
```  
  
#### <a name="parameters"></a>パラメーター  
 *pUnk*  
 [in]エラー レコードを取得する対象のオブジェクトへのインターフェイスします。  
  
 `iid`  
 [in]エラーに関連付けられているインターフェイスの IID です。  
  
 *pcRecords*  
 [out]エラー レコードの (1 から始まる) の数へのポインター。  
  
## <a name="return-value"></a>戻り値  
 標準の `HRESULT`。  
  
## <a name="remarks"></a>コメント  
 エラー情報を取得するには、どのインターフェイスを確認する場合は、関数の最初の形式を使用します。 それ以外の場合、2 番目の形式を使用します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CDBErrorInfo クラス](../../data/oledb/cdberrorinfo-class.md)