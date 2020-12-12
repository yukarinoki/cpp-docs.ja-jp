---
description: 詳細については、「CStringT を使用した文字列クラスのエクスポート」をご覧ください。
title: CStringT を使用した文字列クラスのエクスポート
ms.date: 11/04/2016
helpviewer_keywords:
- CStringT class, exporting strings
ms.assetid: bdfc441e-8d2a-461c-9885-46178066c09f
ms.openlocfilehash: 8876ea04f1252e4f5861a950b04dabcd99d6a804
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166994"
---
# <a name="exporting-string-classes-using-cstringt"></a>CStringT を使用した文字列クラスのエクスポート

以前は、MFC 開発者は、から派生し、 `CString` 独自の文字列クラスを特殊化していました。 Microsoft Visual C++ .NET (MFC 8.0) では、 [CString](../atl-mfc-shared/using-cstring.md) クラスが [CStringT](../atl-mfc-shared/reference/cstringt-class.md)と呼ばれるテンプレートクラスに置き換えられました。 これにはいくつかの利点があります。

- これにより、MFC `CString` クラスを ATL プロジェクトで使用できるようになりました。これにより、より大きな mfc スタティックライブラリまたは DLL がリンクされることはありません。

- 新しいテンプレートクラスを使用すると、 `CStringT` `CString` C++ 標準ライブラリのテンプレートと同様に、文字の特徴を指定するテンプレートパラメーターを使用して動作をカスタマイズできます。

- を使用して DLL から独自の文字列クラスをエクスポートすると、コンパイラによって `CStringT` 基本クラスも自動的にエクスポートされ `CString` ます。 `CString`はそれ自体がテンプレートクラスであるため、コンパイラが DLL からインポートしたことを認識しない限り、コンパイラによってインスタンス化される可能性があり `CString` ます。 Visual C++ 6.0 から Visual C++ .NET にプロジェクトを移行した場合、 `CString` DLL およびローカルでインスタンス化されたバージョンからインポートされたの競合が原因で、乗算されたのリンカーシンボルエラーが発生することがあり `CString` ます。 これを行うための適切な方法を以下に示します。

次のシナリオでは、定義された多重クラスのシンボルエラーがリンカーによって生成されます。 `CString`派生クラス ( `CMyString` ) を MFC 拡張 DLL からエクスポートするとします。

[!code-cpp[NVC_MFC_DLL#6](../atl-mfc-shared/codesnippet/cpp/exporting-string-classes-using-cstringt_1.cpp)]

コンシューマーコードは、との組み合わせを使用し `CString` `CMyString` ます。 "MyString" がプリコンパイル済みヘッダーに含まれておらず、の一部の使用方法が表示されてい `CString` ません `CMyString` 。

`CString`クラスとクラスを別々の `CMyString` ソースファイル (Source1 と Source2) で使用するとします。 Source1 では、とを使用して MyString を #include します。 `CMyString` Source2 では、を使用します `CString` が、MyString は #include ません。 この場合、リンカーは乗算が定義されていることを通知 `CStringT` します。 これは、を `CString` エクスポートする DLL からインポートしたもの `CMyString` と、テンプレートを使用してコンパイラによってローカルでインスタンス化されたものの両方があることによって発生し `CStringT` ます。

この問題を解決するには、次の手順を実行します。

`CStringA`と `CStringW` (および必要な基本クラス) を MFC90.DLL からエクスポートします。 MFC を含むプロジェクトは、 `CStringA` 以前の mfc の実装のように、およびでエクスポートされた MFC DLL を常に使用し `CStringW` ます。

次に示すように、テンプレートを使用してエクスポート可能な派生クラスを作成し `CStringT` `CStringT_Exported` ます。次に例を示します。

[!code-cpp[NVC_MFC_DLL#7](../atl-mfc-shared/codesnippet/cpp/exporting-string-classes-using-cstringt_2.cpp)]

AfxStr で、前 `CString` の、 `CStringA` 、および `CStringW` typedef を次のように置き換えます。

[!code-cpp[NVC_MFC_DLL#8](../atl-mfc-shared/codesnippet/cpp/exporting-string-classes-using-cstringt_3.cpp)]

いくつかの注意点があります。

- これによって、 `CStringT` ATL 専用プロジェクトによって特殊なクラスがエクスポートされるため、エクスポートしないでください `CStringT` 。

- からエクスポート可能な派生クラスを使用すると、 `CStringT` 機能を再実装する必要が最小限に抑えら `CStringT` れます。 追加のコードは、コンストラクターを基底クラスに転送する場合にのみ制限され `CStringT` ます。

- `CString`、 `CStringA` 、およびは、 `CStringW` `__declspec(dllexport/dllimport)` MFC 共有 DLL を使用してビルドする場合にのみマークする必要があります。 MFC スタティックライブラリとリンクする場合は、これらのクラスをエクスポート済みとしてマークしないでください。そうしないと、ユーザー Dll 内で、、およびを内部で使用して `CString` `CStringA` も、エクスポート済みとし `CStringW` てマークされ `CString` ます。

## <a name="related-topics"></a>関連トピック

[CStringT クラス](../atl-mfc-shared/reference/cstringt-class.md)

## <a name="see-also"></a>関連項目

[CStringT の使用](../atl-mfc-shared/using-cstringt.md)<br/>
[CString の使用](../atl-mfc-shared/using-cstring.md)
