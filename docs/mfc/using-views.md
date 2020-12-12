---
description: '詳細情報: ビューの使用'
title: ビューの使い方
ms.date: 11/04/2016
helpviewer_keywords:
- interacting with users and role of view class [MFC]
- drawing [MFC], data
- rendering data
- view classes [MFC], role in managing user interaction
- CView class [MFC], view architecture
- MFC, views
- views [MFC], using
- painting data
- user input [MFC], interpreting through view class [MFC]
- view classes [MFC], role in displaying application data
ms.assetid: dc3de6ad-5c64-4317-8f10-8bdcc38cdbd5
ms.openlocfilehash: f17855c1389da44630a21830033c4457db6e3703
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97236647"
---
# <a name="using-views"></a>ビューの使い方

ビューの役割は、ドキュメントのデータをユーザーにグラフィカルに表示し、ドキュメントに対する操作としてユーザー入力を受け入れて解釈することです。 ビュークラスを記述するためのタスクは次のとおりです。

- ドキュメントのデータを表示する、ビュークラスの [OnDraw](../mfc/reference/cview-class.md#ondraw) メンバー関数を記述します。

- 適切な Windows メッセージと、メニュー項目などのユーザーインターフェイスオブジェクトを、ビュークラスのメッセージハンドラーメンバー関数に接続します。

- これらのハンドラーを実装して、ユーザー入力を解釈します。

また、派生ビュークラスの他のメンバー関数をオーバーライドする必要がある場合もあり `CView` ます。 特に、ビューの特別な初期化を実行し、ビューがそれ自体を再描画する直前に必要な特別な処理を行うために、 [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) をオーバーライドすることをお [勧めします](../mfc/reference/cview-class.md#onupdate) 。 マルチページドキュメントの場合は、 [OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting) をオーバーライドして、印刷するページ数とその他の情報を含む [印刷] ダイアログボックスを初期化する必要もあります。 オーバーライドするメンバー関数の詳細につい `CView` ては、 *MFC リファレンス* の「 [CView](../mfc/reference/cview-class.md)クラス」を参照してください。

## <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [MFC で使用できる派生ビュー クラス](../mfc/derived-view-classes-available-in-mfc.md)

- [ビューの描画](../mfc/drawing-in-a-view.md)

- [ビューを使用したユーザー入力の解釈](../mfc/interpreting-user-input-through-a-view.md)

- [印刷でのビューの役割](../mfc/role-of-the-view-in-printing.md)

- [ビューのスクロールと拡大/縮小](../mfc/scrolling-and-scaling-views.md)

- [ドキュメントとビューの初期化と後処理](../mfc/initializing-and-cleaning-up-documents-and-views.md)

## <a name="see-also"></a>関連項目

[ドキュメント/ビューアーキテクチャ](../mfc/document-view-architecture.md)<br/>
[CFormView クラス](../mfc/reference/cformview-class.md)<br/>
[レコードビュー (MFC データアクセス)](../data/record-views-mfc-data-access.md)<br/>
[シリアル化機構のバイパス](../mfc/bypassing-the-serialization-mechanism.md)
