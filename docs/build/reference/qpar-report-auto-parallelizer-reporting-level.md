---
title: -Qpar-report (自動並行化レポート作成レベル) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
ms.assetid: 562673b9-02da-4bf8-bb64-70bc25ef4651
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 70ac8433b4692586880648d6c5d5d83f1cbb15fd
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43681696"
---
# <a name="qpar-report-auto-parallelizer-reporting-level"></a>/Qpar-report (自動並行化レポート作成レベル)
コンパイラのレポート機能を有効に[自動並行化](../../parallel/auto-parallelization-and-auto-vectorization.md)し、コンパイル時に出力の情報メッセージのレベルを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
/Qpar-report:{1}{2}  
```  
  
## <a name="remarks"></a>Remarks  
 **/Qpar-レポート: 1**  
 並列化されたループに対する情報メッセージを出力します。  
  
 **/Qpar-レポート: 2**  
 並列化されたループと並列化されていないループの情報メッセージを理由コードと共に出力します。  
  
 メッセージは stdout に報告されます。 情報メッセージが報告されない場合、コードにループが含まれていないか、並列化されていないループが報告されるようにレポートのレベルが設定されていませんでした。 理由コードとメッセージの詳細については、次を参照してください。[ベクター化と並行化メッセージ](../../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md)します。  
  
### <a name="to-set-the-qpar-report-compiler-option-in-visual-studio"></a>/Qpar-report コンパイラ オプションを Visual Studio で設定するには  
  
1.  **ソリューション エクスプローラー**で、プロジェクトのショートカット メニューを開き、 **[プロパティ]** をクリックします。  
  
2.  **プロパティ ページ**ダイアログ ボックスで、 **C/C++**、**コマンド ライン**。  
  
3.  **追加オプション**ボックスに、入力`/Qpar-report:1`または`/Qpar-report:2`します。  
  
### <a name="to-set-the-qpar-report-compiler-option-programmatically"></a>/Qpar-report コンパイラ オプションをコードから設定するには  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A> のコード例を使用してください。  
  
## <a name="see-also"></a>関連項目  
 [/Q オプション (低水準の操作)](../../build/reference/q-options-low-level-operations.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)   
 [ネイティブ コードでの並列プログラミング](https://blogs.msdn.microsoft.com/nativeconcurrency/2012/04/12/auto-vectorizer-in-visual-studio-2012-overview/)