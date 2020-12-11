---
description: 詳細については、「フレームウィンドウでのファイルのドラッグアンドドロップ」を参照してください。
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
ms.openlocfilehash: dafbeca8b74ee07c80315c15ab93097977125d89
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159948"
---
# <a name="dragging-and-dropping-files-in-a-frame-window"></a>ファイルのフレーム ウィンドウへのドラッグ アンド ドロップ

フレームウィンドウは、エクスプローラーまたはファイルマネージャーとの関係を管理します。

「CWinApp: Application クラス」で説明されているように、メンバー関数のオーバーライドでいくつかの初期化呼び出しを追加することにより、 `CWinApp` `InitInstance` フレームウィンドウでファイルエクスプローラーまたはファイルマネージャーからドラッグしてフレームウィンドウにドロップしたファイルを間接的に開くことができます。 [](cwinapp-the-application-class.md) 「 [ファイルマネージャーのドラッグアンドドロップ」を](special-cwinapp-services.md)参照してください。

## <a name="see-also"></a>関連項目

[フレームウィンドウの使用](using-frame-windows.md)
