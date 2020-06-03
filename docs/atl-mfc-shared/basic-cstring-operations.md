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
ms.openlocfilehash: 68947dc37e5398ac7caa4754e9af40223cec7bf2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317962"
---
# <a name="basic-cstring-operations"></a>CString の基本操作

このトピックでは、次の基本的な[CString](../atl-mfc-shared/reference/cstringt-class.md)操作について説明します。

- [標準 C リテラル文字列からの CString オブジェクトの作成](#_core_creating_cstring_objects_from_standard_c_literal_strings)

- [CString 内の個々の文字へのアクセス](#_core_accessing_individual_characters_in_a_cstring)

- [2 つの CString オブジェクトを連結する](#_core_concatenating_two_cstring_objects)

- [CString オブジェクトの比較](#_core_comparing_cstring_objects)

- [CString オブジェクトの変換](#_core_converting_cstring_objects)

`Class CString`はクラス テンプレート[CStringT クラス](../atl-mfc-shared/reference/cstringt-class.md)に基づいています。 `CString`は**の型定義**です`CStringT`。 より正確には`CString`、 の*明示的特殊化*の`CStringT` **typedef**であり、クラス テンプレートを使用してクラスを定義する一般的な方法です。 同様に定義された`CStringA`クラス`CStringW`と です。

`CString`、、`CStringA`および`CStringW`は atlstr.h で定義されます。 `CStringT`は cstringt.h で定義されています。

`CString`、、`CStringA`および`CStringW`それぞれが、サポートする文字列データで使用するために定義された`CStringT`メソッドと演算子のセットを取得します。 いくつかのメソッドは重複し、場合によっては C ランタイム ライブラリの文字列サービスを上回ります。

注意:`CString`ネイティブクラスです。 C++/CLI マネージ プロジェクトで使用する文字列クラスの場合は、`System.String`を使用します。

## <a name="creating-cstring-objects-from-standard-c-literal-strings"></a><a name="_core_creating_cstring_objects_from_standard_c_literal_strings"></a>標準 C リテラル文字列からの CString オブジェクトの作成

C スタイルのリテラル文字列は、ある`CString``CString`オブジェクトを別のオブジェクトに割り当てるのと同じように、C スタイルのリテラル文字列を割り当てることができます。

- C リテラル文字列の値をオブジェクトに`CString`代入します。

   [!code-cpp[NVC_ATLMFC_Utilities#183](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_1.cpp)]

- ある`CString`値を別`CString`のオブジェクトに割り当てます。

   [!code-cpp[NVC_ATLMFC_Utilities#184](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_2.cpp)]

   オブジェクトの内容は`CString`、ある`CString`オブジェクトが別のオブジェクトに割り当てられるとコピーされます。 したがって、2 つの文字列は、文字列を構成する実際の文字への参照を共有しません。 オブジェクトを値として使用`CString`する方法の詳細については、「 [CString セマンティクス](../atl-mfc-shared/cstring-semantics.md)」を参照してください。

   > [!NOTE]
   > Unicode または ANSI 用にコンパイルできるようにアプリケーションを記述するには、_T マクロを使用してリテラル文字列をコーディングします。 詳細については[、Unicode およびマルチバイト文字セット (MBCS) のサポート](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md)を参照してください。

## <a name="accessing-individual-characters-in-a-cstring"></a><a name="_core_accessing_individual_characters_in_a_cstring"></a>CString 内の個々の文字へのアクセス

メソッドを使用して、オブジェクト内`CString`の個々の文字`GetAt`に`SetAt`アクセスできます。 個々の文字を取得する代わりに`GetAt`、配列要素または添字演算子 ([ ] ) を使用することもできます。 (これは、標準の C スタイルの文字列のように、インデックスによって配列要素にアクセスするのと似ています)。文字の`CString`インデックス値は 0 から始まります。

## <a name="concatenating-two-cstring-objects"></a><a name="_core_concatenating_two_cstring_objects"></a>2 つの CString オブジェクトを連結する

2 つの`CString`オブジェクトを連結するには、次のように連結演算子 (+または +=) を使用します。

[!code-cpp[NVC_ATLMFC_Utilities#185](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_3.cpp)]

連結演算子 (+または +=) に対する少なくとも 1`CString`つの引数はオブジェクトである必要がありますが、もう一方の引数には`"big"`定数文字列 (たとえば) または**char** ('x' など) を使用できます。

## <a name="comparing-cstring-objects"></a><a name="_core_comparing_cstring_objects"></a>CString オブジェクトの比較

メソッド`Compare`と == 演算子`CString`は同等です。 `Compare`、**演算子==**、`CompareNoCase`および MBCS およびユニコード対応です。`CompareNoCase`また、大文字と小文字を区別しません。 の`Collate``CString`方法はロケールに依存し、 より`Compare`遅い場合が多い。 現在`Collate`のロケールで指定されている並べ替え規則に従う必要がある場合にのみ使用してください。

次の表は、C ランタイム ライブラリで使用できる[CString](../atl-mfc-shared/reference/cstringt-class.md)比較関数と、それに相当する Unicode/MBCS ポータブル関数を示しています。

|C文字列関数|MBCS 機能|ユニコード関数|
|----------------------|-------------------|----------------------|
|`Compare`|`_mbscmp`|`wcscmp`|
|`CompareNoCase`|`_mbsicmp`|`_wcsicmp`|
|`Collate`|`_mbscoll`|`wcscoll`|

クラス`CStringT`テンプレートは、関係演算子 (<、=、>\<= 、>、==、および !=) を`CString`定義します。 次の例に`CStrings`示すように、これらの演算子を使用して 2 つを比較できます。

[!code-cpp[NVC_ATLMFC_Utilities#186](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_4.cpp)]

## <a name="converting-cstring-objects"></a><a name="_core_converting_cstring_objects"></a>C 文字列オブジェクトの変換

CString オブジェクトを他の文字列型に変換する方法については、「[方法 : さまざまな文字列型間で変換する](../text/how-to-convert-between-various-string-types.md)」を参照してください。

## <a name="using-cstring-with-wcout"></a>wcout での C 文字列の使用

CString を使用`wcout`するには、次の例に示すように、オブジェクト`const wchar_t*`を明示的に a にキャストする必要があります。

```cpp
CString cs("meow");

wcout << (const wchar_t*) cs << endl;
```

キャストを行わない`cs`場合は、a `void*` `wcout`として扱われ、オブジェクトのアドレスが出力されます。 この動作は、テンプレート引数の推論と、C++ 標準に準拠したオーバーロードの解決との間の微妙な相互作用によって発生します。

## <a name="see-also"></a>関連項目

[文字列 (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[CStringT クラス](../atl-mfc-shared/reference/cstringt-class.md)<br/>
[テンプレート特化](../cpp/template-specialization-cpp.md)<br/>
[方法: さまざまな文字列型間で変換する](../text/how-to-convert-between-various-string-types.md)
