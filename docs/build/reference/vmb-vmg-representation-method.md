---
title: -vmb、-vmg (表記法) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /vmb
- /vmg
dev_langs:
- C++
helpviewer_keywords:
- vmb compiler option [C++]
- -vmg compiler option [C++]
- vmg compiler option [C++]
- -vmb compiler option [C++]
- /vmb compiler option [C++]
- representation method compiler options [C++]
- /vmg compiler option [C++]
ms.assetid: ecdb391c-7dab-40b1-916b-673d10889fd4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5263b6c7ca227a10b34c32e0b0801eeddf07b9cd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377184"
---
# <a name="vmb-vmg-representation-method"></a>/vmb、/vmg (処理形式)
コンパイラがクラス メンバーへのポインターを表すに使用する方法を選択します。  
  
 使用して **/vmb**クラスのメンバーへのポインターを宣言する前に常にクラスを定義するかどうか。  
  
 使用して **/vmg**クラスを定義する前にクラスのメンバーへのポインターを宣言します。 このニーズは、相互に参照する 2 つの異なるクラスのメンバーを定義する場合に発生することができます。 このような相互に参照元のクラスの 1 つのクラスが定義されている前に、それが参照する必要があります。  
  
## <a name="syntax"></a>構文  
  
```  
/vmb  
/vmg  
```  
  
## <a name="remarks"></a>コメント  
 使用することも[pointers_to_members](../../preprocessor/pointers-to-members.md)または[継承キーワード](../../cpp/inheritance-keywords.md)をコードにポインター表現を指定します。  
  
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