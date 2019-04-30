---
title: is_constructible クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_constructible
helpviewer_keywords:
- is_constructible
ms.assetid: 7cdec5ff-73cf-4f78-a9db-ced2e9c0fd7f
ms.openlocfilehash: c921efd5b7e12873ce986952029ae39f118ad763
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62336856"
---
# <a name="isconstructible-class"></a>is_constructible クラス

指定した引数型の使用時に型を構築できるかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class T, class... Args>
struct is_constructible;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
照会する型。

*Args*<br/>
引数の型のコンス トラクターで一致するように*T*します。

## <a name="remarks"></a>Remarks

場合、型述語のインスタンスは true を保持型*T*の引数の型を使用して構築できる*Args*、それ以外の場合は false を保持します。 型*T*を構築できる場合は、変数定義`T t(std::declval<Args>()...);`が整形式。 両方*T*とすべての種類で*Args*完全な型は、必要があります**void**、または不明なバインドの配列。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
