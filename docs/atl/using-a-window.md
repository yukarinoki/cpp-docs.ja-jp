---
title: ウィンドウ (ATL) を使用して |Microsoft ドキュメント
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
ms.openlocfilehash: f946f99fd198db281418e2a471489b2236972435
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32358395"
---
# <a name="using-a-window"></a>ウィンドウを使用します。
クラス[CWindow](../atl/reference/cwindow-class.md)ウィンドウを使用することができます。 ウィンドウをアタッチすると、`CWindow`オブジェクトを呼び出すことができますし、`CWindow`ウィンドウを操作するメソッド。 `CWindow` 含まれています、`HWND`に変換する演算子、`CWindow`オブジェクトを`HWND`です。 そのために渡すことができます、`CWindow`ウィンドウへのハンドルを必要とするすべての関数オブジェクト。 簡単に組み合わせることができます`CWindow`メソッド呼び出しと、一時オブジェクトを作成しなくても、Win32 関数の呼び出しです。  
  
 `CWindow`のみに 2 つのデータ メンバーを持ちます (ウィンドウ ハンドルと既定のサイズ)、コードのオーバーヘッドは必要ありません。 さらに、多くの`CWindow`メソッドは、単純に対応する Win32 API 関数をラップします。 使用して`CWindow`、`HWND`メンバーが自動的に Win32 関数に渡されます。  
  
 使用するだけでなく`CWindow`を直接ことができますもから派生したクラスにデータやコードを追加します。 ATL 自体から 3 つのクラスを派生する`CWindow`: [CWindowImpl](../atl/implementing-a-window.md)、 [CDialogImpl](../atl/implementing-a-dialog-box.md)、および[CContainedWindowT](../atl/using-contained-windows.md)です。  
  
## <a name="see-also"></a>関連項目  
 [ウィンドウ クラス](../atl/atl-window-classes.md)

