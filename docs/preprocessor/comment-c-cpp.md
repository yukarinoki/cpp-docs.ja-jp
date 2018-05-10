---
title: コメント (C/C++) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.comment
- comment_CPP
dev_langs:
- C++
helpviewer_keywords:
- annotations [C++]
- comments [C++], compiled files
- pragmas, comment
- comment pragma
ms.assetid: 20f099ff-6303-49b3-9c03-a94b6aa69b85
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 30683bb76ce674becb81321607bc95fefdb78ac1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="comment-cc"></a>コメント (C/C++)
オブジェクト ファイルまたは実行可能ファイル内にコメント レコードを配置します。  
  
## <a name="syntax"></a>構文  
  
```  
  
#pragma comment( comment-type [,"commentstring"] )  
```  
  
## <a name="remarks"></a>コメント  
 *コメント型*の 1 つ以下に示す定義済みの識別子は、コメント レコードの種類を指定します。 省略可能な `commentstring` は、いくつかのコメントの種類で追加情報を指定する文字列リテラルです。 `commentstring`は文字列リテラル、エスケープ文字、埋め込まれた引用符に関して、文字列リテラルのすべての規則に従います (**"**)、および連結します。  
  
 **compiler**  
 オブジェクト ファイル内にコンパイラの名前とバージョン番号を配置します。 このコメント レコードはリンカーには無視されます。 このレコードの種類で `commentstring` パラメーターを指定すると、コンパイラが警告を生成します。  
  
 **exestr**  
 オブジェクト ファイル内に `commentstring` を配置します。 リンク時に、この文字列は実行可能ファイルに配置されます。 実行可能ファイルが読み込まれるとき、この文字列はメモリには読み込まれません。ただし、ファイル内の出力可能文字列を検出するプログラムで検出できます。 このコメント レコードの種類の使用方法の 1 つは、実行可能ファイルにバージョン番号や同様の情報を埋め込むことです。  
  
 
  `exestr` の使用は非推奨とされており、将来のリリースで削除されます。リンカーは、このコメント レコードを処理しません。  
  
 **lib**  
 オブジェクト ファイル内にライブラリ検索レコードを配置します。 このコメントの種類では、リンカーで検索するライブラリの名前 (および場合によってはパス) を含む `commentstring` パラメーターを指定する必要があります。 オブジェクト ファイルにある既定のライブラリ検索レコードに依存して、ライブラリの名前必要があるという名前が、コマンドラインでことで、ライブラリを指定しない場合と同様に、リンカーがこのライブラリの検索[/nodefaultlib](../build/reference/nodefaultlib-ignore-libraries.md)です。 同じソース ファイルに複数のライブラリ検索レコードを配置できます。各レコードは、ソース ファイルで見つかった順序と同じ順序でオブジェクト ファイルに出現します。  
  
 既定のライブラリおよび追加されたライブラリの順序が重要な場合は、コンパイル、 [/Zl](../build/reference/zl-omit-default-library-name.md)スイッチにより、既定のライブラリ名はオブジェクト モジュールに配置されているからです。 2 つ目の comment プラグマを使用して、追加したライブラリの後に既定のライブラリの名前を挿入することができます。 これらのプラグマを使用して指定したライブラリは、ソース コードと同じ順序でオブジェクト モジュールに出現します。  
  
 **linker**  
 場所、[リンカー オプション](../build/reference/linker-options.md)オブジェクト ファイルにします。 このコメントの種類を使用して、コマンド ラインに渡す代わりにリンカー オプションを指定するか、開発環境でリンカー オプションを指定することができます。 たとえば、/include オプションを指定して、強制的にシンボルを追加できます。  
  
```  
#pragma comment(linker, "/include:__mySymbol")  
```  
  
 次のオプションのみ (*コメント型*) リンカー オプションをリンカー識別子に渡される使用できます。  
  
-   [/DEFAULTLIB](../build/reference/defaultlib-specify-default-library.md)  
  
-   [/EXPORT](../build/reference/export-exports-a-function.md)  
  
-   [/INCLUDE](../build/reference/include-force-symbol-references.md)  
  
-   [/MANIFESTDEPENDENCY](../build/reference/manifestdependency-specify-manifest-dependencies.md)  
  
-   [/MERGE](../build/reference/merge-combine-sections.md)  
  
-   [/SECTION](../build/reference/section-specify-section-attributes.md)  
  
 **user**  
 オブジェクト ファイル内に一般的なコメントを配置します。 `commentstring` パラメーターで、コメントのテキストを指定します。 このコメント レコードはリンカーには無視されます。  
  
 次のプラグマを指定すると、リンカーはリンク中に EMAPI.LIB ライブラリを探します。 リンカーは、まず現在の作業ディレクトリ内を検索し、次に LIB 環境変数で指定されたパス内を検索します。  
  
```  
#pragma comment( lib, "emapi" )  
```  
  
 次のプラグマを指定すると、コンパイラはオブジェクト ファイル内にコンパイラの名前とバージョン番号を埋め込みます。  
  
```  
#pragma comment( compiler )  
```  
  
> [!NOTE]
>  `commentstring` パラメーターを受け取るコメントの場合、マクロが文字列リテラルに展開されるのであれば、文字列リテラルを使用するどの場所でもそのマクロを使用できます。 文字列リテラルと、文字列リテラルに展開されるマクロとの任意の組み合わせを連結することもできます。 たとえば、次のステートメントは許容されます。  
  
```  
#pragma comment( user, "Compiled on " __DATE__ " at " __TIME__ )   
```  
  
## <a name="see-also"></a>関連項目  
 [プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)