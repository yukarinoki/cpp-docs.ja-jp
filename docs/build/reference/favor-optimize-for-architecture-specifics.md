---
title: -優先 (アーキテクチャ固有の最適化) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /favor
dev_langs:
- C++
helpviewer_keywords:
- -favor compiler option [C++]
- /favor compiler option [C++]
ms.assetid: ad264df2-e30f-4d68-8bd0-10d6bee71a2a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 75081c3a2e8918bfe8abf43373d755ca258f2595
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2018
ms.locfileid: "42572412"
---
# <a name="favor-optimize-for-architecture-specifics"></a>/favor (アーキテクチャ固有の最適化)
**/favor:** `option` AMD と Intel アーキテクチャでのマイクロ アーキテクチャの詳細または特定のアーキテクチャ用に最適化されたコードが生成されます。  
  
## <a name="syntax"></a>構文  
  
```  
/favor:{blend | ATOM | AMD64 | INTEL64}  
```  
  
## <a name="remarks"></a>Remarks  
 **/favor:blend**  
 (x86 および x64)、AMD と Intel アーキテクチャでのマイクロ アーキテクチャの詳細用に最適化されたコードを生成します。 中に **/favor:blend**最適なパフォーマンスを得られない場合が可能であれば、特定のプロセッサ、その設計が幅広い x86 および x64 プロセッサで最適なパフォーマンスを提供します。 既定では、 **/favor:blend**が有効になっています。  
  
 **/favor:ATOM**  
 (x86 および x64) は、Intel Atom プロセッサや Intel Centrino Atom プロセッサ テクノロジの仕様用に最適化されたコードを生成します。 使用して生成されるコード **/favor:ATOM** Intel プロセッサの Intel SSSE3、SSE3、SSE2、および SSE 命令が生じることもできます。  
  
 **/favor:AMD64**  
 (x64 のみ) の 64 ビットの拡張機能をサポートする Athlon プロセッサ、AMD Opteron、生成されたコードを最適化します。 最適化されたコードは、互換性のあるプラットフォームにすべての x64 で実行できます。 使用して生成されるコード **/favor:AMD64** Intel64 をサポートする Intel プロセッサでパフォーマンスが低下が発生する可能性があります。  
  
 **/favor:INTEL64**  
 (x64 のみ)、そのプラットフォームのパフォーマンス向上を通常生成 Intel64 をサポートする Intel プロセッサに対して生成されたコードを最適化します。 結果のコードを実行できるすべての x64 プラットフォーム。 生成されたコード **/favor:INTEL64** AMD Opteron、および 64 ビットの拡張機能をサポートする Athlon プロセッサのパフォーマンスが低下が発生する可能性があります。  
  
> [!NOTE]
>  Intel64 アーキテクチャは、以前メモリ 64 テクノロジの拡張と呼ばれていましたし、対応するコンパイラ オプションが **/favor:EM64T**します。  
  
 X64 をプログラムする方法については、アーキテクチャを参照してください[x64 ソフトウェア規約](../../build/x64-software-conventions.md)します。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  選択、 **C/C++** フォルダー。  
  
3.  選択、**コマンドライン**プロパティ ページ。  
  
4.  コンパイラ オプションを入力して、**追加オプション**ボックス。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)