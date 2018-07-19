---
title: DLL でのオートメーション |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DLLs [C++], Automation
- Automation [C++], DLLs
ms.assetid: 2728ecd1-14e2-4ae0-a946-e749e11dbb74
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 41c5f31a72cf734296ecb281e0785d415c8043a7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32360655"
---
# <a name="automation-in-a-dll"></a>DLL でのオートメーション
MFC DLL ウィザードで [オートメーション] オプションを選択すると、ウィザードは、次のように。  
  
-   スターター オブジェクト記述言語 (です。ODL) ファイル  
  
-   STDAFX.h ファイル Afxole.h の include ディレクティブ  
  
-   実装、`DllGetClassObject`を呼び出した関数、 **AfxDllGetClassObject**関数  
  
-   実装、`DllCanUnloadNow`を呼び出した関数、 **AfxDllCanUnloadNow**関数  
  
-   実装、`DllRegisterServer`を呼び出した関数、[されます](../mfc/reference/coleobjectfactory-class.md#updateregistryall)関数  
  
## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください  
  
-   [オートメーション サーバー](../mfc/automation-servers.md)  
  
## <a name="see-also"></a>関連項目  
 [Visual C++ の DLL](../build/dlls-in-visual-cpp.md)