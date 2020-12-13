---
description: '詳細情報: オプション、ATL プロパティページウィザード'
title: オプション、ATL プロパティ ページ ウィザード
ms.date: 05/09/2019
f1_keywords:
- vc.codewiz.class.atl.ppg.options
helpviewer_keywords:
- ATL Property Page Wizard, options
ms.assetid: a7107779-b2ea-4f99-b84b-7f3e0c504bc8
ms.openlocfilehash: ea7508f49e48c2ef1387fb4b48b816f4e16cdb99
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138997"
---
# <a name="options-atl-property-page-wizard"></a>オプション、ATL プロパティ ページ ウィザード

::: moniker range="msvc-160"

ATL プロパティ ページ ウィザードは、Visual Studio 2019 以降では使用できません。

::: moniker-end

::: moniker range="<=msvc-150"

このウィザード ページを使用して、作成するスレッド モデルとプロパティ ページの集計レベルを定義します。

- **スレッド モデル**

   プロパティ ページで使用されるスレッド モデルを指定します。

   詳細については、「[プロジェクトのスレッド モデルの指定 (ATL)](../../atl/specifying-the-threading-model-for-a-project-atl.md)」を参照してください。

   |オプション|説明|
   |------------|-----------------|
   |**Single**|プロパティ ページは、プライマリ COM スレッドでのみ実行されます。|
   |**スレッド**|任意の単一のスレッド アパートメントにプロパティ ページを作成できます。 これが既定値です。|

- **集計**

   作成するプロパティ ページに集計サポートを追加します。 詳細については、「[集計](../../atl/aggregation.md)」を参照してください。

   |オプション|説明|
   |------------|-----------------|
   |**あり**|集計可能なプロパティ ページを作成します。|
   |**いいえ**|集計が不可能なプロパティ ページを作成します。|
   |**専用**|集計経由でのみインスタンス化できるプロパティ ページを作成します。|

::: moniker-end

## <a name="see-also"></a>関連項目

[ATL プロパティ ページ ウィザード](../../atl/reference/atl-property-page-wizard.md)<br/>
[文字列、ATL プロパティ ページ ウィザード](../../atl/reference/strings-atl-property-page-wizard.md)
