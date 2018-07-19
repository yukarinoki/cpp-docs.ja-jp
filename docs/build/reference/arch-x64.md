---
title: -arch (x64) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
ms.assetid: ecda22bf-5bed-43f4-99fb-88aedd83d9d8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 848d229d6cf8df7d08494d0c300e082c6dc7d0a9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32371672"
---
# <a name="arch-x64"></a>/arch (x64)
x64 でのコード生成のアーキテクチャを指定します。 参照してください[/arch (x86)](../../build/reference/arch-x86.md)と[/arch (ARM)](../../build/reference/arch-arm.md)です。  
  
## <a name="syntax"></a>構文  
  
```  
/arch:[AVX|AVX2]  
```  
  
## <a name="arguments"></a>引数  
 **/arch:AVX**  
 Advanced Vector Extensions 命令の使用を有効にします。  
  
 **/arch:AVX2**  
 Advanced Vector Extensions 2 命令の使用を有効にします。  
  
## <a name="remarks"></a>コメント  
 **/arch**だけでネイティブ関数の生成のコードに影響します。 使用すると[/clr](../../build/reference/clr-common-language-runtime-compilation.md)をコンパイルする **/arch**マネージ関数のコード生成に影響を与えません。  
  
 `__AVX__`プリプロセッサ シンボルが定義されているときに、 **/arch:AVX**コンパイラ オプションを指定します。 `__AVX2__`プリプロセッサ シンボルが定義されているときに、 **/arch:AVX2**コンパイラ オプションを指定します。 詳細については、「 [Predefined Macros](../../preprocessor/predefined-macros.md)」を参照してください。 **/Arch:AVX2**オプションは、Visual Studio 2013 Update 2、バージョン 12.0.34567.1 で導入されました。  
  
### <a name="to-set-the-archavx-or-archavx2-compiler-option-in-visual-studio"></a>/arch:AVX または /arch:AVX2 コンパイラ オプションを Visual Studio で設定するには  
  
1.  開く、**プロパティ ページ**プロジェクトのダイアログ ボックス。 詳細については、次を参照してください。[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  選択、**構成プロパティ**、 **C/C++** フォルダーです。  
  
3.  選択、**コード生成**プロパティ ページ。  
  
4.  **拡張命令セットを有効にする**ドロップダウン ボックスで、選択**Advanced Vector Extensions (//ARCH:AVX)** または**Advanced Vector Extensions 2 (/arch: AVX2)** です。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableEnhancedInstructionSet%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [/arch (最小限の CPU アーキテクチャ)](../../build/reference/arch-minimum-cpu-architecture.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)