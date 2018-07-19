---
title: Caccessorbase::gethaccessor |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- GetHAccessor
- CAccessorBase::GetHAccessor
- CAccessorBase.GetHAccessor
dev_langs:
- C++
helpviewer_keywords:
- GetHAccessor method
ms.assetid: 1bb98762-0752-4aae-a0b6-ba96bec03621
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2bacc7f24d112fc6714200c6347e66bb66866831
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33088786"
---
# <a name="caccessorbasegethaccessor"></a>CAccessorBase::GetHAccessor
指定されたアクセサーのアクセサー ハンドルを取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp
      HACCESSOR GetHAccessor(ULONG nAccessor) const;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `nAccessor`  
 [in]アクセサーのゼロ オフセットの数です。  
  
## <a name="return-value"></a>戻り値  
 アクセサーのハンドルです。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CAccessorBase クラス](../../data/oledb/caccessorbase-class.md)