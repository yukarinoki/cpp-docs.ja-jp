---
title: エクスポート方式の使い分け
ms.date: 11/04/2016
helpviewer_keywords:
- __declspec(dllexport) keyword [C++]
- exporting DLLs [C++], method comparison
- def files [C++], exporting from DLLs
- .def files [C++], exporting from DLLs
ms.assetid: 66d773ed-935c-45c2-ad03-1a060874b34d
ms.openlocfilehash: 974c32cef87801599ba0d14fd146e84ad874467f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62273738"
---
# <a name="determine-which-exporting-method-to-use"></a>エクスポート方式の使い分け

関数は .def ファイルか `__declspec(dllexport)` キーワードでエクスポートできます。 自分の DLL に最適な方法を判断するとき、以下の質問について検討すると役立ちます。

- エクスポートする関数は後で増える予定ですか。

- DLL は、再構築できるアプリケーションでのみ利用されますか、それとも、再構築できないアプリケーション、たとえば、サード パーティ製のアプリケーションで利用されますか。

## <a name="pros-and-cons-of-using-def-files"></a>.def ファイル使用の利点と欠点

.def ファイルで関数をエクスポートすると、エクスポートの順序を制御できます。 エクスポートした関数を DLL に追加するとき、エクスポートされた他の関数より上の順序値を割り当てることができます。 そのとき、暗黙的なリンクを利用するアプリケーションでは、新しい関数が含まれるインポート ライブラリを再リンクする必要がありません。 これは、さまざまなアプリケーションで利用される DLL の設計時に非常に便利です。新しい機能を追加するとき、その機能は、それに既に依存しているアプリケーションと引き続き正しく連動するためです。 たとえば、MFC DLL は .def ファイルを利用して構築されます。

.def ファイルを利用するもう 1 つの利点は、`NONAME` 属性を利用して関数をエクスポートできることです。 そのとき、エクスポート テーブルの順序のみが DLL に入ります。 エクスポートされる関数の数が多い DLL の場合、`NONAME` 属性を利用すると、DLL ファイルのサイズを削減できます。 モジュール定義ステートメントを記述する方法については、「[モジュール定義ステートメントに関する規則](reference/rules-for-module-definition-statements.md)」を参照してください。 順序によるエクスポートについては、「[名前ではなく序数値による DLL 関数のエクスポート](exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md)」を参照してください。

.def ファイル利用の欠点は、C++ ファイルで関数をエクスポートする場合、.def ファイルに修飾名を入れるか、MSVC コンパイラの名前修飾を回避する目的で、エクスポートされる関数を extern "C" を使用して定義する必要があります。

.def ファイルに装飾名を入れる場合、装飾名を取得するには、[DUMPBIN](reference/dumpbin-reference.md) ツールか [/MAP](reference/map-generate-mapfile.md) リンカー オプションを使用します。 コンパイラで生成される修飾名はコンパイラ固有です。そのため、コンパイラで生成された修飾名を .def ファイルに入れる場合、呼び出し元アプリケーションの修飾名が DLL の .def ファイルのエクスポート名に一致するよう、DLL にリンクされるアプリケーションも同じバージョンのコンパイラを使用して構築する必要があります。

## <a name="pros-and-cons-of-using-__declspecdllexport"></a>__declspec(dllexport) 使用の利点と欠点

`__declspec(dllexport)` を使用するときは、.def ファイルを維持し、エクスポートされる関数の修飾名を取得する必要がないため、便利です。 ただし、このエクスポート方法が便利かどうかは、リンクされているアプリケーションを再構築する件数によります。 新しいエクスポートで DLL を再構築する場合、アプリケーションも再構築する必要があります。別バージョンのコンパイラを利用して再構築する場合、エクスポートされる C++ 関数の修飾名が変わることがあるためです。

### <a name="what-do-you-want-to-do"></a>実行する操作

- [.DEF ファイルを使用した DLL からのエクスポート](exporting-from-a-dll-using-def-files.md)

- [__declspec(dllexport) を使用した DLL からのエクスポート](exporting-from-a-dll-using-declspec-dllexport.md)

- [AFX_EXT_CLASS を使用したエクスポートとインポート](exporting-and-importing-using-afx-ext-class.md)

- [C 言語の実行可能ファイルで使用する C++ 関数のエクスポート](exporting-cpp-functions-for-use-in-c-language-executables.md)

- [C または C++ 言語の実行可能ファイルで使用する C 関数のエクスポート](exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)

- [__declspec(dllimport) を使用してアプリケーションにインポートする](importing-into-an-application-using-declspec-dllimport.md)

- [DLL の初期化](run-time-library-behavior.md#initializing-a-dll)

### <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [インライン関数のインポートとエクスポート](importing-and-exporting-inline-functions.md)

- [相互インポート](mutual-imports.md)

- [装飾名](reference/decorated-names.md)

## <a name="see-also"></a>関連項目

[DLL からのエクスポート](exporting-from-a-dll.md)
