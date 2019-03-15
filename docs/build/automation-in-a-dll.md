---
title: DLL でのオートメーション
ms.date: 11/04/2016
helpviewer_keywords:
- DLLs [C++], Automation
- Automation [C++], DLLs
ms.assetid: 2728ecd1-14e2-4ae0-a946-e749e11dbb74
ms.openlocfilehash: 4ac60c44348ea21f490cb312285ae88ac682cf7d
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57821249"
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

[Visual C++ の DLL](dlls-in-visual-cpp.md)
