---
title: _ReturnAddress
ms.date: 11/04/2016
f1_keywords:
- _ReturnAddress
helpviewer_keywords:
- _ReturnAddress intrinsic
- ReturnAddress intrinsic
ms.assetid: 7f4a5811-35e6-4f64-ba7c-21203380eeda
ms.openlocfilehash: e5013b20f9e7ed0349d940d9be61cc1b4afc95d4
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59041138"
---
# <a name="returnaddress"></a>_ReturnAddress

## <a name="microsoft-specific"></a>Microsoft 固有の仕様

`_ReturnAddress`組み込みコントロールが呼び出し元に戻った後に実行される呼び出し元の関数の命令のアドレスを提供します。

次のプログラムと、デバッガーでステップをビルドします。 プログラムをステップ実行するから返されるアドレスに注意してください`_ReturnAddress`します。 その後、関数から取得した直後に、`_ReturnAddress`が開き、使用、[方法。[逆アセンブル] ウィンドウを使用して](/visualstudio/debugger/how-to-use-the-disassembly-window)から返されたアドレスが実行される次の命令のアドレスに一致することに注意してくださいと`_ReturnAddress`します。

インライン展開月などの最適化に影響するリターン アドレス。 たとえば、次のサンプル プログラムをコンパイルした場合[/Ob1](../build/reference/ob-inline-function-expansion.md)、`inline_func`は呼び出し元の関数をインラインになります`main`します。 そのため、呼び出しを`_ReturnAddress`から`inline_func`と`main`それぞれ同じの値が生成されます。

ときに`_ReturnAddress`でコンパイルされたプログラムで使用[/clr](../build/reference/clr-common-language-runtime-compilation.md)、関数を含む、`_ReturnAddress`呼び出しは、ネイティブ関数としてコンパイルされます。 含まれる関数呼び出しとして関数をコンパイルするときに管理されている`_ReturnAddress`、`_ReturnAddress`期待どおりに動作しない可能性があります。

## <a name="requirements"></a>必要条件

**ヘッダー ファイル** \<intrin.h >

## <a name="example"></a>例

```
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

[_AddressOfReturnAddress](../intrinsics/addressofreturnaddress.md)<br/>
[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)<br/>
[キーワード](../cpp/keywords-cpp.md)