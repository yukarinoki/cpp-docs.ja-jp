---
title: ドキュメントとビューの初期化と後処理
ms.date: 11/04/2016
helpviewer_keywords:
- initializing documents [MFC]
- views [MFC], cleaning up
- documents [MFC], initializing
- documents [MFC], cleaning up
- views [MFC], initializing
- initializing objects [MFC], document objects
- document objects [MFC], life cycle of
- initializing views [MFC]
ms.assetid: 95d6f09b-a047-4079-856a-ae7d0548e9d2
ms.openlocfilehash: 3c92d60941cd6542bd0d6c27e8a879dc85e3a3d6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377201"
---
# <a name="initializing-and-cleaning-up-documents-and-views"></a>ドキュメントとビューの初期化と後処理

ドキュメントとビューの後の初期化とクリーンアップについては、次のガイドラインに従います。

- MFC フレームワークはドキュメントとビューを初期化します。追加するデータは初期化します。

- フレームワークは、ドキュメントとビューが閉じるとクリーンアップします。これらのドキュメントとビューのメンバー関数内から、ヒープに割り当てたメモリを割り当て解除する必要があります。

> [!NOTE]
> アプリケーション全体の初期化は、 クラス`CWinApp`の`CWinApp`[InitInstance](../mfc/reference/cwinapp-class.md#initinstance)メンバー関数のオーバーライドで行うのが最善であり、アプリケーション全体のクリーンアップは、メンバー関数[ExitInstance](../mfc/reference/cwinapp-class.md#exitinstance)のオーバーライドで行うのが最善です。

MDI アプリケーションでのドキュメント (およびそのフレーム ウィンドウ、ビュー、ビュー) のライフ サイクルは次のとおりです。

1. 動的な作成時に、ドキュメント コンストラクターが呼び出されます。

1. 新しいドキュメントごとに、ドキュメントの[OnNewDocument](../mfc/reference/cdocument-class.md#onnewdocument)または[OnOpenDocument](../mfc/reference/cdocument-class.md#onopendocument)が呼び出されます。

1. ユーザーは、ドキュメントの有効期間中にドキュメントを操作します。 通常、この問題は、ユーザーがビューを通じてドキュメント データを操作し、データを選択および編集するときに発生します。 ビューは、ドキュメントに変更を渡して、他のビューを保存および更新します。 この間、ドキュメントとビューの両方がコマンドを処理する場合があります。

1. フレームワークは、ドキュメントに固有のデータを削除する[DeleteContents](../mfc/reference/cdocument-class.md#deletecontents)を呼び出します。

1. ドキュメントのデストラクターが呼び出されます。

SDI アプリケーションでは、ドキュメントが最初に作成されるときに、手順 1 が 1 回実行されます。 次に、手順 2 ~ 4 は、新しいドキュメントを開くたびに繰り返し実行されます。 新しいドキュメントは、既存のドキュメント オブジェクトを再利用します。 最後に、アプリケーションが終了したときにステップ 5 が実行されます。

## <a name="what-do-you-want-to-know-more-about"></a>何についてもっと知りたいのですか?

- [ドキュメントとビューの初期化](../mfc/initializing-documents-and-views.md)

- [ドキュメントとビューの後処理](../mfc/cleaning-up-documents-and-views.md)

## <a name="see-also"></a>関連項目

[ドキュメント/ビュー アーキテクチャ](../mfc/document-view-architecture.md)
