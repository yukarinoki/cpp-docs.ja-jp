---
description: '詳細については、次を参照してください: nullopt_t 構造体'
title: nullopt_t 構造体
ms.date: 08/04/2019
f1_keywords:
- optional/std::nullopt_t
- optional/std::nullopt
ms.openlocfilehash: 7a597dcc5f15843f125dc7572dc4c5694320f0bb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338109"
---
# <a name="nullopt_t-struct"></a>nullopt_t 構造体

`nullopt_t`型は、[オプション](optional-class.md)のオブジェクトに値が含まれていないことを示すために使用される一意の空の型です。

型の定数は、 `nullopt` `nullopt_t` `optional` 型が初期化されていない状態であることを示します。 オブジェクトを初期化する `optional` か、またはオブジェクトと比較するために使用できます。

## <a name="syntax"></a>構文

```cpp
struct nullopt_t;
inline constexpr nullopt_t nullopt{ /*implementation-defined*/ };
```

## <a name="see-also"></a>関連項目

[\<optional>](optional.md)\
[optional クラス](optional-class.md)
