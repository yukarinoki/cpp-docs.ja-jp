---
title: ドラッグして、フレーム ウィンドウ内のファイルの削除 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- drag and drop [MFC], files
- drag and drop [MFC], File Manager
- Windows Explorer [MFC]
- File Manager drag and drop support [MFC]
- files [MFC], drag and drop
- frame windows [MFC], dragging and dropping files in
- drag and drop [MFC], Windows Explorer
ms.assetid: 85560fe9-121b-4105-bd7b-216b966e19fa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6fc68923de531240a2d59336c79e54f6562b369c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46380530"
---
# <a name="dragging-and-dropping-files-in-a-frame-window"></a>ファイルのフレーム ウィンドウへのドラッグ アンド ドロップ

フレーム ウィンドウは、ファイル エクスプ ローラーまたはファイル マネージャーとの関係を管理します。

オーバーライドで呼び出し、いくつかの初期化を追加、`CWinApp`メンバー関数は`InitInstance`」の説明に従って、 [CWinApp: アプリケーション クラス](../mfc/cwinapp-the-application-class.md)、ファイルからドラッグされたファイルを直接開く、フレーム ウィンドウは使用できますエクスプ ローラーまたはファイル マネージャーと、フレーム ウィンドウにドロップします。 参照してください[ファイル マネージャーでのドラッグ アンド ドロップ](../mfc/special-cwinapp-services.md)します。

## <a name="see-also"></a>関連項目

[フレーム ウィンドウの使用](../mfc/using-frame-windows.md)

