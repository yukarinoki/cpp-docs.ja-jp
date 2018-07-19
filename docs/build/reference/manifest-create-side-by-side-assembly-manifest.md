---
title: -マニフェスト (サイド バイ サイド アセンブリ マニフェストの作成) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.GenerateManifest
dev_langs:
- C++
helpviewer_keywords:
- -MANIFEST linker option
- /MANIFEST linker option
- MANIFEST linker option
ms.assetid: 98c52e1e-712c-4f49-b149-4d0a3501b600
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5486eca41c93adb074cde6dc9602149d7dfa4f13
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32378315"
---
# <a name="manifest-create-side-by-side-assembly-manifest"></a>/MANIFEST (side-by-side アセンブリ マニフェストを作成する)
```  
/MANIFEST[:{EMBED[,ID=#]|NO}]  
```  
  
## <a name="remarks"></a>コメント  
 /MANIFEST は、リンカーが side-by-side マニフェストファイルを作成することを指定します。 マニフェスト ファイルの詳細については、次を参照してください。 [Manifest Files Reference](http://msdn.microsoft.com/library/aa375632)です。  
  
 既定値は、"/MANIFEST" です。  
  
 /MANIFEST:EMBED オプションは、リンカーが RT_MANIFEST 型のリソースとしてイメージにマニフェスト ファイルを埋め込む必要があることを指定します。 省略可能な `ID` パラメーターは、マニフェストで使用するリソース ID です。 実行可能ファイルの場合は値 1 を使用します。 DLL の場合は値 2 を使用して、プライベート依存関係を指定できるようにします。 `ID` パラメーターを指定しない場合、/DLL オプションが設定されている場合の既定値は 2、それ以外の場合の既定値は 1 になります。  
  
 Visual Studio 2008 以降では、実行可能ファイルのマニフェスト ファイルには、ユーザー アカウント制御 (UAC) 情報を指定するセクションが含まれています。 /MANIFEST を指定するが、いずれも指定して[/MANIFESTUAC](../../build/reference/manifestuac-embeds-uac-information-in-manifest.md)も[/DLL](../../build/reference/dll-build-a-dll.md)に、UAC レベルが設定されている既定の UAC フラグメント*asInvoker*がマニフェストに挿入します。 UAC レベルの詳細については、次を参照してください。 [/MANIFESTUAC (マニフェストに UAC 情報)](../../build/reference/manifestuac-embeds-uac-information-in-manifest.md)です。  
  
 UAC の既定の動作を変更するには、次のいずれかを行います。  
  
-   /MANIFESTUAC オプションを指定して、UAC レベルを所定の値に設定します。  
  
-   マニフェストに UAC フラグメントを生成しない場合は、/MANIFESTUAC:NO オプションを指定します。  
  
 /MANIFEST を指定しないかどうかが、指定しないでください[/MANIFESTDEPENDENCY](../../build/reference/manifestdependency-specify-manifest-dependencies.md)コメントのマニフェスト ファイルを作成します。 /MANIFEST:NO を指定すると、マニフェスト ファイルは作成されません。  
  
 /MANIFEST を指定すると、マニフェスト ファイルの名前は出力ファイルの名前と同じになりますが、ファイル名に .manifest が追加されます。 たとえば、出力ファイルの名前が MyFile.exe の場合、マニフェスト ファイル名は MyFile.exe.manifest になります。  /MANIFESTFILE を指定する場合:*名前*、マニフェストの名前がで指定した*名前*です。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  展開して、**構成プロパティ**ノード。  
  
3.  展開して、**リンカー**ノード。  
  
4.  選択、**マニフェスト ファイル**プロパティ ページ。  
  
5.  変更、**マニフェストの生成**プロパティです。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
1.  「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateManifest%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)