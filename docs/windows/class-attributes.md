---
title: クラス属性 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++], class attributes
- class attributes
ms.assetid: fad04ea1-d8ff-46d4-bb42-2b4500a6ab60
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0a2fe111028f952482dbd6b2eedebc157d39a9a4
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39645176"
---
# <a name="class-attributes"></a>クラス属性
次の属性を適用する、[クラス](../cpp/class-cpp.md)C++ のキーワード。  
  
|属性|説明|  
|---------------|-----------------|  
|[aggregatable](../windows/aggregatable.md)|クラスは、集計をサポートしていることを示します。|  
|[aggregates](../windows/aggregates.md)|コントロールがターゲット クラスを集約することを示します。|  
|[appobject](../windows/appobject.md)|完全な .exe アプリケーションに関連付けられ、関数と、コクラスのプロパティがグローバルに使用できるこのタイプ ライブラリを示しますアプリケーション オブジェクトとしてコクラスを識別します。|  
|[case](../windows/case-cpp.md)|使用される、 [switch_type](../windows/switch-type.md)共用体の属性。|  
|[coclass](../windows/coclass.md)|ActiveX コントロールを作成します。|  
|[com_interface_entry](../windows/com-interface-entry-cpp.md)|COM マップには、インターフェイスのエントリを追加します。|  
|[control](../windows/control.md)|コントロールに、ユーザー定義型を指定します。|  
|[custom](../windows/custom-cpp.md)|独自の属性を定義できます。|  
|[db_command](../windows/db-command.md)|OLE DB コマンドを作成します。|  
|[db_param](../windows/db-param.md)|入力または出力パラメーターを使用して、指定したメンバー変数を関連付けるし、変数を区切ります。|  
|[db_source](../windows/db-source.md)|データ ソースへの接続を作成します。|  
|[db_table](../windows/db-table.md)|OLE DB、テーブルを開きます。|  
|[default](../windows/default-cpp.md)|コクラス内で定義されるカスタムまたはディスパッチ インターフェイスが既定のプログラミング インターフェイスを表すことを示します。|  
|[defaultvtable](../windows/defaultvtable.md)|コントロールの既定の vtable インターフェイスとしてインターフェイスを定義します。|  
|[event_receiver](../windows/event-receiver.md)|イベント レシーバーを作成します。|  
|[event_source](../windows/event-source.md)|イベント ソースを作成します。|  
|[helpcontext](../windows/helpcontext.md)|ユーザーには、この要素に関する情報を表示できるようにコンテキスト ID を指定します、**ヘルプ**ファイル。|  
|[helpfile](../windows/helpfile.md)|タイプ ライブラリのヘルプ ファイルの名前を設定します。|  
|[helpstringcontext](../windows/helpstringcontext.md)|.Hlp または .chm ファイルをヘルプ トピックの ID を指定します。|  
|[helpstring](../windows/helpstring.md)|適用先となる要素を記述するために使用される文字列を指定します。|  
|[hidden](../windows/hidden.md)|項目が存在しますが、ユーザー指向ブラウザーで表示する必要がありますされませんを示します。|  
|[実装](../windows/implements-cpp.md)|IDL コクラスのメンバーであるが強制されているディスパッチ インターフェイスを指定します。|  
|[implements_category](../windows/implements-category.md)|クラスの実装されたコンポーネントのカテゴリを指定します。|  
|[モジュール](../windows/module-cpp.md)|.idl ファイルのライブラリ ブロックを定義します。|  
|[noncreatable](../windows/noncreatable.md)|単独でインスタンス化できないオブジェクトを定義します。|  
|[progid](../windows/progid.md)|コントロールの ProgID を定義します。|  
|[registration_script](../windows/registration-script.md)|指定した登録スクリプトを実行します。|  
|[requestedit](../windows/requestedit.md)|プロパティをサポートしていることを示します、`OnRequestEdit`通知します。|  
|[source](../windows/source-cpp.md)|コネクション ポイントのソース インターフェイスのコントロールのクラスを指定します。 プロパティまたはメソッドで、`source`属性は、メンバーがオブジェクトを返すことを示しますまたは`VARIANT`イベントのソースは。|  
|[support_error_info](../windows/support-error-info.md)|ターゲット オブジェクトのエラー報告をサポートしています。|  
|[スレッド処理](../windows/threading-cpp.md)|コントロールのスレッド モデルを指定します。|  
|[uuid](../windows/uuid-cpp-attributes.md)|クラスまたはインターフェイスの一意の ID を指定します。|  
|[version](../windows/version-cpp.md)|クラスの複数のバージョン間で特定のバージョンを識別します。|  
|[vi_progid](../windows/vi-progid.md)|ProgID のバージョンに依存しない形式を指定します。|  
  
## <a name="see-also"></a>関連項目  
 [使用法別の属性](../windows/attributes-by-usage.md)