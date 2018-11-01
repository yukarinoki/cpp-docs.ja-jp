---
title: C++ ウィンドウ オブジェクトと HWND の関係
ms.date: 11/04/2016
f1_keywords:
- HWND
helpviewer_keywords:
- Windows window [MFC]
- window objects [MFC], HWND and
- HWND [MFC]
- CWnd class [MFC], HWND
- HWND, window objects [MFC]
ms.assetid: f2e76340-6691-4ee6-9424-0345634a9469
ms.openlocfilehash: 46a3bdfdc3a9d1a41463eaf913e224a3f7c886e4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50519510"
---
# <a name="relationship-between-a-c-window-object-and-an-hwnd"></a>C++ ウィンドウ オブジェクトと HWND の関係

ウィンドウ*オブジェクト*、C++ のオブジェクトである`CWnd`クラス (または派生クラス)、プログラムを直接作成します。 付属し、プログラムのコンス トラクターとデストラクターの呼び出しに応答がします。 Windows*ウィンドウ*、一方で、非透過ハンドルをウィンドウに対応し、存在する場合、システム リソースを消費する、Windows 内部データ構造には、します。 Windows ウィンドウは、「ウィンドウ ハンドル」によって識別されます (`HWND`) 後に作成し、`CWnd`への呼び出しによってオブジェクトが作成された、`Create`クラスのメンバー関数`CWnd`します。 プログラムの呼び出しまたはユーザーの操作のいずれか、ウィンドウを破壊する可能性があります。 ウィンドウ オブジェクトのウィンドウ ハンドルが格納されている*m_hWnd*メンバー変数。 次の図は、C++ ウィンドウ オブジェクトと、Windows のウィンドウ間のリレーションシップを示します。 ウィンドウの作成については[作成 Windows](../mfc/creating-windows.md)します。 ウィンドウの破棄、後ほど[ウィンドウ オブジェクトの破棄](../mfc/destroying-window-objects.md)します。

![CWnd ウィンドウ オブジェクトとウィンドウの結果として得られる](../mfc/media/vc37fj1.gif "vc37fj1")ウィンドウ オブジェクトと Windows ウィンドウ

## <a name="see-also"></a>関連項目

[Window オブジェクト](../mfc/window-objects.md)

