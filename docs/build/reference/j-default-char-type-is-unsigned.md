---
title: -J (既定の char 型の unsigned) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.DefaultCharIsUnsigned
- VC.Project.VCCLWCECompilerTool.DefaultCharIsUnsigned
- /j
dev_langs:
- C++
helpviewer_keywords:
- defaults, char type
- char data type
- -J compiler option [C++]
- /J compiler option [C++]
- J compiler option [C++]
- default char type is unsigned
ms.assetid: 50973667-6638-491e-9c41-bff73acae19f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a93172296b0e2e6d54dc428ffc62812ad979b160
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374467"
---
# <a name="j-default-char-type-is-unsigned"></a>/J (既定の char 型の unsigned への変更)
既定値が変更`char`から入力`signed char`に`unsigned char`、および`char`型は、ゼロ拡張に上位変換することは、`int`型です。  
  
## <a name="syntax"></a>構文  
  
```  
/J  
```  
  
## <a name="remarks"></a>コメント  
 場合、`char`として値が明示的に宣言`signed`、 **/J**オプションには影響しません、および値を符号拡張に上位変換するには、`int`型です。  
  
 **/J**オプションを定義`_CHAR_UNSIGNED`で使用される`#ifndef`既定値の範囲を定義する LIMITS.h ファイルで`char`型です。  
  
 ANSI C および C++ での特定の実装が必要ありません、`char`型です。 このオプションは、最終的に英語以外の言語に変換する文字データを扱うときに便利です。  
  
> [!NOTE]
>  ATL と MFC でこのコンパイラ オプションを使用する場合、エラーを生成する可能性があります。 定義することでこのエラーを無効にすることが`_ATL_ALLOW_CHAR_UNSIGNED`、この回避策がサポートされておらず、常には動作しない可能性があります。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  **ソリューション エクスプローラー**で、プロジェクトのショートカット メニューを開き、 **[プロパティ]** をクリックします。  
  
2.  プロジェクトで**プロパティ ページ**ダイアログ ボックスの下の左ペインで**構成プロパティ**、展開**C/C++** し、**コマンドライン**.  
  
3.  **追加オプション** ウィンドウで、指定、 **/J**コンパイラ オプション。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DefaultCharIsUnsigned%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)   
 [プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)