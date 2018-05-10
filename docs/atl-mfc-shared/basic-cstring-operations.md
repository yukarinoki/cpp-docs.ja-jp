---
title: CString の基本操作 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- CString objects, basic operations
- string literals, CString operations
- literal strings, CString operations
- CString objects
- string comparison, CString operations
- characters, accessing in CStrings
ms.assetid: 41db66b2-9427-4bb3-845a-9b6869159a6c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b66b6fc5578960e4b6ec9b392622256b66db9cfa
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="basic-cstring-operations"></a>CString の基本操作
このトピックの次の基本的な[CString](../atl-mfc-shared/reference/cstringt-class.md)操作。  
  
- [標準の C リテラル文字列を CString オブジェクトの作成](#_core_creating_cstring_objects_from_standard_c_literal_strings)  
  
- [CString の個々 の文字へのアクセス](#_core_accessing_individual_characters_in_a_cstring)  
  
- [連結する 2 つの CString オブジェクト](#_core_concatenating_two_cstring_objects)  
  
- [CString オブジェクトの比較](#_core_comparing_cstring_objects)  
  
- [CString オブジェクトを変換します。](#_core_converting_cstring_objects)  
  
 `Class CString` クラス テンプレートに基づく[CStringT クラス](../atl-mfc-shared/reference/cstringt-class.md)です。 `CString` `typedef`の`CStringT`します。 正確に`CString`は、`typedef`の*明示的な特殊化*の`CStringT`、クラス テンプレートを使用してクラスを定義する一般的な方法であります。 同様に定義されたクラスは、`CStringA`と`CStringW`です。  
  
 `CString`、 `CStringA`、および`CStringW`atlstr.h で定義されます。 `CStringT` cstringt.h で定義されます。  
  
 `CString`、 `CStringA`、および`CStringW`メソッドおよびで定義された演算子のセットを取得各`CStringT`サポートされる文字列データで使用するためです。 C ランタイム ライブラリの文字列のサービスと重複して、場合によっては、メソッドの一部になります。  
  
 注:`CString`ネイティブ クラスです。 C++ で使用される文字列クラスの +/CLI を使用して、プロジェクトのマネージ`System.String`です。  
  
##  <a name="_core_creating_cstring_objects_from_standard_c_literal_strings"></a> 標準 C リテラル文字列を CString オブジェクトの作成  
 C スタイルのリテラル文字列を割り当てることができます、`CString`だけ割り当てることができます、`CString`を別のオブジェクト。  
  
-   C リテラル文字列の値を割り当てる、`CString`オブジェクト。  
  
 [!code-cpp[NVC_ATLMFC_Utilities#183](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_1.cpp)]  
  
-   いずれかの値を割り当てる`CString`別`CString`オブジェクト。  
  
 [!code-cpp[NVC_ATLMFC_Utilities#184](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_2.cpp)]  
  
     内容、`CString`とき 1 つにオブジェクトがコピーされる`CString`別にオブジェクトが割り当てられます。 そのため、2 つの文字列では、文字列を構成する実際の文字への参照は共有されません。 使用する方法の詳細についての`CString`値として、オブジェクトを参照してください[Cstring](../atl-mfc-shared/cstring-semantics.md)です。  
  
    > [!NOTE]
    >  Unicode または ANSI 用にコンパイルできるように、アプリケーションを作成するには、_T マクロを使用してリテラル文字列を記述します。 詳細については、次を参照してください。 [Unicode およびマルチバイト文字セット (MBCS) のサポート](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md)です。  
  
##  <a name="_core_accessing_individual_characters_in_a_cstring"></a> CString の個々 の文字へのアクセス  
 個々 の文字にアクセスすることができます、`CString`オブジェクトを使用して、`GetAt`と`SetAt`メソッドです。 代わりに、配列の要素、または添字演算子 () を使用することができますも`GetAt`を個々 の文字を取得します。 (配列の要素へのアクセスがインデックスで標準の C スタイル文字列と同様に似ています)値をインデックス`CString`文字は 0 から始まります。  
  
##  <a name="_core_concatenating_two_cstring_objects"></a> 連結する 2 つの CString オブジェクト  
 2 つを連結する`CString`オブジェクト、連結演算子を使用して (+ または + =)、次のようにします。  
  
 [!code-cpp[NVC_ATLMFC_Utilities#185](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_3.cpp)]  
  
 連結演算子には、少なくとも 1 つの引数 (+ または + =) する必要があります、`CString`がオブジェクトには、文字列定数を使用できます (たとえば、 `"big"`) または`char`(たとえば、' x') に対するその他の引数。  
  
##  <a name="_core_comparing_cstring_objects"></a> CString オブジェクトの比較  
 `Compare`メソッドと演算子 = =`CString`は同等です。 `Compare`、 `operator==`、および`CompareNoCase`は MBCS および Unicode が対応しています。`CompareNoCase`も区別されません。 `Collate`メソッドの`CString`ロケールは、多くの場合よりも低速`Compare`です。 使用して`Collate`現在のロケールで指定されたルールのみをする必要がありますに従う並べ替え。  
  
 次の表は、使用可能な[CString](../atl-mfc-shared/reference/cstringt-class.md)比較関数と C ランタイム ライブラリで同等の Unicode と MBCS ポータブル関数。  
  
|CString 関数|MBCS 関数|Unicode 関数|  
|----------------------|-------------------|----------------------|  
|`Compare`|`_mbscmp`|`wcscmp`|  
|`CompareNoCase`|`_mbsicmp`|`_wcsicmp`|  
|`Collate`|`_mbscoll`|`wcscoll`|  
  
 `CStringT`クラス テンプレート定義関係演算子 (<、 \<=、> =、>、= =、および! =) で使用するために使用可能な`CString`します。 2 つの比較できます`CStrings`の次の例に示すように、これらの演算子を使用しています。  
  
 [!code-cpp[NVC_ATLMFC_Utilities#186](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_4.cpp)]  
  
##  <a name="_core_converting_cstring_objects"></a> CString オブジェクトを変換します。  
 CString オブジェクトを他の文字列型に変換する方法については、次を参照してください。[する方法: さまざまな文字列型の間で変換](../text/how-to-convert-between-various-string-types.md)です。  
  
## <a name="using-cstring-with-wcout"></a>Wcout での CString の使用  
 CString を使用する`wcout`するオブジェクトを明示的にキャストする必要があります、`const wchar_t*`次の例で示すように。  
  
```  
CString cs("meow");

    wcout <<(const wchar_t*) cs <<endl;  
 
```  
  
 キャストなし`cs`として扱われる、`void*`と`wcout`オブジェクトのアドレスを印刷します。 この動作は微妙なテンプレート引数の推論し、オーバー ロードの解決は正しい自体にとのやり取りに準拠する、C++ 標準にで発生します。  
  
## <a name="see-also"></a>関連項目  
 [文字列 (ATL と MFC)](../atl-mfc-shared/strings-atl-mfc.md)   
 [CStringT クラス](../atl-mfc-shared/reference/cstringt-class.md)   
 [テンプレートの特殊化](../cpp/template-specialization-cpp.md)   
 [方法: さまざまな文字列型間で変換する](../text/how-to-convert-between-various-string-types.md)

