---
title: _MBCS コードでの TCHAR.H データ型の使用
ms.date: 11/04/2016
helpviewer_keywords:
- mapping generic-text
- generic-text data types [C++]
- generic-text mappings [C++]
- MBCS [C++], generic-text mappings
- TCHAR.H data types, mapping
- mappings [C++], TCHAR.H
ms.assetid: 298583c5-22c3-40f6-920e-9ec96d42abd8
ms.openlocfilehash: 78e5d89e1e87d081e762fab1298eb990b914324c
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446592"
---
# <a name="using-tcharh-data-types-with-_mbcs-code"></a>_MBCS コードでの TCHAR.H データ型の使用

マニフェスト定数 `_MBCS` が定義されている場合、特定の汎用テキストルーチンは次のいずれかのルーチンにマップされます。

- マルチバイト、文字、文字列を適切に処理する SBCS ルーチン。 この場合、文字列引数は `char*` 型であることを想定しています。 たとえば、`_tprintf` は `printf` にマップされ、`printf` への文字列引数は `char*` 型になります。 文字列型として汎用テキストのデータ型である `_TCHAR` を使用する場合、`printf` は `_TCHAR*` にマップされるため `char*` の仮パラメーターと実パラメーターの型は一致します。

- MBCS 固有ルーチン。 この場合、文字列引数は `unsigned char*` 型であることを想定しています。 たとえば、`_tcsrev` は、`_mbsrev` 型の文字列を必要とし、それを返す `unsigned char*` にマップされます。 文字列型に `_TCHAR` 汎用テキストデータ型を使用する場合、`_TCHAR` は `char`型にマップされるため、型が競合する可能性があります。

この型の競合 (および C コンパイラの警告または C++ コンパイラのエラーという結果) を回避するためには、次のような 3 つの解決方法があります。

- 既定の動作を使用します。 tchar.h は、次の例に示すように、ランタイムライブラリのルーチンに汎用テキストルーチンのプロトタイプを提供します。

    ```cpp
    char * _tcsrev(char *);
    ```

   既定の場合、`_tcsrev` のプロトタイプは、Libc のサンクを介して `_mbsrev` にマップされます。 これにより、`_mbsrev` の受信パラメーターと送信戻り値の型が `_TCHAR*` (つまり、`char *`) から `unsigned char *`に変更されます。 このメソッドは `_TCHAR`を使用する場合に型の照合を保証しますが、関数呼び出しのオーバーヘッドが原因で比較的低速になります。

- コードに次のプリプロセッサ ステートメントを組み込むことにより、関数のインライン展開を使用します。

    ```cpp
    #define _USE_INLINING
    ```

   このメソッドにより、tchar. h で指定されたインライン関数サンクによって、汎用テキストルーチンが適切な MBCS ルーチンに直接マップされます。 次に示す tchar.h のコードの抜粋では、この方法の例を示しています。

    ```cpp
    __inline char *_tcsrev(char *_s1)
    {return (char *)_mbsrev((unsigned char *)_s1);}
    ```

   インライン展開を使用できる場合は、この方法が最適な解決法になります。確実に型が一致し、追加の時間コストが発生しないからです。

- コードに次のプリプロセッサステートメントを組み込むことにより、直接マッピングを使用します。

    ```cpp
    #define _MB_MAP_DIRECT
    ```

   この方法は、既定の動作を使用したくない場合、またはインライン展開を使用できない場合の代替手段であり、高速です。 これにより、次の tchar.h の例のように、汎用テキストルーチンがマクロによって直接 MBCS バージョンのルーチンにマップされます。

    ```cpp
    #define _tcschr _mbschr
    ```

   この方法を使用する場合は、文字列の引数と文字列の戻り値に適切なデータ型を使用するように注意する必要があります。 適切に型を一致させるために型キャストを使用できます。または、汎用テキストのデータ型である `_TXCHAR` を使用できます。 `_TXCHAR` は、SBCS コードで**char**型にマップされますが、MBCS コードでは**unsigned char**型にマップされます。 汎用テキストマクロの詳細については、「*ランタイムライブラリリファレンス*」の「[汎用テキストマップ](../c-runtime-library/generic-text-mappings.md)」を参照してください。

## <a name="see-also"></a>参照

[tchar.h における汎用テキストのマッピング](../text/generic-text-mappings-in-tchar-h.md)
