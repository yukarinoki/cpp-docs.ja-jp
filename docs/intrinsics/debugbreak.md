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
ms.openlocfilehash: b52c34014402a235e03c45f82dcd1e5c542e4919
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62349044"
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
|`__debugbreak`|x86、ARM、x64|\<intrin.h>|

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

このルーチンは、組み込みとしてのみ使用できます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)<br/>
[キーワード](../cpp/keywords-cpp.md)