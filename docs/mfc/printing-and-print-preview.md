---
title: 印刷および印刷プレビュー
ms.date: 11/04/2016
helpviewer_keywords:
- printing [MFC]
- previewing printing
- printing [MFC]
- print preview
- printing [MFC], print preview
ms.assetid: d15059cd-32de-4450-95f7-e73aece238f6
ms.openlocfilehash: 26ced8172a36d34883d6b65997bb3a81fdc3c319
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84625271"
---
# <a name="printing-and-print-preview"></a>印刷および印刷プレビュー

MFC では、 [CView](reference/cview-class.md)クラスを使用して、プログラムのドキュメントの印刷と印刷プレビューをサポートしています。 基本的な印刷と印刷プレビューの場合は、ビュークラスの[OnDraw](reference/cview-class.md#ondraw)メンバー関数をオーバーライドするだけです。この操作を行う必要があります。 この関数は、画面上のビュー、実際のプリンターのプリンターデバイスコンテキスト、または画面上でプリンターをシミュレートするデバイスコンテキストに描画できます。

また、複数ページにわたるドキュメントの印刷とプレビューを管理したり、印刷したドキュメントの改ページを調整したり、ヘッダーとフッターを追加したりするコードを追加することもできます。

この一連の記事では、Microsoft Foundation Class ライブラリ (MFC) での印刷の実装方法と、フレームワークに既に組み込まれている印刷アーキテクチャを活用する方法について説明します。 また、この記事では、MFC で印刷プレビュー機能を簡単に実装する方法と、その機能を使用および変更する方法についても説明しています。

## <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [印刷](printing.md)

- [印刷プレビューのアーキテクチャ](print-preview-architecture.md)

- [サンプル](../overview/visual-cpp-samples.md)

## <a name="see-also"></a>関連項目

[ユーザーインターフェイス要素](user-interface-elements-mfc.md)
