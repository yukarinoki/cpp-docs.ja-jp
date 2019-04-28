---
title: __ptr32、__ptr64
ms.date: 10/09/2018
f1_keywords:
- __ptr32_cpp
- __ptr64_cpp
- __ptr32
- __ptr64
- _ptr32
- _ptr64
helpviewer_keywords:
- __ptr64 keyword [C++]
- _ptr32 keyword [C++]
- ptr32 keyword [C++]
- ptr64 keyword [C++]
- _ptr64 keyword [C++]
- __ptr32 keyword [C++]
ms.assetid: afb563d8-7458-4fe7-9c30-bd4b5385a59f
ms.openlocfilehash: 0e979ed51f9c34700cef75113018c23e69a304f9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62244464"
---
# <a name="ptr32-ptr64"></a>__ptr32、__ptr64

**Microsoft 固有の仕様**

**_ _ptr32** 32 ビット システムでネイティブ ポインターを表すときに **_ _ptr64**の 64 ビット システムでネイティブ ポインターを表します。

次の例は、これらのポインター型のそれぞれを宣言する方法を示します。

```cpp
int * __ptr32 p32;
int * __ptr64 p64;
```

32 ビット システムで宣言されたポインター **_ _ptr64**は 32 ビット ポインターに切り詰められます。 64 ビット システムで宣言されたポインター **_ _ptr32**は 64 ビット ポインターに変換します。

> [!NOTE]
> 使用することはできません **_ _ptr32**または **_ _ptr64**でコンパイルするときに **/clr: 純粋な**します。 それ以外の場合、コンパイラ エラー C2472 が生成されます。 **/Clr: 純粋な**と **/clr:safe**コンパイラ オプションは Visual Studio 2015 で非推奨とされ、Visual Studio 2017 でサポートされていません。

以前のバージョンとの互換性のため **_ptr32**と **_ptr64**のシノニムで **_ _ptr32**と **_ _ptr64**しない限り、コンパイラ オプション[/Za\(言語拡張機能を無効にする)](../build/reference/za-ze-disable-language-extensions.md)を指定します。

## <a name="example"></a>例

次の例を宣言のポインターの割り当てでは、 **_ _ptr32**と **_ _ptr64**キーワード。

```cpp
#include <cstdlib>
#include <iostream>

int main()
{
    using namespace std;

    int * __ptr32 p32;
    int * __ptr64 p64;

    p32 = (int * __ptr32)malloc(4);
    *p32 = 32;
    cout << *p32 << endl;

    p64 = (int * __ptr64)malloc(4);
    *p64 = 64;
    cout << *p64 << endl;
}
```

```Output
32
64
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[基本的な型](../cpp/fundamental-types-cpp.md)