---
title: _ _ptr32、_ _ptr64 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __ptr32_cpp
- __ptr64_cpp
dev_langs:
- C++
helpviewer_keywords:
- __ptr64 keyword [C++]
- _ptr32 keyword [C++]
- ptr32 keyword [C++]
- ptr64 keyword [C++]
- _ptr64 keyword [C++]
- __ptr32 keyword [C++]
ms.assetid: afb563d8-7458-4fe7-9c30-bd4b5385a59f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5746c8f54a51e24bad23dcb66f6648266e2e4b56
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2018
ms.locfileid: "34704816"
---
# <a name="ptr32-ptr64"></a>__ptr32、__ptr64

**Microsoft 固有の仕様**

`__ptr32` は 32 ビット システムのネイティブ ポインターを表し、`__ptr64` は、64 ビット システムのネイティブ ポインターを表します。

次の例は、これらのポインター型のそれぞれを宣言する方法を示します。

```cpp
int * __ptr32 p32;
int * __ptr64 p64;
```

 32 ビット システムでは、`__ptr64` で宣言されたポインターは 32 ビット ポインターに切り詰められます。 64 ビット システムでは、`__ptr32` で宣言されたポインターは 64 ビットのポインター型に変換されます。

> [!NOTE]
> 使用することはできません`__ptr32`または`__ptr64`でコンパイルするときに **/clr: 純粋な**します。 それ以外の場合、コンパイラ エラー C2472 が生成されます。 **/Clr: 純粋な**と **/clr:safe**コンパイラ オプションが Visual Studio 2015 では廃止され、Visual Studio 2017 でサポートされていません。

## <a name="example"></a>例

次の例は、`__ptr32` キーワードと `__ptr64` キーワードを持つポインターを宣言して割り当てる方法を示します。

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

- [基本的な型](../cpp/fundamental-types-cpp.md)