---
title: コンパイラの組み込み |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- intrinsics, compiler
- compiler intrinsics
- cl.exe compiler, performance
- cl.exe compiler, intrinsics
ms.assetid: 48bb9929-7d78-4fd8-a092-ae3c9f971858
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c05a2843e5daff980d1c84d4d3f2185ac361144d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-intrinsics"></a>コンパイラ組み込み
ほとんどの関数はライブラリに含まれますが、関数によっては、コンパイラに組み込まれているものもあります。 これらは、組み込み関数または組み込みと呼ばれます。  
  
## <a name="remarks"></a>コメント  
 関数が組み込みの場合、その関数のコードは通常、インラインで挿入されます。これにより、関数呼び出しのオーバーヘッドを回避し、その関数の非常に効率的なマシン語命令が生成されるようにします。 組み込みは通常、同等のインライン アセンブリよりも高速です。これは、オプティマイザーに組み込み関数の動作数に関する組み込まれた知識があるため、インライン アセンブリが使用できない最適化を使用できるためです。 また、オプティマイザーは、組み込みの展開、バッファーの配置、その他の調節を、呼び出しのコンテキストと引数に応じて行うことができます。  
  
 組み込みの使用はコードの移植性に影響します。これは、Visual C++ で使用できる組み込み関数が、コードが他のコンパイラでコンパイルされた場合には利用できない場合があったり、また、あるターゲット アーキテクチャで使用できる組み込みが、すべてのアーキテクチャで使用できるとは限らないためです。 ただし、組み込みは通常、インライン アセンブリよりも移植性があります。 組み込みはインライン アセンブリがサポートされていない 64 ビット アーキテクチャに必要です。  
  
 `__assume` や `__ReadWriteBarrier` などの組み込みは、オプティマイザーの動作に影響を与える情報をコンパイラを提供します。  
  
 組み込み関数としてのみ使用できる組み込みもあり、また関数および組み込み実装の両方で使用できる組み込みもあります。 特定の関数のみを有効化するか、またはすべての組み込みを有効化するかによって、2 つのうちの 1 つの方法で組み込みの実装を使用するようにコンパイラに指示を与えることができます。 最初の方法が使用するには`#pragma intrinsic(`*組み込み関数名のリスト ・*`)`です。 プラグマを使用して、コンマで区切った 1 つの組み込みまたは複数の組み込みを指定することができます。 2 つ目は、使用する、 [/Oi (組み込み関数の生成)](../build/reference/oi-generate-intrinsic-functions.md)コンパイラ オプションは、特定のプラットフォーム上のすべての組み込みが利用可能なになります。 **/Oi**を使用して`#pragma function(`*組み込み関数名のリスト ・* `)`組み込みの代わりに使用する関数呼び出しを強制的にします。 ノートの内容をドキュメントに特定の組み込み場合は、ルーチンが、組み込みとしてのみ、組み込みの実装がかどうかに関係なく使用 **/Oi**または`#pragma intrinsic`を指定します。 すべてのケースで **/Oi**または`#pragma intrinsic`でもわけで、オプティマイザーは組み込みを使用します。 オプティマイザーは、関数を呼び出すことも可能です。  
  
 いくつかの標準 C/C++ ライブラリ関数は、いくつかのアーキテクチャの組み込み実装で使用できます。 場合に、組み込みの実装を使用する CRT 関数を呼び出すときに **/Oi**をコマンドラインで指定します。  
  
 ヘッダー ファイル、 \<intrin.h > は共通の組み込み関数のプロトタイプを宣言する使用可能な。 製造元固有の組み込みがで使用可能な\<immintrin.h > と\<ammintrin.h > ヘッダー ファイルです。 さらに、特定の Windows ヘッダーは、コンパイラの組み込みにマップする関数を宣言します。  
  
 次のセクションでは、さまざまなアーキテクチャで使用できるすべての組み込みを示します。 特定のターゲット プロセッサでの組み込みの動作の詳細については、開発元のリファレンス ドキュメントを参照してください。  
  
-   [ARM 組み込み](../intrinsics/arm-intrinsics.md)  
  
-   [x86 組み込み一覧](../intrinsics/x86-intrinsics-list.md)  
  
-   [x64 (amd64) 組み込み一覧](../intrinsics/x64-amd64-intrinsics-list.md)  
  
-   [すべてのアーキテクチャで使用可能な組み込みクラス](../intrinsics/intrinsics-available-on-all-architectures.md)  
  
-   [組み込み関数のアルファベット順の一覧](../intrinsics/alphabetical-listing-of-intrinsic-functions.md)  
  
## <a name="see-also"></a>関連項目  
 [ARM アセンブラー リファレンス](../assembler/arm/arm-assembler-reference.md)   
 [Microsoft Macro Assembler リファレンス](../assembler/masm/microsoft-macro-assembler-reference.md)   
 [キーワード](../cpp/keywords-cpp.md)   
 [C ランタイム ライブラリ リファレンス](../c-runtime-library/c-run-time-library-reference.md)