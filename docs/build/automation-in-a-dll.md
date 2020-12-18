---
description: '詳細情報: DLL でのオートメーション'
title: DLL でのオートメーション
ms.date: 11/04/2016
helpviewer_keywords:
- DLLs [C++], Automation
- Automation [C++], DLLs
ms.assetid: 2728ecd1-14e2-4ae0-a946-e749e11dbb74
ms.openlocfilehash: e0d6d0beec71f3994f6e726c6946b2069d1b081b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97163237"
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
