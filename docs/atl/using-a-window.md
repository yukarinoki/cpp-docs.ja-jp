---
description: 詳細については、「ウィンドウの使用」を参照してください。
title: ウィンドウの使用 (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, windows
- CWindow class, about CWindow class
- windows [C++], ATL
ms.assetid: b3b9cc8e-4287-486b-b080-38852bc2943a
ms.openlocfilehash: fb9f1e03a27ad8b637da30eacbd100daf920cdb4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157281"
---
# <a name="using-a-window"></a>ウィンドウの使用

[CWindow](../atl/reference/cwindow-class.md)クラスを使用すると、ウィンドウを使用できます。 ウィンドウをオブジェクトにアタッチすると `CWindow` 、そのウィンドウを操作するメソッドを呼び出すことができ `CWindow` ます。 `CWindow` には、オブジェクトを HWND に変換する HWND 演算子も含まれてい `CWindow` ます。 したがって、ウィンドウへのハンドルを必要とする任意の関数にオブジェクトを渡すことができ `CWindow` ます。 `CWindow`一時オブジェクトを作成せずに、メソッド呼び出しと Win32 関数呼び出しを簡単に混在させることができます。

`CWindow`には2つのデータメンバー (ウィンドウハンドルと既定のディメンション) しかないため、コードのオーバーヘッドは発生しません。 また、メソッドの多くは、 `CWindow` 対応する Win32 API 関数をラップするだけです。 を使用する `CWindow` と、HWND メンバーが Win32 関数に自動的に渡されます。

直接を使用するだけで `CWindow` なく、それから派生させて、データやコードをクラスに追加することもできます。 ATL 自体 `CWindow` は、 [CWindowImpl](../atl/implementing-a-window.md)、 [CDialogImpl](../atl/implementing-a-dialog-box.md)、および [CContainedWindowT](../atl/using-contained-windows.md)の3つのクラスを派生しています。

## <a name="see-also"></a>関連項目

[ウィンドウクラス](../atl/atl-window-classes.md)
