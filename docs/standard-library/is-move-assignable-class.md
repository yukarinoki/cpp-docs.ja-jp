---
title: is_move_assignable クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_move_assignable
helpviewer_keywords:
- is_move_assignable
ms.assetid: f33137f2-0639-4912-8745-bc0f9fd18d28
ms.openlocfilehash: da4734507bac14ecf0278117deb7668518305be0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62351067"
---
# <a name="ismoveassignable-class"></a>is_move_assignable クラス

型が移動代入可能であるかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class T>
struct is_move_assignable;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
照会する型。

## <a name="remarks"></a>Remarks

型への右辺値参照を型の参照に割り当てる事ができる場合、その型は移動代入可能です。 型述語は `is_assignable<T&, T&&>` と同じです。 移動代入できる型には、コンパイラにより生成された移動代入演算子またはユーザー定義の移動代入演算子を含む参照可能なスカラー型やクラス型があります。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
