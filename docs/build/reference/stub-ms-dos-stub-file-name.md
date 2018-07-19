---
title: スタブ (MS-DOS スタブ ファイル名) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /stub
- VC.Project.VCLinkerTool.DosStub
dev_langs:
- C++
helpviewer_keywords:
- Win32 [C++], attaching MS-DOS stub program
- STUB linker option
- MS-DOS stub file name linker option
- /STUB linker option
- Windows API [C++], attaching MS-DOS stub program
- -STUB linker option
ms.assetid: 65221ffe-4f9a-4a14-ac69-3cfb79b40b5f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4302040f7d18dcffc07ddd054c34b62c22e400d2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379017"
---
# <a name="stub-ms-dos-stub-file-name"></a>/STUB (MS-DOS スタブ ファイル名)
```  
/STUB:filename  
```  
  
## <a name="remarks"></a>コメント  
 それぞれの文字について以下に説明します。  
  
 *ファイル名*  
 MS-DOS アプリケーションです。  
  
## <a name="remarks"></a>コメント  
 /STUB オプションは、MS-DOS スタブ プログラムを Win32 プログラムにアタッチします。  
  
 MS-DOS でファイルが実行された場合は、スタブ プログラムが呼び出されます。 適切なメッセージです。 通常が表示されます。ただし、有効な任意 MS-DOS アプリケーションでは、スタブ プログラムを指定できます。  
  
 指定、 *filename*のコマンドラインでは、コロン (:) の後にスタブ プログラムです。 リンカー チェック*filename*し、ファイルが、実行可能ファイルではない場合、エラー メッセージを発行します。 プログラムは、.exe ファイルである必要があります。スタブ プログラム .com ファイルが正しくありません。  
  
 このオプションを使用しない場合、リンカーには、次のメッセージを発行する既定のスタブ プログラムがアタッチされます。  
  
```  
This program cannot be run in MS-DOS mode.  
```  
  
 仮想デバイス ドライバーを作成するときに*filename* (WINNT で定義されている IMAGE_DOS_HEADER 構造体を含むファイル名を指定することができます。H) をクリックし、既定のヘッダーではなく、VXD で使用します。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「 [Visual C プロジェクト プロパティの設定](../../ide/working-with-project-properties.md)です。  
  
2.  クリックして、**リンカー**フォルダーです。  
  
3.  **[コマンド ライン]** プロパティ ページをクリックします。  
  
4.  オプションを入力、**追加オプション**ボックス。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)