---
title: Comptr::operator = 演算子 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::operator==
dev_langs:
- C++
ms.assetid: 6a26e936-29d4-4b7d-b44a-7c575ad07509
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e68566b5f8fa519a3cfcd5a406cc812edfaf8480
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39648595"
---
# <a name="comptroperator-operator"></a>ComPtr::operator== 演算子
示す 2 つかどうか**ComPtr**オブジェクトが等しい。  
  
## <a name="syntax"></a>構文  
  
```cpp  
bool operator==(  
   const ComPtr<T>& a,  
   const ComPtr<U>& b  
);  
  
bool operator==(  
   const ComPtr<T>& a,  
   decltype(__nullptr)  
);  
  
bool operator==(  
   decltype(__nullptr),  
   const ComPtr<T>& a  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 *a*  
 参照を**ComPtr**オブジェクト。  
  
 *b*  
 別の参照**ComPtr**オブジェクト。  
  
## <a name="return-value"></a>戻り値  
 最初の演算子と**true**場合オブジェクト *、* がオブジェクトと等しい*b*、それ以外の**false**します。  
  
 2 番目と 3 番目の演算子を生成**true**場合オブジェクト *、* と等しい**nullptr**、それ以外の**false**します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::wrl Namespace](../windows/microsoft-wrl-namespace.md)   
 [ComPtr クラス](../windows/comptr-class.md)