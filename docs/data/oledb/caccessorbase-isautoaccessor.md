---
title: Caccessorbase::isautoaccessor |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IsAutoAccessor
- CAccessorBase.IsAutoAccessor
- CAccessorBase::IsAutoAccessor
dev_langs:
- C++
helpviewer_keywords:
- IsAutoAccessor method
ms.assetid: c330da15-2947-4050-ad00-8f776adc58fb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: fabf5d182b6fb0eb993300e241ae76e1b61f5cef
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="caccessorbaseisautoaccessor"></a>CAccessorBase::IsAutoAccessor
移動操作中にデータが自動的に取得アクセサーの場合は true を返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
      bool IsAutoAccessor(ULONG nAccessor) const;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `nAccessor`  
 [in]アクセサーのゼロ オフセットの数です。  
  
## <a name="return-value"></a>戻り値  
 返します**true**アクセサーが自動場合。 それ以外の場合は **false**を返します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CAccessorBase クラス](../../data/oledb/caccessorbase-class.md)