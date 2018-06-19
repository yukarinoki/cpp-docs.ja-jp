---
title: -H (外部名の長さに制限) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /h
dev_langs:
- C++
helpviewer_keywords:
- public name length
- /H compiler option [C++]
- H compiler option [C++]
- external names
- -H compiler option [C++]
ms.assetid: de701dd3-ed04-4c88-8195-960d2520ec2e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0859c6770da56023df7ba7ba24094bea2e889319
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377562"
---
# <a name="h-restrict-length-of-external-names"></a>/H (外部名の長さの制限)
非推奨。 外部名の長さを制限します。  
  
## <a name="syntax"></a>構文  
  
```  
/Hnumber  
```  
  
## <a name="arguments"></a>引数  
 `number`  
 プログラムで許可された外部名の最大長を指定します。  
  
## <a name="remarks"></a>コメント  
 既定は、外部 (パブリック) 名の長さは 2,047 文字です。 これは、C および C++ プログラムの場合は true です。 使用して **/H**のみ識別子の最大許容長を減らすことができます、長くはできません。 間にスペース **/H**と`number`は省略可能です。  
  
 プログラムより長い外部の名前が含まれている場合`number`、余分な文字は無視されます。 せずにプログラムをコンパイルする場合 **/H**識別子に複数の 2,047 文字が含まれている場合、コンパイラが生成および[致命的なエラー C1064](../../error-messages/compiler-errors-1/fatal-error-c1064.md)です。  
  
 長さの制限には、コンパイラが作成した先頭のアンダー スコア (_) が含まれています。 または、アット マーク (@)。 これらの文字は、識別子の一部であるし、意味のある位置を取得します。  
  
-   コンパイラは、名前に、先頭にアンダー スコア (_) を追加、 `__cdecl` (既定値) と`__stdcall`呼び出し規約、および、先頭がアット マーク (@) によって変更された名前に、`__fastcall`呼び出し規約です。  
  
-   コンパイラによって変更された名前を引数のサイズ情報を追加する、`__fastcall`と`__stdcall`呼び出し規約、および C++ の名前に型情報を追加します。  
  
 検索することがあります **/H**に便利です。  
  
-   混合言語またはポータブル プログラムを作成する場合。  
  
-   外部識別子の長さに制限を課すツールを使用する場合。  
  
-   デバッグ ビルドでシンボルを使用する領域の量を制限する場合。  
  
 次の例に示す方法を使用して **/H**識別子の長さが制限が多すぎる場合はエラーが発生する実際には。  
  
```cpp  
// compiler_option_H.cpp  
// compile with: /H5  
// processor: x86  
// LNK2005 expected  
void func1(void);  
void func2(void);  
  
int main() { func1(); }  
  
void func1(void) {}  
void func2(void) {}  
```  
  
 使用する場合は注意する必要があります、 **/H**コンパイラの定義済みの識別子のためのオプションです。 識別子の最大長が小さすぎる場合、特定済みの識別子が未解決だけでなく特定のライブラリ関数の呼び出しになります。 たとえば場合、`printf`関数が使用されるとオプション **/H5**シンボル、コンパイル時に指定された **_prin**を参照するために作成されます`printf`、これが、見つかりませんライブラリにあります。  
  
 使用 **/H**と互換性がありません[/GL (プログラム全体の最適化)](../../build/reference/gl-whole-program-optimization.md)です。  
  
 **/H**オプションが Visual Studio 2005 以降使用されなくなりました。 最大長の上限を増やすと **/H**は不要です。 非推奨のコンパイラ オプションの一覧は、次を参照してください。**廃止予定とコンパイラ オプションの削除**で[コンパイラ オプションの一覧をカテゴリ別](../../build/reference/compiler-options-listed-by-category.md)です。  
  
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