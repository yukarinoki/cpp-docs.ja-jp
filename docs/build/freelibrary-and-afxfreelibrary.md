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
ms.openlocfilehash: ce52eb43fa8f371b68d836f01163003f056f34c7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50530235"
---
# <a name="freelibrary-and-afxfreelibrary"></a>FreeLibrary と AfxFreeLibrary

明示的にリンクする DLL の呼び出しプロセス、 [FreeLibrary](/windows/desktop/api/libloaderapi/nf-libloaderapi-freelibrary) DLL モジュールが不要になったときに機能します。 モジュールの参照カウントをデクリメントを関数し、参照カウントが 0 の場合は、プロセスのアドレス空間からマッピングを解除します。

MFC アプリケーションで使用して[AfxFreeLibrary](../mfc/reference/application-information-and-management.md#afxfreelibrary)の代わりに`FreeLibrary`MFC 拡張 DLL をアンロードします。 インターフェイス (関数プロトタイプ)`AfxFreeLibrary`と同じ`FreeLibrary`します。

## <a name="what-do-you-want-to-do"></a>実行する操作

- [DLL と暗黙的にリンクする方法](../build/linking-an-executable-to-a-dll.md#linking-implicitly)

- [リンク方式の使用](../build/linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [LoadLibrary と AfxLoadLibrary](../build/loadlibrary-and-afxloadlibrary.md)

- [GetProcAddress](../build/getprocaddress.md)

## <a name="see-also"></a>関連項目

[Visual C++ の DLL](../build/dlls-in-visual-cpp.md)<br/>
[FreeLibrary](/windows/desktop/api/libloaderapi/nf-libloaderapi-freelibrary)
[AfxFreeLibrary](../mfc/reference/application-information-and-management.md#afxfreelibrary)