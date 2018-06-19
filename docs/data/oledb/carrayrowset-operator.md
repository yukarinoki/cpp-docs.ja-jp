---
title: 'Carrayrowset: |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CArrayRowset::operator[]
- CArrayRowset.operator[]
dev_langs:
- C++
helpviewer_keywords:
- operator [], arrays
- '[] operator'
- operator[], arrays
ms.assetid: 3bb8c310-cc1e-46e8-9711-9b565488acaa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 755e484f430f47eb072e3c590bfbee8471984bb6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33089128"
---
# <a name="carrayrowsetoperator"></a>CArrayRowset::operator
行セット内の行にアクセスするためには、配列に似た構文を提供します。  
  
## <a name="syntax"></a>構文  
  
```cpp
      TAccessor  
      & operator[](int nrow);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `TAccessor`  
 行セットに格納されているアクセサーの種類を指定するテンプレート パラメーター。  
  
 `nRow`  
 [in] (配列) にアクセスする、行の数です。  
  
## <a name="return-value"></a>戻り値  
 要求された行の内容。  
  
## <a name="remarks"></a>コメント  
 場合`nRow`行セット内の行の数を超えると、例外がスローされます。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CArrayRowset クラス](../../data/oledb/carrayrowset-class.md)