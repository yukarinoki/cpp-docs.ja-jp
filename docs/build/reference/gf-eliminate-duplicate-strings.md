---
title: -GF (文字列の削除) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.StringPooling
- VC.Project.VCCLWCECompilerTool.StringPooling
- /gf
dev_langs:
- C++
helpviewer_keywords:
- duplicate strings
- Eliminate Duplicate Strings compiler option [C++]
- pooling strings compiler option [C++]
- -GF compiler option [C++]
- /GF compiler option [C++]
- GF compiler option [C++]
- strings [C++], pooling
ms.assetid: bb7b5d1c-8e1f-453b-9298-8fcebf37d16c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9e2710fe8c5cc444d9e2681620f6813312a1d65a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="gf-eliminate-duplicate-strings"></a>/GF (同一文字列の削除)
実行中に、プログラム イメージおよびメモリ内と同じ文字列の 1 つのコピーを作成するコンパイラを有効にします。 これは、最適化と呼ばれる*文字列プール*小さいプログラムを作成することができます。  
  
## <a name="syntax"></a>構文  
  
```  
/GF  
```  
  
## <a name="remarks"></a>コメント  
 使用する場合 **/GF**、オペレーティング システムのメモリの文字列部分が交換されていないと、文字列は、イメージ ファイルからバックアップを読み取ることができます。  
  
 **/GF**読み取り専用として文字列をプールします。 文字列を変更しようとする場合 **/GF**、アプリケーション エラーが発生します。  
  
 文字列プールにより、1 つのバッファーに複数のポインターである場合に複数のバッファーを複数のポインターとして用意されてされています。 次のコードに`s`と`t`同じ文字列で初期化されます。 文字列プールが同じメモリを指すように発生します。  
  
```  
char *s = "This is a character buffer";  
char *t = "This is a character buffer";  
```  
  
> [!NOTE]
>  [/ZI](../../build/reference/z7-zi-zi-debug-information-format.md) 、エディット コンティニュを使用するオプションが自動的に設定、 **/GF**オプション。  
  
> [!NOTE]
>  **/GF**コンパイラ オプションは、各一意の文字列のアドレス指定可能なセクションを作成します。 既定では、オブジェクト ファイルが最大で 65,536 個のアドレス指定可能なセクションを含めることができます。 場合は、プログラムには、65,536 個を超える文字列が含まれているを使用して、 [/bigobj](../../build/reference/bigobj-increase-number-of-sections-in-dot-obj-file.md)コンパイラ オプションをさらにセクションを作成します。  
  
 **/GF**が効果的とき[/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md)または **/O2**を使用します。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  **[C/C++]** フォルダーをクリックします。  
  
3.  クリックして、**コード生成**プロパティ ページ。  
  
4.  変更、**文字列プールを有効にする**プロパティです。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.StringPooling%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)