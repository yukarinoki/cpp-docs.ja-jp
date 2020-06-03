---
title: __func__
ms.date: 10/19/2017
f1_keywords:
- __func__
ms.assetid: a5299b8d-f0ee-4af2-91dd-8fb165e68798
ms.openlocfilehash: 8e94caffe120c325478d8b4f24c1915a516d69f4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80179823"
---
# <a name="__func__"></a>__func__

**(C++ 11)** 定義済みの&#95; &#95;識別子&#95; &#95; func は、外側の関数の修飾されていない名前と非修飾名を含む文字列として暗黙的に定義されます。 &#95;&#95;func&#95; &#95;はC++標準によって義務付けられており、Microsoft の拡張機能ではありません。

## <a name="syntax"></a>構文

```cpp
__func__
```

## <a name="return-value"></a>戻り値

関数名を含む文字の null で終わる const char 配列を返します。

## <a name="example"></a>例

```cpp
#include <string>
#include <iostream>

namespace Test
{
    struct Foo
    {
        static void DoSomething(int i, std::string s)
        {
           std::cout << __func__ << std::endl; // Output: DoSomething
        }
    };
}

int main()
{
    Test::Foo::DoSomething(42, "Hello");

    return 0;
}
```

## <a name="requirements"></a>必要条件

C++11
