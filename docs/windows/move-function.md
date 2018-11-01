---
title: Move 関数
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::Move
helpviewer_keywords:
- Move function
ms.assetid: c9525426-97e8-4d8c-9877-b689d8a0dc67
ms.openlocfilehash: a53dbbe54cef2ac2557648e66e5d8dafc4fb4768
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50591361"
---
# <a name="move-function"></a>Move 関数

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
template<class T>
inline typename RemoveReference<T>::Type&& Move(
   _Inout_ T&& arg
);
```

### <a name="parameters"></a>パラメーター

*T*<br/>
引数の型。

*arg*<br/>
移動する引数。

## <a name="return-value"></a>戻り値

パラメーター *arg*参照または右辺値参照の特徴の後に存在する場合、削除されました。

## <a name="remarks"></a>Remarks

指定した引数を 1 つの場所から移動します。

詳細については、次を参照してください。、**移動セマンティクス**の[右辺値参照宣言子: & &](../cpp/rvalue-reference-declarator-amp-amp.md)します。

## <a name="requirements"></a>必要条件

**ヘッダー:** internal.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>関連項目

[Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)