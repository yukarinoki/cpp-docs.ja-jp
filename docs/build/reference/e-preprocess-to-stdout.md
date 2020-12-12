---
description: 詳細については、次を参照してください:/E (stdout へのプリプロセス)
title: /E (プリプロセス出力の標準出力へのコピー)
ms.date: 11/04/2016
f1_keywords:
- /e
helpviewer_keywords:
- -E compiler option [C++]
- /E compiler option [C++]
- preprocessor output, copy to stdout
- preprocessor output
ms.assetid: ddbb1725-d950-4978-ab2f-30a5cd7b778c
ms.openlocfilehash: 9d6c9ea3a5fcf8e7ba06ede6e7e70d933b5c921a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192610"
---
# <a name="e-preprocess-to-stdout"></a>/E (プリプロセス出力の標準出力へのコピー)

C と C++ のソースファイルをプリプロセスし、前処理されたファイルを標準出力デバイスにコピーします。

## <a name="syntax"></a>構文

```
/E
```

## <a name="remarks"></a>解説

このプロセスでは、すべてのプリプロセッサディレクティブが実行され、マクロの展開が実行されて、コメントが削除されます。 プリプロセスされた出力のコメントを保持するには、 [/c (プリプロセス時のコメントの保持)](c-preserve-comments-during-preprocessing.md) コンパイラオプションも使用します。

**/E** `#line` インクルードされた各ファイルの先頭と末尾の出力にディレクティブを追加し、条件付きコンパイルのプリプロセッサディレクティブによって削除された行を囲みます。 これらのディレクティブは、前処理されたファイルの行の番号を付けます。 その結果、処理の後の段階で生成されたエラーは、前処理されたファイル内の行ではなく、元のソースファイルの行番号を参照します。

**/E** オプションを指定すると、コンパイルが抑制されます。 コンパイルのために、前処理されたファイルを再送信する必要があります。 **/E** 、 **/fa**、 **/fa**、および **/fm** オプションの出力ファイルも抑制します。 詳細については、「 [/fa、/fa (リスティングファイル)](fa-fa-listing-file.md) 」、および「 [/Fm (マップファイル名](fm-name-mapfile.md)の指定)」を参照してください。

ディレクティブを抑制するに `#line` は、代わりに、 [/ep (#line ディレクティブを使用しない stdout へのプリプロセス)](ep-preprocess-to-stdout-without-hash-line-directives.md) オプションを使用します。

プリプロセスされた出力をではなくファイルに送信するに `stdout` は、代わりに [/P (ファイルを前処理する)](p-preprocess-to-a-file.md) オプションを使用します。

ディレクティブを抑制 `#line` し、前処理された出力をファイルに送信するには、 **/P** と **/ep** を一緒に使用します。

**/E** オプションでプリコンパイル済みヘッダーを使用することはできません。

別のファイルにプリプロセスする場合、トークンの後にスペースは出力されないことに注意してください。 これにより、無効なプログラムが発生したり、意図しない副作用が発生したりする可能性があります。 次のプログラムは正常にコンパイルされます。

```
#define m(x) x
m(int)main( )
{
   return 0;
}
```

ただし、を使用してコンパイルする場合は、次のようになります。

```
cl -E test.cpp > test2.cpp
```

`int main` test2 では、.cpp は正しくあり `intmain` ません。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. **[コマンド ライン]** プロパティ ページをクリックします。

1. [ **追加オプション**] ボックスにコンパイラオプションを入力します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GeneratePreprocessedFile%2A>

## <a name="example"></a>例

次のコマンドラインでは、プリコードを実行し、 `ADD.C` コメントを保持し、 `#line` ディレクティブを追加し、結果を標準出力デバイスに表示します。

```
CL /E /C ADD.C
```

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)
