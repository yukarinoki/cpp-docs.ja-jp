---
title: ファイルのフレーム ウィンドウへのドラッグ アンド ドロップ
ms.date: 11/04/2016
helpviewer_keywords:
- drag and drop [MFC], files
- drag and drop [MFC], File Manager
- Windows Explorer [MFC]
- File Manager drag and drop support [MFC]
- files [MFC], drag and drop
- frame windows [MFC], dragging and dropping files in
- drag and drop [MFC], Windows Explorer
ms.assetid: 85560fe9-121b-4105-bd7b-216b966e19fa
ms.openlocfilehash: 42f21e2441f8ba3d2c6a13503c928880fe100f04
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84623156"
---
# <a name="dragging-and-dropping-files-in-a-frame-window"></a>ファイルのフレーム ウィンドウへのドラッグ アンド ドロップ

フレームウィンドウは、エクスプローラーまたはファイルマネージャーとの関係を管理します。

「CWinApp: Application クラス」で説明されているように、メンバー関数のオーバーライドでいくつかの初期化呼び出しを追加することにより、 `CWinApp` `InitInstance` フレームウィンドウでファイルエクスプローラーまたはファイルマネージャーからドラッグしてフレームウィンドウにドロップしたファイルを間接的に開くことができます。 [CWinApp: The Application Class](cwinapp-the-application-class.md) 「[ファイルマネージャーのドラッグアンドドロップ」を](special-cwinapp-services.md)参照してください。

## <a name="see-also"></a>関連項目

[フレームウィンドウの使用](using-frame-windows.md)
