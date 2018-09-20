---
title: _ _debugbreak |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __debugbreak_cpp
- __debugbreak
dev_langs:
- C++
helpviewer_keywords:
- breakpoints, __debugbreak intrinsic
- __debugbreak intrinsic
ms.assetid: 1d1e1c0c-891a-4613-ae4b-d790094ba830
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f2ba9322f4fe94c1c857b0494dc79b417e5d65d8
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46433897"
---
# <a name="debugbreak"></a>__debugbreak

**Microsoft 固有の仕様**

コードのブレークポイントを発生させます。ここで、デバッガーを実行するように求めるメッセージがユーザーに表示されます。

## <a name="syntax"></a>構文

```
void __debugbreak();
```

## <a name="requirements"></a>要件

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