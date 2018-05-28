---
title: クラスの属性 |Microsoft ドキュメント
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
ms.openlocfilehash: 8a932fdb1ef1d9e2af2acace901feaa95b6216d1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="class-attributes"></a>クラス属性
次の属性に適用される、[クラス](../cpp/class-cpp.md)C++ のキーワードです。  
  
|属性|説明|  
|---------------|-----------------|  
|[aggregatable](../windows/aggregatable.md)|クラスが集計をサポートしていることを示します。|  
|[aggregates](../windows/aggregates.md)|コントロールがターゲット クラスを集約することを示します。|  
|[appobject](../windows/appobject.md)|完全 .exe アプリケーションに関連付けられ、関数と、コクラスのプロパティがグローバルに使用できることでこのタイプ ライブラリを示しますアプリケーション オブジェクトとしてコクラスを識別します。|  
|[case](../windows/case-cpp.md)|使用される、 [switch_type](../windows/switch-type.md)共用体の属性です。|  
|[coclass](../windows/coclass.md)|ActiveX コントロールを作成します。|  
|[com_interface_entry](../windows/com-interface-entry-cpp.md)|インターフェイスのエントリを COM マップに追加します。|  
|[control](../windows/control.md)|ユーザー定義型がコントロールであることを指定します。|  
|[custom](../windows/custom-cpp.md)|独自の属性を定義できます。|  
|[db_command](../windows/db-command.md)|OLE DB コマンドを作成します。|  
|[db_param](../windows/db-param.md)|入力または出力パラメーターを持つ指定したメンバー変数を関連付けるし、変数を区切ります。|  
|[db_source](../windows/db-source.md)|データ ソースへの接続を作成します。|  
|[db_table](../windows/db-table.md)|OLE DB テーブルを開きます。|  
|[default](../windows/default-cpp.md)|コクラス内で定義されるカスタムまたはディスパッチ インターフェイスが既定のプログラミング インターフェイスを表すことを示します。|  
|[defaultvtable](../windows/defaultvtable.md)|コントロールの既定の vtable インターフェイスとしてインターフェイスを定義します。|  
|[event_receiver](../windows/event-receiver.md)|イベント レシーバーを作成します。|  
|[event_source](../windows/event-source.md)|イベント ソースを作成します。|  
|[helpcontext](../windows/helpcontext.md)|コンテキスト ID をユーザーに関する情報を表示、ヘルプ ファイル内のこの要素を指定します。|  
|[helpfile](../windows/helpfile.md)|タイプ ライブラリのヘルプ ファイルの名前を設定します。|  
|[helpstringcontext](../windows/helpstringcontext.md)|.Hlp または .chm ファイルには、ヘルプ トピックの ID を指定します。|  
|[helpstring](../windows/helpstring.md)|適用すると、要素の記述に使用される文字の文字列を指定します。|  
|[hidden](../windows/hidden.md)|項目が存在しますが、ユーザー指向ブラウザーで表示する必要がありますされませんを示します。|  
|[実装](../windows/implements-cpp.md)|IDL coclass のメンバーであることを強制するディスパッチ インターフェイスを指定します。|  
|[implements_category](../windows/implements-category.md)|クラスの実装済みのコンポーネントのカテゴリを指定します。|  
|[モジュール](../windows/module-cpp.md)|.idl ファイルのライブラリ ブロックを定義します。|  
|[noncreatable](../windows/noncreatable.md)|単独でインスタンス化できないオブジェクトを定義します。|  
|[progid](../windows/progid.md)|コントロールの ProgID を定義します。|  
|[registration_script](../windows/registration-script.md)|指定した登録スクリプトを実行します。|  
|[requestedit](../windows/requestedit.md)|プロパティをサポートしていることを示します、 **OnRequestEdit**通知します。|  
|[ソース](../windows/source-cpp.md)|クラスのコネクション ポイント用のコントロールのソース インターフェイスを指定します。 プロパティまたはメソッドで、**ソース**属性は、メンバーがオブジェクトまたはイベントのソースであるバリアント型を返すことを示します。|  
|[support_error_info](../windows/support-error-info.md)|ターゲット オブジェクトのエラー報告をサポートしています。|  
|[スレッド処理](../windows/threading-cpp.md)|コントロールのスレッド モデルを指定します。|  
|[uuid](../windows/uuid-cpp-attributes.md)|クラスまたはインターフェイスの一意の ID を指定します。|  
|[version](../windows/version-cpp.md)|クラスの複数のバージョン間で特定のバージョンを識別します。|  
|[vi_progid](../windows/vi-progid.md)|ProgID のバージョンに依存しない形式を指定します。|  
  
## <a name="see-also"></a>関連項目  
 [使用法別の属性](../windows/attributes-by-usage.md)