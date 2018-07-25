---
title: Hstring::getaddressof メソッド |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::GetAddressOf
dev_langs:
- C++
ms.assetid: 6050decf-5f99-49f0-9497-1c8192c485ae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7d4804373045d12c2e251e2de61b7aefd52ec916
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33874669"
---
# <a name="hstringgetaddressof-method"></a>HString::GetAddressOf メソッド
基になる HSTRING ハンドルへのポインターを取得します。  
  
## <a name="syntax"></a>構文  
  
```  
HSTRING* GetAddressOf() throw()  
```  
  
## <a name="return-value"></a>戻り値  
 基になる HSTRING ハンドルへのポインター。  
  
## <a name="remarks"></a>コメント  
 この操作の後に、文字列、基になる HSTRING ハンドルの値は破棄されます。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>関連項目  
 [HString クラス](../windows/hstring-class.md)