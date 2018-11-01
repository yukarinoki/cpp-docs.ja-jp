---
title: オプション、ATL プロパティ ページ ウィザード
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.class.atl.ppg.options
helpviewer_keywords:
- ATL Property Page Wizard, options
ms.assetid: a7107779-b2ea-4f99-b84b-7f3e0c504bc8
ms.openlocfilehash: e891bd9e37bbf2fbedcdd71649305cdc366065fd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50642011"
---
# <a name="options-atl-property-page-wizard"></a>オプション、ATL プロパティ ページ ウィザード

ウィザードのこのページを使用すると、作成する プロパティ ページのスレッド モデルと集計レベルを定義します。

- **スレッド モデル**

   プロパティ ページで使用されるスレッド処理モデルを指定します。

   参照してください[プロジェクトのスレッド モデルを指定する](../../atl/specifying-the-threading-model-for-a-project-atl.md)詳細についてはします。

   |オプション|説明|
   |------------|-----------------|
   |**Single**|プロパティ ページは、プライマリ COM スレッドでのみ実行されます。|
   |**アパートメント**|プロパティ ページは、任意の 1 つのスレッド アパートメントで作成できます。 これが既定値です。|

- **集計**

   作成するプロパティ ページの集計のサポートを追加します。 参照してください[集計](../../atl/aggregation.md)詳細についてはします。

   |オプション|説明|
   |------------|-----------------|
   |**はい**|集計可能なプロパティ ページを作成します。|
   |**No**|集計が不可能なプロパティ ページを作成します。|
   |**のみ**|集計をのみインスタンス化するプロパティ ページを作成します。|

## <a name="see-also"></a>関連項目

[ATL プロパティ ページ ウィザード](../../atl/reference/atl-property-page-wizard.md)<br/>
[文字列、ATL プロパティ ページ ウィザード](../../atl/reference/strings-atl-property-page-wizard.md)

