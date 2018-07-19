---
title: /Qfast_transcendentals (超越関数高速) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Qfast_transcendentals
dev_langs:
- C++
helpviewer_keywords:
- /Qfast_transcendentals
- Force Fast Transcendentals
ms.assetid: 4de24bd1-38e6-49d4-9a05-04c9937d24ac
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c4bb296c8a1fdfde46969ef601fde33c901c9306
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377431"
---
# <a name="qfasttranscendentals-force-fast-transcendentals"></a>/Qfast_transcendentals (超越関数高速化の強制)
超越関数のインライン コードを生成します。  
  
## <a name="syntax"></a>構文  
  
```  
/Qfast_transcendentals  
```  
  
## <a name="remarks"></a>コメント  
 このコンパイラ オプションは、実行速度を向上させるために、インライン コードに変換する超越関数を強制します。 このオプションは、対応する場合にのみ有効 **/fp: 除く**または **/fp: 正確な**します。 超越関数のインライン コードの生成は、その下にある既定の動作では既に **/fp:fast**です。  
  
 このオプションは互換性がない **/fp: 厳密な**します。 参照してください[/fp (浮動小数点の動作を指定)](../../build/reference/fp-specify-floating-point-behavior.md)浮動ポイント コンパイラ オプションの詳細についてはします。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  **[C/C++]** フォルダーをクリックします。  
  
3.  **[コマンド ライン]** プロパティ ページをクリックします。  
  
4.  **[追加のオプション]** ボックスにコンパイラ オプションを入力します。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [/Q オプション (低水準の操作)](../../build/reference/q-options-low-level-operations.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)