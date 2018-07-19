---
title: -Zm (プリコンパイル済みヘッダーのメモリ割り当て制限の指定) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /zm
dev_langs:
- C++
helpviewer_keywords:
- PCH files, memory allocation limit
- Zm compiler option [C++]
- /Zm compiler option [C++]
- precompiled header files, memory allocation limit
- Specify Precompiled Header Memory Allocation Limit compiler option
- cl.exe compiler, memory allocation limit
- .pch files, memory allocation limit
- memory allocation, Memory Allocation Limit compiler option
- -Zm compiler option [C++]
ms.assetid: 94c77d5e-6672-46a7-92e0-3f69e277727d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 379d3d6673e673522334d685a47220bcfa2523ec
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32380902"
---
# <a name="zm-specify-precompiled-header-memory-allocation-limit"></a>/Zm (プリコンパイル済みヘッダーのメモリ割り当て制限の指定)
コンパイラがプリコンパイル済みヘッダーを構築するために割り当てるメモリの量を決定します。  
  
## <a name="syntax"></a>構文  
  
```  
/Zmfactor  
```  
  
## <a name="arguments"></a>引数  
 `factor`  
 コンパイラがプリコンパイル済みヘッダーを構築するために使用するメモリの量を決定するスケール ファクター。  
  
 引数 `factor` は、コンパイラが定義する作業バッファーの既定のサイズに対する割合です。 `factor` の既定値は 100 (パーセント) ですが、これを超える量も、これ未満の量も指定できます。  
  
## <a name="remarks"></a>コメント  
 以前のバージョンの Visual C++ では、コンパイラはいくつかの独立したヒープを使用し、ヒープにはそれぞれ大きさの限界がありました。 現在では、コンパイラは必要に応じてヒープを合計ヒープ サイズ制限まで動的に拡張します。固定サイズのバッファーはプリコンパイル済みヘッダーを構築するためだけに必要です。 その結果、 **/Zm**コンパイラ オプションぱは必要ありません。  
  
 かどうか、コンパイラはヒープの領域が不足しているし、出力、 [C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md)を使用すると、エラー メッセージ、 **/Zm**コンパイラ オプションは、大量のメモリを予約した可能性があります。 削除を検討してください、 **/Zm**オプション。 コンパイラが出力する場合、 [C1076](../../error-messages/compiler-errors-1/fatal-error-c1076.md) 、付随するエラー メッセージ[C3859](../../error-messages/compiler-errors-2/compiler-error-c3859.md)メッセージを指定します、`factor`引数を使用して再コンパイルするときに使用する、 **/Zm**コンパイラ オプション。  
  
 既定のプリコンパイル済みヘッダーのバッファー サイズを 75 MB と仮定した場合に `factor` 引数がメモリ割り当て制限に与える影響を次の表に示します。  
  
|`factor` の値|メモリ割り当て制限|  
|-----------------------|-----------------------------|  
|10|7.5 MB|  
|100|75 MB|  
|200|150 MB|  
|1000|750 MB|  
|2000|1500 MB|  
  
## <a name="other-ways-to-set-the-memory-allocation-limit"></a>メモリ割り当て制限を設定する別の方法  
  
#### <a name="to-set-the-zm-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境で /Zm コンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  ナビゲーション ウィンドウで、次のように選択します。**構成プロパティ**、 **c/c++**、**コマンドライン**です。  
  
3.  入力、 **/Zm**コンパイラ オプション、**追加オプション**ボックス。  
  
#### <a name="to-set-the-zm-compiler-option-programmatically"></a>/Zm コンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)