---
title: リソース専用 DLL の作成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- resource-only DLLs [C++], creating
- DLLs [C++], creating
ms.assetid: e6b1d4da-7275-467f-a58c-a0a8a5835199
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5249f4528038771162bb96b714524ed751ff39a7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32367548"
---
# <a name="creating-a-resource-only-dll"></a>リソースのみの DLL の作成  
  
リソースのみの DLL とは、リソース以外のものを一切含まず、アイコン、ビットマップ、文字列、ダイアログ ボックスだけを含む DLL です。 リソースのみの DLL は、複数のプログラム間でリソース群を共有するのに適しています。 複数の言語にローカライズされたリソースをアプリケーションに提供することをお勧めも (を参照してください[MFC アプリケーションのローカライズされたリソース: サテライト Dll](../build/localized-resources-in-mfc-applications-satellite-dlls.md))。  
  
リソースのみの DLL を作成するには、Win32 DLL (非 MFC) プロジェクトを新規作成し、ここにリソースを追加します。  
  
-   Win32 プロジェクトを選択して、**新しいプロジェクト** ダイアログ ボックスし、Win32 プロジェクト ウィザードで DLL プロジェクトの種類を指定します。  
  
-   DLL 用のリソース (文字列やメニューなど) を含むリソース スクリプトを新規作成し、.rc ファイルに保存します。  
  
-   **プロジェクト** メニューのをクリックして**既存項目の追加**、し、新しい .rc ファイルをプロジェクトに挿入します。  
  
-   指定して、 [/NOENTRY](../build/reference/noentry-no-entry-point.md)リンカー オプション。 /NOENTRY 防止リンカーへの参照をリンク`_main`DLL のリソース専用 DLL の作成には、このオプションが必要です。  
  
-   DLL をビルドします。  
  
リソース専用 DLL を使用するアプリケーションを呼び出す必要があります[LoadLibrary](../build/loadlibrary-and-afxloadlibrary.md) DLL に明示的にリンクします。 リソースへのアクセス、ジェネリック関数を呼び出す`FindResource`と`LoadResource`リソースの種類で機能または次のリソースに固有の機能の 1 つを呼び出しています。  
  
-   `FormatMessage`  
  
-   `LoadAccelerators`  
  
-   `LoadBitmap`  
  
-   `LoadCursor`  
  
-   `LoadIcon`  
  
-   `LoadMenu`  
  
-   `LoadString`  
  
アプリケーションを呼び出す必要があります`FreeLibrary`が完了したときのリソースを使用します。  
  
## <a name="see-also"></a>関連項目  
  
[リソース ファイルの操作](../windows/working-with-resource-files.md)  
[Visual C++ の DLL](../build/dlls-in-visual-cpp.md)