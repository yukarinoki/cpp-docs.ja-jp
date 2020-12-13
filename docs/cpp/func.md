---
description: 詳細については、「 __func__ 」を参照してください。
title: __func__
ms.date: 10/19/2017
f1_keywords:
- __func__
ms.assetid: a5299b8d-f0ee-4af2-91dd-8fb165e68798
ms.openlocfilehash: 6e075d0f566bb8c3eb72e62a30a36ef80528647b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337713"
---
# <a name="__func__"></a>__func__

**(C++ 11)** &#95;&#95;func&#95;&#95; の定義済み識別子は、外側の関数の修飾されていない名前と非修飾名を含む文字列として暗黙的に定義されます。 &#95;&#95;func&#95;&#95; は C++ 標準によって義務付けられており、Microsoft の拡張機能ではありません。

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

## <a name="requirements"></a>要件

C++11
