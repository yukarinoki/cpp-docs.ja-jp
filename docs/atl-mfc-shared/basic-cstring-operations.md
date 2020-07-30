---
title: CString の基本操作
ms.date: 11/04/2016
helpviewer_keywords:
- CString objects, basic operations
- string literals, CString operations
- literal strings, CString operations
- CString objects
- string comparison, CString operations
- characters, accessing in CStrings
ms.assetid: 41db66b2-9427-4bb3-845a-9b6869159a6c
ms.openlocfilehash: fa46e82f19d87c49f652779d0e86e78549935965
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220900"
---
# <a name="basic-cstring-operations"></a>CString の基本操作

このトピックでは、次の基本的な[CString](../atl-mfc-shared/reference/cstringt-class.md)操作について説明します。

- [標準 C リテラル文字列からの CString オブジェクトの作成](#_core_creating_cstring_objects_from_standard_c_literal_strings)

- [CString 内の個々の文字へのアクセス](#_core_accessing_individual_characters_in_a_cstring)

- [2つの CString オブジェクトの連結](#_core_concatenating_two_cstring_objects)

- [CString オブジェクトの比較](#_core_comparing_cstring_objects)

- [変換 (CString オブジェクトを)](#_core_converting_cstring_objects)

`Class CString`は、クラステンプレートの[CStringT クラス](../atl-mfc-shared/reference/cstringt-class.md)に基づいています。 `CString`は **`typedef`** のです `CStringT` 。 より正確に `CString` は、クラス **`typedef`** テンプレートを使用してクラスを定義する一般的な方法である、の*明示的特殊化*のです `CStringT` 。 同様に定義されたクラスは `CStringA` 、と `CStringW` です。

`CString`、 `CStringA` 、および `CStringW` は、atlstr. h で定義されています。 `CStringT`は、cstringt で定義されています。

`CString`、 `CStringA` 、およびは、 `CStringW` それぞれがサポートする `CStringT` 文字列データで使用するためにで定義されたメソッドと演算子のセットを取得します。 一部のメソッドは、C ランタイムライブラリの文字列サービスを複製し、場合によってはそれを超える場合があります。

メモ: `CString` はネイティブクラスです。 C++/CLI マネージプロジェクトで使用する文字列クラスの場合は、を使用し `System.String` ます。

## <a name="creating-cstring-objects-from-standard-c-literal-strings"></a><a name="_core_creating_cstring_objects_from_standard_c_literal_strings"></a>標準 C リテラル文字列からの CString オブジェクトの作成

`CString`オブジェクトを別のオブジェクトに割り当てることができるのと同様に、C スタイルのリテラル文字列をに割り当てることができ `CString` ます。

- C リテラル文字列の値をオブジェクトに代入 `CString` します。

   [!code-cpp[NVC_ATLMFC_Utilities#183](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_1.cpp)]

- 1つの値 `CString` を別の `CString` オブジェクトに代入します。

   [!code-cpp[NVC_ATLMFC_Utilities#184](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_2.cpp)]

   `CString`あるオブジェクト `CString` が別のオブジェクトに割り当てられると、オブジェクトの内容がコピーされます。 したがって、2つの文字列は、文字列を構成する実際の文字への参照を共有しません。 オブジェクトを値として使用する方法の詳細について `CString` は、「 [CString セマンティクス](../atl-mfc-shared/cstring-semantics.md)」を参照してください。

   > [!NOTE]
   > Unicode または ANSI 用にコンパイルできるようにアプリケーションを記述するには、_T マクロを使用してコードリテラル文字列を作成します。 詳細については、「 [Unicode およびマルチバイト文字セット (MBCS) のサポート](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md)」を参照してください。

## <a name="accessing-individual-characters-in-a-cstring"></a><a name="_core_accessing_individual_characters_in_a_cstring"></a>CString 内の個々の文字へのアクセス

オブジェクト内の個々の文字にアクセスするには、 `CString` `GetAt` メソッドとメソッドを使用し `SetAt` ます。 また、の代わりに配列要素または添字演算子 ([]) を使用して、 `GetAt` 個々の文字を取得することもできます。 (これは、標準の C スタイルの文字列のように、インデックスによって配列要素にアクセスすることに似ています)。文字のインデックス値 `CString` は0から始まります。

## <a name="concatenating-two-cstring-objects"></a><a name="_core_concatenating_two_cstring_objects"></a>2つの CString オブジェクトの連結

2つのオブジェクトを連結するには、次のように `CString` 連結演算子 (+ または + =) を使用します。

[!code-cpp[NVC_ATLMFC_Utilities#185](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_3.cpp)]

連結演算子 (+ または + =) に対する少なくとも1つの引数はオブジェクトである必要があり `CString` ますが、他の引数には定数文字列 (たとえば、 `"big"` ) または **`char`** (' x ' など) を使用できます。

## <a name="comparing-cstring-objects"></a><a name="_core_comparing_cstring_objects"></a>CString オブジェクトの比較

`Compare`のメソッドと = = 演算子は `CString` 等価です。 `Compare`、 **operator = =**、および `CompareNoCase` は MBCS および Unicode に対応してい `CompareNoCase` ます。では大文字と小文字が区別されません。 `Collate`のメソッド `CString` はロケールに依存し、多くの場合、よりも遅くなり `Compare` ます。 `Collate`現在のロケールで指定されている並べ替え規則に従う必要がある場合にのみ、を使用します。

次の表に、C ランタイムライブラリで使用できる[CString](../atl-mfc-shared/reference/cstringt-class.md)比較関数と、それに対応する UNICODE/MBCS 関数を示します。

|CString 関数|MBCS 関数|Unicode 関数|
|----------------------|-------------------|----------------------|
|`Compare`|`_mbscmp`|`wcscmp`|
|`CompareNoCase`|`_mbsicmp`|`_wcsicmp`|
|`Collate`|`_mbscoll`|`wcscoll`|

`CStringT`クラステンプレートは、で使用できる関係演算子 (<、 \<=, > =、>、= =、および! =) を定義し `CString` ます。 `CStrings`次の例に示すように、これらの演算子を使用して2つを比較できます。

[!code-cpp[NVC_ATLMFC_Utilities#186](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_4.cpp)]

## <a name="converting-cstring-objects"></a><a name="_core_converting_cstring_objects"></a>変換 (CString オブジェクトを)

CString オブジェクトを他の文字列型に変換する方法については、「[方法: さまざまな文字列型を変換](../text/how-to-convert-between-various-string-types.md)する」を参照してください。

## <a name="using-cstring-with-wcout"></a>CString を wcout と共に使用する

で CString を使用するには、 `wcout` 次の例に示すように、オブジェクトを明示的ににキャストする必要があり `const wchar_t*` ます。

```cpp
CString cs("meow");

wcout << (const wchar_t*) cs << endl;
```

キャストを使用しない場合、 `cs` はとして扱われ、 **`void*`** `wcout` オブジェクトのアドレスを出力します。 この動作は、テンプレート引数の推論と、それ自体が正しく、C++ 標準に準拠しているオーバーロードの解決との間の微妙な相互作用によって発生します。

## <a name="see-also"></a>関連項目

[文字列 (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[CStringT クラス](../atl-mfc-shared/reference/cstringt-class.md)<br/>
[テンプレートの特殊化](../cpp/template-specialization-cpp.md)<br/>
[方法: さまざまな文字列型を変換する](../text/how-to-convert-between-various-string-types.md)
