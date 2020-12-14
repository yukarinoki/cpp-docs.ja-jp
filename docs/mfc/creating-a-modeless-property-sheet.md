---
description: '詳細情報: モードレスプロパティシートの作成'
title: モードレス プロパティ シートの作成
ms.date: 11/04/2016
helpviewer_keywords:
- modeless property sheets
- property sheets, modeless
- Create method [MFC], property sheets
ms.assetid: eafd8a92-cc67-4a69-a5fb-742c920d1ae8
ms.openlocfilehash: 1eaec55fe3c7c69ba558a10616dc2658025282d0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97310058"
---
# <a name="creating-a-modeless-property-sheet"></a>モードレス プロパティ シートの作成

通常、作成するプロパティシートはモーダルになります。 モーダルプロパティシートを使用する場合、ユーザーはアプリケーションの他の部分を使用する前に、プロパティシートを閉じる必要があります。 この記事では、アプリケーションの他の部分を使用しているときに、ユーザーがプロパティシートを開いたままにできるようにするモードレスプロパティシートの作成に使用できるメソッドについて説明します。

モーダルダイアログボックスとしてではなく、モードレスダイアログボックスとしてプロパティシートを表示するには、 [DoModal](reference/cpropertysheet-class.md#domodal)ではなく[CPropertySheet:: Create](reference/cpropertysheet-class.md#create)を呼び出します。 また、モードレスプロパティシートをサポートするために、いくつかの追加タスクを実装する必要があります。

追加のタスクの1つとして、プロパティシートとプロパティシートが開いているときに変更する外部オブジェクトとの間でデータを交換することがあります。 これは、通常、標準のモードレスダイアログボックスの場合と同じタスクです。 このタスクの一部は、モードレスプロパティシートと、プロパティ設定が適用される外部オブジェクトとの間の通信チャネルを実装することです。 モードレスプロパティシートの [CPropertySheet](reference/cpropertysheet-class.md) からクラスを派生させると、この実装ははるかに簡単になります。 この記事では、これを行うことを前提としています。

モードレスプロパティシートと外部オブジェクト (ビューで現在選択されている項目など) との間で通信を行う方法の1つは、プロパティシートから外部オブジェクトへのポインターを定義することです。 の派生クラスで関数 (など) を定義して、 `SetMyExternalObject` `CPropertySheet` ポインターがある外部オブジェクトから別の外部オブジェクトに変更されるたびにポインターを変更します。 関数は、 `SetMyExternalObject` 新しく選択された外部オブジェクトを反映するように、各プロパティページの設定をリセットする必要があります。 これを実現するには、 `SetMyExternalObject` クラスに属する [CPropertyPage](reference/cpropertypage-class.md) オブジェクトに関数がアクセスできる必要があり `CPropertySheet` ます。

プロパティシート内のプロパティページへのアクセスを提供する最も便利な方法は、 `CPropertyPage` から派生したオブジェクトにオブジェクトを埋め込むことです `CPropertySheet` 。 派生オブジェクトにオブジェクトを埋め込むことは、 `CPropertyPage` `CPropertySheet` モーダルダイアログボックスの一般的な設計とは異なります。このダイアログボックスでは、プロパティシートの所有者がオブジェクトを作成 `CPropertyPage` し、 [CPropertySheet:: AddPage](reference/cpropertysheet-class.md#addpage)を使用してプロパティシートに渡します。

モードレスプロパティシートの設定を外部オブジェクトに適用するかどうかを判断するための、多くのユーザーインターフェイスの代替手段が用意されています。 別の方法としては、ユーザーが任意の値を変更したときに、現在のプロパティページの設定を適用する方法があります。 別の方法として、[適用] ボタンを用意する方法もあります。このボタンを使用すると、ユーザーはプロパティページに変更を蓄積してから、外部オブジェクトにコミットすることができます。 [適用] ボタンの処理方法の詳細については、「[ [適用] ボタンの処理](handling-the-apply-button.md)」を参照してください。

## <a name="see-also"></a>関連項目

[プロパティシート](property-sheets-mfc.md)<br/>
[データの交換](exchanging-data.md)<br/>
[MFC でのダイアログ ボックスの操作](life-cycle-of-a-dialog-box.md)
