---
title: '[適用] ボタンの処理 |Microsoft ドキュメント'
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
ms.openlocfilehash: acbbd4ec8e075abbcbbeeaf199cae0d3a8d3c41a
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930453"
---
# <a name="handling-the-apply-button"></a>[適用] ボタンの処理
プロパティ シートの標準的なダイアログ ボックスがない機能があります: プロパティ シートを閉じる前に行った変更を適用するユーザーを許可します。 これは、[適用] ボタンを使用します。 この記事では、この機能を正しく実装に使用できるメソッドについて説明します。  
  
 モーダル ダイアログ ボックスは、ユーザー ダイアログ ボックスを閉じるには、ok をクリックしたときに通常設定と外部のオブジェクトに適用されます。 プロパティ シートの場合も同様です。 ユーザーは、[ok] をクリックすると、プロパティ シートで、新しい設定が反映されます。  
  
 ただし、プロパティ シート ダイアログ ボックスを閉じることがなく設定を保存するユーザーを許可することがあります。 これは、[適用] ボタンの機能です。 [適用] ボタンには、現在のページの現在の設定のみを適用するのではなく、外部のオブジェクトにすべてのプロパティ ページの現在の設定が適用されます。  
  
 既定では、[適用] ボタンは常に無効になります。 適切な時点では、[適用] ボタンを有効にするコードを記述する必要があり、以下に示すように、適用の効果を実装するコードを記述する必要があります。  
  
 ユーザーに適用機能を提供しない場合、[適用] ボタンを削除する必要はありません。 使用できなくなり、将来のバージョンの Windows で使用できる標準のプロパティ シートのサポートを使用してアプリケーションに共通するはそのままでかまいません。  
  
 変更されると、ページのレポートを [適用] ボタンを有効にするには、呼び出す`CPropertyPage::SetModified( TRUE )`です。 変更されているページのレポートのいずれか場合、[適用] ボタンは引き続き現在のページが変更されたかどうかに関係なく、有効です。  
  
 呼び出す必要があります[CPropertyPage::SetModified](../mfc/reference/cpropertypage-class.md#setmodified)ユーザーが任意のページで設定が変更されるたびにします。 ページで設定を変更するときを検出する方法の 1 つなどのプロパティ ページで、コントロールの変更通知のハンドラーを実装する**EN_CHANGE**または**BN_CLICKED**です。  
  
 [適用] ボタンの効果を実装するのにプロパティ シートは、アプリケーションで、プロパティ ページで、現在の設定を適用する、所有者、またはその他の外部オブジェクトを伝えます必要があります。 同時に、プロパティ シートを無効に適用 ボタンを呼び出して`CPropertyPage::SetModified( FALSE )`すべてのページの外部のオブジェクトに、その変更を適用します。  
  
 このプロセスの例は、MFC 標準サンプルを参照してください。 [PROPDLG](../visual-cpp-samples.md)です。  
  
## <a name="see-also"></a>関連項目  
 [プロパティ シート](../mfc/property-sheets-mfc.md)

