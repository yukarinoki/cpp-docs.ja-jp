---
title: -実行-文字セット (セット実行文字セット) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- execution-charset
- /execution-charset
dev_langs:
- C++
helpviewer_keywords:
- /execution-charset compiler option
- -execution-charset compiler option
ms.assetid: 0e02f487-2236-45bc-95f3-5760933a8f96
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5bffe1e39aa181a6d53784fbb4501bf8f662b221
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32375953"
---
# <a name="execution-charset-set-execution-character-set"></a>/execution-charset (設定実行文字セット)
実行文字セットの実行可能ファイルで指定することができます。  
  
## <a name="syntax"></a>構文  
  
```  
/execution-charset:[IANA_name|.CPID]  
```  
  
## <a name="arguments"></a>引数  
 **IANA_name**  
 IANA で定義されている文字セットの名前。  
  
 **CPID**  
 コード ページ識別子です。  
  
## <a name="remarks"></a>コメント  
 使用することができます、 **/execution-charset**実行文字セットを指定するオプションです。 実行文字セットは、すべての前処理ステップ コンパイルの段階への入力は、プログラムのテキストに使用されるエンコーディングです。 この文字セットは、コンパイルされたコード内の文字列または文字リテラルの内部表現に使用されます。 ソース ファイルは、基本実行文字セット内ではない文字を含めるときに使用する拡張実行文字セットを指定するには、このオプションを設定します。 IANA が、いずれかを使用する ISO 文字セットの名前、またはドット (.) の後に、使用する文字セットを指定する 3 ~ 5 桁の 10 進コード ページ識別子。 一覧には、コード ページ識別子がサポートされている文字セットの名前を参照してください。[コード ページ識別子](http://msdn.microsoft.com/library/windows/desktop/dd317756)です。  
  
 既定では、Visual Studio を判断するかどうか、ソース ファイルを Unicode 形式でエンコードされたなど、utf-8 または utf-16 バイト順マークを検出します。 バイト順マークが見つからない場合、ソース ファイルがエンコードされて、現在のユーザー コード ページを使用して、文字を使用して名前またはコード ページのセットを指定していない場合に想定しています、 **/source-charset**オプションまたは **/utf-8。** オプション。 Visual Studio では、いくつかの文字エン コードのいずれかを使用して、C++ ソース コードを保存することができます。 ソースおよび実行文字セットの詳細については、次を参照してください。[文字セット](../../cpp/character-sets.md)言語のドキュメントにします。  
  
 使用することができます、ソース文字セットと実行文字セットの両方を utf-8 に設定する場合、 **/utf-8**ショートカットとしてコンパイラ オプション。 指定することと等価である **/source -charset:utf-8/execution-charset:utf-8**コマンド ラインでします。 これらのいずれかのオプションも有効、 **/validate-charset**既定ではオプションです。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  展開して、**構成プロパティ**、 **C/C++**、**コマンド ライン**フォルダーです。  
  
3.  **オプションの高度な**、追加、 **/execution-charset**オプション、および最適なエンコーディングを指定します。  
  
4.  選択**OK**して変更を保存します。  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)   
 [/source-charset (設定ソース文字セット)](../../build/reference/source-charset-set-source-character-set.md)   
 [/utf-8 (ソースの設定と実行可能ファイルの文字セットを utf-8 に)](../../build/reference/utf-8-set-source-and-executable-character-sets-to-utf-8.md)   
 [/validate-charset (互換性のある文字の検証)](../../build/reference/validate-charset-validate-for-compatible-characters.md)