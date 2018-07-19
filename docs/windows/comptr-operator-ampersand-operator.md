---
title: Comptr::operator&amp;演算子 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::operator&
dev_langs:
- C++
helpviewer_keywords:
- operator& operator
ms.assetid: 2d77fda6-f4b2-45c1-8a0e-fbc355013531
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0bfe8cf9091d888c33420f53f584ca5509d80527
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33872407"
---
# <a name="comptroperatoramp-operator"></a>Comptr::operator&amp;演算子
これに関連付けられているインターフェイスを解放`ComPtr`オブジェクトし、のアドレスを取得し、`ComPtr`オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```cpp  
Details::ComPtrRef<WeakRef> operator&()  
  
const Details::ComPtrRef<const WeakRef> operator&() const  
```  
  
## <a name="return-value"></a>戻り値  
 現在への弱い参照`ComPtr`です。  
  
## <a name="remarks"></a>コメント  
 このメソッドが異なる[comptr::getaddressof](../windows/comptr-getaddressof-method.md)点で、このメソッドは、インターフェイス ポインターへの参照を解放します。 使用して`ComPtr::GetAddressOf`インターフェイス ポインターのアドレスを必要なものの、そのインターフェイスを解放したくないとき。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [ComPtr クラス](../windows/comptr-class.md)