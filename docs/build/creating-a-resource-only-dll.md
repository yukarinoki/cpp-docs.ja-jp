---
title: リソースのみの DLL の作成
ms.date: 11/04/2016
helpviewer_keywords:
- resource-only DLLs [C++], creating
- DLLs [C++], creating
ms.assetid: e6b1d4da-7275-467f-a58c-a0a8a5835199
ms.openlocfilehash: d2854c9ca993e9f1f27cab60cdd09e28ce2985f1
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57412650"
---
# <a name="creating-a-resource-only-dll"></a>リソースのみの DLL の作成

リソースのみの DLL とは、リソース以外のものを一切含まず、アイコン、ビットマップ、文字列、ダイアログ ボックスだけを含む DLL です。 リソースのみの DLL は、複数のプログラム間でリソース群を共有するのに適しています。 複数の言語にローカライズされたリソースをアプリケーションに提供する優れた方法も (を参照してください[MFC アプリケーションのローカライズされたリソース。サテライト Dll](../build/localized-resources-in-mfc-applications-satellite-dlls.md))。

リソースのみの DLL を作成するには、Win32 DLL (非 MFC) プロジェクトを新規作成し、ここにリソースを追加します。

- Win32 プロジェクトを選択、**新しいプロジェクト** ダイアログ ボックスし、Win32 プロジェクト ウィザードで DLL プロジェクトの種類を指定します。

- DLL 用のリソース (文字列やメニューなど) を含むリソース スクリプトを新規作成し、.rc ファイルに保存します。

- **プロジェクト** メニューのをクリックして**既存項目の追加**、し、新しい .rc ファイルをプロジェクトに挿入します。

- 指定、 [/NOENTRY](../build/reference/noentry-no-entry-point.md)リンカー オプション。 /NOENTRY への参照のリンクから、リンカーを防止する`_main`リソース専用 DLL を作成する DLL のこのオプションが必要です。

- DLL をビルドします。

リソース専用 DLL を使用するアプリケーションを呼び出す必要があります[LoadLibrary](../build/loadlibrary-and-afxloadlibrary.md) DLL に明示的にリンクします。 リソースにアクセスするには、ジェネリック関数を呼び出す`FindResource`と`LoadResource`リソースの種類にまたは、次のリソースに固有の関数のいずれかを呼び出します。

- `FormatMessage`

- `LoadAccelerators`

- `LoadBitmap`

- `LoadCursor`

- `LoadIcon`

- `LoadMenu`

- `LoadString`

アプリケーションを呼び出す必要があります`FreeLibrary`が完了すると、リソースを使用します。

## <a name="see-also"></a>関連項目

[リソース ファイルの操作](../windows/working-with-resource-files.md)<br/>
[Visual C++ の DLL](../build/dlls-in-visual-cpp.md)
