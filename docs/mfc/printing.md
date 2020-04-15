---
title: 印刷
ms.date: 11/04/2016
helpviewer_keywords:
- view classes [MFC], print operations
- documents [MFC], printing
- printing [MFC], from framework
- printing [MFC]
ms.assetid: be465e8d-b0c9-4fc5-9fa8-d10486064f76
ms.openlocfilehash: a46096592c9983d04d2122bfabb56ece9346c4bc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371202"
---
# <a name="printing"></a>印刷

デバイスに依存しないディスプレイが実装されています。 MFC では、ビュー クラスの`OnDraw`メンバー関数で同じ描画呼び出しが、ディスプレイ上およびプリンターなどの他のデバイス上で描画する必要があることを意味します。 印刷プレビューの場合、ターゲット デバイスは、ディスプレイへのプリンター出力をシミュレートします。

## <a name="your-role-in-printing-vs-the-frameworks-role"></a><a name="_core_your_role_in_printing_vs.._the_framework.92.s_role"></a>印刷におけるあなたの役割とフレームワークの役割

ビュー クラスには、次の責任があります。

- ドキュメント内のページ数をフレームワークに通知します。

- 指定したページを印刷するように求められたら、その部分を文書に描画します。

- 印刷に必要なフォントやその他のグラフィックス デバイス インターフェイス (GDI) リソースを割り当て、割り当て解除します。

- 必要に応じて、特定のページを印刷する前に、プリンタ モードを変更するために必要なエスケープ コードを送信します。

フレームワークの責任は次のとおりです。

- **[印刷**] ダイアログ ボックスを表示します。

- プリンタの[CDC](../mfc/reference/cdc-class.md)オブジェクトを作成します。

- オブジェクトの[開始Doc](../mfc/reference/cdc-class.md#startdoc)および[EndDoc](../mfc/reference/cdc-class.md#enddoc)メンバー`CDC`関数を呼び出します。

- オブジェクトの[StartPage](../mfc/reference/cdc-class.md#startpage)メンバー関数を繰り返し呼び出し、印刷するページをビュー クラスに通知し、オブジェクトの`CDC` [EndPage](../mfc/reference/cdc-class.md#endpage)メンバー関数を呼び出します。 `CDC`

- ビュー内でオーバーライド可能な関数を適切な時間に呼び出します。

次の記事では、フレームワークが印刷プレビューと印刷プレビューをサポートする方法について説明します。

### <a name="what-do-you-want-to-know-more-about"></a>何についてもっと知りたいのですか?

- [既定の印刷の実行方法](../mfc/how-default-printing-is-done.md)

- [複数ページのドキュメント](../mfc/multipage-documents.md)

- [ヘッダーとフッター](../mfc/headers-and-footers.md)

- [印刷用の GDI リソースの割り当て](../mfc/allocating-gdi-resources.md)

- [印刷プレビュー](../mfc/print-preview-architecture.md)

## <a name="see-also"></a>関連項目

[[印刷と印刷プレビュー]](../mfc/printing-and-print-preview.md)
