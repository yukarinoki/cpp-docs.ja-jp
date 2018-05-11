---
title: COM 属性 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++], reference topics
- attributes [COM]
- COM, attributes
ms.assetid: 52a5dd70-e8be-4bba-afd6-daf90fe689a0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9d37ba5c690b61840ad261e6ab966d0cc74c07c1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="com-attributes"></a>COM 属性
COM 属性は、COM で開発および .NET Framework 共通言語ランタイムの数多くの領域をサポートするためにコードを挿入します。 これらの分野カスタム インターフェイスの実装と、既存のインターフェイスからストック プロパティ、メソッド、およびイベントをサポートします。 さらに、複合と ActiveX コントロールの実装のサポートを確認できます。  
  
|属性|説明|  
|---------------|-----------------|  
|[aggregatable](../windows/aggregatable.md)|別のコントロールでコントロールを集計できることを示します。|  
|[aggregates](../windows/aggregates.md)|コントロールがターゲット クラスを集約することを示します。|  
|[coclass](../windows/coclass.md)|COM インターフェイスを実装する COM オブジェクトを作成します。|  
|[com_interface_entry](../windows/com-interface-entry-cpp.md)|インターフェイスのエントリを COM マップに追加します。|  
|[implements_category](../windows/implements-category.md)|クラスの実装済みのコンポーネントのカテゴリを指定します。|  
|[progid](../windows/progid.md)|コントロールの ProgID を定義します。|  
|[rdx](../windows/rdx.md)|作成するか、レジストリ キーを変更します。|  
|[registration_script](../windows/registration-script.md)|指定した登録スクリプトを実行します。|  
|[requires_category](../windows/requires-category.md)|クラスの必須コンポーネントのカテゴリを指定します。|  
|[support_error_info](../windows/support-error-info.md)|ターゲット オブジェクトのエラー報告をサポートしています。|  
|[synchronize](../windows/synchronize.md)|メソッドへのアクセスを同期します。|  
|[スレッド処理](../windows/threading-cpp.md)|COM オブジェクトのスレッド モデルを指定します。|  
|[vi_progid](../windows/vi-progid.md)|コントロールのバージョン依存 ProgID を定義します。|  
  
## <a name="see-also"></a>関連項目  
 [グループ別の属性](../windows/attributes-by-group.md)