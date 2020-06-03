---
title: レコード ビュー クラスの機能 (MFC データ アクセス)
ms.date: 11/04/2016
helpviewer_keywords:
- record views, classes
- record view classes
ms.assetid: e7b2820f-09c4-483f-83c0-317e8be42bdf
ms.openlocfilehash: 62597a3eb3f7a7e779ca57c9781565176df568d4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213435"
---
# <a name="features-of-record-view-classes--mfc-data-access"></a>レコード ビュー クラスの機能 (MFC データ アクセス)

フォームベースのデータアクセスプログラミングは、 [CFormView](../mfc/reference/cformview-class.md)クラスを使用して行う[ことができますが、](../mfc/reference/crecordview-class.md)通常は、から派生することをお勧めします。 `CFormView` の機能に加えて、次の `CRecordView`ます。

- フォームコントロールと関連付けられたレコードセットオブジェクトとの間にダイアログデータエクスチェンジ (DDX) を提供します。

- 関連付けられたレコードセットオブジェクト内のレコード間を移動するために、[最初に移動]、[次に移動]、[前に移動]、および [最後のコマンドを移動] を処理します

- ユーザーが別のレコードに移動したときに、現在のレコードの変更を更新します。

ナビゲーションの詳細については、「[レコードビュー: レコードビューでのナビゲーションのサポート](../data/supporting-navigation-in-a-record-view-mfc-data-access.md)」を参照してください。

## <a name="see-also"></a>参照

[レコード ビュー (MFC データ アクセス)](../data/record-views-mfc-data-access.md)<br/>
[ODBC ドライバーの一覧](../data/odbc/odbc-driver-list.md)
