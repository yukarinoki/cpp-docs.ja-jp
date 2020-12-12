---
description: 詳細については、「TCHAR を使用する」を参照してください。_MBCS コードを使用した H データ型
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
ms.openlocfilehash: 4672ba210e0df0af1a4f4ee106d31cc978bdf2fc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97306587"
---
# <a name="using-tcharh-data-types-with-_mbcs-code"></a>_MBCS コードでの TCHAR.H データ型の使用

マニフェスト定数 `_MBCS` が定義されている場合、特定の汎用テキストルーチンは、次のいずれかのルーチンにマップされます。

- マルチバイト、文字、文字列を適切に処理する SBCS ルーチン。 この場合、文字列引数は型である必要があり **`char*`** ます。 たとえば、は `_tprintf` にマップ `printf` され、への文字列引数 `printf` は型に **`char*`** なります。 `_TCHAR`文字列型に汎用テキストのデータ型を使用する場合は、 `printf` がにマップされるため、の仮パラメーターと実パラメーターの型が一致し `_TCHAR*` **`char*`** ます。

- MBCS 固有ルーチン。 この場合、文字列引数は `unsigned char*` 型であることを想定しています。 たとえば、`_tcsrev` は、`unsigned char*` 型の文字列を必要とし、それを返す `_mbsrev` にマップされます。 `_TCHAR`文字列型に汎用テキストデータ型を使用する場合は、が型にマップされるため、型が競合する可能性があり `_TCHAR` **`char`** ます。

この型の競合 (および C コンパイラの警告または C++ コンパイラのエラーという結果) を回避するためには、次のような 3 つの解決方法があります。

- 既定の動作を使用します。 tchar.h は、次の例に示すように、ランタイムライブラリのルーチンに汎用テキストルーチンのプロトタイプを提供します。

    ```cpp
    char * _tcsrev(char *);
    ```

   既定の場合、のプロトタイプは、 `_tcsrev` Libc の `_mbsrev` サンクを介してにマップされます。 これにより、 `_mbsrev` 受信パラメーターと送信戻り値の型が `_TCHAR*` (つまり、) からに変更され `char *` `unsigned char *` ます。 このメソッドは、を使用している場合に型の一致を保証し `_TCHAR` ますが、関数呼び出しのオーバーヘッドが原因で比較的低速になります。

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

   この方法を使用する場合は、文字列の引数と文字列の戻り値に適切なデータ型を使用するように注意する必要があります。 適切に型を一致させるために型キャストを使用できます。または、汎用テキストのデータ型である `_TXCHAR` を使用できます。 `_TXCHAR` SBCS コードの型にマップさ **`char`** れますが、MBCS コードでは型にマップさ **`unsigned char`** れます。 汎用テキストマクロの詳細については、「*ランタイムライブラリリファレンス*」の「[汎用テキストマップ](../c-runtime-library/generic-text-mappings.md)」を参照してください。

## <a name="see-also"></a>関連項目

[Tchar. h の汎用テキストマッピング](../text/generic-text-mappings-in-tchar-h.md)
