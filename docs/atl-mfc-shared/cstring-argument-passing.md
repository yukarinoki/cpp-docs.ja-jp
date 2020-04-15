---
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
ms.openlocfilehash: 53977eb47520a20571a2d5ba8aa105c567ff40d1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317931"
---
# <a name="cstring-argument-passing"></a>CString 引数の渡し方

この記事では、関数に[CString](../atl-mfc-shared/reference/cstringt-class.md)オブジェクトを渡す方法`CString`と、関数からオブジェクトを返す方法について説明します。

## <a name="cstring-argument-passing-conventions"></a><a name="_core_cstring_argument.2d.passing_conventions"></a>CString 引数渡し規約

クラス インターフェイスを定義する場合は、メンバー関数の引数渡し規約を決定する必要があります。 オブジェクトの受け渡しと戻り`CString`には、いくつかの標準的な規則があります。 [「関数入力」と「関数の出力としての文字列](#_core_strings_as_function_inputs)」で[Strings as Function Outputs](#_core_strings_as_function_outputs)説明されている規則に従えば、効率的で正確なコードが得られます。

## <a name="strings-as-function-inputs"></a><a name="_core_strings_as_function_inputs"></a>関数入力としての文字列

呼び出された関数でオブジェクトを使用`CString`する最も効率的で安全な方法`CString`は、オブジェクトを関数に渡す方法です。 名前に関わらず、`CString`オブジェクトは、null 終端文字を持つ C スタイルの文字列として文字列を内部的に格納しません。 代わりに、`CString`オブジェクトは、そのオブジェクトの文字数を慎重に追跡します。 NULL`CString`で終わる文字列への LPCTSTR ポインターを提供することは、コードで常に行う必要がある場合に重要になる可能性がある少量の作業です。 内容を変更すると LPCTSTR`CString`ポインターの古いコピーが無効になるので、結果は一時的なものになります。

C スタイルの文字列を提供する場合には意味があります。 たとえば、呼び出された関数が C で書き込まれ、オブジェクトをサポートしていない場合があります。 この場合、パラメーターを`CString`LPCTSTR に強制変換すると、関数は C スタイルの null 終端文字列を取得します。 C スタイルの文字列パラメーターを受け取`CString`るコンストラクターを使用`CString`して、他の方向に移動してオブジェクトを作成することもできます。

文字列の内容を関数によって変更する場合は、パラメーターを非定数`CString`参照 ( )`CString&`として宣言します。

## <a name="strings-as-function-outputs"></a><a name="_core_strings_as_function_outputs"></a>関数出力としての文字列

オブジェクトはプリミティブ型`CString`などの値セマンティクス`CString`に従うので、通常は関数からオブジェクトを返すことができます。 読み取り専用の文字列を返す場合`CString`は、`const CString&`定数参照 ( ) を使用します。 次の例は、パラメーターと戻`CString`り値の型の使用方法を示しています。

[!code-cpp[NVC_ATLMFC_Utilities#197](../atl-mfc-shared/codesnippet/cpp/cstring-argument-passing_1.cpp)]

[!code-cpp[NVC_ATLMFC_Utilities#198](../atl-mfc-shared/codesnippet/cpp/cstring-argument-passing_2.cpp)]

## <a name="see-also"></a>関連項目

[文字列 (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)
