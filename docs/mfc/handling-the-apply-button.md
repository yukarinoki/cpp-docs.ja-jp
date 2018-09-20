---
title: '[適用] ボタンの処理 |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Apply button in property sheet
- property sheets, Apply button
ms.assetid: 7e977015-59b8-406f-b545-aad0bfd8d55b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8286bc15d3bbc3716263bf76b0eea953366b0947
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46405919"
---
# <a name="handling-the-apply-button"></a>[適用] ボタンの処理

プロパティ シートの標準的なダイアログ ボックスがない機能があります: プロパティ シートを閉じる前に行った変更を適用するユーザーを許可します。 これは、[適用] ボタンを使用します。 この記事では、この機能を正しく実装するために使用できる方法について説明します。

モーダル ダイアログ ボックスは、ユーザーがダイアログ ボックスを閉じるには、[ok] をクリックしたときに通常設定と外部のオブジェクトに適用されます。 プロパティ シートにも同様です。 ユーザーは、[ok] をクリックすると、プロパティ シート内の新しい設定が有効です。

ただし、ユーザーがプロパティ シート ダイアログ ボックスを閉じることがなく設定を保存できるようにしたい場合があります。 これは、[適用] ボタンの機能です。 [適用] ボタンには、現在アクティブなページの現在の設定のみを適用するのではなく、外部のオブジェクトにすべてのプロパティ ページの現在の設定が適用されます。

既定では、常に [適用] ボタンが無効にします。 適切なタイミングでは、適用 ボタンを有効にするコードを記述する必要があり、次に示すように、適用の効果を実装するコードを記述する必要があります。

ユーザーに適用機能を提供しない場合、[適用] ボタンを削除する必要はありません。 Windows の将来のバージョンで使用可能な標準のプロパティ シートのサポートを使用してアプリケーションに共通するは、無効ままにすることができます。

変更されると、ページをレポートし、[適用] ボタンを有効にする、`CPropertyPage::SetModified( TRUE )`します。 変更対象ページのレポートの存在する場合、[適用] ボタンは引き続き現在のページが変更されているかどうかに関係なく、有効です。

呼び出す必要があります[CPropertyPage::SetModified](../mfc/reference/cpropertypage-class.md#setmodified)ユーザーがページのすべての設定を変更するたびにします。 などのプロパティ ページで、コントロールの変更通知ハンドラーを実装するために、ページの設定を変更するときを検出する方法の 1 つは、 **EN_CHANGE**または**BN_CLICKED**します。

[適用] ボタンの効果を実装するには、プロパティ シートはプロパティ ページで、現在の設定を適用する、アプリケーションでも、所有者、またはその他の外部オブジェクトに伝える必要があります。 同時に、プロパティ シートは、呼び出すことによって、[適用] ボタンを無効する必要があります`CPropertyPage::SetModified( FALSE )`の外部のオブジェクトには、その変更を適用するすべてのページ。

このプロセスの例は、MFC 標準サンプルを参照してください。 [PROPDLG](../visual-cpp-samples.md)します。

## <a name="see-also"></a>関連項目

[プロパティ シート](../mfc/property-sheets-mfc.md)

