---
title: Typedef、Enum、Union、および Struct 属性 (C++ COM)
ms.date: 10/02/2018
helpviewer_keywords:
- union attributes
- attributes [C++/CLI], reference topics
ms.assetid: f8a4fe94-dc02-4aed-bc31-3e500d42f4c7
ms.openlocfilehash: fdc380cdc207361a145862f87d809a4bcea01c27
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214475"
---
# <a name="typedef-enum-union-and-struct-attributes"></a>Typedef、Enum、Union、および Struct 型の属性

[Typedef](../../cpp/aliases-and-typedefs-cpp.md)、 [struct](../../cpp/struct-cpp.md)、および[enum](../../cpp/enumerations-cpp.md) C++キーワードには、次の属性が適用されます。

### <a name="typedef"></a>Typedef

|Attribute|説明|
|---------------|-----------------|
|[case](case-cpp.md)|**共用体**の[switch_type](switch-type.md)属性と共に使用されます。|
|[custom](custom-cpp.md)|では、独自の属性を定義できます。|
|[export](export.md)|データ構造を .idl ファイルに配置します。|
|[first_is](first-is.md)|転送される最初の配列要素のインデックスを指定します。|
|[helpcontext](helpcontext.md)|ヘルプファイル内のこの要素に関する情報をユーザーが表示できるようにするコンテキスト ID を指定します。|
|[helpfile](helpfile.md)|タイプライブラリのヘルプファイルの名前を設定します。|
|[helpstring](helpstring.md)|適用先となる要素を記述するために使用される文字列を指定します。|
|[library_block](library-block.md)|.Idl ファイルのライブラリブロック内にコンストラクトを配置します。|
|[ptr](ptr.md)|ポインターをフルポインターとして指定します。|
|[public](public-cpp-attributes.md)|は、.idl ファイル内から参照されていない場合でも、typedef がタイプライブラリに入ることを保証します。|
|[ref](ref-cpp.md)|参照ポインターを識別します。|
|[switch_is](switch-is.md)|共用体メンバーを選択する union 判別として機能する式または識別子を指定します。|
|[switch_type](switch-type.md)|Union 判別として使用される変数の型を識別します。|
|[unique](unique-cpp.md)|一意のポインターを指定します。|
|[wire_marshal](wire-marshal.md)|アプリケーション固有のデータ型ではなく、転送に使用されるデータ型を指定します。|

### <a name="enum"></a>enum

|Attribute|説明|
|---------------|-----------------|
|[custom](custom-cpp.md)|では、独自の属性を定義できます。|
|[export](export.md)|データ構造を .idl ファイルに配置します。|
|[uuid](uuid-cpp-attributes.md)|クラスまたはインターフェイスの一意の ID を指定します。|
|[v1_enum](v1-enum.md)|指定された列挙型を16ビットの既定値ではなく、32ビットのエンティティとして送信するように指示します。|

### <a name="union"></a>union

|Attribute|説明|
|---------------|-----------------|
|[custom](custom-cpp.md)|では、独自の属性を定義できます。|
|[export](export.md)|データ構造を .idl ファイルに配置します。|
|[first_is](first-is.md)|転送される最初の配列要素のインデックスを指定します。|
|[last_is](last-is.md)|転送する最後の配列要素のインデックスを指定します。|
|[length_is](length-is.md)|転送する配列要素の数を指定します。|
|[max_is](max-is.md)|有効な配列インデックスの最大値を指定します。|
|[size_is](size-is.md)|サイズポインターに割り当てられたメモリのサイズ、サイズ設定されたポインターへのサイズポインター、および単一または多次元の配列を指定します。|
|[unique](unique-cpp.md)|一意のポインターを指定します。|
|[uuid](uuid-cpp-attributes.md)|クラスまたはインターフェイスの一意の ID を指定します。|

### <a name="nonencapsulated-union"></a>カプセル化されていない共用体

|Attribute|説明|
|---------------|-----------------|
|[ms_union](ms-union.md)|カプセル化されていない共用体のネットワークデータ表現の配置を制御します。|
|[no_injected_text](no-injected-text.md)|属性の使用によってコードが挿入されないようにします。|

### <a name="struct"></a>struct

|Attribute|説明|
|---------------|-----------------|
|[aggregatable](aggregatable.md)|クラスが集計をサポートしていることを示します。|
|[aggregates](aggregates.md)|コントロールがターゲットクラスを集計することを示します。|
|[appobject](appobject.md)|コクラスをアプリケーションオブジェクトとして識別します。このオブジェクトは、完全な .exe アプリケーションに関連付けられています。また、コクラスの関数とプロパティは、このタイプライブラリでグローバルに使用できることを示します。|
|[coclass](coclass.md)|ActiveX コントロールを作成します。|
|[com_interface_entry](com-interface-entry-cpp.md)|COM マップにインターフェイスエントリを追加します。|
|[control](control.md)|ユーザー定義型がコントロールであることを指定します。|
|[custom](custom-cpp.md)|では、独自の属性を定義できます。|
|[db_column](db-column.md)|指定された列を行セットにバインドします。|
|[db_command](db-command.md)|OLE DB コマンドを作成します。|
|[db_param](db-param.md)|指定されたメンバー変数を入力パラメーターまたは出力パラメーターに関連付けて、その変数を区切ります。|
|[db_source](db-source.md)|データソースへの接続を作成します。|
|[db_table](db-table.md)|OLE DB テーブルを開きます。|
|[既定値](default-cpp.md)|コクラス内で定義されるカスタムまたはディスパッチ インターフェイスが既定のプログラミング インターフェイスを表すことを示します。|
|[defaultvtable](defaultvtable.md)|コントロールの既定の vtable インターフェイスとしてインターフェイスを定義します。|
|[event_receiver](event-receiver.md)|イベントレシーバーを作成します。|
|[event_source](event-source.md)|イベント ソースを作成します。|
|[export](export.md)|データ構造を .idl ファイルに配置します。|
|[first_is](first-is.md)|転送される最初の配列要素のインデックスを指定します。|
|[hidden](hidden.md)|項目が存在するが、ユーザー指向のブラウザーに表示されないことを示します。|
|[implements_category](implements-category.md)|クラスに実装されているコンポーネントのカテゴリを指定します。|
|[last_is](last-is.md)|転送する最後の配列要素のインデックスを指定します。|
|[length_is](length-is.md)|転送する配列要素の数を指定します。|
|[max_is](max-is.md)|有効な配列インデックスの最大値を指定します。|
|[requires_category](requires-category.md)|ターゲットクラスの必須コンポーネントカテゴリを指定します。|
|[size_is](size-is.md)|サイズポインターに割り当てられたメモリのサイズ、サイズ設定されたポインターへのサイズポインター、および単一または多次元の配列を指定します。|
|[source](source-cpp.md)|クラスで、COM オブジェクトの接続ポイントのソースインターフェイスを指定します。 プロパティまたはメソッドで、メンバーがイベントのソースであるオブジェクトまたはバリアントを返すことを示します。|
|[threading](threading-cpp.md)|COM オブジェクトのスレッド処理モデルを指定します。|
|[unique](unique-cpp.md)|一意のポインターを指定します。|
|[uuid](uuid-cpp-attributes.md)|クラスまたはインターフェイスの一意の ID を指定します。|
|[version](version-cpp.md)|クラスの複数のバージョン間で特定のバージョンを識別します。|
|[vi_progid](vi-progid.md)|バージョンに依存しない ProgID の形式を指定します。|

## <a name="see-also"></a>参照

[使用法別の属性](attributes-by-usage.md)
