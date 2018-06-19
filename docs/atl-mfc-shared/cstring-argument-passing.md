---
title: CString 引数の渡し方 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 642ff20028a0929bb7bc11815e66b9f845ef9bd7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32356831"
---
# <a name="cstring-argument-passing"></a>CString 引数の渡し方
この記事に渡す方法を説明します[CString](../atl-mfc-shared/reference/cstringt-class.md)関数のオブジェクトを返す方法`CString`関数からのオブジェクト。  
  
##  <a name="_core_cstring_argument.2d.passing_conventions"></a> CString 引数渡し規約  
 クラス インターフェイスを定義する際に、メンバー関数の引数渡し規約を決定する必要があります。 一部の標準的なルールを渡すと、返すことがある`CString`オブジェクト。 説明する規則に従う場合[関数の入力として文字列](#_core_strings_as_function_inputs)と[関数の出力として文字列](#_core_strings_as_function_outputs)、効率が高く、正しいコードになります。  
  
##  <a name="_core_strings_as_function_inputs"></a> 関数の入力として文字列  
 最も効率的な安全な方法を使用して、`CString`を渡すには、呼び出された関数内のオブジェクト、`CString`関数オブジェクト。 、名前に関係なく、`CString`オブジェクトは格納されません文字列内部的には null 終端文字を含む C スタイル文字列として。 代わりに、`CString`オブジェクトを追跡がある文字の数。 持つ`CString`提供、 `LPCTSTR` null で終わる文字列へのポインターは、コードには常にそれを実行する場合は、長くなることがある作業量が少ない。 変更を加えたために、結果は一時的な`CString`内容の古いコピーを無効化、`LPCTSTR`ポインター。  
  
 意味が場合によっては、C スタイル文字列を指定します。 たとえば、呼び出された関数が C で記述しでサポートされないオブジェクトの状況があります。 この例では、強制、`CString`パラメーターを`LPCTSTR`、および関数が C スタイルの null で終わる文字列を取得します。 前に、他の方向を作成、`CString`オブジェクトを使用して、`CString`を C スタイル文字列パラメーターを受け取るコンス トラクターです。  
  
 文字列の内容が、関数が変更する場合は、宣言のパラメーターを定数として`CString`参照 (**CString &**)。  
  
##  <a name="_core_strings_as_function_outputs"></a> 関数の出力として文字列  
 一般に戻ることができます`CString`ため関数からのオブジェクト`CString`オブジェクトがプリミティブ型のような値のセマンティクスに従います。 読み取り専用文字列を取得するには、定数を使用`CString`参照 (**const CString &**)。 次の例は、の使用を示しています。`CString`パラメーターと戻り値の型。  
  
 [!code-cpp[NVC_ATLMFC_Utilities#197](../atl-mfc-shared/codesnippet/cpp/cstring-argument-passing_1.cpp)]  
  
 [!code-cpp[NVC_ATLMFC_Utilities#198](../atl-mfc-shared/codesnippet/cpp/cstring-argument-passing_2.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [文字列 (ATL と MFC)](../atl-mfc-shared/strings-atl-mfc.md)

