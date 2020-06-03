---
title: クラス属性 (C++ COM)
ms.date: 10/02/2018
helpviewer_keywords:
- attributes [C++/CLI], class attributes
ms.assetid: fad04ea1-d8ff-46d4-bb42-2b4500a6ab60
ms.openlocfilehash: 5e10b7831e59211b73ce947ac21e43bc1a8af1c9
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80167317"
---
# <a name="class-attributes"></a>クラス属性

[Class](../../cpp/class-cpp.md) C++キーワードには、次の属性が適用されます。

|Attribute|説明|
|---------------|-----------------|
|[aggregatable](aggregatable.md)|クラスが集計をサポートしていることを示します。|
|[aggregates](aggregates.md)|コントロールがターゲットクラスを集計することを示します。|
|[appobject](appobject.md)|コクラスをアプリケーションオブジェクトとして識別します。このオブジェクトは、完全な .exe アプリケーションに関連付けられています。また、コクラスの関数とプロパティは、このタイプライブラリでグローバルに使用できることを示します。|
|[case](case-cpp.md)|共用体の[switch_type](switch-type.md)属性と共に使用されます。|
|[coclass](coclass.md)|ActiveX コントロールを作成します。|
|[com_interface_entry](com-interface-entry-cpp.md)|COM マップにインターフェイスエントリを追加します。|
|[control](control.md)|ユーザー定義型がコントロールであることを指定します。|
|[custom](custom-cpp.md)|では、独自の属性を定義できます。|
|[db_command](db-command.md)|OLE DB コマンドを作成します。|
|[db_param](db-param.md)|指定されたメンバー変数を入力パラメーターまたは出力パラメーターに関連付けて、その変数を区切ります。|
|[db_source](db-source.md)|データソースへの接続を作成します。|
|[db_table](db-table.md)|OLE DB テーブルを開きます。|
|[既定値](default-cpp.md)|コクラス内で定義されるカスタムまたはディスパッチ インターフェイスが既定のプログラミング インターフェイスを表すことを示します。|
|[defaultvtable](defaultvtable.md)|コントロールの既定の vtable インターフェイスとしてインターフェイスを定義します。|
|[event_receiver](event-receiver.md)|イベントレシーバーを作成します。|
|[event_source](event-source.md)|イベント ソースを作成します。|
|[helpcontext](helpcontext.md)|**ヘルプ**ファイル内のこの要素に関する情報をユーザーが表示できるようにするコンテキスト ID を指定します。|
|[helpfile](helpfile.md)|タイプライブラリのヘルプファイルの名前を設定します。|
|[helpstringcontext](helpstringcontext.md)|.Hlp または .chm ファイルのヘルプトピックの ID を指定します。|
|[helpstring](helpstring.md)|適用先となる要素を記述するために使用される文字列を指定します。|
|[hidden](hidden.md)|項目が存在するが、ユーザー指向のブラウザーに表示されないことを示します。|
|[implements](implements-cpp.md)|IDL コクラスのメンバーとして強制されるディスパッチインターフェイスを指定します。|
|[implements_category](implements-category.md)|クラスに実装されているコンポーネントのカテゴリを指定します。|
|[name](module-cpp.md)|.idl ファイルのライブラリ ブロックを定義します。|
|[noncreatable](noncreatable.md)|単独ではインスタンス化できないオブジェクトを定義します。|
|[progid](progid.md)|コントロールの ProgID を定義します。|
|[registration_script](registration-script.md)|指定された登録スクリプトを実行します。|
|[requestedit](requestedit.md)|`OnRequestEdit` 通知がプロパティでサポートされることを示します。|
|[source](source-cpp.md)|クラスの接続ポイントのコントロールのソースインターフェイスを指定します。 プロパティまたはメソッドでは、`source` 属性は、メンバーがイベントのソースであるオブジェクトまたは `VARIANT` を返すことを示します。|
|[support_error_info](support-error-info.md)|ターゲットオブジェクトのエラー報告をサポートします。|
|[threading](threading-cpp.md)|コントロールのスレッド処理モデルを指定します。|
|[uuid](uuid-cpp-attributes.md)|クラスまたはインターフェイスの一意の ID を指定します。|
|[version](version-cpp.md)|クラスの複数のバージョン間で特定のバージョンを識別します。|
|[vi_progid](vi-progid.md)|バージョンに依存しない ProgID の形式を指定します。|

## <a name="see-also"></a>参照

[使用法別の属性](attributes-by-usage.md)
