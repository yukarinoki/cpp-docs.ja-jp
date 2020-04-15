---
title: CComBSTR を使用したプログラミング (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- CComBSTR class, programming with
- Unicode, using CComBSTR [ATL]
ms.assetid: d3bd0851-d132-4be9-9c4c-6ccba17acb2b
ms.openlocfilehash: 020c2d18c721e658d15bb1451039154ae50b99f6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321792"
---
# <a name="programming-with-ccombstr-atl"></a>CComBSTR を使用したプログラミング (ATL)

ATL クラス[CComBSTR](../atl/reference/ccombstr-class.md)は、BSTR データ型のラッパーを提供します。 便利`CComBSTR`なツールですが、注意が必要な状況がいくつかあります。

- [変換の問題](#programmingwithccombstr_conversionissues)

- [スコープの問題](#programmingwithccombstr_scopeissues)

- [明示的に CComBSTR オブジェクトを解放する](#programmingwithccombstr_explicitlyfreeing)

- [ループでの CComBSTR オブジェクトの使用](#programmingwithccombstr_usingloops)

- [メモリ リークの問題](#programmingwithccombstr_memoryleaks)

## <a name="conversion-issues"></a><a name="programmingwithccombstr_conversionissues"></a>変換の問題

いくつかの`CComBSTR`メソッドは ANSI 文字列引数を自動的に Unicode に変換しますが、これらのメソッドは常に Unicode 形式文字列を返します。 出力文字列を ANSI に変換するには、ATL 変換クラスを使用します。 ATL 変換クラスの詳細については[、「ATL および MFC 文字列変換マクロ](reference/string-conversion-macros.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#114](../atl/codesnippet/cpp/programming-with-ccombstr-atl_1.cpp)]

文字列リテラルを使用してオブジェクトを変更する場合`CComBSTR`は、ワイド文字列を使用します。 これにより、不要な変換が減ります。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#115](../atl/codesnippet/cpp/programming-with-ccombstr-atl_2.cpp)]

## <a name="scope-issues"></a><a name="programmingwithccombstr_scopeissues"></a>スコープの問題

他の行き届いたクラスと同様に`CComBSTR`、スコープ外に出るとリソースが解放されます。 関数が`CComBSTR`文字列へのポインタを返す場合、既に解放されたメモリをポインタが参照するので、問題が発生する可能性があります。 このような場合は、以下に`Copy`示すように、この方法を使用します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#116](../atl/codesnippet/cpp/programming-with-ccombstr-atl_3.cpp)]

## <a name="explicitly-freeing-the-ccombstr-object"></a><a name="programmingwithccombstr_explicitlyfreeing"></a>明示的に CComBSTR オブジェクトを解放する

オブジェクトがスコープから外れる前に、`CComBSTR`オブジェクトに含まれる文字列を明示的に解放できます。 文字列が解放された場合、`CComBSTR`オブジェクトは無効です。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#117](../atl/codesnippet/cpp/programming-with-ccombstr-atl_4.cpp)]

## <a name="using-ccombstr-objects-in-loops"></a><a name="programmingwithccombstr_usingloops"></a>ループでの CComBSTR オブジェクトの使用

このクラス`CComBSTR`は、演算子や`+=``Append`メソッドなどの特定の操作を実行するためにバッファを割り当てるため、厳密なループの中で文字列操作を実行することはお勧めしません。 このような状況では、`CStringT`パフォーマンスが向上します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#118](../atl/codesnippet/cpp/programming-with-ccombstr-atl_5.cpp)]

## <a name="memory-leak-issues"></a><a name="programmingwithccombstr_memoryleaks"></a>メモリ リークの問題

初期化`CComBSTR`されたアドレスを関数に **[out]** パラメータとして渡すと、メモリ リークが発生します。

次の例では、関数`"Initialized"``MyGoodFunction`が文字列を置き換えると、文字列を保持するために割り当てられた文字列がリークされます。

[!code-cpp[NVC_ATL_Utilities#119](../atl/codesnippet/cpp/programming-with-ccombstr-atl_6.cpp)]

リークを回避するには、アドレスを`Empty` `CComBSTR` **[out]** パラメータとして渡す前に、既存のオブジェクトに対してメソッドを呼び出します。

関数のパラメータが **[in, out]** の場合、同じコードでリークが発生しないことに注意してください。

## <a name="see-also"></a>関連項目

[概念](../atl/active-template-library-atl-concepts.md)<br/>
[CStringT クラス](../atl-mfc-shared/reference/cstringt-class.md)<br/>
[wstring](../standard-library/basic-string-class.md)<br/>
[文字列変換マクロ](../atl/reference/string-conversion-macros.md)
