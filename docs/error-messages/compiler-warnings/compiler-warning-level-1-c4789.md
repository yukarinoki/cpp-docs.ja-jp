---
title: コンパイラの警告 (レベル 1) C4789
ms.date: 03/25/2019
f1_keywords:
- C4789
helpviewer_keywords:
- C4789
ms.assetid: 5800c301-5afb-4af0-85c1-ceb54d775234
ms.openlocfilehash: 36a5032098c5caabb1b050833e487fd58679a782
ms.sourcegitcommit: 6e4dd21759caaed262a7255735cf8d6e8fb9f4d7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2019
ms.locfileid: "58476854"
---
# <a name="compiler-warning-level-1-c4789"></a>コンパイラの警告 (レベル 1) C4789

> バッファー '*識別子*' のサイズの*N* (バイト) でオーバーランが発生されます。*M*オフセットから始まるバイトが書き込まれます*L*

## <a name="remarks"></a>Remarks

**C4789**特定の C ランタイム (CRT) 関数を使用する場合、バッファー オーバーランについて警告が表示されます。 サイズの不一致がある場合は、パラメーターが渡されるまたは割り当てが行われたときにも報告できます。 警告は、コンパイル時に、データ サイズがわかっている場合は。 この警告は、一般的なデータ サイズの不一致の検出が回避されるような状況のためのものです。

**C4789**ときに警告が表示されます、コンパイル時に小さすぎることが知られているデータ ブロックにデータをコピーします。

コピーは、これらの CRT 関数のいずれかの組み込みの形式を使用している場合、警告が発生します。

- [strcpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)

- [memset](../../c-runtime-library/reference/memset-wmemset.md)

- [memcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md)、 [wmemcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md)

警告には、大きいデータ型、パラメーターをキャストし、左辺値参照からのコピー割り当てを作成するときにも表示されます。

Visual C では、決して実行されるコード パスに対してこの警告を生成可能性があります。 次の例に示すように、`#pragma` を使用して、警告を一時的に無効にすることができます。

```cpp
#pragma warning( push )
#pragma warning( disable : 4789 )
// unused code that generates compiler warning C4789`
#pragma warning( pop )
```

この手法では、その特定のコード ブロックの警告を生成すると Visual C が保持されます。 `#pragma warning(push)` は、`#pragma warning(disable: 4789)` によって変更される前に、既存の状態を維持します。 `#pragma warning(pop)` はプッシュされた状態を復元し、`#pragma warning(disable:4789)` の効果を削除します。 C++ プリプロセッサ ディレクティブの詳細については`#pragma`を参照してください[警告](../../preprocessor/warning.md)と[プラグマ ディレクティブと _ _pragma キーワード](../../preprocessor/pragma-directives-and-the-pragma-keyword.md)します。

## <a name="example"></a>例

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

## <a name="example"></a>例

次の例でも C4789 が生成されます。

```cpp
// C4789b.cpp
// compile with: /W1 /O2 /c
// processor: x86
short G;

void main()
{
   int * p = (int *)&G;
   *p = 3;   // C4789 - writes an int through a pointer to short
}
```