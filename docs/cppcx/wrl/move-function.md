---
title: Move 関数
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::Move
helpviewer_keywords:
- Move function
ms.assetid: c9525426-97e8-4d8c-9877-b689d8a0dc67
ms.openlocfilehash: 65fe85e95453165430c7ef3cfd4c4bb2babd9868
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213708"
---
# <a name="move-function"></a>Move 関数

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

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

参照または rvalue 参照の特徴 (存在する場合) の後のパラメーター*引数*が削除されました。

## <a name="remarks"></a>解説

指定された引数をある場所から別の場所に移動します。

詳細については、「[右辺値参照宣言子: & &](../../cpp/rvalue-reference-declarator-amp-amp.md)」の「**移動セマンティクス**」セクションを参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** 内部 .h

**名前空間:** Microsoft:: WRL::D etails

## <a name="see-also"></a>参照

[Microsoft::WRL::Details 名前空間](microsoft-wrl-details-namespace.md)
