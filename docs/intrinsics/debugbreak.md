---
title: __debugbreak
ms.date: 11/04/2016
f1_keywords:
- __debugbreak_cpp
- __debugbreak
helpviewer_keywords:
- breakpoints, __debugbreak intrinsic
- __debugbreak intrinsic
ms.assetid: 1d1e1c0c-891a-4613-ae4b-d790094ba830
ms.openlocfilehash: 97932dfe0e187a13b72ae5fe70d761224721c3ff
ms.sourcegitcommit: 1acb6755e11379026a96f63facac4d33f4dc47ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/21/2019
ms.locfileid: "67314251"
---
# <a name="debugbreak"></a>__debugbreak

**Microsoft 固有の仕様**

コードのブレークポイントを発生させます。ここで、デバッガーを実行するように求めるメッセージがユーザーに表示されます。

## <a name="syntax"></a>構文

```
void __debugbreak();
```

## <a name="requirements"></a>必要条件

|組み込み|アーキテクチャ|Header|
|---------------|------------------|------------|
|`__debugbreak`|x86、x64、ARM、ARM64|\<intrin.h>|

## <a name="remarks"></a>Remarks

`__debugbreak`コンパイラと同様に、組み込み[DebugBreak](https://msdn.microsoft.com/library/windows/desktop/ms679297.aspx)は、移植可能な Win32 手法でブレークポイントを発生します。

> [!NOTE]
>  コンパイルするときに **/clr**を含む関数`__debugbreak`は MSIL にコンパイルされます。 `asm int 3` により、関数がネイティブにコンパイルされます。 詳細については、次を参照してください。 [_ _asm](../assembler/inline/asm.md)します。

例えば:

```
main() {
   __debugbreak();
}
```

上記のコードは、以下と似ています。

```
main() {
   __asm {
      int 3
   }
}
```

このコードは x86 コンピューターにあります。

ARM64 で、`__debugbreak`組み込み命令にコンパイルされます`brk #0xF000`します。

このルーチンは、組み込みとしてのみ使用できます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)<br/>
[キーワード](../cpp/keywords-cpp.md)
