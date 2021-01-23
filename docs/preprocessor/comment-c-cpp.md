---
description: pragmaMicrosoft C/c + + での comment ディレクティブの詳細について説明します。
title: 関する pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.comment
- comment_CPP
helpviewer_keywords:
- annotations [C++]
- comments [C++], compiled files
- pragma, comment
- comment pragma
no-loc:
- pragma
ms.openlocfilehash: 8a4df005b672cb108a2b55004a1149693acd4f95
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713065"
---
# <a name="comment-no-locpragma"></a>`comment` pragma

オブジェクト ファイルまたは実行可能ファイル内にコメント レコードを配置します。

## <a name="syntax"></a>構文

> **`#pragma comment(`***comment-type* [ **`,`** "*comment-string*"]**`)`**

## <a name="remarks"></a>解説

*コメントの種類* は、次に示す定義済みの識別子の1つで、コメントレコードの種類を指定します。 *コメント文字列*(省略可能) は、一部のコメントの種類に関する追加情報を提供する文字列リテラルです。 *コメント文字列* は文字列リテラルであるため、エスケープ文字、埋め込み引用符 ()、および連結を使用する場合の文字列リテラルのすべての規則に従い `"` ます。

### <a name="compiler"></a>compiler

オブジェクト ファイル内にコンパイラの名前とバージョン番号を配置します。 このコメント レコードはリンカーには無視されます。 このレコードの種類に *コメント文字列* パラメーターを指定すると、コンパイラによって警告が生成されます。

### <a name="lib"></a>lib

オブジェクト ファイル内にライブラリ検索レコードを配置します。 このコメントの種類には、リンカーが検索するライブラリの名前 (および場合によってはパス) を持つ *コメント文字列* パラメーターが指定されている必要があります。 ライブラリ名は、オブジェクトファイル内の既定のライブラリ検索レコードに従います。 リンカーは、を使用してライブラリが指定されていない限り、コマンドラインで指定した場合と同じ方法でこのライブラリを検索し [`/nodefaultlib`](../build/reference/nodefaultlib-ignore-libraries.md) ます。 同じソースファイルに複数のライブラリ検索レコードを配置できます。 各レコードは、ソースファイル内で見つかった順序で、オブジェクトファイルに表示されます。

既定のライブラリと追加されたライブラリの順序が重要な場合は、スイッチを使用してコンパイルすると、 [`/Zl`](../build/reference/zl-omit-default-library-name.md) 既定のライブラリ名がオブジェクトモジュールに配置されなくなります。 2番目のコメントは、追加され pragma たライブラリの後に既定のライブラリの名前を挿入するために使用できます。 これらのディレクティブと共に一覧表示されたライブラリ pragma は、ソースコード内で見つかった順序でオブジェクトモジュールに表示されます。

### <a name="linker"></a>リンカー

[リンカーオプション](../build/reference/linker-options.md)をオブジェクトファイルに配置します。 このコメントの種類を使用して、コマンド ラインに渡す代わりにリンカー オプションを指定するか、開発環境でリンカー オプションを指定することができます。 たとえば、/include オプションを指定して、強制的にシンボルを追加できます。

```C
#pragma comment(linker, "/include:__mySymbol")
```

リンカー識別子に渡すことができるのは、次の (*コメントの種類*) リンカーオプションだけです。

- [`/DEFAULTLIB`](../build/reference/defaultlib-specify-default-library.md)

- [`/EXPORT`](../build/reference/export-exports-a-function.md)

- [`/INCLUDE`](../build/reference/include-force-symbol-references.md)

- [`/MANIFESTDEPENDENCY`](../build/reference/manifestdependency-specify-manifest-dependencies.md)

- [`/MERGE`](../build/reference/merge-combine-sections.md)

- [`/SECTION`](../build/reference/section-specify-section-attributes.md)

### <a name="user"></a>user

オブジェクト ファイル内に一般的なコメントを配置します。 *コメント文字列* パラメーターには、コメントのテキストが含まれています。 このコメント レコードはリンカーには無視されます。

## <a name="examples"></a>例

次の pragma ようにすると、リンカーによって EMAPI が検索されます。リンク中の LIB ライブラリ。 リンカーは、最初に現在の作業ディレクトリを検索し、次に LIB 環境変数で指定されたパスを検索します。

```C
#pragma comment( lib, "emapi" )
```

次のようにすると、コンパイラ pragma によってコンパイラの名前とバージョン番号がオブジェクトファイルに格納されます。

```C
#pragma comment( compiler )
```

*コメント文字列* パラメーターを受け取るコメントの場合、マクロが文字列リテラルに展開されていれば、文字列リテラルを使用する任意の場所でマクロを使用できます。 文字列リテラルと、文字列リテラルに展開されるマクロとの任意の組み合わせを連結することもできます。 たとえば、次のステートメントは許容されます。

```C
#pragma comment( user, "Compiled on " __DATE__ " at " __TIME__ )
```

## <a name="see-also"></a>関連項目

[プラグマディレクティブと `__pragma` `_Pragma` キーワードおよびキーワード](./pragma-directives-and-the-pragma-keyword.md)
