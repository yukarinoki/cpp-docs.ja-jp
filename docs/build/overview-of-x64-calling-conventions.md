---
title: 概要の x64 呼び出し規約 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: a05db5eb-0844-4d9d-8b92-b1b2434be0ea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eb4071cd3223ad2ab073f84418e641b515c05112
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374909"
---
# <a name="overview-of-x64-calling-conventions"></a>x64 呼び出し規則の概要
X86 の 2 つの重要な違いと[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]は 64 ビット アドレッシング機能と、一般的な用途のレジスタを 64 ビットの 16 のフラットなセット。 展開した特定の登録のセット、[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]を使用して、 [_ _fastcall](../cpp/fastcall.md)呼び出し規約および RISC ベースの例外処理モデル。 `__fastcall`規則では、最初の 4 つの引数と、スタック フレームのレジスタを使用して、追加の引数を渡します。  
  
 次のコンパイラ オプションでは、アプリケーションを最適化できます[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]:。  
  
-   [/favor (アーキテクチャ固有の最適化)](../build/reference/favor-optimize-for-architecture-specifics.md)  
  
## <a name="calling-convention"></a>呼び出し規則  
 [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]アプリケーション バイナリ インターフェイス (ABI) は、既定では 4 つのレジスタ呼び出しの高速の呼び出し規約を使用します。 領域は、それらのレジスタを保存する呼び出し先のシャドウ ストアとして、呼び出し履歴上に割り当てられます。 関数の呼び出しに引数および引数に使用されるレジスタ間が、厳密な 1 対 1 の対応があります。 8 バイトに収まらないまたは 1、2、4、または 8 バイトではない任意の引数は、参照渡しで渡す必要があります。 1 つの引数を複数のレジスタに分散することはありません。 X87 レジスタ スタックは使用されません。 呼び出し先で使用できますが、考慮すべき揮発性関数呼び出しで。 すべての浮動小数点の操作が完了したら個の XMM レジスタを 16 を使用します。 整数の引数は、RCX、RDX、R8、R9 レジスタに渡されます。 浮動小数点引数は XMM0L、XMM1L、XMM2L、および XMM3L で渡されます。 16 バイトの引数は、参照によって渡されます。 パラメーターの引き渡しはで詳しく説明[パラメーターの引き渡し](../build/parameter-passing.md)です。 これらのレジスタに加えて RAX、R10、R11、XMM4、および XMM5 と見なされます揮発性。 その他のすべてのレジスタは、非揮発性です。 レジスタの使用状況の詳細については[Usage の登録](../build/register-usage.md)と[呼び出し元/呼び出し先保存登録](../build/caller-callee-saved-registers.md)です。  
  
 呼び出し元は、呼び出し先へのパラメーター領域を割り当てる必要があり、呼び出し先はそれほど多くのパラメーターを受け取らない場合でも常に、4 つの登録パラメーターを格納するための十分な領域を割り当てる必要があります。 これには、プロトタイプ宣言されていない C 言語の関数、および vararg C と C++ の関数のサポートが簡略化します。 任意の浮動小数点値をする必要があります vararg またはプロトタイプ宣言されていない関数では、対応する汎用レジスタ内で重複します。 最初の 4 つを超えるすべてのパラメーターは、呼び出しの前に、最初の 4 つのシャドウ ストア上のスタックに格納する必要があります。 Vararg 関数の詳細は含まれて[Varargs](../build/varargs.md)です。 プロトタイプ宣言されていない関数についての詳細については、[プロトタイプ宣言されていない関数](../build/unprototyped-functions.md)です。  
  
## <a name="alignment"></a>アラインメント  
 ほとんどの構造体は、自然な配置を配置します。 プライマリの例外は、スタック ポインターと`malloc`または`alloca`メモリで、パフォーマンスを支援するために、16 バイトに揃えられます。 16 バイトを超える配置を手動で行う必要がありますが、XMM 操作の一般的な配置のサイズを 16 バイトには、これは機能するほとんどのコードにします。 構造体レイアウトと位置合わせの詳細については、次を参照してください。[型とストレージ](../build/types-and-storage.md)です。 スタックのレイアウト方法については、次を参照してください。[スタックの使用](../build/stack-usage.md)です。  
  
## <a name="unwindability"></a>Unwindability  
 リーフ関数は、任意の非 volatile レジスタが変更されない関数です。 非リーフ関数は、関数を呼び出すか、ローカル変数の追加のスタック領域の割り当てによって、非揮発性 RSP をなど、変更可能性があります。 例外を処理するときに非 volatile レジスタを回復するために非リーフ関数は、正しく任意命令に関数をアンワインドする方法を説明する静的データと注釈する必要があります。 このデータは*pdata*、またはプロシージャのデータは、順番を指す*xdata*、例外データを処理します。 Xdata は、アンワインドの情報が含まれています、追加 pdata または例外ハンドラー関数を指すことができます。 プロローグとエピローグは、正しく xdata に記載されていることができるように非常に制限されます。 スタック ポインターは、16 バイトの任意のリーフ関数内を除き、プロローグまたはエピローグの一部でないコード領域に配置する必要があります。 リーフ関数は、pdata および xdata は必要ありませんので、戻り値をシミュレートするだけでアンワインドされます。 関数のプロローグとエピローグの適切な構造に関する詳細については、「[プロローグとエピローグ](../build/prolog-and-epilog.md)です。 例外処理、および pdata と xdata のアンワインドの処理と例外に関する詳細については、次を参照してください。[例外処理 (x64)](../build/exception-handling-x64.md)です。  
  
## <a name="see-also"></a>関連項目  
 [x64 ソフトウェア規約](../build/x64-software-conventions.md)