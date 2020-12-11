---
description: '詳細情報: CComBSTR を使用したプログラミング (ATL)'
title: CComBSTR を使用したプログラミング (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- CComBSTR class, programming with
- Unicode, using CComBSTR [ATL]
ms.assetid: d3bd0851-d132-4be9-9c4c-6ccba17acb2b
ms.openlocfilehash: 6c348d703aeaeba40f1f47b8f6fd0ee858b7babd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159220"
---
# <a name="programming-with-ccombstr-atl"></a>CComBSTR を使用したプログラミング (ATL)

ATL クラス [CComBSTR](../atl/reference/ccombstr-class.md) には、BSTR データ型のラッパーが用意されています。 `CComBSTR`は便利なツールですが、注意が必要な状況がいくつかあります。

- [変換の問題](#programmingwithccombstr_conversionissues)

- [スコープの問題](#programmingwithccombstr_scopeissues)

- [CComBSTR オブジェクトを明示的に解放する](#programmingwithccombstr_explicitlyfreeing)

- [使用 (CComBSTR オブジェクトをループで)](#programmingwithccombstr_usingloops)

- [メモリリークの問題](#programmingwithccombstr_memoryleaks)

## <a name="conversion-issues"></a><a name="programmingwithccombstr_conversionissues"></a> 変換の問題

いくつか `CComBSTR` のメソッドは ANSI 文字列引数を unicode に自動的に変換しますが、メソッドは常に unicode 書式指定文字列を返します。 出力文字列を ANSI に変換するには、ATL 変換クラスを使用します。 ATL 変換クラスの詳細については、「 [atl および MFC 文字列変換マクロ](reference/string-conversion-macros.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#114](../atl/codesnippet/cpp/programming-with-ccombstr-atl_1.cpp)]

文字列リテラルを使用してオブジェクトを変更する場合は `CComBSTR` 、ワイド文字列を使用します。 これにより、不要な変換が減少します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#115](../atl/codesnippet/cpp/programming-with-ccombstr-atl_2.cpp)]

## <a name="scope-issues"></a><a name="programmingwithccombstr_scopeissues"></a> スコープの問題

正常に動作するクラスと同様に、 `CComBSTR` はスコープ外に出たときにそのリソースを解放します。 関数が文字列へのポインターを返す場合、 `CComBSTR` ポインターは既に解放されているメモリを参照するので、問題が発生する可能性があります。 このような場合は、 `Copy` 次に示すようにメソッドを使用します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#116](../atl/codesnippet/cpp/programming-with-ccombstr-atl_3.cpp)]

## <a name="explicitly-freeing-the-ccombstr-object"></a><a name="programmingwithccombstr_explicitlyfreeing"></a> CComBSTR オブジェクトを明示的に解放する

オブジェクトがスコープ外に出る前に、オブジェクトに含まれている文字列を明示的に解放することができ `CComBSTR` ます。 文字列が解放されると、 `CComBSTR` オブジェクトは無効になります。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#117](../atl/codesnippet/cpp/programming-with-ccombstr-atl_4.cpp)]

## <a name="using-ccombstr-objects-in-loops"></a><a name="programmingwithccombstr_usingloops"></a> 使用 (CComBSTR オブジェクトをループで)

クラスは、 `CComBSTR` 演算子やメソッドなどの特定の操作を実行するためにバッファーを割り当てるため `+=` `Append` 、短いループ内で文字列操作を実行することは推奨されません。 このような状況では、に `CStringT` よってパフォーマンスが向上します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#118](../atl/codesnippet/cpp/programming-with-ccombstr-atl_5.cpp)]

## <a name="memory-leak-issues"></a><a name="programmingwithccombstr_memoryleaks"></a> メモリリークの問題

初期化されたのアドレスを `CComBSTR` **[out]** パラメーターとして関数に渡すと、メモリリークが発生します。

次の例では、文字列を格納するために割り当てられた文字列は、 `"Initialized"` 関数が文字列を置換するときにリークし `MyGoodFunction` ます。

[!code-cpp[NVC_ATL_Utilities#119](../atl/codesnippet/cpp/programming-with-ccombstr-atl_6.cpp)]

リークを回避するには、 `Empty` `CComBSTR` アドレスを **[out]** パラメーターとして渡す前に、既存のオブジェクトに対してメソッドを呼び出します。

関数のパラメーターが **[in, out]** の場合、同じコードでリークが発生することはないことに注意してください。

## <a name="see-also"></a>関連項目

[概念](../atl/active-template-library-atl-concepts.md)<br/>
[CStringT クラス](../atl-mfc-shared/reference/cstringt-class.md)<br/>
[wstring](../standard-library/basic-string-class.md)<br/>
[文字列変換マクロ](../atl/reference/string-conversion-macros.md)
