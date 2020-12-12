---
description: '詳細情報: COM 属性'
title: COM 属性
ms.date: 10/03/2018
helpviewer_keywords:
- attributes [C++/CLI], reference topics
- attributes [COM]
- COM, attributes
ms.assetid: 52a5dd70-e8be-4bba-afd6-daf90fe689a0
ms.openlocfilehash: d1377bdcb449190d01f529b2a4c713f138cbef5f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97269173"
---
# <a name="com-attributes"></a>COM 属性

COM 属性は、COM 開発のさまざまな領域をサポートし、共通言語ランタイム開発を .NET Framework コードを挿入します。 これらの領域は、カスタムインターフェイスの実装や既存のインターフェイスのサポートから、ストックプロパティ、メソッド、およびイベントのサポートまで多岐においています。 また、複合コントロールと ActiveX コントロールの実装についてもサポートされています。

|属性|説明|
|---------------|-----------------|
|[aggregatable](aggregatable.md)|コントロールを別のコントロールで集計できることを示します。|
|[集計](aggregates.md)|コントロールがターゲットクラスを集計することを示します。|
|[coclass](coclass.md)|Com インターフェイスを実装できる COM オブジェクトを作成します。|
|[com_interface_entry](com-interface-entry-cpp.md)|COM マップにインターフェイスエントリを追加します。|
|[implements_category](implements-category.md)|クラスに実装されているコンポーネントのカテゴリを指定します。|
|[progid](progid.md)|コントロールの ProgID を定義します。|
|[rdx](rdx.md)|レジストリキーを作成または変更します。|
|[registration_script](registration-script.md)|指定された登録スクリプトを実行します。|
|[requires_category](requires-category.md)|クラスに必要なコンポーネントのカテゴリを指定します。|
|[support_error_info](support-error-info.md)|ターゲットオブジェクトのエラー報告をサポートします。|
|[化](synchronize.md)|メソッドへのアクセスを同期します。|
|[おける](threading-cpp.md)|COM オブジェクトのスレッド処理モデルを指定します。|
|[vi_progid](vi-progid.md)|コントロールのバージョンに依存しない ProgID を定義します。|

## <a name="see-also"></a>関連項目

[グループ別の属性](attributes-by-group.md)
