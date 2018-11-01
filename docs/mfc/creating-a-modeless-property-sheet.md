---
title: モードレス プロパティ シートの作成
ms.date: 11/04/2016
helpviewer_keywords:
- modeless property sheets
- property sheets, modeless
- Create method [MFC], property sheets
ms.assetid: eafd8a92-cc67-4a69-a5fb-742c920d1ae8
ms.openlocfilehash: 9012700ef145079cf01ee1eac1cee58449ab5b79
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50524901"
---
# <a name="creating-a-modeless-property-sheet"></a>モードレス プロパティ シートの作成

通常、作成するプロパティ シートは、モーダルになります。 モーダル プロパティ シートを使用する場合は、アプリケーションの他の部分を使用する前に、プロパティ シートを閉じる必要があります。 この記事では、ユーザーがアプリケーションの他の部分を使用しているときに、プロパティ シートを開いたままにできるモードレス プロパティ シートの作成に使用できる方法について説明します。

プロパティ シートの代わりに、モーダル ダイアログ ボックスとモードレス ダイアログ ボックスとして表示するに[CPropertySheet::Create](../mfc/reference/cpropertysheet-class.md#create)の代わりに[DoModal](../mfc/reference/cpropertysheet-class.md#domodal)します。 モードレス プロパティ シートをサポートするためにいくつか追加のタスクを実装することも必要があります。

プロパティ シートとプロパティ シートが開いているときに変更される外部のオブジェクトの間のデータを交換、追加のタスクのいずれかです。 これは、一般に、標準のモードレス ダイアログ ボックスの場合と同じタスクです。 このタスクの一部のモードレス プロパティ シートとプロパティの設定を適用する外部のオブジェクト間の通信チャネルの実装です。 この実装はからクラスを派生させる場合に、はるかに簡単な[CPropertySheet](../mfc/reference/cpropertysheet-class.md)モードレス プロパティ シートの。 この記事では、同意している前提としています。

モードレス プロパティ シートと外部の間の通信に 1 つのメソッド、プロパティ シートから外部のオブジェクトへのポインターを定義するオブジェクト (たとえば、ビューの現在の選択) ことです。 関数の定義 (ような`SetMyExternalObject`) で、 `CPropertySheet`-別に 1 つの外部オブジェクトから、フォーカスが変更されるたびにポインターを変更するクラスを派生します。 `SetMyExternalObject`関数は、新しく選択した外部オブジェクトを反映するように各プロパティ ページの設定をリセットする必要があります。 これを実現する、`SetMyExternalObject`関数は、アクセスできる必要があります、 [CPropertyPage](../mfc/reference/cpropertypage-class.md)オブジェクトに属する、`CPropertySheet`クラス。

プロパティ シート内のプロパティ ページへのアクセスを提供する最も簡単な方法を埋め込むには、`CPropertyPage`内のオブジェクト、 `CPropertySheet`-派生オブジェクト。 埋め込み`CPropertyPage`内のオブジェクト、 `CPropertySheet`-派生オブジェクトはモーダル ダイアログ ボックスで、プロパティ シートの所有者を作成する、一般的なデザインとは異なる、`CPropertyPage`オブジェクトを使用して、プロパティ シートに渡す、 [CPropertySheet::AddPage](../mfc/reference/cpropertysheet-class.md#addpage)です。

モードレス プロパティ シートの設定を外部オブジェクトに適用するときに決定する多くのユーザー インターフェイスの代替案がないです。 代わりに 1 つでは、ユーザーが任意の値を変更するたびに現在のプロパティ ページの設定を適用します。 別の方法として、ユーザーが外部オブジェクトにそれらをコミットする前にプロパティ ページでの変更を蓄積する [適用] ボタンを提供することです。 [適用] ボタンを処理する方法については、記事を参照してください。[適用ボタンの処理](../mfc/handling-the-apply-button.md)です。

## <a name="see-also"></a>関連項目

[プロパティ シート](../mfc/property-sheets-mfc.md)<br/>
[データの交換](../mfc/exchanging-data.md)<br/>
[ダイアログ ボックスの有効期間](../mfc/life-cycle-of-a-dialog-box.md)

