---
title: Comptrref::operator! = 演算子 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRef::operator!=
dev_langs:
- C++
ms.assetid: ab3093cc-6fbd-4039-890a-6df1cde992b6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 97a0f98044e18ec6eff1f1b99e9c9178b711e040
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42596024"
---
# <a name="comptrrefoperator-operator"></a>ComPtrRef::operator!= 演算子

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
bool operator!=(
   const Details::ComPtrRef<ComPtr<T>>& a,
   const Details::ComPtrRef<ComPtr<U>>& b
);

bool operator!=(
   const Details::ComPtrRef<ComPtr<T>>& a,
   decltype(__nullptr)  
);

bool operator!=(
   decltype(__nullptr),
   const Details::ComPtrRef<ComPtr<T>>& a
);

bool operator!=(
   const Details::ComPtrRef<ComPtr<T>>& a,
   void* b
);

bool operator!=(
   void* b,
   const Details::ComPtrRef<ComPtr<T>>& a
);
```

### <a name="parameters"></a>パラメーター

*a*  
参照を**ComPtrRef**オブジェクト。

*b*  
別の参照**ComPtrRef**オブジェクト、または匿名のオブジェクトへのポインター (`void*`)。

## <a name="return-value"></a>戻り値

最初の演算子と**true**場合オブジェクト *、* オブジェクトと等しくない*b*、それ以外の**false**します。

2 番目と 3 番目の演算子を生成**true**場合オブジェクト *、* が等しくない**nullptr**、それ以外の**false**します。

4 番目と 5 番目の演算子を生成**true**場合オブジェクト *、* オブジェクトと等しくない*b*、それ以外の**false**します。

## <a name="remarks"></a>Remarks

示す 2 つかどうか**ComPtrRef**オブジェクトが等しくないです。

## <a name="requirements"></a>要件

**ヘッダー:** client.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)  
[ComPtrRef クラス](../windows/comptrref-class.md)