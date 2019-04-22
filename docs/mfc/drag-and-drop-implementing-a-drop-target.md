---
title: ドラッグ アンド ドロップします。ドロップ ターゲットの実装
ms.date: 11/04/2016
helpviewer_keywords:
- OLE drag and drop [MFC], implementing drop targets
- OLE drag and drop [MFC], drop target
- drag and drop [MFC], drop target
ms.assetid: 0689f1ec-5326-4008-b226-4b373c881358
ms.openlocfilehash: 46501193569d7f3098e23c67c68c76ce20a82ea3
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "58766678"
---
# <a name="drag-and-drop-implementing-a-drop-target"></a>ドラッグ アンド ドロップします。ドロップ ターゲットの実装

この記事では、ドロップ先のアプリケーションを作成する方法について説明します。 ドロップ ソースを実装するよりも少し多い作業を受け取るドロップ ターゲットの実装が、それでも比較的簡単です。 これらの手法は、非 OLE アプリケーションにも適用されます。

#### <a name="to-implement-a-drop-target"></a>ドロップ先を実装するには

1. ドロップ ターゲットにアプリケーションでは、各ビューには、メンバー変数を追加します。 このメンバー変数は、型でなければなりません`COleDropTarget`またはその派生クラス。

1. 処理するビュー クラスの関数から、 **WM_CREATE**メッセージ (通常`OnCreate`)、新しいメンバー変数を呼び出す`Register`メンバー関数。 `Revoke` 呼び出されます自動的に、ビューが破棄されるときにします。

1. 次の関数をオーバーライドします。 アプリケーション全体で同じ動作をする場合は、ビュー クラスでこれらの関数をオーバーライドします。 特殊なケースでの動作を変更または以外の削除を有効にする場合`CView`、windows でこれらの関数のオーバーライド、 `COleDropTarget`-クラスを派生します。

    |オーバーライド|許可するには|
    |--------------|--------------|
    |`OnDragEnter`|ウィンドウで発生する操作を削除します。 カーソルが最初に、ウィンドウに入ったときに呼び出されます。|
    |`OnDragLeave`|ドラッグ操作が指定したウィンドウを離れるときの特別な動作はします。|
    |`OnDragOver`|ウィンドウで発生する操作を削除します。 カーソルがウィンドウ全体でドラッグされているときに呼び出されます。|
    |`OnDrop`|指定したウィンドウにドロップされたデータを処理します。|
    |`OnScrollBy`|スクロールが必要な場合、ターゲット ウィンドウでの特殊な動作はします。|

MAINVIEW を参照してください。MFC OLE サンプルの一部を CPP ファイル[OCLIENT](../overview/visual-cpp-samples.md)これらの関数の動作の例についてはします。

詳細については次を参照してください:

- [ドロップ ソースの実装](../mfc/drag-and-drop-implementing-a-drop-source.md)

- [作成と破棄 OLE データ オブジェクトとデータ ソース](../mfc/data-objects-and-data-sources-creation-and-destruction.md)

- [OLE データ オブジェクトとデータ ソースを操作します。](../mfc/data-objects-and-data-sources-manipulation.md)

## <a name="see-also"></a>関連項目

[ドラッグ アンド ドロップ (OLE)](../mfc/drag-and-drop-ole.md)<br/>
[COleDropTarget クラス](../mfc/reference/coledroptarget-class.md)
