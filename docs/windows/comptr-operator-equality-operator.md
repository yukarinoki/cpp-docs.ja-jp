---
title: Comptr::operator = = 演算子 |Microsoft ドキュメント
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
ms.openlocfilehash: 703204541a05c260e77562729703677b98fb8e9d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33883356"
---
# <a name="comptroperator-operator"></a>ComPtr::operator== 演算子
2 つの ComPtr オブジェクトが等しいかどうかを示します。  
  
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
  
#### <a name="parameters"></a>パラメーター  
 `a`  
 ComPtr オブジェクトへの参照。  
  
 `b`  
 もう 1 つの ComPtr オブジェクトへの参照。  
  
## <a name="return-value"></a>戻り値  
 最初の演算子によって生成`true`場合オブジェクト`a`がオブジェクトと等しい`b`、それ以外の`false`します。  
  
 2 番目と 3 番目の演算子の yield`true`場合オブジェクト`a`と等しい`nullptr`、それ以外の`false`します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::wrl Namespace](../windows/microsoft-wrl-namespace.md)   
 [ComPtr クラス](../windows/comptr-class.md)