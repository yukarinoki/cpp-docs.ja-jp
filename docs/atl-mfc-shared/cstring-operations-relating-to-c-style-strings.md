---
description: 詳細については、C スタイルの文字列に関連する CString 操作に関するページを参照してください。
title: C スタイルの文字列に関連する CString の操作方法
ms.date: 11/04/2016
helpviewer_keywords:
- CString objects, basic operations
- MFC [C++], string handling class
- string conversion [C++], C-style strings
- strings [C++], string operations
- standard run-time library string functions
- null values, Null-terminated string conversion
- string functions
- strings [C++], in C
- string arguments
- C-style strings
- strings [C++], class CString
- casting CString objects
ms.assetid: 5048de8a-5298-4891-b8a0-c554b5a3ac1b
ms.openlocfilehash: a9f34ad1a7e38197b4714b073bdb47db046a394c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167137"
---
# <a name="cstring-operations-relating-to-c-style-strings"></a>C スタイルの文字列に関連する CString の操作方法

[CString](../atl-mfc-shared/using-cstring.md)オブジェクトには、文字列データが含まれています。 `CString`文字列データを操作するために、クラステンプレート[CStringT](../atl-mfc-shared/reference/cstringt-class.md)で定義されている[メソッドと演算子](../atl-mfc-shared/reference/cstringt-class.md)のセットを継承します。 ( `CString` は、で **`typedef`** `CStringT` サポートされる文字データの種類を操作することを専門とするです `CString` )。

`CString` は文字データを C スタイルの null で終わる文字列として内部的に格納しません。 代わりに、`CString` は文字データの長さを追跡して、より安全にデータとそれに必要な領域を監視できるようにします。

`CString` は C スタイルの文字列を受け入れ、C スタイルの文字列として文字データにアクセスする方法を提供します。 このトピックの次のセクションで、`CString` オブジェクトを C スタイルの null で終わる文字列と同じように使用する方法について説明します。

