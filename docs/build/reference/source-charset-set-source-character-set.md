---
title: -ソース-文字セット (一連のソース文字セット) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- source-charset
- /source-charset
dev_langs:
- C++
helpviewer_keywords:
- /execution-charset compiler option
ms.assetid: d3c5bf7f-526d-4ee4-acc5-c1a02a4fc481
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e4f010eb0f0b83dbc41ebeff624033e59d582535
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379225"
---
# <a name="source-charset-set-source-character-set"></a>/source-charset (設定ソース文字セット)
ソース文字セットの実行可能ファイルで指定することができます。  
  
## <a name="syntax"></a>構文  
  
```  
/source-charset:[IANA_name|.CPID]  
```  
  
## <a name="arguments"></a>引数  
 **IANA_name**  
 IANA で定義されている文字セットの名前。  
  
 **CPID**  
 10 進数としてコード ページ id。  
  
## <a name="remarks"></a>コメント  
 使用することができます、 **/source-charset**ソース ファイルは、基本ソース文字セットには表されない文字を含める場合に使用する、拡張のソース文字セットを指定するオプションです。 ソース文字セットは、コンパイル前に、プリプロセス フェーズへの入力として使用される内部表現に、プログラムのソース テキストを解釈するために使用するエンコードです。 内部表現は、実行可能ファイルに文字列と文字の値を格納する、実行文字セットに変換されます。 IANA が、いずれかを使用する ISO 文字セットの名前、またはドット (.) の後に、使用する文字セットを指定する 3 ~ 5 桁の 10 進コード ページ識別子。 一覧には、コード ページ識別子がサポートされている文字セットの名前を参照してください。[コード ページ識別子](http://msdn.microsoft.com/library/windows/desktop/dd317756)です。  
  
 既定では、Visual Studio を判断するかどうか、ソース ファイルを Unicode 形式でエンコードされたなど、utf-8 または utf-16 バイト順マークを検出します。 バイト順マークが見つからない場合は、ソース ファイルがエンコードされている、現在のユーザー コード ページを使用して文字を使用して名前またはコード ページの設定を指定しない限り、想定しています。、 **/source-charset**オプション。 Visual Studio では、いくつかの文字エン コードのいずれかを使用して、C++ ソース コードを保存することができます。 ソースと実行文字セットの詳細については、次を参照してください。[文字セット](../../cpp/character-sets.md)言語のドキュメントにします。  
  
 指定するソース文字セットは、の文字セットで同じコード ポイントを 7 ビット ASCII 文字をマップする必要がありますか、コンパイル エラーの多くが従う可能性があります。 ソース文字セットも拡張の Unicode 文字の utf-8 で encodable セットにマップ可能な場合があります。 Encodable utf-8 ではない文字は、実装固有 substitute で表されます。 Microsoft コンパイラでは、これらの文字を疑問符 () を使用します。  
  
 使用することができます、ソース文字セットと実行文字セットの両方を utf-8 に設定する場合、 **/utf-8**ショートカットとしてコンパイラ オプション。 指定することと等価である **/source -charset:utf-8/execution-charset:utf-8**コマンド ラインでします。 これらのいずれかのオプションも有効、 **/validate-charset**既定ではオプションです。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  展開して、**構成プロパティ**、 **C/C++**、**コマンド ライン**フォルダーです。  
  
3.  **オプションの高度な**、追加、 **/source-charset**オプション、および最適なエンコーディングを指定します。  
  
4.  選択**OK**して変更を保存します。  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)   
 [/execution-charset (設定実行文字セット)](../../build/reference/execution-charset-set-execution-character-set.md)   
 [/utf-8 (ソースの設定と実行可能ファイルの文字セットを utf-8 に)](../../build/reference/utf-8-set-source-and-executable-character-sets-to-utf-8.md)   
 [/validate-charset (互換性のある文字の検証)](../../build/reference/validate-charset-validate-for-compatible-characters.md)