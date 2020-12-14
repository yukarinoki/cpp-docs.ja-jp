---
description: 詳細情報:/H (外部名の長さを制限する)
title: /H (外部名の長さの制限)
ms.date: 09/05/2018
f1_keywords:
- /h
helpviewer_keywords:
- public name length
- /H compiler option [C++]
- H compiler option [C++]
- external names
- -H compiler option [C++]
ms.assetid: de701dd3-ed04-4c88-8195-960d2520ec2e
ms.openlocfilehash: 5df4c4765cc4917e6914eab0b4818c34fceea853
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200079"
---
# <a name="h-restrict-length-of-external-names"></a>/H (外部名の長さの制限)

非推奨になりました。 外部名の長さを制限します。

## <a name="syntax"></a>構文

> **/H**<em>番号</em>

## <a name="arguments"></a>引数

*number*<br/>
プログラムで許可される外部名の最大長を指定します。

## <a name="remarks"></a>解説

既定では、外部 (パブリック) 名の長さは2047文字です。 これは、C および C++ プログラムに当てはまります。 **/H** を使用すると、識別子の許容最大長だけを減らすことができ、値を増やすことはできません。 **/H** と *number* の間のスペースは省略可能です。

*数値* よりも長い外部名がプログラムに含まれている場合、余分な文字は無視されます。 **/H** を指定せずにプログラムをコンパイルし、識別子に2047文字を超える文字が含まれている場合は、コンパイラによって [致命的なエラー C1064](../../error-messages/compiler-errors-1/fatal-error-c1064.md)が生成されます。

長さの制限には、コンパイラによって作成される先頭のアンダースコア ( **\_** ) またはアットマーク () が含まれ **\@** ます。 これらの文字は、識別子の一部であり、重要な場所を取ります。

- コンパイラは **\_** 、(既定) および呼び出し規約によって修飾された名前に先頭のアンダースコア () を追加し、呼び出し規約によって修飾された名前に先頭の **`__cdecl`** **`__stdcall`** アットマーク () を追加し **\@** **`__fastcall`** ます。

- コンパイラは、およびの呼び出し規約によって変更された名前に引数サイズ情報を追加 **`__fastcall`** **`__stdcall`** し、C++ 名に型情報を追加します。

**/H** が役に立つ場合があります。

- 混合言語またはポータブルプログラムを作成する場合。

- 外部識別子の長さに制限を課すツールを使用する場合。

- デバッグビルドでシンボルが使用する領域の量を制限する場合。

次の例では、識別子の長さが制限を超えている場合に、 **/h** を使用して実際にエラーが発生する方法を示します。

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

また、定義済みのコンパイラ識別子により、 **/h** オプションを使用する場合は注意が必要です。 識別子の最大長が小さすぎる場合、特定の定義済み識別子が未解決になり、特定のライブラリ関数呼び出しが解決されます。 たとえば、 `printf` 関数が使用されており、コンパイル時にオプション **/H5** が指定されている場合、を参照するためにシンボル **_prin** が作成され、 `printf` ライブラリには見つかりません。

**/H** の使用は、 [/Gl (プログラム全体の最適化)](gl-whole-program-optimization.md)と互換性がありません。

**/H** オプションは Visual Studio 2005 以降では非推奨とされます。最大長の制限が増加し、 **/h** は不要になりました。 非推奨のコンパイラオプションの一覧については、「[カテゴリ別に一覧表示さ](compiler-options-listed-by-category.md)れたコンパイラオプションの **非推奨のコンパイラオプション**」を参照してください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] [  >  **C/c + +**  >  **コマンドライン**] プロパティページを選択します。

1. [ **追加オプション** ] ボックスにコンパイラオプションを入力します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)
