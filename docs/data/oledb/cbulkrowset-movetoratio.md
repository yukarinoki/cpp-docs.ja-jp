---
title: Cbulkrowset::movetoratio |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CBulkRowset.MoveToRatio
- ATL::CBulkRowset::MoveToRatio
- MoveToRatio
- CBulkRowset::MoveToRatio
- ATL.CBulkRowset<TAccessor>.MoveToRatio
- ATL::CBulkRowset<TAccessor>::MoveToRatio
- ATL.CBulkRowset.MoveToRatio
- CBulkRowset<TAccessor>::MoveToRatio
dev_langs:
- C++
helpviewer_keywords:
- MoveToRatio method
ms.assetid: 86be60f5-9341-44c1-8e1e-9174c082d0d5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0ab702781ed47a4520b53e9698319b5c245e2dfc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33093361"
---
# <a name="cbulkrowsetmovetoratio"></a>CBulkRowset::MoveToRatio
行セット内の小数部の位置から始まる行がフェッチされます。  
  
## <a name="syntax"></a>構文  
  
```
HRESULT MoveToRatio(DBCOUNTITEM nNumerator,  
   DBCOUNTITEM nDenominator)throw();  
```  
  
#### <a name="parameters"></a>パラメーター  
 `nNumerator`  
 [in]データをフェッチするための小数部の位置を決定するための分子です。  
  
 `nDenominator`  
 [in]分母では、元のデータをフェッチする小数部の位置を決定するために使用します。  
  
## <a name="return-value"></a>戻り値  
 標準の `HRESULT`。  
  
## <a name="remarks"></a>コメント  
 `MoveToRatio` 次の数式に従ってほぼ行がフェッチされます。  
  
 `(nNumerator *  RowsetSize ) / nDenominator`  
  
 ここで`RowsetSize`行数で指定された、行セットのサイズです。 この式の精度は、特定のプロバイダーによって異なります。 詳細については、「 [::getrowsatratio](https://msdn.microsoft.com/en-us/library/ms709602.aspx)で、 *OLE DB プログラマーズ リファレンス*です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CBulkRowset クラス](../../data/oledb/cbulkrowset-class.md)