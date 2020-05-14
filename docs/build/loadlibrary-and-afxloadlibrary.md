---
title: LoadLibrary と AfxLoadLibrary
description: MSVC での DLL の明示的読み込みに LoadLibrary と AfxLoadLibrary を使用します。
ms.date: 01/28/2020
f1_keywords:
- LoadLibrary
helpviewer_keywords:
- DLLs [C++], AfxLoadLibrary
- DLLs [C++], LoadLibrary
- AfxLoadLibrary method
- LoadLibrary method
- explicit linking [C++]
ms.assetid: b4535d19-6243-4146-a31a-a5cca4c7c9e3
ms.openlocfilehash: f803212c4485f7517dc42802f1ff581ffa4e609d
ms.sourcegitcommit: b8c22e6d555cf833510753cba7a368d57e5886db
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821539"
---
# <a name="loadlibrary-and-afxloadlibrary"></a>LoadLibrary と AfxLoadLibrary

プロセスでは、DLL に明示的にリンクするために、[LoadLibrary](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryw) または [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw) が呼び出されます (MFC アプリは [AfxLoadLibrary](../mfc/reference/application-information-and-management.md#afxloadlibrary) または [AfxLoadLibraryEx](../mfc/reference/application-information-and-management.md#afxloadlibraryex) を使用します)。この関数が正常終了した場合、呼び出し元プロセスのアドレス空間に指定された DLL が割り当てられ、DLL へのハンドルが返されます。 このハンドルは、`GetProcAddress` や `FreeLibrary` など、明示的リンクに必要な他の関数で使用できます。 詳細については、[明示的リンク](linking-an-executable-to-a-dll.md#linking-explicitly)に関するセクションを参照してください。

`LoadLibrary` は、暗黙リンクと同じ検索シーケンスで DLL を探します。 `LoadLibraryEx` を使用すると、検索パスの順序をより細かく制御できます。 詳細については、[ダイナミック リンク ライブラリの検索順序](/windows/win32/dlls/dynamic-link-library-search-order)に関するページを参照してください。 システムが DLL を見つけられない場合、またはエントリ ポイント関数が FALSE を返した場合、`LoadLibrary` は NULL を返します。 `LoadLibrary` への呼び出しで指定される DLL モジュールが呼び出し元プロセスのアドレス空間に既に割り当てられている場合、この関数は DLL のハンドルを返し、モジュールの参照カウントをインクリメントします。

DLL にエントリ ポイント関数が含まれる場合、オペレーティング システムは、`LoadLibrary` または `LoadLibraryEx` を呼び出したスレッドのコンテキスト内でその関数を呼び出します。 DLL が既にプロセスにアタッチされている場合、エントリポイント関数は呼び出されません。 これは、DLL の `LoadLibrary` または `LoadLibraryEx` への以前の呼び出し時に、対応する `FreeLibrary` 関数への呼び出しがなかった場合に発生します。

拡張 DLL を読み込む MFC アプリケーションでは、`LoadLibrary` または `LoadLibraryEx` の代わりに `AfxLoadLibrary` または `AfxLoadLibraryEx` を使用することをお勧めします。 MFC 関数は、DLL を明示的に読み込む前にスレッドの同期を処理します。 `AfxLoadLibrary` と `AfxLoadLibraryEx` に対するインターフェイス (関数プロトタイプ) は、`LoadLibrary` と `LoadLibraryEx` に対するものと同じです。

Windows が DLL を読み込むことができない場合は、プロセスでエラーからの回復を試みることができます。 たとえば、ユーザーにエラーを通知し、DLL への別のパスを要求することができます。

> [!IMPORTANT]
> DLL の完全パスを指定してください。 `LoadLibrary` によってファイルが読み込まれるときに、現在のディレクトリが最初に検索される場合があります。 ファイルのパスを完全に指定しないと、意図したファイルでないファイルが読み込まれる可能性があります。 DLL を作成するときは、[/DEPENDENTLOADFLAG](reference/dependentloadflag.md) リンカー オプションを使用して、静的にリンクされた DLL の依存関係の検索順序を指定します。 DLL 内では、依存関係を明示的に読み込むための完全なパスと、モジュールの検索順序を指定するための呼び出しパラメーター `LoadLibraryEx` または `AfxLoadLibraryEx` を使用します。 詳細については、[ダイナミック リンク ライブラリのセキュリティ](/windows/win32/dlls/dynamic-link-library-security)と[ダイナミック リンク ライブラリの検索順序](/windows/win32/dlls/dynamic-link-library-search-order)に関するページを参照してください。

## <a name="what-do-you-want-to-do"></a>実行する操作

- [実行可能ファイルと DLL のリンク](linking-an-executable-to-a-dll.md#linking-implicitly)

- [実行可能ファイルと DLL のリンク](linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [ダイナミック リンク ライブラリの検索順序](/windows/win32/Dlls/dynamic-link-library-search-order)

- [FreeLibrary と AfxFreeLibrary](freelibrary-and-afxfreelibrary.md)

- [GetProcAddress](getprocaddress.md)

## <a name="see-also"></a>関連項目

- [Visual Studio での C/C++ Dll の作成](dlls-in-visual-cpp.md)
