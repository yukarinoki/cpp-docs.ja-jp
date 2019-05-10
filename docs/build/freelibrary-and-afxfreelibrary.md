---
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
ms.openlocfilehash: 59deb75ad77b0a80efc69d9991e093ecef95c51e
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221416"
---
# <a name="freelibrary-and-afxfreelibrary"></a>FreeLibrary と AfxFreeLibrary

明示的にリンクする DLL の呼び出しプロセス、 [FreeLibrary](/windows/desktop/api/libloaderapi/nf-libloaderapi-freelibrary) DLL モジュールが不要になったときに機能します。 モジュールの参照カウントをデクリメントを関数し、参照カウントが 0 の場合は、プロセスのアドレス空間からマッピングを解除します。

MFC アプリケーションで使用して[AfxFreeLibrary](../mfc/reference/application-information-and-management.md#afxfreelibrary)の代わりに`FreeLibrary`MFC 拡張 DLL をアンロードします。 インターフェイス (関数プロトタイプ)`AfxFreeLibrary`と同じ`FreeLibrary`します。

## <a name="what-do-you-want-to-do"></a>実行する操作

- [実行可能ファイルと DLL のリンク](linking-an-executable-to-a-dll.md#linking-implicitly)

- [実行可能ファイルと DLL のリンク](linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [LoadLibrary と AfxLoadLibrary](loadlibrary-and-afxloadlibrary.md)

- [GetProcAddress](getprocaddress.md)

## <a name="see-also"></a>関連項目

[Visual Studio で C/C++ Dll を作成します。](dlls-in-visual-cpp.md)<br/>
[FreeLibrary](/windows/desktop/api/libloaderapi/nf-libloaderapi-freelibrary)
[AfxFreeLibrary](../mfc/reference/application-information-and-management.md#afxfreelibrary)
