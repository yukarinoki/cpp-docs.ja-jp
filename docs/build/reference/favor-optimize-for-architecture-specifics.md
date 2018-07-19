---
title: -優先 (アーキテクチャ固有の最適化) |Microsoft ドキュメント
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
ms.openlocfilehash: 91f91373eef29adcb9a632e80520ed6713d3e39b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376222"
---
# <a name="favor-optimize-for-architecture-specifics"></a>/favor (アーキテクチャ固有の最適化)
**/favor:** `option` AMD および Intel アーキテクチャのマイクロ アーキテクチャの仕様または特定のアーキテクチャ用に最適化されたコードが生成されます。  
  
## <a name="syntax"></a>構文  
  
```  
/favor:{blend | ATOM | AMD64 | INTEL64}  
```  
  
## <a name="remarks"></a>コメント  
 **/favor:blend**  
 (x86 および x64) は、AMD、および Intel アーキテクチャのマイクロ アーキテクチャの仕様に最適化されたコードを生成します。 中に **/favor:blend**最適なパフォーマンスを得られない場合が可能であれば、特定のプロセッサ、ものでは x86 および x64 プロセッサの広範な範囲で、最適なパフォーマンスが得られる。 既定では、 **/favor:blend**が有効になっています。  
  
 **/favor:ATOM**  
 (x86 および x64) は、Intel Atom プロセッサや Intel Centrino Atom プロセッサ テクノロジの仕様用に最適化されたコードを生成します。 使用して生成されるコード **/favor:ATOM** Intel プロセッサ Intel SSSE3、SSE3、SSE2、および SSE 命令を生成も可能性があります。  
  
 **/favor:AMD64**  
 (x64 のみ) の 64 ビットの拡張機能をサポートする Athlon プロセッサと AMD Opteron、生成されたコードを最適化します。 最適化されたコードは、互換性のあるプラットフォームにすべての x64 で実行できます。 使用して生成されるコード **/favor:AMD64** Intel64 をサポートする Intel プロセッサのパフォーマンスは低下が発生する可能性があります。  
  
 **/favor:INTEL64**  
 (x64 のみ) Intel64 で、そのプラットフォームのパフォーマンスの向上を通常生成をサポートする Intel プロセッサに対して生成されたコードを最適化します。 結果として得られるコードをすべての x64 で実行できるプラットフォームです。 生成されたコード **/favor:INTEL64** AMD Opteron、および 64 ビットの拡張機能をサポートする Athlon プロセッサのパフォーマンスは低下が発生する可能性があります。  
  
> [!NOTE]
>  Intel64 アーキテクチャが以前の拡張メモリ 64 テクノロジ、および対応するコンパイラ オプションが **/favor:EM64T**です。  
  
 プログラム方法については、[!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]アーキテクチャを参照してください[x64 ソフトウェア規約](../../build/x64-software-conventions.md)です。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  選択、 **C/C++** フォルダーです。  
  
3.  選択、**コマンドライン**プロパティ ページ。  
  
4.  コンパイラ オプションを入力して、**追加オプション**ボックス。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)