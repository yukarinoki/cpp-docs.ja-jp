---
description: '詳細情報: is_rvalue_reference クラス'
title: is_rvalue_reference クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_rvalue_reference
helpviewer_keywords:
- is_rvalue_reference class
- is_rvalue_reference
ms.assetid: 40a97072-7b5c-4274-9154-298d3dcf064a
ms.openlocfilehash: 1fb3de556f3a8b1b9aa70034a23e5e487336cd56
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339039"
---
# <a name="is_rvalue_reference-class"></a>is_rvalue_reference クラス

型が右辺値参照かどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
struct is_rvalue_reference;
```

### <a name="parameters"></a>パラメーター

*~*\
照会する型。

## <a name="remarks"></a>解説

型 *Ty* が [右辺値参照](../cpp/rvalue-reference-declarator-amp-amp.md)である場合、この型述語のインスタンスは true を保持します。

## <a name="requirements"></a>要件

**ヘッダー:**\<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)\
[左辺値と右辺値](../cpp/lvalues-and-rvalues-visual-cpp.md)
