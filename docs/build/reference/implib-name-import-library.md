---
title: -IMPLIB (インポート ライブラリ名の) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /implib
- VC.Project.VCLinkerTool.ImportLIbrary
dev_langs:
- C++
helpviewer_keywords:
- IMPLIB linker option
- /IMPLIB linker option
- -IMPLIB linker option
- import libraries, overriding default name
ms.assetid: fe8f71ab-7055-41b5-8ef8-2b97cfa4a432
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 72edc0fcb1b216319d6f6c9924cb92a165b3196b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32375273"
---
# <a name="implib-name-import-library"></a>/IMPLIB (インポート ライブラリ名の設定)
  
> /IMPLIB:*ファイル名*  
  
## <a name="parameters"></a>パラメーター  
  
*ファイル名*  
インポート ライブラリのユーザー指定の名前。 既定の名前に置き換えます。  
  
## <a name="remarks"></a>コメント  
  
/IMPLIB オプションでは、エクスポートを含むプログラムをビルドするときにリンクが作成されるインポート ライブラリの既定の名前をオーバーライドします。 メイン出力ファイルと拡張機能の基本名から既定の名前を形成します。 lib です。 プログラムには、次の 1 つ以上が指定されている場合、エクスポートが含まれます。  
  
-   [方式](../../cpp/dllexport-dllimport.md)ソース コード内のキーワード  
  
-   [エクスポート](../../build/reference/exports.md).def ファイル内のステートメント  
  
-   [/Export](../../build/reference/export-exports-a-function.md) LINK コマンド内の指定  
  
 リンクは、インポート ライブラリが作成されていない場合、/IMPLIB を無視します。 エクスポートが指定されていない場合、リンクは、インポート ライブラリを作成できません。 エクスポート ファイルがビルドに使用されている場合のリンクには、インポート ライブラリが既に存在し、作成されていないことが前提とします。 詳細については、インポート ライブラリとエクスポート ファイルは、次を参照してください。 [LIB リファレンス](../../build/reference/lib-reference.md)です。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「 [Visual C プロジェクト プロパティの設定](../../ide/working-with-project-properties.md)です。  
  
2.  クリックして、**リンカー**フォルダーです。  
  
3.  クリックして、**詳細**プロパティ ページ。  
  
4.  変更、**インポート ライブラリ**プロパティです。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ImportLibrary%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)