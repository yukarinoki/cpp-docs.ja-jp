---
title: DEF ファイルを使った DLL からのエクスポート |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- def files [C++], exporting from DLLs
- .def files [C++], exporting from DLLs
- exporting DLLs [C++], DEF files
ms.assetid: 9d31eda2-184e-47de-a2ee-a93ebd603f8e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 22bcca929d687ef3b10ee65bcb2230c03bfb0a11
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45706005"
---
# <a name="exporting-from-a-dll-using-def-files"></a>DEF ファイルを使った DLL からのエクスポート

モジュール定義ファイル (.def) は、テキスト ファイルです。DLL のさまざまな属性を記述する 1 つ以上のモジュール文が含まれています。 使用していない場合、**方式**キーワード DLL の関数をエクスポートする DLL に .def ファイルが必要です。

.def ファイルには、最低限でも以下のモジュール定義文を記述する必要があります。

- ファイルの先頭には、必ず LIBRARY 文を記述します。 LIBRARY 文は、その .def ファイルが所属する DLL を特定します。 LIBRARY 文の引数には、DLL の名前を指定します。 リンカーは、この名前を DLL のインポート ライブラリに配置します。

- EXPORTS 文には、DLL のエクスポート関数の名前と、オプションで序数値を指定します。 序数値を関数に割り当てるには、アット マーク (@) と数字の後に関数名を記述します。 序数値の場合は、1 から N の範囲で指定する必要があります。N は DLL のエクスポート関数の数字です。 関数を序数でエクスポートする場合は、「[関数名ではなく序数による DLL のエクスポート](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md)」もいます。

たとえば、バイナリ検索ツリーを実装するコードを含む DLL は、以下のようになります。

```
LIBRARY   BTREE
EXPORTS
   Insert   @1
   Delete   @2
   Member   @3
   Min   @4
```

使用する場合、 [MFC DLL ウィザード](../mfc/reference/mfc-dll-wizard.md)MFC DLL を作成するウィザードはスケルトンの .def ファイルを作成して、自動的にそれをプロジェクトに追加します。 エクスポートされる関数の名前は、このファイルに追加します。 非 MFC DLL の場合、.def ファイルをプログラマ自身が作成してプロジェクトに追加する必要があります。

C++ ファイル内の関数をエクスポートする場合は、装飾名を .def ファイルに配置するか、標準の C リンケージで extern "C" を使ってエクスポート関数を定義する必要があります。 使用して取得できます、装飾名を .def ファイルに配置する必要がある場合、 [DUMPBIN](../build/reference/dumpbin-reference.md)ツールまたはリンカーを使用して[/map](../build/reference/map-generate-mapfile.md)オプション。 コンパイラが作成した装飾名は、コンパイラ独自のものであることに注意してください。 Visual C++ コンパイラが作成した装飾名を .def ファイルに配置する場合は、DLL とリンクするアプリケーションは、同じバージョンの Visual C++ を使ってビルドする必要があります。これは、呼び出しアプリケーション内の装飾名と、DLL の .def ファイル内のエクスポート名を一致させるためです。

構築している場合、[拡張 DLL](../build/extension-dlls-overview.md)、エクスポートされたクラスを含むヘッダー ファイルの末尾、先頭にある次のコードを配置する .def ファイルを使用してエクスポートします。

```
#undef AFX_DATA
#define AFX_DATA AFX_EXT_DATA
// <body of your header file>
#undef AFX_DATA
#define AFX_DATA
```

これらの行が、内部的に使用される、クラスに追加される MFC 変数エクスポート (またはインポート)、MFC 拡張 DLL から。 たとえば、`DECLARE_DYNAMIC` を使って派生クラスを作成する場合、このマクロが展開して、`CRuntimeClass` メンバー関数をクラスに追加します。 上の 4 行をコードに追加しないと、DLL の不正なコンパイルまたはリンクが行われたり、クライアント アプリケーションが DLL とリンクするときにエラーが発生することになります。

DLL のビルド時に、リンカーは .def ファイルを使って、エクスポート ファイル (.exp) とインポート ライブラリ ファイル (.lib) を作成します。 次にリンカーはエクスポート ファイルを使って、.DLL ファイルを作成します。 DLL と暗黙的にリンクする実行形式は、ビルド時にインポート ライブラリと DLL をリンクします。

MFC 自体は、.def ファイルを使用して MFCx0.dll のクラスと関数をエクスポートします。

## <a name="what-do-you-want-to-do"></a>実行する操作

- [関数を使った DLL からエクスポートします。](../build/exporting-from-a-dll-using-declspec-dllexport.md)

- [AFX_EXT_CLASS を使ったエクスポート/インポート](../build/exporting-and-importing-using-afx-ext-class.md)

- [C 言語の実行可能ファイルで使用するための C++ 関数をエクスポートします。](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)

- [C または C++ 言語の実行可能ファイルで使用するための C 関数をエクスポートします。](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)

- [エクスポート方式の使用](../build/determining-which-exporting-method-to-use.md)

- [使用してアプリケーションをインポートします。](../build/importing-into-an-application-using-declspec-dllimport.md)

- [DLL を初期化します。](../build/run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [.def ファイル](../build/reference/module-definition-dot-def-files.md)

- [モジュール定義ステートメントに関する規則](../build/reference/rules-for-module-definition-statements.md)

- [装飾名](../build/reference/decorated-names.md)

- [インポートとエクスポートのインライン関数](../build/importing-and-exporting-inline-functions.md)

- [相互インポート](../build/mutual-imports.md)

## <a name="see-also"></a>関連項目

[DLL からのエクスポート](../build/exporting-from-a-dll.md)