---
title: アセンブリ言語のコメント
ms.date: 08/30/2018
helpviewer_keywords:
- assembly language [C++], comments
- comments [C++], assembly language
- macros [C++], assembly language
- __asm keyword [C++], instructions
ms.assetid: 0dc10850-77f5-426e-9dab-185ea28e06e4
ms.openlocfilehash: a8b2c98c61d58d72e78dbffd4f3b6ed7707d2d7a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80169605"
---
# <a name="assembly-language-comments"></a>アセンブリ言語のコメント

**Microsoft 固有の仕様**

`__asm` ブロック内の指示では、アセンブリ言語のコメントを使用できます。

```cpp
__asm mov ax, offset buff ; Load address of buff
```

C マクロは1つの論理行に展開されるので、マクロではアセンブリ言語のコメントを使用しないようにしてください。 (「 [C マクロとしての __Asm ブロックの定義」を](../../assembler/inline/defining-asm-blocks-as-c-macros.md)参照してください)。`__asm` ブロックに C スタイルのコメントを含めることもできます。詳細については、「 [Using C++ C or In a __asm block](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)」を参照してください。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[__asm ブロックでのアセンブリ言語の使用](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>
