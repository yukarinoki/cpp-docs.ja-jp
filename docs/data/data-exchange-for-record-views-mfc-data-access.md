---
title: レコード ビュー (MFC データ アクセス) のデータの交換 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- RFX (record field exchange), data exchange mechanism
- RFX (record field exchange), record views
- record views, data exchange
- DDX (dialog data exchange), record views
- RFX (record field exchange)
ms.assetid: abc52ca7-6997-47a7-98f3-f347f52b1f72
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 41c3ed8fc08478077a2f9f463db6dc743aab7f11
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46047617"
---
# <a name="data-exchange-for-record-views---mfc-data-access"></a>レコード ビューのデータ交換 (MFC データ アクセス)

使用すると[クラスの追加](../mfc/reference/adding-an-mfc-odbc-consumer.md)レコード ビューのダイアログ テンプレート リソース内のコントロールをレコード セットのフィールドにマップするには、フレームワークは双方向のデータ交換を管理 — コントロールをレコード セットとレコード セットへのコントロールから。 DDX 機構を使用すると、データを双方向で転送するコードを自分で記述する必要がなくなります。  
  
レコード ビューの DDX はと共に動作[RFX](../data/odbc/record-field-exchange-rfx.md)クラスのレコード セット`CRecordset`(ODBC)。  Rfx 関数は、データ ソースの現在のレコードとレコード セット オブジェクトのフィールド データ メンバーの間のデータを移動します。 DDX は、フィールド データ メンバーからフォーム内のコントロールにデータを移動します。 このように組み合わせると、フォーム コントロールに初期値が設定され、ユーザーがレコード間を移動したときにも値が設定されます。 更新されたデータをレコードセットに戻し、さらにデータ ソースまで移動することもできます。  
  
次の図は、レコード ビューの DDX と RFX 間のリレーションシップを示します。  
  
![ダイアログ&#45;データ交換およびレコード&#45;フィールド エクス チェンジ](../data/media/vc37xt1.gif "vc37xt1")  
ダイアログ データ エクスチェンジ (DDX) とレコード フィールド エクスチェンジ (RFX)  
  
DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../mfc/dialog-data-exchange-and-validation.md)です。 RFX の詳細については、次を参照してください。[レコード フィールド エクス チェンジ (RFX)](../data/odbc/record-field-exchange-rfx.md)します。  
  
## <a name="see-also"></a>関連項目  

[レコード ビュー (MFC データ アクセス)](../data/record-views-mfc-data-access.md)<br/>
[ODBC ドライバーの一覧](../data/odbc/odbc-driver-list.md)