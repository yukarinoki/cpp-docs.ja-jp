---
title: Cutlprops::setpropvalue |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- SetPropValue
- ATL::CUtlProps<T>::SetPropValue
- ATL.CUtlProps<T>.SetPropValue
- ATL.CUtlProps.SetPropValue
- CUtlProps::SetPropValue
- CUtlProps<T>::SetPropValue
- CUtlProps.SetPropValue
- CUtlProps<T>.SetPropValue
- ATL::CUtlProps::SetPropValue
dev_langs:
- C++
helpviewer_keywords:
- SetPropValue method
ms.assetid: 69a703c0-f640-4ca3-8850-0c4e75d52429
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 73f2432a23adf8fe11f759c2caa85d9653040635
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cutlpropssetpropvalue"></a>CUtlProps::SetPropValue
プロパティ セットのプロパティを設定します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT SetPropValue(const GUID* pguidPropSet,  
   DBPROPID dwPropId,  
   VARIANT* pvValue);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pguidPropSet`  
 [in]PropSet の GUID です。  
  
 `dwPropId`  
 [in]プロパティのインデックス。  
  
 `pvValue`  
 [in]新しいプロパティ値を含んでいるバリアントへのポインター。  
  
## <a name="return-value"></a>戻り値  
 `Failure` エラー発生時に、`S_OK`正常終了した場合。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>関連項目  
 [CUtlProps クラス](../../data/oledb/cutlprops-class.md)