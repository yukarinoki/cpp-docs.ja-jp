---
title: DEF ファイルを使った DLL からのエクスポート
ms.date: 05/06/2019
helpviewer_keywords:
- def files [C++], exporting from DLLs
- .def files [C++], exporting from DLLs
- exporting DLLs [C++], DEF files
ms.assetid: 9d31eda2-184e-47de-a2ee-a93ebd603f8e
ms.openlocfilehash: 6f7d58bcb42edd89527fff41b08a15321722a6cf
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80078522"
---
# <a name="exporting-from-a-dll-using-def-files"></a>DEF ファイルを使った DLL からのエクスポート

モジュール定義または DEF ファイル (* .def) は、DLL のさまざまな属性を記述する1つ以上の module ステートメントを含むテキストファイルです。 DLL の関数をエクスポートするために **__declspec (dllexport)** キーワードを使用していない場合、dll には DEF ファイルが必要です。

最小 DEF ファイルには、次のモジュール定義ステートメントが含まれている必要があります。

- ファイルの先頭には、必ず LIBRARY 文を記述します。 このステートメントは、DLL に属する DEF ファイルを識別します。 LIBRARY 文の引数には、DLL の名前を指定します。 リンカーは、この名前を DLL のインポート ライブラリに配置します。

- EXPORTS 文には、DLL のエクスポート関数の名前と、オプションで序数値を指定します。 序数値を関数に割り当てるには、アット マーク (@) と数字の後に関数名を記述します。 序数値の場合は、1 から N の範囲で指定する必要があります。N は DLL のエクスポート関数の数字です。 序数によって関数をエクスポートする場合は、「[名前ではなく序数による DLL からの関数のエクスポート](exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md)」を参照してください。

たとえば、バイナリ検索ツリーを実装するコードを含む DLL は、以下のようになります。

```
LIBRARY   BTREE
EXPORTS
   Insert   @1
   Delete   @2
   Member   @3
   Min   @4
```

Mfc [Dll ウィザード](../mfc/reference/mfc-dll-wizard.md)を使用して mfc dll を作成する場合、ウィザードによってスケルトン DEF ファイルが作成され、プロジェクトに自動的に追加されます。 エクスポートされる関数の名前は、このファイルに追加します。 非 MFC Dll の場合は、DEF ファイルを自分で作成し、プロジェクトに追加します。 次に、 **[プロジェクト]**  >  **[プロパティ]**  > [**リンカー** > **入力** > **モジュール定義ファイル**] の順に選択し、DEF ファイルの名前を入力します。 各構成とプラットフォームに対してこの手順を繰り返します。または、[**構成] = [すべての構成**]、 **[プラットフォーム = すべて]** のプラットフォーム の順に選択して、すべてを一度に実行します。

C++ファイル内の関数をエクスポートする場合は、装飾名を DEF ファイルに配置するか、Extern "c" を使用して標準 C リンケージでエクスポートされた関数を定義する必要があります。 装飾名を DEF ファイルに配置する必要がある場合は、 [DUMPBIN](../build/reference/dumpbin-reference.md)ツールを使用するか、またはリンカーの[/map](../build/reference/map-generate-mapfile.md)オプションを使用して取得できます。 コンパイラが作成した装飾名は、コンパイラ独自のものであることに注意してください。 Microsoft C++ COMPILER (MSVC) によって生成された装飾名を DEF ファイルに配置する場合は、dll にリンクするアプリケーションも同じバージョンの MSVC を使用してビルドする必要があります。これにより、呼び出し元アプリケーションの装飾名が DLL の def ファイル内のエクスポートされた名前と一致するようになります。

> [!NOTE]
> Visual Studio 2015 でビルドされた DLL は、Visual Studio 2017 または Visual Studio 2019 でビルドされたアプリケーションで使用できます。

[拡張 DLL](../build/extension-dlls-overview.md)をビルドし、DEF ファイルを使用してエクスポートする場合は、エクスポートされたクラスを含むヘッダーファイルの先頭と末尾に次のコードを配置します。

```
#undef AFX_DATA
#define AFX_DATA AFX_EXT_DATA
// <body of your header file>
#undef AFX_DATA
#define AFX_DATA
```

これらの行によって、内部で使用される MFC 変数またはクラスに追加される MFC 変数が、MFC 拡張 DLL からエクスポート (またはインポート) されます。 たとえば、`DECLARE_DYNAMIC` を使って派生クラスを作成する場合、このマクロが展開して、`CRuntimeClass` メンバー関数をクラスに追加します。 上の 4 行をコードに追加しないと、DLL の不正なコンパイルまたはリンクが行われたり、クライアント アプリケーションが DLL とリンクするときにエラーが発生することになります。

DLL のビルド時に、リンカーは DEF ファイルを使用してエクスポート (.exp) ファイルとインポートライブラリ (.lib) ファイルを作成します。 次にリンカーはエクスポート ファイルを使って、.DLL ファイルを作成します。 DLL と暗黙的にリンクする実行形式は、ビルド時にインポート ライブラリと DLL をリンクします。

MFC 自体では、DEF ファイルを使用して、Mfcx0.dll から関数およびクラスをエクスポートすることに注意してください。

## <a name="what-do-you-want-to-do"></a>目的に合ったトピックをクリックしてください

- [__Declspec (dllexport) を使用して DLL からエクスポートする](exporting-from-a-dll-using-declspec-dllexport.md)

- [AFX_EXT_CLASS を使用したエクスポートとインポート](exporting-and-importing-using-afx-ext-class.md)

- [C C++言語の実行可能ファイルで使用するエクスポート関数](exporting-cpp-functions-for-use-in-c-language-executables.md)

- [C またはC++言語の実行可能ファイルで使用する c 関数をエクスポートする](exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)

- [使用するエクスポート方法を決定する](determining-which-exporting-method-to-use.md)

- [__declspec(dllimport) を使用してアプリケーションにインポートする](importing-into-an-application-using-declspec-dllimport.md)

- [DLL の初期化](run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [.def ファイル](reference/module-definition-dot-def-files.md)

- [モジュール定義ステートメントの規則](reference/rules-for-module-definition-statements.md)

- [装飾名](reference/decorated-names.md)

- [インライン関数のインポートとエクスポート](importing-and-exporting-inline-functions.md)

- [相互インポート](mutual-imports.md)

## <a name="see-also"></a>参照

[DLL からのエクスポート](exporting-from-a-dll.md)
