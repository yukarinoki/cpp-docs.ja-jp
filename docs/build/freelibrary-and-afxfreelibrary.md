---
description: '詳細情報: FreeLibrary と AfxFreeLibrary'
title: FreeLibrary と AfxFreeLibrary
ms.date: 11/04/2016
f1_keywords:
- FreeLibrary
- AfxFreeLibrary
helpviewer_keywords:
- extension DLLs [C++], unloading
- AfxFreeLibrary method
- unloading DLLs
- FreeLibrary method
- DLLs [C++], linking
- explicit linking [C++]
- DLLs [C++], unloading
ms.assetid: 4a48d290-3971-43e9-8e97-ba656cd0c8f8
ms.openlocfilehash: ea4da8c69aa663add85e740d99b68731e263b442
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97162795"
---
# <a name="freelibrary-and-afxfreelibrary"></a>FreeLibrary と AfxFreeLibrary

DLL に明示的にリンクするプロセスは、DLL モジュールが不要になったときに、[FreeLibrary](/windows/win32/api/libloaderapi/nf-libloaderapi-freelibrary) 関数を呼び出します。 この関数は、モジュールの参照数をデクリメントします。 また、参照数が 0 の場合は、プロセスのアドレス空間からマップ解除されます。

MFC アプリケーションでは、`FreeLibrary` ではなく [AfxFreeLibrary](../mfc/reference/application-information-and-management.md#afxfreelibrary) を使用して、MFC 拡張 DLL をアンロードします。 `AfxFreeLibrary` のインターフェイス (関数プロトタイプ) は、`FreeLibrary` と同じです。

## <a name="what-do-you-want-to-do"></a>実行する操作

- [実行可能ファイルと DLL のリンク](linking-an-executable-to-a-dll.md#linking-implicitly)

- [実行可能ファイルと DLL のリンク](linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [LoadLibrary と AfxLoadLibrary](loadlibrary-and-afxloadlibrary.md)

- [GetProcAddress](getprocaddress.md)

## <a name="see-also"></a>関連項目

[Visual Studio での C/C++ DLL の作成](dlls-in-visual-cpp.md)\
[FreeLibrary](/windows/win32/api/libloaderapi/nf-libloaderapi-freelibrary)\
[AfxFreeLibrary](../mfc/reference/application-information-and-management.md#afxfreelibrary)
