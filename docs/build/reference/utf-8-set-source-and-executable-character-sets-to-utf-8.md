---
title: -utf-8 (ソースの設定および実行可能ファイルの文字セットを utf-8) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- /utf-8
dev_langs:
- C++
helpviewer_keywords:
- /utf-8 compiler option
ms.assetid: f0e1f3cb-6cae-46eb-9483-04ed13d9b504
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 90520cd9ad4af484714306c37567ab041a826fcc
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377496"
---
# <a name="utf-8-set-source-and-executable-character-sets-to-utf-8"></a>/utf-8 (ソースの設定と実行可能ファイルの文字セットを utf-8 に)
ソース文字セットし、実行文字セットを utf-8 としての両方を指定します。  
  
## <a name="syntax"></a>構文  
  
```  
/utf-8  
```  
  
## <a name="remarks"></a>コメント  
 使用することができます、 **/utf-8**ソースと実行の両方の文字セットと utf-8 を使用してエンコードを指定するオプションです。 指定することと等価である **/source -charset:utf-8/execution-charset:utf-8**コマンド ラインでします。 これらのいずれかのオプションも有効、 **/validate-charset**既定ではオプションです。 一覧には、コード ページ識別子がサポートされている文字セットの名前を参照してください。[コード ページ識別子](http://msdn.microsoft.com/library/windows/desktop/dd317756)です。  
  
 既定では、Visual Studio を判断するかどうか、ソース ファイルを Unicode 形式でエンコードされたなど、utf-8 または utf-16 バイト順マークを検出します。 バイト順マークが見つからない場合は、ソース ファイルを使用してエンコード、現在のユーザー コード ページを使用して、コード ページを指定した場合を除き、想定しています。 **/utf-8**または **/source-charset**オプション。 Visual Studio では、いくつかの文字エン コードのいずれかを使用して、C++ ソース コードを保存することができます。 ソースおよび実行文字セットの詳細については、次を参照してください。[文字セット](../../cpp/character-sets.md)言語のドキュメントにします。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  展開して、**構成プロパティ**、 **C/C++**、**コマンド ライン**フォルダーです。  
  
3.  **オプションの高度な**、追加、 **/utf-8**オプション、および最適なエンコーディングを指定します。  
  
4.  選択**OK**して変更を保存します。  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)   
 [/execution-charset (設定実行文字セット)](../../build/reference/execution-charset-set-execution-character-set.md)   
 [/source-charset (設定ソース文字セット)](../../build/reference/source-charset-set-source-character-set.md)   
 [/validate-charset (互換性のある文字の検証)](../../build/reference/validate-charset-validate-for-compatible-characters.md)