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
ms.openlocfilehash: c5beed5618d4fa991160ad1688a5a686aeaa842f
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84626365"
---
# <a name="initializing-and-cleaning-up-documents-and-views"></a>ドキュメントとビューの初期化と後処理

ドキュメントとビューの初期化とクリーンアップには、次のガイドラインを使用します。

- MFC フレームワークは、ドキュメントとビューを初期化します。追加したすべてのデータを初期化します。

- フレームワークはドキュメントとビューを閉じるとクリーンアップされます。これらのドキュメントとビューのメンバー関数内から、ヒープに割り当てられたメモリの割り当てを解除する必要があります。

> [!NOTE]
> クラスの[InitInstance](reference/cwinapp-class.md#initinstance)メンバー関数をオーバーライドする場合は、アプリケーション全体の初期化を行うことをお勧め `CWinApp` します。また、アプリケーション全体のクリーンアップは、 `CWinApp` メンバー関数[exitinstance](reference/cwinapp-class.md#exitinstance)のオーバーライドで実行することをお勧めします。

MDI アプリケーションのドキュメント (およびそのフレームウィンドウとビューまたはビュー) のライフサイクルは次のとおりです。

1. 動的作成中に、ドキュメントコンストラクターが呼び出されます。

1. 新しいドキュメントごとに、ドキュメントの[OnNewDocument](reference/cdocument-class.md#onnewdocument)または[onopendocument](reference/cdocument-class.md#onopendocument)が呼び出されます。

1. ユーザーは、その有効期間全体にわたってドキュメントを操作します。 通常、これは、ユーザーがビューを介してドキュメントデータを操作し、データを選択して編集すると発生します。 ビューは、ストレージの変更と他のビューの更新をドキュメントに渡します。 この期間中は、ドキュメントとビューの両方でコマンドが処理される可能性があります。

1. フレームワークは、 [DeleteContents](reference/cdocument-class.md#deletecontents)を呼び出して、ドキュメントに固有のデータを削除します。

1. ドキュメントのデストラクターが呼び出されます。

SDI アプリケーションでは、ドキュメントが最初に作成されたときにステップ1が1回実行されます。 次に、新しいドキュメントが開かれるたびに、手順 2. ~ 4. が繰り返し実行されます。 新しいドキュメントは、既存のドキュメントオブジェクトを再利用します。 最後に、手順5は、アプリケーションの終了時に実行されます。

## <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [ドキュメントとビューの初期化](initializing-documents-and-views.md)

- [ドキュメントとビューの後処理](cleaning-up-documents-and-views.md)

## <a name="see-also"></a>関連項目

[ドキュメント/ビューアーキテクチャ](document-view-architecture.md)
