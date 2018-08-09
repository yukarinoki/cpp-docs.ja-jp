---
title: Typedef、Enum、Union、および struct 型の属性 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- union attributes
- attributes [C++], reference topics
- struct attributes
- typedef attributes
- enum attributes
ms.assetid: f8a4fe94-dc02-4aed-bc31-3e500d42f4c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2e4e8ad94e96c6bfc45102f1c970476c484d756f
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39649124"
---
# <a name="typedef-enum-union-and-struct-attributes"></a>Typedef、Enum、Union、および Struct 型の属性
次の属性を適用する、 [typedef](http://msdn.microsoft.com/cc96cf26-ba93-4179-951e-695d1f5fdcf1)、[構造体](../cpp/struct-cpp.md)、および[列挙](../cpp/enumerations-cpp.md)C++ のキーワード。  
  
### <a name="typedef"></a>Typedef  
  
|属性|説明|  
|---------------|-----------------|  
|[case](../windows/case-cpp.md)|使用される、 [switch_type](../windows/switch-type.md)属性、**共用体**します。|  
|[custom](../windows/custom-cpp.md)|独自の属性を定義できます。|  
|[export](../windows/export.md)|.Idl ファイルに配置するデータ構造をによりします。|  
|[first_is](../windows/first-is.md)|転送する最初の配列要素のインデックスを指定します。|  
|[helpcontext](../windows/helpcontext.md)|ユーザーがヘルプ ファイル内のこの要素についての情報を表示できるようにコンテキスト ID を指定します。|  
|[helpfile](../windows/helpfile.md)|タイプ ライブラリのヘルプ ファイルの名前を設定します。|  
|[helpstring](../windows/helpstring.md)|適用先となる要素を記述するために使用される文字列を指定します。|  
|[library_block](../windows/library-block.md)|.Idl ファイルのライブラリ ブロック内で構成要素を配置します。|  
|[ptr](../windows/ptr.md)|完全なポインターとしてのポインターを指定します。|  
|[public](../windows/public-cpp-attributes.md)|.Idl ファイル内から参照されていない場合でも、typedef がタイプ ライブラリに送られるようにします。|  
|[ref](../windows/ref-cpp.md)|参照ポインターを識別します。|  
|[switch_is](../windows/switch-is.md)|式または共用体の判別共用体のメンバーを選択するとして機能する識別子を指定します。|  
|[switch_type](../windows/switch-type.md)|共用体の判別式として使用される変数の型を識別します。|  
|[unique](../windows/unique-cpp.md)|一意のポインターを指定します。|  
|[wire_marshal](../windows/wire-marshal.md)|アプリケーションに固有のデータ型ではなく転送されるデータ型を指定します。|  
  
### <a name="enum"></a>enum  
  
|属性|説明|  
|---------------|-----------------|  
|[custom](../windows/custom-cpp.md)|独自の属性を定義できます。|  
|[export](../windows/export.md)|.Idl ファイルに配置するデータ構造をによりします。|  
|[uuid](../windows/uuid-cpp-attributes.md)|クラスまたはインターフェイスの一意の ID を指定します。|  
|[v1_enum](../windows/v1-enum.md)|指定した列挙型は、16 ビットの既定ではなく、32 ビットのエンティティとして送信するよう指示します。|  
  
### <a name="union"></a>union  
  
|属性|説明|  
|---------------|-----------------|  
|[custom](../windows/custom-cpp.md)|独自の属性を定義できます。|  
|[export](../windows/export.md)|.Idl ファイルに配置するデータ構造をによりします。|  
|[first_is](../windows/first-is.md)|転送する最初の配列要素のインデックスを指定します。|  
|[last_is](../windows/last-is.md)|転送する最後の配列要素のインデックスを指定します。|  
|[length_is](../windows/length-is.md)|転送する配列要素の数を指定します。|  
|[max_is](../windows/max-is.md)|有効な配列のインデックスの最大値を指定します。|  
|[size_is](../windows/size-is.md)|メモリのサイズがサイズのポインターに割り当てられた、サイズのポインター、および 1 次元または多次元配列へのポインターのサイズを指定します。|  
|[unique](../windows/unique-cpp.md)|一意のポインターを指定します。|  
|[uuid](../windows/uuid-cpp-attributes.md)|クラスまたはインターフェイスの一意の ID を指定します。|  
  
### <a name="nonencapsulated-union"></a>カプセル化されていない共用体  
  
|属性|説明|  
|---------------|-----------------|  
|[ms_union](../windows/ms-union.md)|カプセル化されていない共用体のネットワーク データ表現の整列を制御します。|  
|[no_injected_text](../windows/no-injected-text.md)|コンパイラがコードの属性を使用した結果として挿入するを防ぎます。|  
  
### <a name="struct"></a>struct  
  
|属性|説明|  
|---------------|-----------------|  
|[aggregatable](../windows/aggregatable.md)|クラスは、集計をサポートしていることを示します。|  
|[aggregates](../windows/aggregates.md)|コントロールがターゲット クラスを集約することを示します。|  
|[appobject](../windows/appobject.md)|完全な .exe アプリケーションに関連付けられ、関数と、コクラスのプロパティがグローバルに使用できるこのタイプ ライブラリを示しますアプリケーション オブジェクトとしてコクラスを識別します。|  
|[coclass](../windows/coclass.md)|ActiveX コントロールを作成します。|  
|[com_interface_entry](../windows/com-interface-entry-cpp.md)|COM マップには、インターフェイスのエントリを追加します。|  
|[control](../windows/control.md)|コントロールに、ユーザー定義型を指定します。|  
|[custom](../windows/custom-cpp.md)|独自の属性を定義できます。|  
|[db_column](../windows/db-column.md)|行セットに指定された列をバインドします。|  
|[db_command](../windows/db-command.md)|OLE DB コマンドを作成します。|  
|[db_param](../windows/db-param.md)|入力または出力パラメーターを使用して、指定したメンバー変数を関連付けるし、変数を区切ります。|  
|[db_source](../windows/db-source.md)|データ ソースへの接続を作成します。|  
|[db_table](../windows/db-table.md)|OLE DB、テーブルを開きます。|  
|[default](../windows/default-cpp.md)|コクラス内で定義されるカスタムまたはディスパッチ インターフェイスが既定のプログラミング インターフェイスを表すことを示します。|  
|[defaultvtable](../windows/defaultvtable.md)|コントロールの既定の vtable インターフェイスとしてインターフェイスを定義します。|  
|[event_receiver](../windows/event-receiver.md)|イベント レシーバーを作成します。|  
|[event_source](../windows/event-source.md)|イベント ソースを作成します。|  
|[export](../windows/export.md)|.Idl ファイルに配置するデータ構造をによりします。|  
|[first_is](../windows/first-is.md)|転送する最初の配列要素のインデックスを指定します。|  
|[hidden](../windows/hidden.md)|項目が存在しますが、ユーザー指向ブラウザーで表示する必要がありますされませんを示します。|  
|[implements_category](../windows/implements-category.md)|クラスの実装されたコンポーネントのカテゴリを指定します。|  
|[last_is](../windows/last-is.md)|転送する最後の配列要素のインデックスを指定します。|  
|[length_is](../windows/length-is.md)|転送する配列要素の数を指定します。|  
|[max_is](../windows/max-is.md)|有効な配列のインデックスの最大値を指定します。|  
|[requires_category](../windows/requires-category.md)|ターゲット クラスの必須コンポーネントのカテゴリを指定します。|  
|[size_is](../windows/size-is.md)|メモリのサイズがサイズのポインターに割り当てられた、サイズのポインター、および 1 次元または多次元配列へのポインターのサイズを指定します。|  
|[source](../windows/source-cpp.md)|クラスの場合、接続ポイント用の COM オブジェクトのソース インターフェイスを指定します。 プロパティまたはメソッドでは、オブジェクトまたはイベントのソースをバリアントにメンバーを返すことを示します。|  
|[スレッド処理](../windows/threading-cpp.md)|COM オブジェクトのスレッド モデルを指定します。|  
|[unique](../windows/unique-cpp.md)|一意のポインターを指定します。|  
|[uuid](../windows/uuid-cpp-attributes.md)|クラスまたはインターフェイスの一意の ID を指定します。|  
|[version](../windows/version-cpp.md)|クラスの複数のバージョン間で特定のバージョンを識別します。|  
|[vi_progid](../windows/vi-progid.md)|ProgID のバージョンに依存しない形式を指定します。|  
  
## <a name="see-also"></a>関連項目  
 [使用法別の属性](../windows/attributes-by-usage.md)