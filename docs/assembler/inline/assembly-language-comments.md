---
title: アセンブリ言語のコメント
ms.date: 08/30/2018
helpviewer_keywords:
- assembly language [C++], comments
- comments [C++], assembly language
- macros [C++], assembly language
- __asm keyword [C++], instructions
ms.assetid: 0dc10850-77f5-426e-9dab-185ea28e06e4
ms.openlocfilehash: fc37658eccd99b61d45aa9a9a7a2675ef90eee89
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50578643"
---
# <a name="assembly-language-comments"></a>アセンブリ言語のコメント

**Microsoft 固有の仕様**

」の手順に、`__asm`ブロックは、アセンブリ言語のコメントを使用できます。

```cpp
__asm mov ax, offset buff ; Load address of buff
```

C マクロを 1 論理行に展開するためは、マクロのアセンブリ言語のコメントを使用しないでください。 (を参照してください[_ _asm ブロックの C マクロとして定義](../../assembler/inline/defining-asm-blocks-as-c-macros.md))。`__asm`ブロックすることもできます C スタイルのコメントを含めることが。 詳細については、[を使用して C または C++ _ _asm ブロックで](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)を参照してください。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[__asm ブロックでのアセンブリ言語の使用](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>