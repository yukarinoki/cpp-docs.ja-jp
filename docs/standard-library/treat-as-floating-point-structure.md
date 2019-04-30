---
title: treat_as_floating_point 構造体
ms.date: 11/04/2016
f1_keywords:
- chrono/std::chrono::treat_as_floating_point
ms.assetid: d0a2161c-bbb2-4924-8961-7568d5ad5434
ms.openlocfilehash: 1b7b58983032ee74ed3d88feb7325cd537e1cc2f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62411943"
---
# <a name="treatasfloatingpoint-structure"></a>treat_as_floating_point 構造体

`Rep` を浮動小数点型として扱うことができるかどうかを指定します。

## <a name="syntax"></a>構文

```cpp
template <class Rep>
struct treat_as_floating_point : is_floating_point<Rep>;
```

## <a name="remarks"></a>Remarks

`Rep` は、特殊化 `treat_as_floating_point<Rep>` が [true_type](../standard-library/type-traits-typedefs.md#true_type) から派生したときにのみ浮動小数点型として処理できます。 このテンプレート クラスは、ユーザー定義型に特殊化することができます。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<chrono >

**名前空間:** std::chrono

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<chrono>](../standard-library/chrono.md)<br/>
