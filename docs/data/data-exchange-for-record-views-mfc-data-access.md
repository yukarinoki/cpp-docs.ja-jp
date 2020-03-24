---
title: レコード ビューのデータ交換 (MFC データ アクセス)
ms.date: 11/19/2018
helpviewer_keywords:
- RFX (record field exchange), data exchange mechanism
- RFX (record field exchange), record views
- record views, data exchange
- DDX (dialog data exchange), record views
- RFX (record field exchange)
ms.assetid: abc52ca7-6997-47a7-98f3-f347f52b1f72
ms.openlocfilehash: f9f460305b55a2313b64effdf4d1dbbfd9823def
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213474"
---
# <a name="data-exchange-for-record-views---mfc-data-access"></a>レコード ビューのデータ交換 (MFC データ アクセス)

[クラスの[追加](../mfc/reference/adding-an-mfc-odbc-consumer.md)] を使用して、レコードビューのダイアログテンプレートリソース内のコントロールをレコードセットのフィールドにマップすると、フレームワークは、レコードセットからコントロール、およびコントロールからレコードセットへの双方向のデータ交換を管理します。 DDX 機構を使用すると、データを双方向で転送するコードを自分で記述する必要がなくなります。

レコードビューの DDX は、クラス `CRecordset` (ODBC) のレコードセットの[RFX](../data/odbc/record-field-exchange-rfx.md)と組み合わせて使用できます。  RFX は、データソースの現在のレコードとレコードセットオブジェクトのフィールドデータメンバーの間でデータを移動します。 DDX は、フィールド データ メンバーからフォーム内のコントロールにデータを移動します。 このように組み合わせると、フォーム コントロールに初期値が設定され、ユーザーがレコード間を移動したときにも値が設定されます。 更新されたデータをレコードセットに戻し、さらにデータ ソースまで移動することもできます。

次の図は、レコードビューの DDX と RFX の関係を示しています。

![ダイアログ&#45;データエクスチェンジとレコード&#45;フィールドエクスチェンジ](../data/media/vc37xt1.gif "ダイアログ&#45;データエクスチェンジとレコード&#45;フィールドエクスチェンジ")<br/>
ダイアログ データ エクスチェンジ (DDX) とレコード フィールド エクスチェンジ (RFX)

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../mfc/dialog-data-exchange-and-validation.md)」を参照してください。 RFX の詳細については、「[レコードフィールドエクスチェンジ (rfx)](../data/odbc/record-field-exchange-rfx.md)」を参照してください。

## <a name="see-also"></a>参照

[レコード ビュー (MFC データ アクセス)](../data/record-views-mfc-data-access.md)<br/>
[ODBC ドライバーの一覧](../data/odbc/odbc-driver-list.md)
