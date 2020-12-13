---
description: '詳細情報: コンパイラの警告 (レベル 1) C4789'
title: コンパイラの警告 (レベル 1) C4789
ms.date: 03/25/2019
f1_keywords:
- C4789
helpviewer_keywords:
- C4789
ms.assetid: 5800c301-5afb-4af0-85c1-ceb54d775234
ms.openlocfilehash: c08264b1790788c2eaba7857f473a5bff42a2da3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334963"
---
# <a name="compiler-warning-level-1-c4789"></a>コンパイラの警告 (レベル 1) C4789

> サイズが *N* バイトのバッファー '*identifier*' がオーバーランします。*M* バイトはオフセット *L* から書き込まれます

## <a name="remarks"></a>解説

特定の C ランタイム (CRT) 関数が使用されている場合、 **C4789** はバッファーオーバーランについて警告します。 また、パラメーターが渡されたときや割り当てが行われたときに、サイズの不一致を報告することもできます。 コンパイル時にデータサイズがわかっている場合は、警告が発生する可能性があります。 この警告は、一般的なデータ サイズの不一致の検出が回避されるような状況のためのものです。

**C4789** は、コンパイル時に小さすぎることがわかっているデータブロックにデータがコピーされるときに警告を出します。

この警告は、次のいずれかの CRT 関数の組み込み形式をコピーで使用した場合に発生します。

- [strcpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)

- [memset](../../c-runtime-library/reference/memset-wmemset.md)

- [memcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md)、 [wmemcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md)

また、パラメーターをより大きなデータ型にキャストしてから、左辺値参照からコピー割り当てを作成した場合にも、警告が表示されます。

Visual C++ では、実行されないコードパスに対してこの警告が生成されることがあります。 次の例に示すように、`#pragma` を使用して、警告を一時的に無効にすることができます。

```cpp
#pragma warning( push )
#pragma warning( disable : 4789 )
// unused code that generates compiler warning C4789`
#pragma warning( pop )
```

この表現形式は、その特定のコードブロックに対して警告を生成することを Visual C++ します。 `#pragma warning(push)` は、`#pragma warning(disable: 4789)` によって変更される前に、既存の状態を維持します。 `#pragma warning(pop)` はプッシュされた状態を復元し、`#pragma warning(disable:4789)` の効果を削除します。 C++ プリプロセッサディレクティブの詳細につい `#pragma` ては、「 [warning](../../preprocessor/warning.md) [ディレクティブと Pragma ディレクティブ」および「__Pragma キーワード](../../preprocessor/pragma-directives-and-the-pragma-keyword.md)」を参照してください。

## <a name="examples"></a>例

次の例では C4789 が生成されます。

```cpp
// C4789.cpp
// compile with: /Oi /W1 /c
#include <string.h>
#include <stdio.h>

int main()
{
    char a[20];
    strcpy(a, "0000000000000000000000000\n");   // C4789

    char buf2[20];
    memset(buf2, 'a', 21);   // C4789

    char c;
    wchar_t w = 0;
    memcpy(&c, &w, sizeof(wchar_t));
}
```

次の例でも C4789 が生成されます。

```cpp
// C4789b.cpp
// compile with: /W1 /O2 /c
// processor: x86
short G;

int main()
{
   int * p = (int *)&G;
   *p = 3;   // C4789 - writes an int through a pointer to short
}
```
