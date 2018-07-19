---
title: -検証-文字セット (互換性のある文字の検証) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- /validate-charset
- validate-charset
dev_langs:
- C++
helpviewer_keywords:
- /validate-charset compiler option
ms.assetid: 50360fd0-4d32-4a4f-95d0-53d38c12ad4c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0804d9d2714cc8c4f065b6908788c067c34ca44b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377389"
---
# <a name="validate-charset-validate-for-compatible-characters"></a>/validate-charset (互換性のある文字の検証)
ソース ファイルのテキストに表現できる文字だけが含まれている検証 utf-8 として。  
  
## <a name="syntax"></a>構文  
  
```  
/validate-charset[-]  
```  
  
## <a name="remarks"></a>コメント  
 使用することができます、 **/validate-charset**ソース コードには、ソース文字で表すことができる文字セットし、実行文字セットのみが含まれることを検証するにはオプションです。 指定すると、このチェックが自動的に有効 **/source-charset**、 **/execution-charset**、または **/utf-8**コンパイラ オプション。 指定してこのチェックを無効にすることが明示的に、 **/validate -文字セットの**オプション。  
  
 既定では、Visual Studio を判断するかどうか、ソース ファイルを Unicode 形式でエンコードされたなど、utf-8 または utf-16 バイト順マークを検出します。 バイト順マークが見つからない場合は、ソース ファイルを使用してエンコード、現在のユーザー コード ページを使用して、コード ページを指定した場合を除き、想定しています。 **/utf-8**または **/source-charset**オプション。 Visual Studio では、いくつかの文字エン コードのいずれかを使用して、C++ ソース コードを保存することができます。 ソースおよび実行文字セットの詳細については、次を参照してください。[文字セット](../../cpp/character-sets.md)言語のドキュメントにします。 一覧には、コード ページ識別子がサポートされている文字セットの名前を参照してください。[コード ページ識別子](http://msdn.microsoft.com/library/windows/desktop/dd317756)です。  
  
 Visual Studio では、ソース文字セットと実行文字セットの間で変換中に内部の文字エン コードとして utf-8 を使用します。 Utf-8 変換が疑問符 () を置き換える場合は、ソース ファイル内の文字は、実行文字セットで表されることはできません、'?' 文字です。 **/Validate-charset**オプションは、このような場合に警告を報告する、コンパイルします。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  展開して、**構成プロパティ**、 **C/C++**、**コマンド ライン**フォルダーです。  
  
3.  **オプションの高度な**、追加、 **/validate-charset**オプション、および最適なエンコーディングを指定します。  
  
4.  選択**OK**して変更を保存します。  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)   
 [/execution-charset (設定実行文字セット)](../../build/reference/execution-charset-set-execution-character-set.md)   
 [/source-charset (設定ソース文字セット)](../../build/reference/source-charset-set-source-character-set.md)   
 [/utf-8 (ソースと実行可能ファイルの文字セットを UTF-8 に設定する)](../../build/reference/utf-8-set-source-and-executable-character-sets-to-utf-8.md)