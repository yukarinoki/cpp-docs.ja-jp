---
title: _ _Asm ブロックでの C または C++ の使用 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- inline assembly, mixing instructions with C/C++ statements
- symbols, in __asm blocks
- macros, __asm blocks
- preprocessor directives, used in __asm blocks
- type names, used in __asm blocks
- preprocessor directives
- preprocessor, directives
- constants, in __asm blocks
- comments, in __asm blocks
- typedef names, used in __asm blocks
- __asm keyword [C++], C/C++ elements in
ms.assetid: ae8b2b52-6b75-42e3-ac0c-ad02d922ed97
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5e9451a0b665e5377c2acaf871154ec78a38c8b5
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2018
ms.locfileid: "32051454"
---
# <a name="using-c-or-c-in-asm-blocks"></a>__asm ブロックでの C または C++ の使用
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 インライン アセンブリの命令は、C または C++ ステートメントと混合できる、ため、C または C++ の変数を名前で参照し、それらの言語の他の多くの要素を使用します。  
  
 `__asm`ブロックは、次の言語要素を使用できます。  
  
-   ラベルと変数および関数の名前を含むシンボル  
  
-   定数、シンボリック定数を含むと`enum`メンバー  
  
-   マクロとプリプロセッサ ディレクティブ  
  
-   コメント (両方**/ \* \* /** と**//** )  
  
-   (任意の場所、MASM 型は有効になります) の名前を入力します。  
  
-   `typedef` などの演算子と共に使用される通常名前**PTR**と**型**または構造体または共用体のメンバーを指定するには  
  
 内で、`__asm`ブロック、C の表記またはアセンブラー小数点表記のいずれかの整数定数を指定することができます (0x100 と h 100 は同等ですが、たとえば)。 定義できます (を使用して`#define`) C 内で定数をし、プログラムの C または C++ とアセンブリの両方の部分で使用します。 使用される定数を指定することもできます。 その前に、0、8 進数。 たとえば、0777 は 8 進数の定数を指定します。  
  
## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください  
  
-   [__asm ブロックでの演算子の使用](../../assembler/inline/using-operators-in-asm-blocks.md)  
  
-   [_ _Asm ブロックの C または C++ Symbols_in を使用します。](../../assembler/inline/using-c-or-cpp-symbols-in-asm-blocks.md)  
  
-   [__asm ブロックの C または C++ のデータへのアクセス](../../assembler/inline/accessing-c-or-cpp-data-in-asm-blocks.md)  
  
-   [インライン アセンブリでの関数の記述](../../assembler/inline/writing-functions-with-inline-assembly.md)  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [インライン アセンブラー](../../assembler/inline/inline-assembler.md)