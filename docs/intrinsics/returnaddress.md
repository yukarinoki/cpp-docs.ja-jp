---
description: '詳細については、次を参照してください: _ReturnAddress'
title: _ReturnAddress
ms.date: 09/02/2019
f1_keywords:
- _ReturnAddress
helpviewer_keywords:
- _ReturnAddress intrinsic
- ReturnAddress intrinsic
ms.assetid: 7f4a5811-35e6-4f64-ba7c-21203380eeda
ms.openlocfilehash: abb6b879c466372fce0ecbeb7371101e3a3ef82b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143742"
---
# <a name="_returnaddress"></a>_ReturnAddress

**Microsoft 固有の仕様**

組み込みは、呼び出し `_ReturnAddress` 元に制御が戻った後に実行される呼び出し元関数の命令のアドレスを提供します。

次のプログラムをビルドし、デバッガーでステップスルーします。 プログラムをステップ実行するときに、から返されたアドレスをメモしておき `_ReturnAddress` ます。 次に、が使用された関数から制御が戻った直後に、「 `_ReturnAddress` [方法: [逆アセンブル] ウィンドウを使用する」](/visualstudio/debugger/how-to-use-the-disassembly-window) を開いて、次に実行される命令のアドレスがから返されたアドレスと一致することを確認し `_ReturnAddress` ます。

インライン展開などの最適化は、返信先アドレスに影響を与える可能性があります。 たとえば、以下のサンプルプログラムが [/ob1](../build/reference/ob-inline-function-expansion.md)でコンパイルされると、 `inline_func` は呼び出し元の関数にインライン化され `main` ます。 したがって、およびからへの呼び出しで `_ReturnAddress` `inline_func` は、 `main` それぞれ同じ値が生成されます。

`_ReturnAddress` [/Clr](../build/reference/clr-common-language-runtime-compilation.md)でコンパイルされたプログラムでを使用する場合、呼び出しを含む関数 `_ReturnAddress` はネイティブ関数としてコンパイルされます。 を含む関数へのマネージ呼び出しとしてコンパイルされた関数 `_ReturnAddress` `_ReturnAddress` が、予期したとおりに動作しないことがあります。

## <a name="requirements"></a>要件

**ヘッダー ファイル** \<intrin.h>

## <a name="example"></a>例

```cpp
// compiler_intrinsics__ReturnAddress.cpp
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(_ReturnAddress)

__declspec(noinline)
void noinline_func(void)
{
   printf("Return address from %s: %p\n", __FUNCTION__, _ReturnAddress());
}

__forceinline
void inline_func(void)
{
   printf("Return address from %s: %p\n", __FUNCTION__, _ReturnAddress());
}

int main(void)
{
   noinline_func();
   inline_func();
   printf("Return address from %s: %p\n", __FUNCTION__, _ReturnAddress());

   return 0;
}
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_AddressOfReturnAddress](../intrinsics/addressofreturnaddress.md)\
[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)\
[キーワード](../cpp/keywords-cpp.md)
