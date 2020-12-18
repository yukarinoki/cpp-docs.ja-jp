---
description: '詳細情報: DEF ファイルを使った DLL からのエクスポート'
title: DEF ファイルを使った DLL からのエクスポート
ms.date: 05/06/2019
helpviewer_keywords:
- def files [C++], exporting from DLLs
- .def files [C++], exporting from DLLs
- exporting DLLs [C++], DEF files
ms.assetid: 9d31eda2-184e-47de-a2ee-a93ebd603f8e
ms.openlocfilehash: 5be5f2c4a5f6db5f1983da940d8a336f02c938f7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97156529"
---
# <a name="exporting-from-a-dll-using-def-files"></a>DEF ファイルを使った DLL からのエクスポート

モジュール定義または DEF ファイル (*.def) は、DLL のさまざまな属性を記述する 1 つ以上のモジュール文が含まれるテキスト ファイルです。 DLL の関数をエクスポートする **`__declspec(dllexport)`** キーワードを使わない場合は、DLL に DEF ファイルが必要です。

DEF ファイルには、最低限、以下のモジュール定義文を記述する必要があります。

- ファイルの先頭には、必ず LIBRARY 文を記述します。 この文は、DEF ファイルが DLL に所属していることを識別します。 LIBRARY 文の引数には、DLL の名前を指定します。 リンカーは、この名前を DLL のインポート ライブラリに配置します。

- EXPORTS 文には、DLL のエクスポート関数の名前と、オプションで序数値を指定します。 序数値を関数に割り当てるには、アット マーク (@) と数字の後に関数名を記述します。 序数値の場合は、1 から N の範囲で指定する必要があります。N は DLL のエクスポート関数の数字です。 関数を序数値でエクスポートする場合は、このトピックに加え、「[名前ではなく序数値による DLL 関数のエクスポート](exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md)」も参照してください。

たとえば、バイナリ検索ツリーを実装するコードを含む DLL は、以下のようになります。

```
LIBRARY   BTREE
EXPORTS
   Insert   @1
   Delete   @2
   Member   @3
   Min   @4
```

[MFC DLL ウィザード](../mfc/reference/mfc-dll-wizard.md)を使って MFC DLL を作成すると、ウィザードによってスケルトンの DEF ファイルが作成され、プロジェクトに自動的に追加されます。 エクスポートされる関数の名前は、このファイルに追加します。 非 MFC DLL の場合は、DEF ファイルを自分で作成してプロジェクトに追加します。 次に、 **[プロジェクト]**  >  **[プロパティ]**  >  **[リンカー]**  >  **[入力]**  >  **[モジュール定義ファイル]** の順に移動し、DEF ファイルの名前を入力します。 構成とプラットフォームごとにこの手順を繰り返します。または、 **[構成 = すべての構成]** と **[プラットフォーム = すべてのプラットフォーム]** を選択することで、すべてを一度に実行できます。

C++ ファイル内の関数をエクスポートする場合は、装飾名を DEF ファイルに配置するか、標準の C リンケージで extern "C" を使ってエクスポート関数を定義する必要があります。 DEF ファイル内に装飾名を配置する必要がある場合は、[DUMPBIN](../build/reference/dumpbin-reference.md) ツールまたは [/MAP](../build/reference/map-generate-mapfile.md) リンカー オプションを使用して装飾名を取得できます。 コンパイラが作成した装飾名は、コンパイラ独自のものであることに注意してください。 Microsoft C++ コンパイラ (MSVC) が作成した装飾名を DEF ファイルに配置する場合は、同じバージョンの MSVC を使用して DLL とリンクするアプリケーションをビルドする必要があります。これは、呼び出し元のアプリケーション内の装飾名と、DLL の DEF ファイル内のエクスポート名を一致させるためです。

> [!NOTE]
> Visual Studio 2017 または Visual Studio 2019 でビルドされたアプリケーションで、Visual Studio 2015 でビルドされた DLL を使用できます。

[拡張 DLL](../build/extension-dlls-overview.md) をビルドする場合、および DEF ファイルを使ってエクスポートする場合、エクスポートされるクラスを含むヘッダー ファイルの先頭と末尾に次のコードを追加します。

```
#undef AFX_DATA
#define AFX_DATA AFX_EXT_DATA
// <body of your header file>
#undef AFX_DATA
#define AFX_DATA
```

これらの行によって、内部で使用される MFC 変数やクラスに追加される MFC 変数が、MFC 拡張 DLL から確実にエクスポート (またはインポート) されます。 たとえば、`DECLARE_DYNAMIC` を使って派生クラスを作成する場合、このマクロが展開して、`CRuntimeClass` メンバー関数をクラスに追加します。 上の 4 行をコードに追加しないと、DLL の不正なコンパイルまたはリンクが行われたり、クライアント アプリケーションが DLL とリンクするときにエラーが発生することになります。

DLL のビルド時に、リンカーで DEF ファイルを使用して、エクスポート ファイル (.exp) とインポート ライブラリ ファイル (.lib) が作成されます。 次にリンカーはエクスポート ファイルを使って、.DLL ファイルを作成します。 DLL と暗黙的にリンクする実行形式は、ビルド時にインポート ライブラリと DLL をリンクします。

MFC 自体は、DEF ファイルを使用して MFCx0.dll からクラスと関数をエクスポートします。

## <a name="what-do-you-want-to-do"></a>実行する操作

- [__declspec(dllexport) を使用して DLL からエクスポートする](exporting-from-a-dll-using-declspec-dllexport.md)

- [AFX_EXT_CLASS を使用してエクスポートとインポートを行う](exporting-and-importing-using-afx-ext-class.md)

- [C 言語の実行可能ファイルで使用する C++ 関数をエクスポートする](exporting-cpp-functions-for-use-in-c-language-executables.md)

- [C または C++ 言語の実行可能ファイルで使用する C 関数をエクスポートする](exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)

- [エクスポート方式の使い分け](determining-which-exporting-method-to-use.md)

- [__declspec(dllimport) を使用してアプリケーションにインポートする](importing-into-an-application-using-declspec-dllimport.md)

- [DLL の初期化](run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [def ファイル](reference/module-definition-dot-def-files.md)

- [モジュール定義ステートメントに関する規則](reference/rules-for-module-definition-statements.md)

- [装飾名](reference/decorated-names.md)

- [インライン関数のインポートとエクスポート](importing-and-exporting-inline-functions.md)

- [相互インポート](mutual-imports.md)

## <a name="see-also"></a>関連項目

[DLL からのエクスポート](exporting-from-a-dll.md)
