---
title: アセンブリ言語のコメント |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 048635a874db604f872b4fa87d72bd06d0455438
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2018
ms.locfileid: "32050764"
---
# <a name="assembly-language-comments"></a>アセンブリ言語のコメント
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 」の手順に、`__asm`ブロックは、アセンブリ言語のコメントを使用できます。  
  
```  
__asm mov ax, offset buff ; Load address of buff  
```  
  
 C マクロは、論理の単一行に展開するためは、マクロ内のアセンブリ言語のコメントを使用しないでください。 (を参照してください[_ _asm ブロックの C マクロとして定義](../../assembler/inline/defining-asm-blocks-as-c-macros.md))。`__asm`ブロックすることもできます C スタイルのコメントを含むです。 詳細については、次を参照してください。[を使用して C または C++ _ _asm ブロックで](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)です。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [__asm ブロックでのアセンブリ言語の使用](../../assembler/inline/using-assembly-language-in-asm-blocks.md)