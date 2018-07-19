---
title: __func__ |Microsoft ドキュメント
ms.custom: ''
ms.date: 10/19/2017
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __func__
dev_langs:
- C++
ms.assetid: a5299b8d-f0ee-4af2-91dd-8fb165e68798
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3d78a249fe5b111c17c29895edcdc3fa5ba2f27a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32413596"
---
# <a name="func"></a>__func__

**(C++ 11)** 事前定義の識別子&#95; &#95;func&#95; &#95; 、外側の関数の非修飾かつ非装飾名を含む文字列として暗黙的に定義されています。 &#95;&#95;func&#95; &#95;は、C++ 標準で必須であり、Microsoft 拡張機能ではありません。

## <a name="syntax"></a>構文

```cpp
__func__
```

## <a name="return-value"></a>戻り値

返します。 null で終わる const char する文字の配列、関数名が含まれています。

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