---
title: <span>
description: 標準テンプレートライブラリ (STL) スパン名前空間の API リファレンス。連続した一連のオブジェクトに対して簡易ビューを提供します。
ms.date: 05/28/2020
f1_keywords:
- <span>
helpviewer_keywords:
- span header
ms.openlocfilehash: 6f8a7e6ecbc02adeae7301dfc7eead2812c3c1f5
ms.sourcegitcommit: bac5dde649d5b0447de1d26a73365e36d74595f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "107381156"
---
# `<span>`

は、 `span` 連続した一連のオブジェクトに対するビューです。 高速および境界の安全なアクセスを提供します。 またはとは異なり `vector` `array` 、アクセスを提供する要素を "所有" することはできません。

詳細については、 [span クラス](span-class.md) を参照してください。 スパンを使用する方法の例を次に示します。

```cpp
#include <span>
#include <iostream>

void Show(std::span<int> someValues)
{
    // show values in reverse
    for (auto rIt = someValues.rbegin(); rIt != someValues.rend(); ++rIt)
    {
        std::cout << *rIt;
    }

    // show a subspan
    for (auto& i : someValues.subspan(1, 2))
    {
        std::cout << i;
    }
}

int main()
{
    int numbers[]{ 0,1,2,3,4 };
    Show(numbers); // note conversion from array to span
}
```

## <a name="requirements"></a>要件

**ヘッダー:**\<span>

**名前空間:** std

**コンパイラオプション:** [/std: c + + latest](../build/reference/std-specify-language-standard-version.md)

## <a name="members"></a>メンバー

### <a name="classes"></a>クラス

|名前|説明|
|-|:-|
|[スパン](span-class.md)| 連続した一連のオブジェクトに対するビューを提供します。 |

### <a name="operators"></a>オペレーター

|名前|説明|
|-|:-|
|[operator =](span-class.md#op_eq)| スパンの割り当て |
|[operator\[\]](span-class.md#op_at)| 要素アクセス |

### <a name="functions"></a>関数

|名前|説明|
|-|:-|
| [as_bytes](span-functions.md#as_bytes)| スパンの基になる読み取り専用のバイトを取得します。 |
| [as_writable_bytes](span-functions.md#as_writable_bytes) | スパンの基になるバイトを取得します。 |

### <a name="constants"></a>定数

|名前|説明|
|-|:-|
| **dynamic_extent** | スパンサイズがコンパイル時ではなく実行時に決定されることを示します。 スパン内の要素の数がコンパイル時にわかっている場合は、テンプレートパラメーターとして指定され `Extent` ます。 ランタイムまでの数値がわからない場合は、代わりにを指定し `dynamic_extent` ます。 |

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)
