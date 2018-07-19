---
title: Crowset::movetoratio |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- MoveToRatio
- CRowset<TAccessor>::MoveToRatio
- CRowset::MoveToRatio
- CRowset<TAccessor>.MoveToRatio
- ATL.CRowset.MoveToRatio
- ATL::CRowset::MoveToRatio
- CRowset.MoveToRatio
- ATL.CRowset<TAccessor>.MoveToRatio
- ATL::CRowset<TAccessor>::MoveToRatio
dev_langs:
- C++
helpviewer_keywords:
- MoveToRatio method
ms.assetid: 1fa313bd-8fd1-4608-8e85-44993b97dd88
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9c864933070af4f2a40572d0133027fb81f0855a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33096666"
---
# <a name="crowsetmovetoratio"></a>CRowset::MoveToRatio
行セット内の小数部の位置から始まる行がフェッチされます。  
  
## <a name="syntax"></a>構文  
  
```
HRESULT MoveToRatio(DBCOUNTITEM nNumerator,   
   DBCOUNTITEM nDenominator,bool bForward = true) throw();  
```  
  
#### <a name="parameters"></a>パラメーター  
 `nNumerator`  
 [in]小数部を決定するため、分子元となるデータをフェッチする位置を指定します。  
  
 `nDenominator`  
 [in]分母の小数部を決定するためデータをフェッチする位置を指定します。  
  
 `bForward`  
 [in]前方または後方に移動するかどうかを示します。 既定値は順方向です。  
  
## <a name="return-value"></a>戻り値  
 標準の `HRESULT`。  
  
## <a name="remarks"></a>コメント  
 `MoveToRatio` 次の数式にほぼに従って行がフェッチされます。  
  
 `(nNumerator *  RowsetSize ) / nDenominator`  
  
 ここで`RowsetSize`行数で指定された、行セットのサイズです。 この式の精度は、特定のプロバイダーによって異なります。 詳細については、「 [::getrowsatratio](https://msdn.microsoft.com/en-us/library/ms709602.aspx)です。  
  
 このメソッドには、省略可能なインターフェイスが必要とする`IRowsetScroll`、する可能性がありますすべてのプロバイダーでサポートされていない以外の場合は、そうでは、返されます**E_NOINTERFACE**です。 設定する必要もあります**DBPROP_IRowsetScroll**に`VARIANT_TRUE`呼び出す前に**開く**テーブルまたは行セットを含むコマンドをします。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CRowset クラス](../../data/oledb/crowset-class.md)