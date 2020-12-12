---
description: '詳細については、次を参照してください: CString 引数の引き渡し'
title: CString 引数の渡し方
ms.date: 11/04/2016
helpviewer_keywords:
- strings [C++], as function input/output
- argument passing [C++]
- arguments [C++], passing
- functions [C++], strings as input/output
- argument passing [C++], C strings
- passing arguments, C strings
- CString objects, passing arguments
- string arguments
ms.assetid: a67bebff-edf1-4cf4-bbff-d1cc6a901099
ms.openlocfilehash: ee47898ffdfc5129b11b0f9480669fa142d12818
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167176"
---
# <a name="cstring-argument-passing"></a>CString 引数の渡し方

この記事では、 [CString](../atl-mfc-shared/reference/cstringt-class.md) オブジェクトを関数に渡す方法と、関数からオブジェクトを返す方法について説明し `CString` ます。

## <a name="cstring-argument-passing-conventions"></a><a name="_core_cstring_argument.2d.passing_conventions"></a> CString Argument-Passing 規則

クラスインターフェイスを定義する場合は、メンバー関数の引数渡し規約を決定する必要があります。 オブジェクトを受け渡しするための標準的なルールがいくつかあり `CString` ます。 「 [文字列](#_core_strings_as_function_inputs) 」に記載されているルールを関数の [出力](#_core_strings_as_function_outputs)として使用する場合は、効率的で正しいコードが得られます。

## <a name="strings-as-function-inputs"></a><a name="_core_strings_as_function_inputs"></a> 関数入力としての文字列

呼び出された関数でオブジェクトを使用する最も効率的で安全な方法 `CString` は、 `CString` オブジェクトを関数に渡すことです。 名前にかかわらず、オブジェクトには、 `CString` null 終端文字を持つ C スタイルの文字列として内部的に文字列が格納されることはありません。 代わりに、オブジェクトは、 `CString` その文字数を十分に追跡します。 `CString`Null で終わる文字列への LPCTSTR ポインターを提供することは、コードで常に実行する必要がある場合に有意になる可能性がある少量の作業です。 内容を変更すると、 `CString` LPCTSTR ポインターの古いコピーが無効になるため、結果は一時的になります。

C スタイルの文字列を提供する場合には意味があります。 たとえば、呼び出された関数が C で記述され、オブジェクトをサポートしていない状況が発生する場合があります。 この場合、 `CString` パラメーターは LPCTSTR に強制的に適用され、関数は C スタイルの null で終わる文字列を取得します。 また、 `CString` `CString` C スタイルの文字列パラメーターを受け取るコンストラクターを使用して、他の方向にアクセスしたり、オブジェクトを作成したりすることもできます。

文字列の内容が関数によって変更される場合は、パラメーターを非定数 reference () として宣言し `CString` `CString&` ます。

## <a name="strings-as-function-outputs"></a><a name="_core_strings_as_function_outputs"></a> 関数の出力としての文字列

通常、オブジェクトは関数から返すことができ `CString` ます。これは、 `CString` オブジェクトがプリミティブ型などの値のセマンティクスに従うためです。 読み取り専用の文字列を返すには、定数 `CString` 参照 () を使用し `const CString&` ます。 次の例は、パラメーターと戻り値の型の使用方法を示してい `CString` ます。

[!code-cpp[NVC_ATLMFC_Utilities#197](../atl-mfc-shared/codesnippet/cpp/cstring-argument-passing_1.cpp)]

[!code-cpp[NVC_ATLMFC_Utilities#198](../atl-mfc-shared/codesnippet/cpp/cstring-argument-passing_2.cpp)]

## <a name="see-also"></a>関連項目

[文字列 (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)
