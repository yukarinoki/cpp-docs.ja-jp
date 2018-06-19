---
title: -Zl (既定のライブラリ名を省略) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /zi
- VC.Project.VCCLCompilerTool.OmitDefaultLibName
dev_langs:
- C++
helpviewer_keywords:
- -Zl compiler option [C++]
- ZI compiler option
- Omit Default Library Name compiler option
- /Zl compiler option [C++]
- default libraries, omitting names
ms.assetid: b27d39d0-44d6-498c-84ae-27c1326fee59
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4c14a3217334c2c43bac7fbcce8b0bfd60a609d3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379719"
---
# <a name="zl-omit-default-library-name"></a>/Zl (既定のライブラリ名の省略)
.Obj ファイルから既定の C ランタイム ライブラリ名を省略します。 既定では、コンパイラでライブラリ名が .obj ファイルにプッシュされ、リンカーに適切なライブラリが示されます。  
  
## <a name="syntax"></a>構文  
  
```  
/Zl  
```  
  
## <a name="remarks"></a>コメント  
 既定のライブラリの詳細については、次を参照してください。[ランタイム ライブラリの使用](../../build/reference/md-mt-ld-use-run-time-library.md)です。  
  
 使用することができます **/Zl**ライブラリに格納する .obj ファイルをコンパイルします。 少量の単一の .obj ファイルの領域のみを保存するライブラリの名前を省略すると、保存領域の合計は重要で多数のオブジェクト モジュールを含むライブラリ。  
  
 このオプションは、高度なオプションです。 このオプションを設定すると、リンク時のエラーの結果として得られる場合はこのサポートに依存するアプリケーション、アプリケーションで必要になる特定の C ランタイム ライブラリのサポートが削除されます。 このオプションを使用する場合は、その他の何らかの方法で必要なコンポーネントを提供する必要があります。  
  
 使用して[/NODEFAULTLIB (ライブラリの無視)](../../build/reference/nodefaultlib-ignore-libraries.md)です。 ライブラリを無視するようにリンカーに指示するには、すべての .obj ファイルで参照します。  
  
 詳しくは、「[CRT ライブラリの機能](../../c-runtime-library/crt-library-features.md)」をご覧ください。  
  
 コンパイルするときに **/Zl**、`_VC_NODEFAULTLIB`が定義されています。  例えば:  
  
```  
// vc_nodefaultlib.cpp  
// compile with: /Zl  
void Test() {  
   #ifdef _VC_NODEFAULTLIB  
      int i;  
   #endif  
  
   int i;   // C2086  
}  
```  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  **[C/C++]** フォルダーをクリックします。  
  
3.  クリックして、**詳細**プロパティ ページ。  
  
4.  変更、**既定ライブラリ名の省略**プロパティです。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OmitDefaultLibName%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)