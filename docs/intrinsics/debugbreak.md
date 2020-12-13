---
description: '詳細については、次を参照してください: __debugbreak'
title: __debugbreak
ms.date: 09/02/2019
f1_keywords:
- __debugbreak_cpp
- __debugbreak
helpviewer_keywords:
- breakpoints, __debugbreak intrinsic
- __debugbreak intrinsic
ms.assetid: 1d1e1c0c-891a-4613-ae4b-d790094ba830
ms.openlocfilehash: 83a670d9fa9c1f6b41c1c405c59af71c7aa0c8a1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337108"
---
# <a name="__debugbreak"></a>__debugbreak

**Microsoft 固有の仕様**

コードのブレークポイントを発生させます。ここで、デバッガーを実行するように求めるメッセージがユーザーに表示されます。

## <a name="syntax"></a>構文

```C
void __debugbreak();
```

## <a name="requirements"></a>必要条件

|Intrinsic|アーキテクチャ|ヘッダー|
|---------------|------------------|------------|
|`__debugbreak`|x86、x64、ARM、ARM64|\<intrin.h>|

## <a name="remarks"></a>解説

`__debugbreak` [DebugBreak](/windows/win32/api/debugapi/nf-debugapi-debugbreak)のようなコンパイラ組み込みは、移植可能な Win32 によってブレークポイントを発生させます。

> [!NOTE]
> **/Clr** を指定してコンパイルすると、を含む関数 `__debugbreak` が MSIL にコンパイルされます。 `asm int 3` により、関数がネイティブにコンパイルされます。 詳細については、「 [__asm](../assembler/inline/asm.md)」を参照してください。

次に例を示します。

```C
main() {
   __debugbreak();
}
```

上記のコードは、以下と似ています。

```C
main() {
   __asm {
      int 3
   }
}
```

このコードは x86 コンピューターにあります。

ARM64 では、 `__debugbreak` 組み込みは命令にコンパイルされ `brk #0xF000` ます。

このルーチンは、組み込みとしてのみ使用できます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)\
[キーワード](../cpp/keywords-cpp.md)
