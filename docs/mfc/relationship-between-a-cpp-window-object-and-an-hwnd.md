---
title: C++ ウィンドウ オブジェクトと HWND 間のリレーションシップ |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- HWND
dev_langs:
- C++
helpviewer_keywords:
- Windows window [MFC]
- window objects [MFC], HWND and
- HWND [MFC]
- CWnd class [MFC], HWND
- HWND, window objects [MFC]
ms.assetid: f2e76340-6691-4ee6-9424-0345634a9469
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 844f62b110f54ba3e2c8909a78d58c9f2c01dcac
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46392815"
---
# <a name="relationship-between-a-c-window-object-and-an-hwnd"></a>C++ ウィンドウ オブジェクトと HWND の関係

ウィンドウ*オブジェクト*、C++ のオブジェクトである`CWnd`クラス (または派生クラス)、プログラムを直接作成します。 付属し、プログラムのコンス トラクターとデストラクターの呼び出しに応答がします。 Windows*ウィンドウ*、一方で、非透過ハンドルをウィンドウに対応し、存在する場合、システム リソースを消費する、Windows 内部データ構造には、します。 Windows ウィンドウは、「ウィンドウ ハンドル」によって識別されます (`HWND`) 後に作成し、`CWnd`への呼び出しによってオブジェクトが作成された、`Create`クラスのメンバー関数`CWnd`します。 プログラムの呼び出しまたはユーザーの操作のいずれか、ウィンドウを破壊する可能性があります。 ウィンドウ オブジェクトのウィンドウ ハンドルが格納されている*m_hWnd*メンバー変数。 次の図は、C++ ウィンドウ オブジェクトと、Windows のウィンドウ間のリレーションシップを示します。 ウィンドウの作成については[作成 Windows](../mfc/creating-windows.md)します。 ウィンドウの破棄、後ほど[ウィンドウ オブジェクトの破棄](../mfc/destroying-window-objects.md)します。

![CWnd ウィンドウ オブジェクトとウィンドウの結果として得られる](../mfc/media/vc37fj1.gif "vc37fj1")ウィンドウ オブジェクトと Windows ウィンドウ

## <a name="see-also"></a>関連項目

[Window オブジェクト](../mfc/window-objects.md)

