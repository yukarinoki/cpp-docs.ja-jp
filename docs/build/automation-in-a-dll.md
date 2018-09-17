---
title: DLL でのオートメーション |Microsoft Docs
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
ms.openlocfilehash: cde5d0e400f1bdd3f5a851d47da581380273b04a
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45717784"
---
# <a name="automation-in-a-dll"></a>DLL でのオートメーション

MFC DLL ウィザード [オートメーション] オプションを選択すると、ウィザードは次のように提供します。

- 初期のオブジェクト記述言語 (します。ODL) ファイル

- Afxole.h の STDAFX.h ファイルに include ディレクティブ

- 実装、`DllGetClassObject`を呼び出す関数、 **AfxDllGetClassObject**関数

- 実装、`DllCanUnloadNow`を呼び出す関数、 **AfxDllCanUnloadNow**関数

- 実装、`DllRegisterServer`を呼び出す関数、[されます](../mfc/reference/coleobjectfactory-class.md#updateregistryall)関数

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [オートメーション サーバー](../mfc/automation-servers.md)

## <a name="see-also"></a>関連項目

[Visual C++ の DLL](../build/dlls-in-visual-cpp.md)