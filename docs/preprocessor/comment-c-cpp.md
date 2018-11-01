---
title: コメント (C/C++)
ms.date: 11/04/2016
f1_keywords:
- vc-pragma.comment
- comment_CPP
helpviewer_keywords:
- annotations [C++]
- comments [C++], compiled files
- pragmas, comment
- comment pragma
ms.assetid: 20f099ff-6303-49b3-9c03-a94b6aa69b85
ms.openlocfilehash: ec80e8cf177becdc25bdf49d6dfa9ad9c7794b88
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50612824"
---
# <a name="comment-cc"></a>コメント (C/C++)

オブジェクト ファイルまたは実行可能ファイル内にコメント レコードを配置します。

## <a name="syntax"></a>構文

```
#pragma comment( comment-type [,"commentstring"] )
```

## <a name="remarks"></a>Remarks

*コメント型*の 1 つ以下に示す定義済みの識別子は、コメント レコードの型を指定します。 省略可能な*commentstring*はいくつかの種類の注釈の追加情報を提供する文字列リテラルです。 *Commentstring*は文字列リテラル、エスケープ文字を埋め込み引用符に関して、文字列リテラルのすべての規則に従います (`"`)、および連結します。

### <a name="compiler"></a>コンパイラ

オブジェクト ファイル内にコンパイラの名前とバージョン番号を配置します。 このコメント レコードはリンカーには無視されます。 指定した場合、 *commentstring*パラメーターがこのレコードの種類、コンパイラの警告が生成されます。

### <a name="exestr"></a>exestr

場所*commentstring*オブジェクト ファイルにします。 リンク時に、この文字列は実行可能ファイルに配置されます。 実行可能ファイルが読み込まれるとき、この文字列はメモリには読み込まれません。ただし、ファイル内の出力可能文字列を検出するプログラムで検出できます。 このコメント レコードの種類の使用方法の 1 つは、実行可能ファイルにバージョン番号や同様の情報を埋め込むことです。

`exestr` の使用は非推奨とされており、将来のリリースで削除されます。リンカーは、このコメント レコードを処理しません。

### <a name="lib"></a>lib

オブジェクト ファイル内にライブラリ検索レコードを配置します。 このコメントの型を含める必要があります、 *commentstring*名前 (と可能性がある、パス)、リンカー検索に使用するライブラリを含むパラメーター。 後に、オブジェクト ファイル内の既定のライブラリ検索レコードをライブラリ名という名前をコマンドラインで提供されることで、ライブラリが指定されていない場合と同様にこのライブラリをリンカーが検索[/nodefaultlib](../build/reference/nodefaultlib-ignore-libraries.md)します。 同じソース ファイルに複数のライブラリ検索レコードを配置できます。各レコードは、ソース ファイルで見つかった順序と同じ順序でオブジェクト ファイルに出現します。

使用して、既定のライブラリと追加のライブラリの順序が重要な場合は、コンパイル、 [/Zl](../build/reference/zl-omit-default-library-name.md)スイッチは、オブジェクト モジュールに配置されているから既定のライブラリ名を防止します。 2 つ目の comment プラグマを使用して、追加したライブラリの後に既定のライブラリの名前を挿入することができます。 これらのプラグマを使用して指定したライブラリは、ソース コードと同じ順序でオブジェクト モジュールに出現します。

### <a name="linker"></a>リンカー

場所、[リンカー オプション](../build/reference/linker-options.md)オブジェクト ファイルにします。 このコメントの種類を使用して、コマンド ラインに渡す代わりにリンカー オプションを指定するか、開発環境でリンカー オプションを指定することができます。 たとえば、/include オプションを指定して、強制的にシンボルを追加できます。

```
#pragma comment(linker, "/include:__mySymbol")
```

次のオプションのみ (*コメント型*) リンカー オプションは linker 識別子に渡すこと。

- [/DEFAULTLIB](../build/reference/defaultlib-specify-default-library.md)

- [/EXPORT](../build/reference/export-exports-a-function.md)

- [/INCLUDE](../build/reference/include-force-symbol-references.md)

- [/MANIFESTDEPENDENCY](../build/reference/manifestdependency-specify-manifest-dependencies.md)

- [/MERGE](../build/reference/merge-combine-sections.md)

- [/SECTION](../build/reference/section-specify-section-attributes.md)

### <a name="user"></a>ユーザー

オブジェクト ファイル内に一般的なコメントを配置します。 *Commentstring*パラメーターには、コメントのテキストが含まれています。 このコメント レコードはリンカーには無視されます。

次のプラグマを指定すると、リンカーはリンク中に EMAPI.LIB ライブラリを探します。 リンカーは、まず現在の作業ディレクトリ内を検索し、次に LIB 環境変数で指定されたパス内を検索します。

```
#pragma comment( lib, "emapi" )
```

次のプラグマを指定すると、コンパイラはオブジェクト ファイル内にコンパイラの名前とバージョン番号を埋め込みます。

```
#pragma comment( compiler )
```

> [!NOTE]
> 受け取るコメントの場合、 *commentstring*パラメーターできますマクロを使用する、リテラル文字列を使用する任意の場所で文字列リテラル、マクロが展開されています。 文字列リテラルと、文字列リテラルに展開されるマクロとの任意の組み合わせを連結することもできます。 たとえば、次のステートメントは許容されます。

```
#pragma comment( user, "Compiled on " __DATE__ " at " __TIME__ )
```

## <a name="see-also"></a>関連項目

[プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)