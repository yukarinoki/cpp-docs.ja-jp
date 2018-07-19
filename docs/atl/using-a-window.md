---
title: ウィンドウ (ATL) を使用して |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ATL, windows
- CWindow class, about CWindow class
- windows [C++], ATL
ms.assetid: b3b9cc8e-4287-486b-b080-38852bc2943a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 44b9988c0ecde4d0aee917fea686ec6511473318
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/05/2018
ms.locfileid: "37847925"
---
# <a name="using-a-window"></a>ウィンドウを使用します。
クラス[CWindow](../atl/reference/cwindow-class.md)ウィンドウを使用することができます。 ウィンドウをアタッチした後、`CWindow`を呼び出して、オブジェクト`CWindow`ウィンドウを操作するメソッド。 `CWindow` 変換する HWND 演算子も含む、 `CWindow` HWND するオブジェクト。 そのために渡すことができます、`CWindow`ウィンドウのハンドルを必要とするすべての関数オブジェクト。 簡単に組み合わせることができます`CWindow`メソッドの呼び出しと、一時オブジェクトを作成せず、Win32 関数の呼び出し。  
  
 `CWindow`が 2 つだけのデータ メンバー (ウィンドウ ハンドルと既定のサイズ)、コードのオーバーヘッドを強制しません。 さらに、多くの`CWindow`メソッドは単に対応する Win32 API 関数をラップします。 使用して`CWindow`HWND のメンバーが自動的に Win32 関数に渡されます。  
  
 使用するだけでなく`CWindow`クラスにデータやコードを追加してから派生できますも、直接します。 ATL 自体から 3 つのクラスを派生する`CWindow`: [CWindowImpl](../atl/implementing-a-window.md)、 [CDialogImpl](../atl/implementing-a-dialog-box.md)、および[CContainedWindowT](../atl/using-contained-windows.md)します。  
  
## <a name="see-also"></a>関連項目  
 [ウィンドウ クラス](../atl/atl-window-classes.md)

