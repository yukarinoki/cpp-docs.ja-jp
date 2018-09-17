---
title: SafeLessThan |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeLessThan
dev_langs:
- C++
helpviewer_keywords:
- SafeLessThan function
ms.assetid: 9d85bc0d-8d94-4d59-9b72-ef3c63a120a0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 88f734cbcee303741858c933d1c3729720f0e76f
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45710308"
---
# <a name="safelessthan"></a>SafeLessThan

1 つの数値が他よりも小さいかどうかを判断します。

## <a name="syntax"></a>構文

```cpp
template<typename T, typename U>
inline bool SafeLessThan (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>パラメーター

*t*<br/>
[in]最初の数値。 これは、型でなければなりません`T`します。

*u*<br/>
[in]2 番目の数値。 これは、型でなければなりません`U`します。

## <a name="return-value"></a>戻り値

**true**場合*t*がより小さい*u*。 そうしないと**false**します。

## <a name="remarks"></a>Remarks

このメソッドでは、ため、標準的な比較演算子が強化されます**SafeLessThan**数の 2 つの異なる型を比較することができます。

このメソッドの一部は、 [SafeInt ライブラリ](../windows/safeint-library.md)のインスタンスを作成せず、単一の比較操作のものでは、 [SafeInt クラス](../windows/safeint-class.md)します。

> [!NOTE]
> このメソッドは、単一の数値演算を保護する必要がありますにのみ使用する必要があります。 使用する必要があります複数の操作がある場合、`SafeInt`個々 のスタンドアロン関数を呼び出すのではなく、クラス。

テンプレートの種類の詳細については`T`と`U`を参照してください[SafeInt 関数](../windows/safeint-functions.md)します。

## <a name="requirements"></a>要件

**ヘッダー:** safeint.h

**Namespace:** Microsoft::Utilities

## <a name="see-also"></a>関連項目

[SafeInt 関数](../windows/safeint-functions.md)  
[SafeInt ライブラリ](../windows/safeint-library.md)  
[SafeInt クラス](../windows/safeint-class.md)  
[SafeLessThanEquals](../windows/safelessthanequals.md)  
[SafeGreaterThan](../windows/safegreaterthan.md)  
[SafeGreaterThanEquals](../windows/safegreaterthanequals.md)