---
title: CStringT を使用して文字列クラスをエクスポート |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- CStringT class, exporting strings
ms.assetid: bdfc441e-8d2a-461c-9885-46178066c09f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7510b1f44f49d17211c71419f4dde5a6e6a78974
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32356397"
---
# <a name="exporting-string-classes-using-cstringt"></a>CStringT を使用して文字列のクラスをエクスポートします。
派生した MFC 開発者まで、`CString`独自文字列クラスを特化します。 Microsoft Visual C .net (MFC 8.0)、 [CString](../atl-mfc-shared/using-cstring.md)と呼ばれるテンプレート クラスによってクラスが置き換えられました[CStringT](../atl-mfc-shared/reference/cstringt-class.md)です。 これには、いくつかの利点が提供されています。  
  
-   MFC が許可されている`CString`ATL で使用するクラスは、大規模な MFC のスタティック ライブラリまたは DLL にリンクせずプロジェクトします。  
  
-   新しい`CStringT`テンプレート クラスをカスタマイズできます`CString`文字の特徴、C++ 標準ライブラリ内のテンプレートのようなを指定するテンプレート パラメーターを使用して動作します。  
  
-   文字列クラスを使った DLL からエクスポートするとき`CStringT`、コンパイラが自動的にエクスポート、`CString`基本クラスです。 `CString`テンプレート クラス自体は、コンパイラが認識しない限りには、使用すると、コンパイラでインスタンス化可能性がありますを`CString`を DLL からインポートします。 Visual C 6.0 から Visual C .NET にプロジェクトを移行する場合がありますきたようにリンカー乗算定義のエラーのシンボル`CString`の競合のため、 `CString` DLL と、ローカルでインスタンス化されたバージョンからインポートします。 これを行う適切な方法は、以下について説明します。 この問題の詳細については、サポート技術情報の記事を参照してください。"CString の派生をインポートするときに、リンク エラー クラス"(Q309801) で[ http://support.microsoft.com/default.aspx](http://support.microsoft.com/default.aspx)です。  
  
 次のシナリオには、リンカーが重複して定義されたクラスのシンボル エラーが発生します。 エクスポートするには前提としています、 `CString`-派生クラス (`CMyString`) MFC 拡張 DLL から。  
  
 [!code-cpp[NVC_MFC_DLL#6](../atl-mfc-shared/codesnippet/cpp/exporting-string-classes-using-cstringt_1.cpp)]  
  
 コンシューマー コードの組み合わせを使用して`CString`と`CMyString`です。 "MyString.h"が、プリコンパイル済みヘッダーとのいくつかの使用状況に含まれていない`CString`いない`CMyString`表示します。  
  
 使用して、`CString`と`CMyString`Source1.cpp および Source2.cpp の別のソース ファイル内のクラスです。 Source1.cpp でを使用して`CMyString`と #include MyString.h です。 Source2.cpp でを使用して`CString`、そうでない #include MyString.h です。 この場合、リンカーが示すエラーを表示`CStringT`定義される乗算します。 これは、原因は`CString`をエクスポートする DLL からインポートされた両方されている`CMyString`、を通じてコンパイラによって、ローカルでインスタンス化、`CStringT`テンプレート。  
  
 この問題を解決するには、次の操作を行います。  
  
 エクスポート`CStringA`と`CStringW`(および必要な基本クラス) MFC90 からです。DLL です。 MFC を含むプロジェクトが MFC DLL エクスポートを使用して常に`CStringA`と`CStringW`以前の MFC 実装のように、します。  
  
 使用して、エクスポート可能な派生クラスを作成し、`CStringT`テンプレートとして`CStringT_Exported`は、たとえば。  
  
 [!code-cpp[NVC_MFC_DLL#7](../atl-mfc-shared/codesnippet/cpp/exporting-string-classes-using-cstringt_2.cpp)]  
  
 AfxStr.h、置き換え前の`CString`、 `CStringA`、および`CStringW`typedef に次のようにします。  
  
 [!code-cpp[NVC_MFC_DLL#8](../atl-mfc-shared/codesnippet/cpp/exporting-string-classes-using-cstringt_3.cpp)]  
  
 これにはいくつかの注意事項があります。  
  
-   エクスポートしないでください`CStringT`自体をエクスポートする特殊な ATL 専用のプロジェクトが生じるため`CStringT`クラスです。  
  
-   クラスを使用して、エクスポート可能な派生`CStringT`を再実装する手間を最小限に抑えます`CStringT`機能します。 追加のコードはコンス トラクターを転送に制限されます、`CStringT`基本クラスです。  
  
-   `CString`、 `CStringA`、および`CStringW`のみに設定されなければなりません`__declspec(dllexport/dllimport)`共有 DLL を、MFC で作成している場合。 エクスポート; としてこれらのクラスをマークする場合は、MFC のスタティック ライブラリとリンク、いない必要があります。それ以外の場合、内部使用`CString`、 `CStringA`、および`CStringW`としてマークされますユーザー Dll 内`CString`と同様にエクスポートします。  
  
## <a name="related-topics"></a>関連トピック  
 [CStringT クラス](../atl-mfc-shared/reference/cstringt-class.md)  
  
## <a name="see-also"></a>関連項目  
 [CStringT を使用します。](../atl-mfc-shared/using-cstringt.md)   
 [CString の使用](../atl-mfc-shared/using-cstring.md)

