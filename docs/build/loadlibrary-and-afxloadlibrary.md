---
title: LoadLibrary と AfxLoadLibrary
ms.date: 05/24/2018
f1_keywords:
- LoadLibrary
helpviewer_keywords:
- DLLs [C++], AfxLoadLibrary
- DLLs [C++], LoadLibrary
- AfxLoadLibrary method
- LoadLibrary method
- explicit linking [C++]
ms.assetid: b4535d19-6243-4146-a31a-a5cca4c7c9e3
ms.openlocfilehash: c7700dd865e320686a2ad8bd036f207b9ecee6ac
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "69493211"
---
# <a name="loadlibrary-and-afxloadlibrary"></a>LoadLibrary と AfxLoadLibrary

[LoadLibraryExA](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexa)または[LoadLibraryExW](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw) (または[AfxLoadLibrary](../mfc/reference/application-information-and-management.md#afxloadlibrary)) を呼び出して、DLL に明示的にリンクします。 この関数が正常終了した場合、呼び出し元プロセスのアドレス空間に指定された DLL が割り当てられ、DLL へのハンドルが返されます。このハンドルは、`GetProcAddress` や `FreeLibrary` など、明示的リンクに必要な他の関数で使用できます。

`LoadLibrary` は、暗黙リンクと同じ検索シーケンスで DLL を探します。 システムが DLL を見つけられない場合、またはエントリ ポイント関数が FALSE を返した場合、`LoadLibrary` は NULL を返します。 `LoadLibrary` への呼び出しで指定される DLL モジュールが呼び出し元プロセスのアドレス空間に既に割り当てられている場合、この関数は DLL のハンドルを返し、モジュールの参照カウントをインクリメントします。

DLL にエントリ ポイント関数が含まれる場合、オペレーティング システムは、`LoadLibrary` を呼び出したスレッドのコンテキスト内でその関数を呼び出します。 `LoadLibrary` の前回の呼び出しに対応する `FreeLibrary` 関数呼び出しが行われていないために、DLL が既にプロセスにアタッチされている場合は、エントリ ポイント関数は呼び出されません。

Mfc 拡張 dll を読み込む mfc アプリケーションでは、の`AfxLoadLibrary` `LoadLibrary`代わりにを使用することをお勧めします。 `AfxLoadLibrary` を呼び出す前に、`LoadLibrary` でスレッド同期を処理します。 `AfxLoadLibrary` のインターフェイス (関数プロトタイプ) は、`LoadLibrary` と同じです。

Windows が DLL を読み込むことができない場合は、プロセスでエラーからの回復を試みることができます。 たとえば、プロセスがユーザーにエラーを通知して、ユーザーに DLL への別のパスを指定するよう要求できます。

> [!IMPORTANT]
> Dll の完全パスを指定してください。 ファイルが読み込まれると、現在のディレクトリが最初に検索されます。 ファイルのパスを指定していないと、目的のファイルでないファイルが読み込まれる場合があります。 これを回避するもう1つの方法は、 [/dependentloadflag](reference/dependentloadflag.md)リンカーオプションを使用することです。

## <a name="what-do-you-want-to-do"></a>実行する操作

- [実行可能ファイルと DLL のリンク](linking-an-executable-to-a-dll.md#linking-implicitly)

- [実行可能ファイルと DLL のリンク](linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [ダイナミックリンクライブラリの検索順序](/windows/win32/Dlls/dynamic-link-library-search-order)

- [FreeLibrary と AfxFreeLibrary](freelibrary-and-afxfreelibrary.md)

- [GetProcAddress](getprocaddress.md)

## <a name="see-also"></a>関連項目

- [Visual Studio での C/C++ Dll の作成](dlls-in-visual-cpp.md)
