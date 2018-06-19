---
title: バージョン (バージョン情報) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.Version
- /version
dev_langs:
- C++
helpviewer_keywords:
- -VERSION linker option
- Version Information linker option
- version numbers, specifying in .exe
- /VERSION linker option
- VERSION linker option
ms.assetid: b86d0e86-dca6-4316-aee2-d863ccb9f223
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 092fd11d7bf062afb59c9b33d620624c63b5e01f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32378991"
---
# <a name="version-version-information"></a>/VERSION (バージョン情報)
```  
/VERSION:major[.minor]  
```  
  
## <a name="remarks"></a>コメント  
 それぞれの文字について以下に説明します。  
  
 *主要な*と*マイナー*  
 .Exe または .dll ファイルのヘッダーに必要なバージョン番号です。  
  
## <a name="remarks"></a>コメント  
 /VERSION オプションは、.exe または .dll ファイルのヘッダーにバージョン番号を含めるようにリンカーに指示します。 DUMPBIN を使用して[/HEADERS](../../build/reference/headers.md) /VERSION の効果を確認する、OPTIONAL HEADER VALUES のイメージ バージョン フィールドを表示します。  
  
 *メジャー*と*マイナー*引数には 0 ~ 65,535 の範囲の 10 進数。 既定値は、バージョン 0.0 です。  
  
 /VERSION で指定された情報は、ファイル エクスプ ローラーでそのプロパティを表示するときに、アプリケーションに対して表示されるバージョン情報には影響しません。 そのバージョン情報は、アプリケーションのビルドに使用されるリソース ファイルから取得されます。 参照してください[バージョン情報 エディター](../../windows/version-information-editor.md)詳細についてはします。  
  
 バージョン番号を挿入する別の方法は、[バージョン](../../build/reference/version-c-cpp.md)モジュール定義ステートメントです。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「 [Visual C プロジェクト プロパティの設定](../../ide/working-with-project-properties.md)です。  
  
2.  クリックして、**リンカー**フォルダーです。  
  
3.  クリックして、**全般**プロパティ ページ。  
  
4.  変更、**バージョン**プロパティです。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.Version%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)