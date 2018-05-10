---
title: CComBSTR (ATL) を使用したプログラミング |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CComBSTR class, programming with
- Unicode, using CComBSTR [ATL]
ms.assetid: d3bd0851-d132-4be9-9c4c-6ccba17acb2b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b957cca4ff1af93d3f62ab0bf667462c91b81bba
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="programming-with-ccombstr-atl"></a>CComBSTR を使用したプログラミング (ATL)
ATL クラス[CComBSTR](../atl/reference/ccombstr-class.md)をラップするラッパーを提供、`BSTR`データ型。 中に`CComBSTR`便利なツールは、注意を必要とするいくつかの状況があります。  
  
-   [変換の問題](#programmingwithccombstr_conversionissues)  
  
-   [範囲の問題](#programmingwithccombstr_scopeissues)  
  
-   [CComBSTR オブジェクトを明示的に解放します。](#programmingwithccombstr_explicitlyfreeing)  
  
-   [CComBSTR オブジェクト ループで使用します。](#programmingwithccombstr_usingloops)  
  
-   [メモリ リークの問題](#programmingwithccombstr_memoryleaks)  
  
##  <a name="programmingwithccombstr_conversionissues"></a> 変換の問題  
 いくつか`CComBSTR`メソッドでは ANSI 文字列引数を Unicode に自動的に変換されます、メソッドは常に Unicode 形式の文字列を返します。 出力文字列を ANSI に変換する、するには、ATL 変換クラスを使用します。 ATL 変換クラスの詳細については、次を参照してください。 [ATL および MFC 文字列変換マクロ](reference/string-conversion-macros.md)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#114](../atl/codesnippet/cpp/programming-with-ccombstr-atl_1.cpp)]  
  
 変更する、文字列リテラルを使用している場合、`CComBSTR`オブジェクト、ワイド文字列を使用します。 これにより、不要な変換が低減されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#115](../atl/codesnippet/cpp/programming-with-ccombstr-atl_2.cpp)]  
  
##  <a name="programmingwithccombstr_scopeissues"></a> 範囲の問題  
 同様に、適切に動作クラス`CComBSTR`はスコープ外になったときにそのリソースを解放します。 関数へのポインターを返す場合、`CComBSTR`文字列、この問題が発生、ポインターは、既に解放されたメモリを参照するためです。 このような場合を使用して、**コピー**メソッドを次のようにします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#116](../atl/codesnippet/cpp/programming-with-ccombstr-atl_3.cpp)]  
  
##  <a name="programmingwithccombstr_explicitlyfreeing"></a> CComBSTR オブジェクトを明示的に解放します。  
 含まれる文字列を明示的に解放することは、`CComBSTR`オブジェクトのオブジェクトがスコープ外に出る前にします。 文字列が解放される場合、`CComBSTR`オブジェクトが無効です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#117](../atl/codesnippet/cpp/programming-with-ccombstr-atl_4.cpp)]  
  
##  <a name="programmingwithccombstr_usingloops"></a> CComBSTR オブジェクト ループで使用します。  
 として、`CComBSTR`クラスなど、特定の操作を実行時にバッファーを割り当て、`+=`演算子または**Append**メソッド、しないでループ文字列操作を実行することです。 このような場合は、`CStringT`パフォーマンスが向上します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#118](../atl/codesnippet/cpp/programming-with-ccombstr-atl_5.cpp)]  
  
##  <a name="programmingwithccombstr_memoryleaks"></a> メモリ リークの問題  
 初期化されたのアドレスを渡す`CComBSTR`として関数に、 **[out]** メモリ リークを発生させます。  
  
 文字列を保持するために次の例では、文字列が割り当てられている`"Initialized"`タイミングがリーク関数`MyGoodFunction`は、文字列を置換します。  
  
 [!code-cpp[NVC_ATL_Utilities#119](../atl/codesnippet/cpp/programming-with-ccombstr-atl_6.cpp)]  
  
 メモリ リークを避けるためには、呼び出し、**空**既存のメソッド`CComBSTR`オブジェクトとしてアドレスを渡す前に、 **[out]** パラメーター。  
  
 エントリの場合は、関数のパラメーターが、同じコードは、リークが発生しませんに注意してください **[で, out]** です。  
  
## <a name="see-also"></a>関連項目  
 [概念](../atl/active-template-library-atl-concepts.md)   
 [CStringT クラス](../atl-mfc-shared/reference/cstringt-class.md)   
 [wstring](../standard-library/basic-string-class.md)   
 [文字列変換に関するマクロ](../atl/reference/string-conversion-macros.md)

