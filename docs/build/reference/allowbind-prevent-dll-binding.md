---
title: -ALLOWBIND (DLL バインディングを避けるため) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.PreventDLLBinding
- /allowbind
dev_langs:
- C++
helpviewer_keywords:
- /ALLOWBIND linker option
- binding DLLs
- preventing DLL binding
- ALLOWBIND linker option
- -ALLOWBIND linker option
- DLLs [C++], preventing binding
ms.assetid: 30e37e24-12e4-407e-988a-39d357403598
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 31968e27c46cb5ea220a4cfe19c36820c4cf8444
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32369641"
---
# <a name="allowbind-prevent-dll-binding"></a>/ALLOWBIND (DLL をバインドしない)
```  
/ALLOWBIND[:NO]  
```  
  
## <a name="remarks"></a>コメント  
 /ALLOWBIND:NO は DLL のヘッダーにビットを設定して、イメージをバインドできないことを Bind.exe に示します。 DLL がデジタル署名されている場合はバインドしないほうがよいでしょう (バインドによって署名が無効になる)。  
  
 /ALLOWBIND 機能の既存の DLL を編集することができます、 [/ALLOWBIND](../../build/reference/allowbind.md) EDITBIN ユーティリティのオプションです。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  展開**構成プロパティ**、**リンカー**を選択して**コマンドライン**です。  
  
3.  入力`/ALLOWBIND:NO`に**追加オプション**です。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)   
 [BindImage 関数](http://msdn.microsoft.com/library/windows/desktop/ms679278.aspx)   
 [BindImageEx 関数](http://msdn.microsoft.com/library/windows/desktop/ms679279.aspx)