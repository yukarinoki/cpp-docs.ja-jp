---
title: Cutlprops::getpropvalue |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CUtlProps::GetPropValue
- CUtlProps.GetPropValue
- GetPropValue
dev_langs:
- C++
helpviewer_keywords:
- GetPropValue method
ms.assetid: 9a3fbadb-7814-48f7-96a4-b960fc4ecf2e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 00f56c317f9325fa51f7165fc3872b1e4ca6e9da
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cutlpropsgetpropvalue"></a>CUtlProps::GetPropValue
プロパティのセットからプロパティを取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp
      OUT_OF_LINE HRESULT GetPropValue(const GUID* pguidPropSet,  
   DBPROPID dwPropId,  
   VARIANT* pvValue);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pguidPropSet`  
 [in]PropSet の GUID です。  
  
 `dwPropId`  
 [in]プロパティのインデックス。  
  
 `pvValue`  
 [out]新しいプロパティ値を含んでいるバリアントへのポインター。  
  
## <a name="return-value"></a>戻り値  
 `Failure` エラー発生時に、`S_OK`正常終了した場合。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>関連項目  
 [CUtlProps クラス](../../data/oledb/cutlprops-class.md)