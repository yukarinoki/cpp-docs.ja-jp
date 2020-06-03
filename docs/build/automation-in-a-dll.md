---
title: DLL でのオートメーション
ms.date: 11/04/2016
helpviewer_keywords:
- DLLs [C++], Automation
- Automation [C++], DLLs
ms.assetid: 2728ecd1-14e2-4ae0-a946-e749e11dbb74
ms.openlocfilehash: dedc832d6726dccf8c0c2e88f9f4d5c67590c1c2
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220919"
---
# <a name="automation-in-a-dll"></a>DLL でのオートメーション

MFC DLL ウィザードで [オートメーション] オプションを選択すると、ウィザードでは次が提供されます。

- 初心者向けのオブジェクト記述言語 (.ODL) ファイル

- Afxole.h 用の STDAFX.h ファイルの include ディレクティブ

- **AfxDllGetClassObject** 関数を呼び出す、`DllGetClassObject` 関数の実装

- **AfxDllCanUnloadNow** 関数を呼び出す、`DllCanUnloadNow` 関数の実装

- [COleObjectFactory::UpdateRegistryAll](../mfc/reference/coleobjectfactory-class.md#updateregistryall) 関数を呼び出す、`DllRegisterServer` 関数の実装

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [オートメーション サーバー](../mfc/automation-servers.md)

## <a name="see-also"></a>関連項目

[Visual Studio での C/C++ Dll の作成](dlls-in-visual-cpp.md)
