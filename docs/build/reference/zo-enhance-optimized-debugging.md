---
title: -Zo (最適化されたデバッグ機能の拡張) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- -Zo
- /Zo
dev_langs:
- C++
helpviewer_keywords:
- Zo compiler option [C++]
- /Zo compiler option [C++]
- -Zo compiler option [C++]
ms.assetid: eea8d89a-7fe0-4fe1-86b2-7689bbebbd7f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 013738ab05bf67d3db066d94d32d398a0555c55e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32380276"
---
# <a name="zo-enhance-optimized-debugging"></a>/Zo (最適化されたデバッグ機能の強化)
非デバッグ ビルドで最適化されたコードに関する拡張デバッグ情報を生成します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
/Zo[-]  
```  
  
## <a name="remarks"></a>コメント  
 **/Zo**コンパイラ スイッチには、最適化されたコードに関する拡張デバッグ情報が生成されます。 最適化では、ローカル変数にレジスターを使い、コードを並べ替え、ループをベクトル化し、関数呼び出しをインライン化することがあります。 これらの最適化により、ソース コードとコンパイル済みのオブジェクト コードの関係が不明瞭になる場合があります。 **/Zo**スイッチをローカル変数とインライン関数の追加のデバッグ情報を生成するコンパイラに指示します。 内の変数を表示する使用、 **[自動変数]**、 **[ローカル]**、および**ウォッチ**をステップ実行する場合に、windows は、Visual Studio デバッガーでコードを最適化します。 また、スタック トレースを有効にして、WinDBG デバッガーでインライン関数を表示します。 デバッグ ビルドの最適化を無効にしている ([/Od](../../build/reference/od-disable-debug.md)) ときに生成された追加のデバッグ情報は必要ありません **/Zo**を指定します。 使用して、 **/Zo**最適化をオンになっているリリース構成をデバッグするスイッチです。 最適化スイッチの詳細については、次を参照してください。 [/O オプション (コードの最適化)](../../build/reference/o-options-optimize-code.md)です。 **/Zo**オプションは、既定では Visual Studio で使用したデバッグ情報を指定するときに **/Zi**または **/Z7**です。 指定 **/Zo-** このコンパイラ オプションを明示的に無効にします。  
  
 **/Zo**スイッチ以降では、Visual Studio 2013 Update 3 を使用して置き換える以前文書化されていない **/d2Zi+** スイッチします。  
  
### <a name="to-set-the-zo-compiler-option-in-visual-studio"></a>Visual Studio で /Zo コンパイラ オプションを設定するには  
  
1.  開く、**プロパティ ページ**プロジェクトのダイアログ ボックス。 詳細については、次を参照してください。[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  選択、**構成プロパティ**、 **C/C++** フォルダーです。  
  
3.  選択、**コマンドライン**プロパティ ページ。  
  
4.  変更、**追加オプション**含めるプロパティを`/Zo`を選択し**OK**です。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [/O オプション (コードの最適化)](../../build/reference/o-options-optimize-code.md)   
 [/Z7、/Zi、/ZI (デバッグ情報の形式)](../../build/reference/z7-zi-zi-debug-information-format.md)   
 [エディット コンティニュ](/visualstudio/debugger/edit-and-continue)