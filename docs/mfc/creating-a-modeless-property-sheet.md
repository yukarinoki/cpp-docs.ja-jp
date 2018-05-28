---
title: モードレス プロパティ シートの作成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- modeless property sheets
- property sheets, modeless
- Create method [MFC], property sheets
ms.assetid: eafd8a92-cc67-4a69-a5fb-742c920d1ae8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 10dbef813d922bd01a5f9215b6d6e642349d2b75
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="creating-a-modeless-property-sheet"></a>モードレス プロパティ シートの作成
通常、作成するプロパティ シートはモーダルになります。 モーダル プロパティ シートを使用する場合、アプリケーションの他の部分を使用する前に、プロパティ シートを閉じる必要があります。 この記事では、ユーザーがアプリケーションの他の部分を使用しているときに、プロパティ シートを開いたままにできるモードレス プロパティ シートの作成に使用できる方法について説明します。  
  
 表示するには、プロパティ シートをモーダル ダイアログ ボックスとしての代わりに、モードレス ダイアログ ボックスとして呼び出します[CPropertySheet::Create](../mfc/reference/cpropertysheet-class.md#create)の代わりに[DoModal](../mfc/reference/cpropertysheet-class.md#domodal)です。 モードレス プロパティ シートをサポートするためにいくつか追加のタスクを実装することも必要があります。  
  
 プロパティ シートとプロパティ シートを開いている場合を変更する外部のオブジェクト間でデータを交換する追加のタスクの 1 つです。 これは、一般に、標準のモードレス ダイアログ ボックスの場合と同じタスクです。 このタスクの一部には、モードレス プロパティ シートとプロパティの設定を適用する外部のオブジェクト間の通信チャネルを実装します。 この実装は非常に簡単にからクラスを派生[CPropertySheet](../mfc/reference/cpropertysheet-class.md)モードレス プロパティ シートのです。 この記事が完了する前提としています。  
  
 モードレス プロパティ シートと外部の間で通信するための 1 つの方法をプロパティ シートから外部のオブジェクトへのポインターを定義するのには、オブジェクト (たとえば、ビューの現在の選択) します。 関数の定義 (と呼ばれるよう`SetMyExternalObject`) で、 `CPropertySheet`-フォーカス 1 つの外部オブジェクトから別に変更されるたびに、ポインターを変更するクラスを派生します。 `SetMyExternalObject`関数は、新しく選択した外部オブジェクトを反映するように各プロパティ ページの設定をリセットする必要があります。 これを実現する、`SetMyExternalObject`関数は、アクセスできる必要があります、 [CPropertyPage](../mfc/reference/cpropertypage-class.md)に属しているオブジェクト、`CPropertySheet`クラスです。  
  
 プロパティ シート内のプロパティ ページへのアクセスを提供する最も簡単な方法は、埋め込む、`CPropertyPage`内のオブジェクト、 `CPropertySheet`-派生オブジェクト。 埋め込み`CPropertyPage`内のオブジェクト、 `CPropertySheet`-派生オブジェクトはモーダル ダイアログ ボックスで、プロパティ シートの所有者を作成する、一般的なデザインとは異なる、`CPropertyPage`オブジェクトを使用して、プロパティ シートに渡す、 [CPropertySheet::AddPage](../mfc/reference/cpropertysheet-class.md#addpage)です。  
  
 モードレス プロパティ シートの設定を適用して、外部のオブジェクトにときを判断するための多くのユーザー インターフェイス選択肢があります。 1 つの代替手段は、ユーザーが任意の値を変更するたびに、現在のプロパティ ページの設定を適用するは。 別の方法としては、外部のオブジェクトにコミットする前に、プロパティ ページで変更を蓄積することができます、[適用] ボタンを提供します。 [適用] ボタンを処理する方法については、記事を参照してください。[適用ボタンの処理](../mfc/handling-the-apply-button.md)です。  
  
## <a name="see-also"></a>関連項目  
 [プロパティ シート](../mfc/property-sheets-mfc.md)   
 [データを交換します。](../mfc/exchanging-data.md)   
 [ダイアログ ボックスの有効期間](../mfc/life-cycle-of-a-dialog-box.md)

