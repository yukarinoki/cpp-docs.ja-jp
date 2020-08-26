---
title: '&lt;スパン&gt;'
ms.date: 05/28/2020
f1_keywords:
- <span>
helpviewer_keywords:
- span header
ms.openlocfilehash: 7d21023c90472e5c2e1b28d9fa85e517da4a21ae
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88846187"
---
# <a name="ltspangt"></a>&lt;スパン&gt;

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

## <a name="requirements"></a>必要条件

**ヘッダー:**\<span>

**名前空間:** std

**コンパイラオプション:** /std: c + + latest

## <a name="members"></a>メンバー

### <a name="classes"></a>クラス

|名前|説明|
|-|:-|
|[スパン](span-class.md)| 連続した一連のオブジェクトに対するビューを提供します。 |

### <a name="operators"></a>演算子

|名前|説明|
|-|:-|
|[operator =](span-class.md#op_eq)| スパンの割り当て |
|[operator\[\]](span-class.md#op_at)| 要素アクセス |

### <a name="functions"></a>Functions

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
