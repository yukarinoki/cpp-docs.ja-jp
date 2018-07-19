---
title: -GX (例外処理を可能にする) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /gx
dev_langs:
- C++
helpviewer_keywords:
- exception handling, enabling
- /GX compiler option [C++]
- -GX compiler option [C++]
- cl.exe compiler, exception handling
- enable exception handling compiler option [C++]
- GX compiler option [C++]
ms.assetid: 933b43ba-de77-4ff8-a48b-7074de90bc1c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ee2d3d31a9f091e6aa3fbed39f702471047a01dd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376716"
---
# <a name="gx-enable-exception-handling"></a>/GX (例外処理の有効化)
非推奨。 使用して宣言されていると想定される関数を使用して同期例外処理を有効`extern "C"`例外はスローされません。  
  
## <a name="syntax"></a>構文  
  
```  
/GX  
```  
  
## <a name="remarks"></a>コメント  
 **/GX**は推奨されなくなりました。 該当するショートカットを使用して[/EHsc](../../build/reference/eh-exception-handling-model.md)オプションを代わりにします。 非推奨のコンパイラ オプションの一覧は、次を参照してください。、**廃止予定とコンパイラ オプションの削除**」の「[コンパイラ オプションの一覧をカテゴリ別](../../build/reference/compiler-options-listed-by-category.md)です。  
  
 既定では、 **/EHsc**と等価の **/GX**、Visual Studio 開発環境を使用してコンパイルするときに、有効にします。 コマンド ライン ツールを使用すると例外処理が指定されていません。 これは、相当の**では/GX-** です。  
  
 詳細については、次を参照してください。 [C++ 例外処理](../../cpp/cpp-exception-handling.md)です。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  ナビゲーション ウィンドウで、次のように選択します。**構成プロパティ**、 **c/c++**、**コマンドライン**です。  
  
3.  **[追加のオプション]** ボックスにコンパイラ オプションを入力します。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)   
 [/EH (例外処理モデル)](../../build/reference/eh-exception-handling-model.md)