---
title: 使用して、インライン アセンブリでのレジスタの維持 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- __asm keyword [C++], register values
- inline assembly, registers
- registers, inline assembly
- preserving registers
ms.assetid: dbcd7360-6f3e-4b22-9ee2-9f65ca6f2543
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8a5db1c9c4facd51b2886d93017ad87a0683b899
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2018
ms.locfileid: "32053419"
---
# <a name="using-and-preserving-registers-in-inline-assembly"></a>インライン アセンブリでのレジスタの使用および保持
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 一般に、考えないでレジスタが指定された値を持つときに、`__asm`ブロックを開始します。 レジスタの値が別の間で保持する保証はありません`__asm`ブロックします。 インライン コードのブロックを終了し、他を開始すると、最初のブロックから値を保持する 2 番目のブロックでのレジスタに依存できません。 `__asm`ブロックは、通常の制御フローからの値の結果を登録内容を継承します。  
  
 使用する場合、`__fastcall`呼び出し規約、コンパイラは渡します関数の引数の代わりにレジスタにスタックにします。 これを持つ関数で問題が生じることができます`__asm`関数にパラメーターがどのサービスに登録を確認する方法があるないためにをブロックします。 関数は、EAX でパラメーターを受信するのには発生し、すぐに EAX で別のものを格納、元のパラメーターは失われます。 さらに、すべての関数を使用して宣言で ECX レジスタを保持する必要がある`__fastcall`です。  
  
 このような登録の競合を避けるためには、使用しない、`__fastcall`を含む関数の規則、`__asm`ブロックします。 指定した場合、`__fastcall`規約/Gr コンパイラ オプションをグローバルに宣言を含むすべての関数、`__asm`ブロックを`__cdecl`または`__stdcall`です。 (、`__cdecl`属性がその関数の C の呼び出し規約を使用するようにコンパイラに指示します)。いないをコンパイルする場合に/Gr、回避を持つ関数を宣言する、`__fastcall`属性。  
  
 使用する場合`__asm`C と C++ の関数では、アセンブリ言語を書き込みは、EAX、EBX、ECX、EDX、ESI、または EDI レジスタを保持する必要はありません。 たとえば、POWER2 で。C の例で[インライン アセンブリで関数の作成](../../assembler/inline/writing-functions-with-inline-assembly.md)、`power2`関数は、EAX レジスタに値を保持しません。 ただし、これらのレジスタの使用に影響はコードの品質レジスタ アロケーターが全体で値を格納する使用できないため`__asm`ブロックします。 さらに、インライン アセンブラー コードで EBX、ESI または EDI を使用すると、保存し、関数プロローグおよびエピローグ内のこれらのレジスタを復元するコンパイラを強制します。  
  
 スコープ (DS、SS、SP、BP、フラグ レジスタなど) を使用するその他のレジスタを保持する必要があります、`__asm`ブロックします。 (たとえば、スタックを切り替える) に変更をいくつかの理由がない限り、ESP および EBP レジスタが保持する必要があります。 参照してください[インライン アセンブリの最適化](../../assembler/inline/optimizing-inline-assembly.md)です。  
  
 いくつか SSE 型には、強制的にスタック配置の動的なコードを出力するコンパイラ スタックの 8 バイト アラインメントが必要です。 配置後に、ローカル変数と関数のパラメーターの両方にアクセスできるようにするには、コンパイラは、2 つのフレーム ポインターを保持します。  コンパイラは、フレーム ポインターの省略 (FPO) を実行する場合、EBP と ESP が使用されます。  コンパイラが FPO を実行していない場合、EBX と EBP が使用されます。 コードの実行を正しくようにするには、関数では、フレーム ポインターを変更できなかったと動的スタック配置が必要な場合は、asm コードで EBX を変更しないでください。 関数から 8 バイトのアラインされた型を移動するか、EBX は使用しないでください。  
  
> [!NOTE]
>  インライン アセンブリ コードは、STD または CLD 命令を使用して方向フラグを変更する場合は、元の値にフラグを復元する必要があります。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [インライン アセンブラー](../../assembler/inline/inline-assembler.md)