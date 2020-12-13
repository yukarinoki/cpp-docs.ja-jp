---
description: '詳細情報: プロジェクトのスレッドモデルの指定 (ATL)'
title: プロジェクトのスレッド モデルの指定 (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- _ATL_FREE_THREADED macro
- _ATL_APARTMENT_THREADED macro
- ATL, multithreading
- threading [ATL], models
- _ATL_SINGLE_THREADED macro
ms.assetid: 6b571078-521c-4f3e-9f08-482aa235a822
ms.openlocfilehash: 81bf8413a2118797ec0e0c177a06468b8e3c7ba0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138477"
---
# <a name="specifying-the-threading-model-for-a-project-atl"></a>プロジェクトのスレッド モデルの指定 (ATL)

ATL プロジェクトのスレッドモデルを指定するには、次のマクロを使用できます。

|マクロ|を使用するためのガイドライン|
|-----------|--------------------------|
|_ATL_SINGLE_THREADED|すべてのオブジェクトが単一のスレッドモデルを使用するかどうかを定義します。|
|_ATL_APARTMENT_THREADED|1つ以上のオブジェクトがアパートメントスレッドを使用するかどうかを定義します。|
|_ATL_FREE_THREADED|1つ以上のオブジェクトが、フリースレッドまたはニュートラルスレッドを使用するかどうかを定義します。 既存のコードには、同等のマクロ [_ATL_MULTI_THREADED](reference/compiler-options-macros.md#_atl_multi_threaded)への参照が含まれている場合があります。|

プロジェクトに対してこれらのマクロを定義しないと、_ATL_FREE_THREADED が有効になります。

マクロは、次のように実行時のパフォーマンスに影響します。

- プロジェクト内のオブジェクトに対応するマクロを指定すると、実行時のパフォーマンスが向上します。

- より高いレベルのマクロを指定する場合 (たとえば、すべてのオブジェクトがシングルスレッドの場合に _ATL_APARTMENT_THREADED を指定すると、では実行時のパフォーマンスが若干低下します。

- 低いレベルのマクロを指定すると、たとえば、1つまたは複数のオブジェクトがアパートメントスレッドまたはフリースレッド処理を使用する場合に _ATL_SINGLE_THREADED を指定すると、アプリケーションが実行時に失敗する可能性があります。

ATL オブジェクトで使用できるスレッド処理モデルの説明については、「オプション」の「 [Atl シンプルオブジェクトウィザード](../atl/reference/options-atl-simple-object-wizard.md) 」を参照してください。

## <a name="see-also"></a>関連項目

[概念](../atl/active-template-library-atl-concepts.md)
