---
title: FreeLibrary と AfxFreeLibrary |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- FreeLibrary
- AfxFreeLibrary
dev_langs:
- C++
helpviewer_keywords:
- extension DLLs [C++], unloading
- AfxFreeLibrary method
- unloading DLLs
- FreeLibrary method
- DLLs [C++], linking
- explicit linking [C++]
- DLLs [C++], unloading
ms.assetid: 4a48d290-3971-43e9-8e97-ba656cd0c8f8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 063c858253c12cfedbf252a124029b8cbc16a691
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43680964"
---
# <a name="freelibrary-and-afxfreelibrary"></a>FreeLibrary と AfxFreeLibrary
明示的にリンクする DLL の呼び出しプロセス、 [FreeLibrary](https://msdn.microsoft.com/library/windows/desktop/ms683152(v=vs.85).aspx) DLL モジュールが不要になったときに機能します。 モジュールの参照カウントをデクリメントを関数し、参照カウントが 0 の場合は、プロセスのアドレス空間からマッピングを解除します。  
  
 MFC アプリケーションで使用して[AfxFreeLibrary](../mfc/reference/application-information-and-management.md#afxfreelibrary)の代わりに`FreeLibrary`MFC 拡張 DLL をアンロードします。 インターフェイス (関数プロトタイプ)`AfxFreeLibrary`と同じ`FreeLibrary`します。  
  
## <a name="what-do-you-want-to-do"></a>実行する操作  
  
-   [DLL と暗黙的にリンクする方法](../build/linking-an-executable-to-a-dll.md#linking-implicitly)  
  
-   [リンク方式の使用](../build/linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)  
  
## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください  
  
-   [LoadLibrary と AfxLoadLibrary](../build/loadlibrary-and-afxloadlibrary.md)  
  
-   [GetProcAddress](../build/getprocaddress.md)  
  
## <a name="see-also"></a>関連項目  
 [Visual C の Dll](../build/dlls-in-visual-cpp.md)   
 [FreeLibrary](https://msdn.microsoft.com/library/windows/desktop/ms683152(v=vs.85).aspx)   
 [AfxFreeLibrary](../mfc/reference/application-information-and-management.md#afxfreelibrary)