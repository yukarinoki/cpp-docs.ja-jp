---
title: リソースのみの DLL の作成
description: Visual Studio でリソースのみの DLL を作成する方法。
ms.date: 01/27/2020
helpviewer_keywords:
- resource-only DLLs [C++], creating
- DLLs [C++], creating
ms.assetid: e6b1d4da-7275-467f-a58c-a0a8a5835199
no-loc:
- noentry
ms.openlocfilehash: 5b7b3b4767c32bce52ad2c36c9ecc5d34b2e29b4
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922167"
---
# <a name="creating-a-resource-only-dll"></a>リソースのみの DLL の作成

リソースのみの DLL とは、リソース以外のものを一切含まず、アイコン、ビットマップ、文字列、ダイアログ ボックスだけを含む DLL です。 リソースのみの DLL は、複数のプログラム間でリソース群を共有するのに適しています。 また、複数の言語にローカライズされたリソースをアプリケーションに提供する場合にも適しています。 詳細については、「[MFC アプリケーションのローカライズされたリソース: サテライト DLL](localized-resources-in-mfc-applications-satellite-dlls.md)」を参照してください。

## <a name="create-a-resource-only-dll"></a>リソースのみの DLL を作成する

リソースのみの DLL を作成するには、Windows DLL (非 MFC) プロジェクトを新規作成し、ここにリソースを追加します。

::: moniker range="msvc-140"

1. **[新しいプロジェクト]** ダイアログ ボックスで **[Win32 プロジェクト]** を選択します。 プロジェクトとソリューションの名前を入力し、 **[OK]** を選択します。

1. **Win32 アプリケーション ウィザード** で、 **[アプリケーション設定]** を選択します。 **[DLL]** の **[アプリケーションの種類]** を選択します。 **[追加のオプション]** の **[空のプロジェクト]** を選択します。 **[完了]** を選択してプロジェクトを作成します。

1. DLL のリソース (文字列やメニューなど) を含む新しいリソース スクリプトを作成します。 `.rc` ファイルを保存します。

1. **[プロジェクト]** メニューで、 **[既存項目の追加]** を選択し、新しい `.rc` ファイルをプロジェクトに挿入します。

1. [/NOENTRY](reference/noentry-no-entry-point.md) リンカー オプションを指定します。 `/NOENTRY` を指定すると、`_main` への参照が DLL にリンクされません。リソースのみの DLL を作成する場合は、このオプションを指定する必要があります。

1. DLL をビルドします。

::: moniker-end
::: moniker range=">=msvc-150"

1. **[新しいプロジェクト]** ダイアログ ボックスで **[Windows デスクトップ ウィザード]** を選択し、 **[次へ]** を選択します **[新しいプロジェクトの構成]** ページで、プロジェクトとソリューションの名前を入力し、 **[作成]** を選択します。

1. **[Windows デスクトップ プロジェクト]** ダイアログ ボックスで、 **[ダイナミック リンク ライブラリ]** の **[アプリケーションの種類]** を選択します。 **[追加のオプション]** の **[空のプロジェクト]** を選択します。 **[OK]** を選択してプロジェクトを作成します。

1. DLL のリソース (文字列やメニューなど) を含む新しいリソース スクリプトを作成します。 `.rc` ファイルを保存します。

1. **[プロジェクト]** メニューで、 **[既存項目の追加]** を選択し、新しい `.rc` ファイルをプロジェクトに挿入します。

1. [/NOENTRY](reference/noentry-no-entry-point.md) リンカー オプションを指定します。 `/NOENTRY` を指定すると、`_main` への参照が DLL にリンクされません。リソースのみの DLL を作成する場合は、このオプションを指定する必要があります。

1. DLL をビルドします。

::: moniker-end

## <a name="use-a-resource-only-dll"></a>リソースのみの DLL を使用する

リソースのみの DLL を使用するアプリケーションの場合、[LoadLibraryEx](loadlibrary-and-afxloadlibrary.md) または関連する関数を呼び出して、DLL に明示的にリンクする必要があります。 リソースにアクセスするには、あらゆる種類のリソースで機能する汎用関数 `FindResource` および `LoadResource` を呼び出します。 または、次のリソース固有の関数のいずれかを呼び出します。

- `FormatMessage`

- `LoadAccelerators`

- `LoadBitmap`

- `LoadCursor`

- `LoadIcon`

- `LoadMenu`

- `LoadString`

リソースの使用が終了したら、アプリケーションから `FreeLibrary` を呼び出す必要があります。

## <a name="see-also"></a>関連項目

[リソース ファイルの操作](../windows/working-with-resource-files.md)\
[Visual Studio での C/C++ Dll の作成](dlls-in-visual-cpp.md)
