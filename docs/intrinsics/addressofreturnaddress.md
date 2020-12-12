---
description: '詳細については、次を参照してください: _AddressOfReturnAddress'
title: _AddressOfReturnAddress
ms.date: 09/02/2019
f1_keywords:
- _AddressOfReturnAddress_cpp
- _AddressOfReturnAddress
helpviewer_keywords:
- _AddressOfReturnAddress intrinsic
- AddressOfReturnAddress intrinsic
ms.assetid: c7e10b8c-445e-4236-a602-e2d90200f70a
ms.openlocfilehash: 1a79ccbe7ddc2865d8225a62cd0d294f0bc66b4a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331933"
---
# <a name="_addressofreturnaddress"></a>_AddressOfReturnAddress

**Microsoft 固有の仕様**

現在の関数の戻りアドレスを保持するメモリ位置のアドレスを提供します。 このアドレスは、他のメモリ位置 (関数の引数など) へのアクセスには使用できません。

## <a name="syntax"></a>構文

```C
void * _AddressOfReturnAddress();
```

## <a name="requirements"></a>必要条件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`_AddressOfReturnAddress`|x86、x64、ARM、ARM64|

**ヘッダー ファイル** \<intrin.h>

## <a name="remarks"></a>解説

`_AddressOfReturnAddress` [/Clr](../build/reference/clr-common-language-runtime-compilation.md)でコンパイルされたプログラムでを使用する場合、呼び出しを含む関数 `_AddressOfReturnAddress` はネイティブ関数としてコンパイルされます。 を含む関数へのマネージ呼び出しとしてコンパイルされた関数 `_AddressOfReturnAddress` `_AddressOfReturnAddress` が、予期したとおりに動作しないことがあります。

このルーチンは、組み込みとしてのみ使用できます。

## <a name="example"></a>例

```cpp
// compiler_intrinsics_AddressOfReturnAddress.cpp
// processor: x86, x64
#include <stdio.h>
#include <intrin.h>

// This function will print three values:
//   (1) The address retrieved from _AddressOfReturnAdress
//   (2) The return address stored at the location returned in (1)
//   (3) The return address retrieved the _ReturnAddress* intrinsic
// Note that (2) and (3) should be the same address.
__declspec(noinline)
void func() {
   void* pvAddressOfReturnAddress = _AddressOfReturnAddress();
   printf_s("%p\n", pvAddressOfReturnAddress);
   printf_s("%p\n", *((void**) pvAddressOfReturnAddress));
   printf_s("%p\n", _ReturnAddress());
}

int main() {
   func();
}
```

```Output
0012FF78
00401058
00401058
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)\
[キーワード](../cpp/keywords-cpp.md)
