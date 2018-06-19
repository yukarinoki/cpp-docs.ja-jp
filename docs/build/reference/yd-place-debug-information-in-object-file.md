---
title: -Yd (デバッグ情報のオブジェクト ファイル) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /yd
dev_langs:
- C++
helpviewer_keywords:
- /Yd compiler option [C++]
- -Yd compiler option [C++]
- debugging [C++], debug information files
- Yd compiler option [C++]
ms.assetid: c5a699fe-65ce-461e-964c-7f5eb2a8320a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 39b03b0faf975caba8c5a287c88afcdf53f7a71f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32378234"
---
# <a name="yd-place-debug-information-in-object-file"></a>/Yd (デバッグ情報のオブジェクト ファイルへの取り込み)
使用する場合は、プリコンパイル済みヘッダー (.pch) ファイルから作成されたデバッグ情報をすべてのオブジェクト ファイルの完全なペース、 [/Yc](../../build/reference/yc-create-precompiled-header-file.md)と[/Z7](../../build/reference/z7-zi-zi-debug-information-format.md)オプション。 非推奨。  
  
## <a name="syntax"></a>構文  
  
```  
/Yd  
```  
  
## <a name="remarks"></a>コメント  
 **/Yd への取り込み**は廃止されました。[!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)]複数のオブジェクトが 1 つの .pdb ファイルへの書き込みの使用を今すぐサポート **/Zi**代わりにします。 非推奨のコンパイラ オプションの一覧は、次を参照してください。**廃止予定とコンパイラ オプションの削除**で[コンパイラ オプションの一覧をカテゴリ別](../../build/reference/compiler-options-listed-by-category.md)です。  
  
 デバッグ情報を含むライブラリを配布する必要がありますしない限り、使用、 [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md)オプションなく **/Z7**と **/yd への取り込み**です。  
  
 すべての .obj ファイルに詳細なデバッグ情報を格納するは、のみ、デバッグ情報が含まれているライブラリを配布する必要があります。 コンパイル速度が低下し、非常に大きなディスク領域が必要です。 ときに **/Yc**と **/Z7**されずに使用されます **/yd への取り込み**コンパイラが .pch ファイルから作成された最初の .obj ファイル内の一般的なデバッグ情報を格納します。 コンパイラが .pch ファイルから、後で作成された .obj ファイルにこの情報を挿入できません。情報への相互参照を挿入します。 .Obj ファイルの数は、.pch ファイルを使用して、関係なく 1 つだけの .obj ファイルには、一般的なデバッグ情報が含まれています。  
  
 この既定の動作の結果も高速ビルド時間、ディスク領域の負担を軽減は望ましくありませんわずかな変更は、一般的なデバッグ情報を含む .obj ファイルの再構築が必要な場合です。 この場合、コンパイラは、元の .obj ファイルへの相互参照を含むすべての .obj ファイルをリビルドする必要があります。 また、さまざまなプロジェクトで共通の .pch ファイルを使用する単一の .obj ファイルへの相互参照への依存は困難です。  
  
 プリコンパイル済みヘッダーの詳細についてを参照してください。  
  
-   [/Y (プリコンパイル済みヘッダー)](../../build/reference/y-precompiled-headers.md)  
  
-   [プリコンパイル済みヘッダー ファイルの作成](../../build/reference/creating-precompiled-header-files.md)  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  **[C/C++]** フォルダーをクリックします。  
  
3.  **[コマンド ライン]** プロパティ ページをクリックします。  
  
4.  **[追加のオプション]** ボックスにコンパイラ オプションを入力します。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>」を参照してください。  
  
## <a name="examples"></a>使用例  
 F.cpp と G.cpp、各を含むこれら 2 つの基本ファイルがあると **#include**ステートメント。  
  
```  
#include "windows.h"  
#include "etc.h"  
```  
  
 次のコマンドは、プリコンパイル済みヘッダーを作成するファイルの ETC.pch とオブジェクト ファイル F.obj:  
  
```  
CL /YcETC.H /Z7 F.CPP  
```  
  
 F.obj オブジェクト ファイルには、型および WINDOWS.h および ETC.h のシンボル情報 (およびが含まれているその他のヘッダー ファイル) が含まれています。 今すぐ ETC.pch プリコンパイル済みヘッダーを使用して、ソース ファイル G.cpp をコンパイルすることができます。  
  
```  
CL /YuETC.H /Z7 G.CPP  
```  
  
 オブジェクト ファイル G.obj はプリコンパイル済みヘッダーのデバッグ情報は含まれませんが、単に F.obj ファイルでは、その情報を参照します。 F.obj とリンクする必要がありますに注意してください。  
  
 プリコンパイル済みヘッダーはでコンパイルされていない場合 **/Z7**、以降のコンパイルを使用してそのまま使用することができます **/Z7**です。 ただし、デバッグ情報が現在のオブジェクト ファイル内に配置し、関数、およびプリコンパイル済みヘッダーで定義されている型のローカル シンボルは、デバッガーを使用できません。  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)