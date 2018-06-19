---
title: C++ ウィンドウ オブジェクトと HWND の関係 |Microsoft ドキュメント
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
ms.openlocfilehash: b51daa375c3c920443316b6e10b6415ee018fdb4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33385779"
---
# <a name="relationship-between-a-c-window-object-and-an-hwnd"></a>C++ ウィンドウ オブジェクトと HWND の関係
ウィンドウ*オブジェクト*の C++ オブジェクトである`CWnd`クラス (または派生クラス)、プログラムを直接作成します。 プログラムのコンス トラクターとデストラクターの呼び出しに対する応答にします。 Windows*ウィンドウ*、不透明ハンドルをウィンドウに対応し、存在する場合、システム リソースを消費する、Windows 内部データ構造には、その一方で、します。 Windows のウィンドウは、「ウィンドウ ハンドル」によって識別される (`HWND`) 後に作成し、`CWnd`オブジェクトへの呼び出しによって作成されて、**作成**クラスのメンバー関数`CWnd`です。 プログラムの呼び出しまたはユーザーの操作のいずれか、ウィンドウを破壊する可能性があります。 ウィンドウ オブジェクトに使用するウィンドウ ハンドルが格納されている`m_hWnd`メンバー変数。 次の図は、C++ ウィンドウ オブジェクトと、Windows の期間の関係を示しています。 ウィンドウの作成は、後ほど[ウィンドウの作成](../mfc/creating-windows.md)です。 ウィンドウの破棄は、後ほど[ウィンドウ オブジェクトの破棄](../mfc/destroying-window-objects.md)です。  
  
 ![CWnd ウィンドウ オブジェクトと表示されるウィンドウ](../mfc/media/vc37fj1.gif "vc37fj1")  
ウィンドウ オブジェクトと Windows のウィンドウ  
  
## <a name="see-also"></a>関連項目  
 [Window オブジェクト](../mfc/window-objects.md)

