---
title: インポートとエクスポート
ms.date: 05/06/2019
helpviewer_keywords:
- DLLs [C++], importing
- exporting DLLs [C++]
- importing DLLs [C++]
- DLLs [C++], exporting from
- __declspec(dllimport) keyword [C++]
ms.assetid: 7c44c2aa-2117-4cec-9615-a65bfd3f8f7b
ms.openlocfilehash: 29c8abf9528c2c34bd918463bccc8f845958759c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87231534"
---
# <a name="importing-and-exporting"></a>インポートとエクスポート

次の 2 つの方法を使用して、パブリック シンボルをアプリケーションにインポートしたり、DLL から関数をエクスポートしたりすることができます。

- DLL をビルドするときにモジュール定義 (.def) ファイルを使用する

- メイン アプリケーションの関数定義でキーワード **`__declspec(dllimport)`** または **`__declspec(dllexport)`** を使用する

## <a name="using-a-def-file"></a>.def ファイルの使用

モジュール定義ファイル (.def) は、テキスト ファイルです。DLL のさまざまな属性を記述する 1 つ以上のモジュール文が含まれています。 DLL の関数をエクスポートするために **`__declspec(dllimport)`** または **`__declspec(dllexport)`** を使用しない場合、DLL には .def ファイルが必要です。

.def ファイルを使用して、[アプリケーションにインポートする](importing-using-def-files.md)か、[DLL からエクスポートする](exporting-from-a-dll-using-def-files.md)ことができます。

## <a name="using-__declspec"></a>__declspec の使用

コードを正しくコンパイルするために **`__declspec(dllimport)`** を使用する必要はありませんが、使用するとコンパイラによってより適切なコードが生成されます。 コンパイラは、関数が DLL に存在するかどうかを判別できるため、より優れたコードを生成できます。これにより、コンパイラは、DLL 境界を越えた関数呼び出しに通常存在する間接参照のレベルをスキップするコードを生成できます。 ただし、DLL で使用されている変数をインポートするには、 **`__declspec(dllimport)`** を使用する必要があります。

適切な .def ファイルの EXPORTS セクションを使用する場合、 **`__declspec(dllexport)`** は不要です。 **`__declspec(dllexport)`** は、.def ファイルを使用せずに .exe または .dll ファイルから関数をエクスポートする簡単な方法を提供するために追加されました。

Win32 ポータブル実行可能形式は、インポートを修正するために操作する必要があるページ数を最小限に抑えるように設計されています。 これを行うには、プログラムのすべてのインポート アドレスを、インポート アドレス テーブルという 1 か所に配置します。 これにより、ローダーでは、これらのインポートにアクセスするときに 1 ページまたは 2 ページのみを変更できます。

## <a name="what-do-you-want-to-do"></a>実行する操作

- [アプリケーションへのインポート](importing-into-an-application-using-declspec-dllimport.md)

- [DLL からのエクスポート](exporting-from-a-dll.md)

## <a name="see-also"></a>関連項目

[Visual Studio での C/C++ Dll の作成](dlls-in-visual-cpp.md)
