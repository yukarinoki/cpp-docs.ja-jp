---
title: アセンブリ言語のコメント |Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- assembly language [C++], comments
- comments [C++], assembly language
- macros [C++], assembly language
- __asm keyword [C++], instructions
ms.assetid: 0dc10850-77f5-426e-9dab-185ea28e06e4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 02f4c493bac5c2a066dc0b24e2a566d49345288d
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43683327"
---
# <a name="assembly-language-comments"></a>アセンブリ言語のコメント

**Microsoft 固有の仕様**

」の手順に、`__asm`ブロックは、アセンブリ言語のコメントを使用できます。

```cpp
__asm mov ax, offset buff ; Load address of buff
```

C マクロを 1 論理行に展開するためは、マクロのアセンブリ言語のコメントを使用しないでください。 (を参照してください[_ _asm ブロックの C マクロとして定義](../../assembler/inline/defining-asm-blocks-as-c-macros.md))。`__asm`ブロックすることもできます C スタイルのコメントを含めることが。 詳細については、次を参照してください。[を使用して C または C++ _ _asm ブロックで](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)します。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[__asm ブロックでのアセンブリ言語の使用](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>