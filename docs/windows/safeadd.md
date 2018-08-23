---
title: SafeAdd |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeAdd
dev_langs:
- C++
helpviewer_keywords:
- SafeAdd function
ms.assetid: 3f82b91d-59fe-4ee1-873b-d056182fa8be
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7e84b76f8079656da3ed19aa2c690bf240854015
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42594357"
---
# <a name="safeadd"></a>SafeAdd

オーバーフローに対する保護できる方法では、2 つの数値を追加します。

## <a name="syntax"></a>構文

```cpp
template<typename T, typename U>
inline bool SafeAdd (
   T t,
   U u,
   T& result
) throw ();
```

### <a name="parameters"></a>パラメーター

[in]*t*  
追加する最初の数値。 これは T 型である必要があります。

[in]*u*  
追加する 2 番目の数値。 これは、型 U のある必要があります。

[out]*結果*  
パラメーターで**SafeAdd**結果を格納します。

## <a name="return-value"></a>戻り値

**true**場合、エラーは発生しません。**false**エラーが発生した場合。

## <a name="remarks"></a>Remarks

このメソッドの一部は、 [SafeInt ライブラリ](../windows/safeint-library.md)のインスタンスを作成せず、1 つの追加操作のものでは、 [SafeInt クラス](../windows/safeint-class.md)します。

> [!NOTE]
> このメソッドは、単一の数値演算を保護する必要がありますにのみ使用する必要があります。 使用する必要があります複数の操作がある場合、`SafeInt`個々 のスタンドアロン関数の呼び出しではなくクラス。

T および U のテンプレートの種類の詳細については、次を参照してください。 [SafeInt 関数](../windows/safeint-functions.md)します。

## <a name="requirements"></a>要件

**ヘッダー:** safeint.h

**Namespace:** Microsoft::Utilities

## <a name="see-also"></a>関連項目

[SafeInt 関数](../windows/safeint-functions.md)  
[SafeInt ライブラリ](../windows/safeint-library.md)  
[SafeInt クラス](../windows/safeint-class.md)  
[SafeSubtract](../windows/safesubtract.md)