---
description: '詳細: C++ ウィンドウオブジェクトと HWND の関係'
title: C++ ウィンドウ オブジェクトと HWND の関係
ms.date: 11/19/2018
f1_keywords:
- HWND
helpviewer_keywords:
- Windows window [MFC]
- window objects [MFC], HWND and
- HWND [MFC]
- CWnd class [MFC], HWND
- HWND, window objects [MFC]
ms.assetid: f2e76340-6691-4ee6-9424-0345634a9469
ms.openlocfilehash: bdcf52d2890265b854e3eef7854b489b47eda6a7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218096"
---
# <a name="relationship-between-a-c-window-object-and-an-hwnd"></a>C++ ウィンドウ オブジェクトと HWND の関係

Window *オブジェクト* は、 `CWnd` プログラムによって直接作成される C++ クラス (または派生クラス) のオブジェクトです。 このメソッドは、プログラムのコンストラクターとデストラクターの呼び出しに応答します。 一方、Windows の *ウィンドウ* は、ウィンドウに対応し、システムリソースを使用する内部 windows データ構造を認識しないハンドルです。 Windows ウィンドウは "ウィンドウハンドル" () で識別され、 `HWND` `CWnd` クラスのメンバー関数の呼び出しによってオブジェクトが作成された後に作成され `Create` `CWnd` ます。 このウィンドウは、プログラム呼び出しまたはユーザーの操作によって破棄される場合があります。 ウィンドウハンドルは、ウィンドウオブジェクトの *m_hWnd* メンバー変数に格納されます。 次の図は、C++ ウィンドウオブジェクトと Windows ウィンドウの関係を示しています。 Windows の作成については、「 [windows の作成](../mfc/creating-windows.md)」で説明しています。 ウィンドウの破棄については、 [「ウィンドウオブジェクトの破棄](../mfc/destroying-window-objects.md)」で説明されています。

![CWnd ウィンドウ オブジェクトおよび結果のウィンドウ](../mfc/media/vc37fj1.gif "CWnd ウィンドウ オブジェクトおよび結果のウィンドウ") <br/>
ウィンドウ オブジェクトと Windows のウィンドウ

## <a name="see-also"></a>関連項目

[ウィンドウオブジェクト](../mfc/window-objects.md)
