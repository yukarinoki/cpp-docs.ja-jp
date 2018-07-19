---
title: -Za、-ze (言語拡張を無効にする) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLWCECompilerTool.DisableLanguageExtensions
- /za
- /ze
- VC.Project.VCCLCompilerTool.DisableLanguageExtensions
dev_langs:
- C++
helpviewer_keywords:
- -Za compiler option [C++]
- Za compiler option [C++]
- language extensions, disabling in compiler
- -Ze compiler option [C++]
- language extensions
- enable language extensions
- /Za compiler option [C++]
- /Ze compiler option [C++]
- Disable Language Extensions compiler option
- Ze compiler option [C++]
ms.assetid: 65e49258-7161-4289-a176-7c5c0656b1a2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2949a3d60af6d9058f02d12aac1fd86dead5affa
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32378146"
---
# <a name="za-ze-disable-language-extensions"></a>/Za、/Ze (言語拡張機能の無効化)
**/Za**コンパイラ オプションは、ANSI C89 または ISO C 11 と互換性がない言語構成要素のエラーを出力します。 **/Ze**コンパイラ オプションは、既定では、Microsoft 拡張機能を有効にします。  
  
## <a name="syntax"></a>構文  
  
```  
/Za  
/Ze  
```  
  
## <a name="remarks"></a>コメント  
  
> [!NOTE]
>  **/Ze**オプションは、その動作は既定であるために推奨されません。 使用することをお勧め、 [/Zc (準拠)](../../build/reference/zc-conformance.md)コンパイラ オプションを特定の言語拡張機能を制御します。 非推奨のコンパイラ オプションの一覧は、次を参照してください。、**廃止予定とコンパイラ オプションの削除**」の「[コンパイラ オプションの一覧をカテゴリ別](../../build/reference/compiler-options-listed-by-category.md)です。  
  
 [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)]コンパイラは、いくつかの ANSI C89、ISO C99 または ISO C 標準で指定されたもの以外の機能を提供しています。 これらの機能は、C および C++ に Microsoft 拡張機能として総称はします。 これらの拡張機能は既定では、使用可能でない場合に、 **/Za**オプションを指定します。 特定の拡張機能の詳細については、次を参照してください。 [C および C++ の Microsoft 拡張機能](../../build/reference/microsoft-extensions-to-c-and-cpp.md)します。  
  
 指定して、言語拡張機能を無効にすることをお勧め、 **/Za**オプションの場合は、プログラムを他の環境に移植する予定です。 ときに **/Za**を指定すると、コンパイラに示す Microsoft 単純な識別子としてのキーワードの拡張し、他の Microsoft 拡張機能を無効にし、自動的に定義、 `__STDC__` C プログラムの定義済みマクロです。  
  
 使用されるその他のコンパイラ オプション **/Za**コンパイラにより、標準への準拠方法に影響を与えることができます。 たとえば、 **/Za**と[/fp (浮動小数点の動作を指定)](../../build/reference/fp-specify-floating-point-behavior.md) ISO C99 や c++ 11 標準に準拠していない浮動小数点型の昇格の動作が発生可能性があります。  
  
 特定の標準に準拠した動作の設定を指定する方法は、次を参照してください。、 [/Zc](../../build/reference/zc-conformance.md)コンパイラ オプション。  
  
 準拠の問題の詳細については[!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)]を参照してください[非標準動作](../../cpp/nonstandard-behavior.md)です。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  ナビゲーション ウィンドウで、次のように選択します。**構成プロパティ**、 **c/c++**、**言語**します。  
  
3.  変更、**言語拡張機能を無効にする**プロパティです。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DisableLanguageExtensions%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)   
 [/Zc (準拠)](../../build/reference/zc-conformance.md)