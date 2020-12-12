---
description: '詳細情報: レコードビュークラスの機能 (MFC データアクセス)'
title: レコード ビュー クラスの機能 (MFC データ アクセス)
ms.date: 11/04/2016
helpviewer_keywords:
- record views, classes
- record view classes
ms.assetid: e7b2820f-09c4-483f-83c0-317e8be42bdf
ms.openlocfilehash: bf2a0bd1a609fcb29eb945f60ab22c4632addf1b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97116536"
---
# <a name="features-of-record-view-classes--mfc-data-access"></a>レコード ビュー クラスの機能 (MFC データ アクセス)

フォームベースのデータアクセスプログラミングは、 [CFormView](../mfc/reference/cformview-class.md)クラスを使用して行う [ことができますが、](../mfc/reference/crecordview-class.md) 通常は、から派生することをお勧めします。 その機能に加えて、次のことを `CFormView` `CRecordView` 行います。

- フォームコントロールと関連付けられたレコードセットオブジェクトとの間にダイアログデータエクスチェンジ (DDX) を提供します。

- 関連付けられたレコードセットオブジェクト内のレコード間を移動するために、[最初に移動]、[次に移動]、[前に移動]、および [最後のコマンドを移動] を処理します

- ユーザーが別のレコードに移動したときに、現在のレコードの変更を更新します。

ナビゲーションの詳細については、「 [レコードビュー: レコードビューでのナビゲーションのサポート](../data/supporting-navigation-in-a-record-view-mfc-data-access.md)」を参照してください。

## <a name="see-also"></a>関連項目

[レコードビュー (MFC データアクセス)](../data/record-views-mfc-data-access.md)<br/>
[ODBC ドライバーの一覧](../data/odbc/odbc-driver-list.md)