- [C スタイルの null で終わる文字列への変換](#_core_using_cstring_as_a_c.2d.style_null.2d.terminated_string)

- [標準ランタイム ライブラリ文字列関数の操作](#_core_working_with_standard_run.2d.time_library_string_functions)

- [CString の内容の直接変更](#_core_modifying_cstring_contents_directly)

- [可変個引数関数での CString オブジェクトの使用](#_core_using_cstring_objects_with_variable_argument_functions)

- [CString 仮パラメーターの指定](#_core_specifying_cstring_formal_parameters)

## <a name="using-cstring-as-a-c-style-null-terminated-string"></a><a name="_core_using_cstring_as_a_c.2d.style_null.2d.terminated_string"></a> CString を C スタイルの Null-Terminated 文字列として使用する

`CString`オブジェクトを C スタイルの文字列として使用するには、オブジェクトを LPCTSTR にキャストします。 次の例では、`CString` は読み取り専用で C スタイルの null で終わる文字列へのポインターを返します。 `strcpy` 関数は、C スタイルの文字列のコピーを変数 `myString` に入れます。

```cpp
CString aCString = "A string";
char myString[256];
strcpy(myString, (LPCTSTR)aCString);
```

`CString` メソッド (`SetAt` など) を使用して、文字列オブジェクトの個々の文字を変更できます。 ただし、LPCTSTR ポインターは一時的であり、に変更が加えられると無効になり `CString` ます。 `CString` がスコープから外れ、自動的に削除されることもあります。 オブジェクトを使用するたびに、オブジェクトの新しい LPCTSTR ポインターを取得することをお勧め `CString` します。

場合によっては、直接変更するために `CString` データのコピーが必要になる場合があります。 より安全な関数 `strcpy_s` (または Unicode/MBCS との移植性がある `_tcscpy_s`) を使用して、`CString` オブジェクトを別のバッファーにコピーします。 次の例に示すように、ここで文字を安全に変更できます。

[!code-cpp[NVC_ATLMFC_Utilities#189](../atl-mfc-shared/codesnippet/cpp/cstring-operations-relating-to-c-style-strings_1.cpp)]

> [!NOTE]
> `strcpy_s`(または unicode/MBCS + ポータブル) の3番目の引数 `_tcscpy_s` は、 `const wchar_t*` (unicode) または `const char*` (ANSI) のいずれかです。 前述の例では、この引数に `CString` を渡しています。 C++ コンパイラは `CString` クラス用に定義されている変換関数を自動的に適用します。この関数は `CString` を `LPCTSTR` に変換します。 ある型から別の型へのキャスト操作を定義する機能は、C++ の最も有効な機能の 1 つです。

## <a name="working-with-standard-run-time-library-string-functions"></a><a name="_core_working_with_standard_run.2d.time_library_string_functions"></a> 標準 Run-Time ライブラリ文字列関数の操作

`CString` などの標準 C ランタイム ライブラリ文字列関数 (または Unicode/MBCS との移植性がある `strcmp`) を使用して検討対象の文字列操作を実行するために、`_tcscmp` メソッドを検索できる必要があります。

C ランタイム文字列関数を使用する必要がある場合は、「_core_using_cstring_as_a_c. style_null. terminated_string」で説明されている手法を使用できます。 `CString` オブジェクトを同等の C スタイルの文字列バッファーにコピーし、そのバッファーに対して操作を実行してから、結果の C スタイルの文字列を `CString` オブジェクトに割り当てることができます。

## <a name="modifying-cstring-contents-directly"></a><a name="_core_modifying_cstring_contents_directly"></a> CString コンテンツを直接変更する

ほとんどの場合、`CString` オブジェクトの内容を変更するか、または `CString` を C スタイルの文字列に変換するには、`CString` メンバー関数を使用する必要があります。

場合によっては、`CString` の内容を直接変更する方が合理的であることがあります。たとえば、文字バッファーを必要とするオペレーティング システム関数を使用する場合などです。

`GetBuffer` メソッドと `ReleaseBuffer` メソッドでは、`CString` オブジェクトの内部文字バッファーへのアクセスが提供され、これを使用して直接変更できます。 次の手順では、このような目的でこれらの関数を使用する方法を示します。

### <a name="to-use-getbuffer-and-releasebuffer-to-access-the-internal-character-buffer-of-a-cstring-object"></a>GetBuffer と ReleaseBuffer を使用して CString オブジェクトの内部文字バッファーにアクセスするには

1. `GetBuffer` オブジェクトの `CString` を呼び出して、必要なバッファーの長さを指定します。

1. `GetBuffer` によって返されたポインターを使用して、`CString` オブジェクトに直接文字を書き込みます。

1. `ReleaseBuffer` オブジェクトの `CString` を呼び出して、文字列の長さなどのすべての内部的な `CString` 状態情報を更新します。 `CString` オブジェクトの内容を直接変更した後、先に `ReleaseBuffer` を呼び出してから、その他の `CString` メンバー関数を呼び出す必要があります。

## <a name="using-cstring-objects-with-variable-argument-functions"></a><a name="_core_using_cstring_objects_with_variable_argument_functions"></a> 可変個引数関数での CString オブジェクトの使用

一部の C 関数は、可変個の引数を受け取ります。 主な例として `printf_s` があります。 この種類の関数の宣言方法では、コンパイラは引数の型がわからず、それぞれの引数で実行する変換操作を決定できません。 そのため、可変個の引数を受け取る関数に `CString` オブジェクトを渡す場合は、明示的な型キャストを使用することが重要です。

`CString`変数引数関数でオブジェクトを使用するには、次の例に示すように、を明示的に `CString` LPCTSTR string にキャストします。

[!code-cpp[NVC_ATLMFC_Utilities#190](../atl-mfc-shared/codesnippet/cpp/cstring-operations-relating-to-c-style-strings_2.cpp)]

## <a name="specifying-cstring-formal-parameters"></a><a name="_core_specifying_cstring_formal_parameters"></a> CString 仮パラメーターの指定

文字列引数を必要とするほとんどの関数では、関数プロトタイプの仮パラメーターを **`const`** 、ではなく文字 () へのポインターとして指定することをお勧めし `LPCTSTR` `CString` ます。 仮パラメーターが文字へのポインターとして指定されている場合は、 **`const`** TCHAR 配列、リテラル文字列 [ `"hi there"` ]、またはオブジェクトへのポインターを渡すことができ `CString` ます。 オブジェクトは、 `CString` 自動的に LPCTSTR に変換されます。 LPCTSTR を使用できる場所であれば、オブジェクトを使用することもでき `CString` ます。

また、 `const CString&` 引数が変更されない場合は、仮パラメーターを定数文字列参照 (つまり、) として指定することもできます。 文字列が **`const`** 関数によって変更される場合は、修飾子を削除します。 既定の null 値が必要な場合は、次に示すように、これを null 文字列 [`""`] に初期化します。

[!code-cpp[NVC_ATLMFC_Utilities#191](../atl-mfc-shared/codesnippet/cpp/cstring-operations-relating-to-c-style-strings_3.cpp)]

ほとんどの関数の結果では、単に値で `CString` オブジェクトを返すことができます。

## <a name="see-also"></a>関連項目

[文字列 (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[CString 引数の引き渡し](../atl-mfc-shared/cstring-argument-passing.md)
