---
title: -V (バージョン番号) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /v
dev_langs:
- C++
helpviewer_keywords:
- embedding version strings
- /V compiler option [C++]
- version numbers, specifying for .obj
- V compiler option [C++]
- -V compiler option [C++]
ms.assetid: 3e93fb7a-5dfd-49a6-bd49-3dca8052e0f3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d3daf62c818b454a5477de04a27c4b4f308c271d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377233"
---
# <a name="v-version-number"></a>/V (バージョン番号)
非推奨。 .Obj ファイルにテキスト文字列を埋め込みます。  
  
## <a name="syntax"></a>構文  
  
```  
/Vstring  
```  
  
## <a name="arguments"></a>引数  
 `string`  
 .Obj ファイルに埋め込まれるバージョン番号または著作権表示を指定する文字列。  
  
## <a name="remarks"></a>コメント  
 文字列のラベル、.obj ファイル バージョン番号と著作権の通知です。 文字列の一部である場合、スペースまたはタブ文字を二重引用符 (") で囲む必要があります。 円記号 (\\) 文字列の一部である場合、二重引用符を付ける必要があります。 間にスペース **/V**と`string`は省略可能です。  
  
 使用することも[コメント (C/C++)](../../preprocessor/comment-c-cpp.md) .obj ファイルに、コンパイラの名前とバージョン番号を格納するコンパイラのコメントの型引数を持つ。  
  
 **/V**以降では、Visual Studio 2005; オプションは推奨されません **/V**が主に仮想デバイス ドライバー (Vxd) の構築をサポートするために使用され、Vxd の構築は、Visual C ツールセットでサポートが不要になった。 非推奨のコンパイラ オプションの一覧は、次を参照してください。**廃止予定とコンパイラ オプションの削除**で[コンパイラ オプションの一覧をカテゴリ別](../../build/reference/compiler-options-listed-by-category.md)です。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  **[C/C++]** フォルダーをクリックします。  
  
3.  **[コマンド ライン]** プロパティ ページをクリックします。  
  
4.  **[追加のオプション]** ボックスにコンパイラ オプションを入力します。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)