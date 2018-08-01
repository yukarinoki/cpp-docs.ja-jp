---
title: _ _ptr32、_ _ptr64 |Microsoft Docs
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
ms.openlocfilehash: 050317be4c5f933ca9e08055a02555f5597c583c
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2018
ms.locfileid: "39406534"
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