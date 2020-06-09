---
title: 印刷
ms.date: 11/04/2016
helpviewer_keywords:
- view classes [MFC], print operations
- documents [MFC], printing
- printing [MFC], from framework
- printing [MFC]
ms.assetid: be465e8d-b0c9-4fc5-9fa8-d10486064f76
ms.openlocfilehash: 3d2ef494be66171cbcbf2b8b9e19c29c8bdc5c2f
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619801"
---
# <a name="printing"></a>印刷

Microsoft Windows では、デバイスに依存しないディスプレイを実装しています。 MFC では、これは、 `OnDraw` ビュークラスのメンバー関数内の同じ描画呼び出しが、ディスプレイや、プリンターなどの他のデバイス上での描画を担当することを意味します。 印刷プレビューの場合、ターゲットデバイスは、シミュレートされたプリンター出力をディスプレイに出力します。

## <a name="your-role-in-printing-vs-the-frameworks-role"></a><a name="_core_your_role_in_printing_vs.._the_framework.92.s_role"></a>印刷におけるロールとフレームワークのロール

ビュークラスには、次の役割があります。

- ドキュメント内のページ数をフレームワークに通知します。

- 指定したページを印刷するように求められたら、文書のその部分を描画します。

- 印刷に必要なフォントまたはその他のグラフィックスデバイスインターフェイス (GDI) リソースを割り当て、割り当てを解除します。

- 必要に応じて、ページごとに印刷の向きを変更するなど、特定のページを印刷する前に、プリンターモードを変更するために必要なすべてのエスケープコードを送信します。

このフレームワークの役割は次のとおりです。

- [**印刷**] ダイアログボックスを表示します。

- プリンターの[CDC](reference/cdc-class.md)オブジェクトを作成します。

- オブジェクトの[StartDoc](reference/cdc-class.md#startdoc)および[EndDoc](reference/cdc-class.md#enddoc)メンバー関数を呼び出し `CDC` ます。

- オブジェクトの[StartPage](reference/cdc-class.md#startpage)メンバー関数を繰り返し呼び出し `CDC` 、出力するページをビュークラスに通知し、オブジェクトの[EndPage](reference/cdc-class.md#endpage)メンバー関数を呼び出し `CDC` ます。

- ビュー内のオーバーライド可能な関数を適切なタイミングで呼び出します。

次の記事では、フレームワークが印刷と印刷プレビューをサポートする方法について説明します。

### <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [既定の印刷方法](how-default-printing-is-done.md)

- [マルチページドキュメント](multipage-documents.md)

- [ヘッダーとフッター](headers-and-footers.md)

- [印刷用の GDI リソースの割り当て](allocating-gdi-resources.md)

- [印刷プレビュー](print-preview-architecture.md)

## <a name="see-also"></a>関連項目

[[印刷と印刷プレビュー]](printing-and-print-preview.md)
