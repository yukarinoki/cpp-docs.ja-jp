---
title: アセンブリ言語のコメント
ms.date: 08/30/2018
helpviewer_keywords:
- assembly language [C++], comments
- comments [C++], assembly language
- macros [C++], assembly language
- __asm keyword [C++], instructions
ms.assetid: 0dc10850-77f5-426e-9dab-185ea28e06e4
ms.openlocfilehash: 2e993bd48c7ec801abd440676c80a5bd8f7b42ec
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87192731"
---
# <a name="assembly-language-comments"></a>アセンブリ言語のコメント

**Microsoft 固有の仕様**

ブロック内の命令で **`__asm`** は、アセンブリ言語のコメントを使用できます。

```cpp
__asm mov ax, offset buff ; Load address of buff
```

C マクロは1つの論理行に展開されるので、マクロではアセンブリ言語のコメントを使用しないようにしてください。 (「 [C マクロとしての __Asm ブロックの定義」を](../../assembler/inline/defining-asm-blocks-as-c-macros.md)参照してください)。ブロックには **`__asm`** c スタイルのコメントを含めることもできます。詳細については、「 [__asm ブロックでの c または C++ の使用](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)」を参照してください。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[__Asm ブロックでのアセンブリ言語の使用](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>
