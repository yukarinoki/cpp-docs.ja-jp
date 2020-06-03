---
title: COM 属性
ms.date: 10/03/2018
helpviewer_keywords:
- attributes [C++/CLI], reference topics
- attributes [COM]
- COM, attributes
ms.assetid: 52a5dd70-e8be-4bba-afd6-daf90fe689a0
ms.openlocfilehash: 15225d23abb66b8aadd5f82b8429334356bdaa8d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80168318"
---
# <a name="com-attributes"></a>COM 属性

COM 属性は、COM 開発のさまざまな領域をサポートし、共通言語ランタイム開発を .NET Framework コードを挿入します。 これらの領域は、カスタムインターフェイスの実装や既存のインターフェイスのサポートから、ストックプロパティ、メソッド、およびイベントのサポートまで多岐においています。 また、複合コントロールと ActiveX コントロールの実装についてもサポートされています。

|Attribute|説明|
|---------------|-----------------|
|[aggregatable](aggregatable.md)|コントロールを別のコントロールで集計できることを示します。|
|[aggregates](aggregates.md)|コントロールがターゲットクラスを集計することを示します。|
|[coclass](coclass.md)|Com インターフェイスを実装できる COM オブジェクトを作成します。|
|[com_interface_entry](com-interface-entry-cpp.md)|COM マップにインターフェイスエントリを追加します。|
|[implements_category](implements-category.md)|クラスに実装されているコンポーネントのカテゴリを指定します。|
|[progid](progid.md)|コントロールの ProgID を定義します。|
|[rdx](rdx.md)|レジストリキーを作成または変更します。|
|[registration_script](registration-script.md)|指定された登録スクリプトを実行します。|
|[requires_category](requires-category.md)|クラスに必要なコンポーネントのカテゴリを指定します。|
|[support_error_info](support-error-info.md)|ターゲットオブジェクトのエラー報告をサポートします。|
|[synchronize](synchronize.md)|メソッドへのアクセスを同期します。|
|[threading](threading-cpp.md)|COM オブジェクトのスレッド処理モデルを指定します。|
|[vi_progid](vi-progid.md)|コントロールのバージョンに依存しない ProgID を定義します。|

## <a name="see-also"></a>参照

[グループ別の属性](attributes-by-group.md)
