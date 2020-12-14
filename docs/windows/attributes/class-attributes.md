---
description: '詳細情報: クラス属性'
title: クラス属性 (C++ COM)
ms.date: 10/02/2018
helpviewer_keywords:
- attributes [C++/CLI], class attributes
ms.assetid: fad04ea1-d8ff-46d4-bb42-2b4500a6ab60
ms.openlocfilehash: ea929ed7f5fac949393e6d3cf2b24195babfeea7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247385"
---
# <a name="class-attributes"></a>クラス属性

[クラス](../../cpp/class-cpp.md)C++ のキーワードには、次の属性が適用されます。

|属性|説明|
|---------------|-----------------|
|[aggregatable](aggregatable.md)|クラスが集計をサポートしていることを示します。|
|[集計](aggregates.md)|コントロールがターゲットクラスを集計することを示します。|
|[appobject](appobject.md)|コクラスをアプリケーションオブジェクトとして識別します。このオブジェクトは、完全な .exe アプリケーションに関連付けられています。また、コクラスの関数とプロパティは、このタイプライブラリでグローバルに使用できることを示します。|
|[case](case-cpp.md)|共用体の [switch_type](switch-type.md) 属性と共に使用されます。|
|[coclass](coclass.md)|ActiveX コントロールを作成します。|
|[com_interface_entry](com-interface-entry-cpp.md)|COM マップにインターフェイスエントリを追加します。|
|[control](control.md)|ユーザー定義型がコントロールであることを指定します。|
|[ショー](custom-cpp.md)|では、独自の属性を定義できます。|
|[db_command](db-command.md)|OLE DB コマンドを作成します。|
|[db_param](db-param.md)|指定されたメンバー変数を入力パラメーターまたは出力パラメーターに関連付けて、その変数を区切ります。|
|[db_source](db-source.md)|データソースへの接続を作成します。|
|[db_table](db-table.md)|OLE DB テーブルを開きます。|
|[default](default-cpp.md)|コクラス内で定義されるカスタムまたはディスパッチ インターフェイスが既定のプログラミング インターフェイスを表すことを示します。|
|[defaultvtable](defaultvtable.md)|コントロールの既定の vtable インターフェイスとしてインターフェイスを定義します。|
|[event_receiver](event-receiver.md)|イベントレシーバーを作成します。|
|[event_source](event-source.md)|イベント ソースを作成します。|
|[helpcontext](helpcontext.md)|**ヘルプ** ファイル内のこの要素に関する情報をユーザーが表示できるようにするコンテキスト ID を指定します。|
|[helpfile](helpfile.md)|タイプライブラリのヘルプファイルの名前を設定します。|
|[helpstringcontext](helpstringcontext.md)|.Hlp または .chm ファイルのヘルプトピックの ID を指定します。|
|[helpstring](helpstring.md)|適用先となる要素を記述するために使用される文字列を指定します。|
|[表示](hidden.md)|項目が存在するが、ユーザー指向のブラウザーに表示されないことを示します。|
|[実装](implements-cpp.md)|IDL コクラスのメンバーとして強制されるディスパッチインターフェイスを指定します。|
|[implements_category](implements-category.md)|クラスに実装されているコンポーネントのカテゴリを指定します。|
|[第](module-cpp.md)|.idl ファイルのライブラリ ブロックを定義します。|
|[noncreatable](noncreatable.md)|単独ではインスタンス化できないオブジェクトを定義します。|
|[progid](progid.md)|コントロールの ProgID を定義します。|
|[registration_script](registration-script.md)|指定された登録スクリプトを実行します。|
|[requestedit](requestedit.md)|`OnRequestEdit` 通知がプロパティでサポートされることを示します。|
|[source](source-cpp.md)|クラスの接続ポイントのコントロールのソースインターフェイスを指定します。 プロパティまたはメソッドでは、 `source` 属性は、メンバーがオブジェクトを返すか、またはイベントのソースであることを示し `VARIANT` ます。|
|[support_error_info](support-error-info.md)|ターゲットオブジェクトのエラー報告をサポートします。|
|[おける](threading-cpp.md)|コントロールのスレッド処理モデルを指定します。|
|[uuid](uuid-cpp-attributes.md)|クラスまたはインターフェイスの一意の ID を指定します。|
|[version](version-cpp.md)|クラスの複数のバージョン間で特定のバージョンを識別します。|
|[vi_progid](vi-progid.md)|バージョンに依存しない ProgID の形式を指定します。|

## <a name="see-also"></a>関連項目

[使用法別の属性](attributes-by-usage.md)
