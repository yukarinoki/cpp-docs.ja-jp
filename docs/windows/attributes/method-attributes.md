---
title: メソッド属性 (C++ COM)
ms.date: 10/02/2018
helpviewer_keywords:
- method attributes
- attributes [C++/CLI], reference topics
ms.assetid: b2313352-480d-488b-8c35-6242ffd3a549
ms.openlocfilehash: c9823869be96f53a3c4fbc36c7b56e1bea0a1303
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166771"
---
# <a name="method-attributes"></a>メソッド属性

クラス、コクラス、またはインターフェイスのメソッドには、次の属性が適用されます。

|Attribute|説明|
|---------------|-----------------|
|[bindable](bindable.md)|プロパティがデータ バインディングをサポートすることを示します。|
|[call_as](call-as.md)|リモート処理不可能関数をリモート関数にマップできるようにします。|
|[custom](custom-cpp.md)|では、独自の属性を定義できます。|
|[db_column](db-column.md)|指定された列を行セットにバインドします。|
|[db_command](db-command.md)|OLE DB コマンドを作成します。|
|[db_param](db-param.md)|指定されたメンバー変数を入力パラメーターまたは出力パラメーターに関連付けて、その変数を区切ります。|
|[db_source](db-source.md)|データソースへの接続を作成します。|
|[db_table](db-table.md)|OLE DB テーブルを開きます。|
|[defaultbind](defaultbind.md)|オブジェクトを最もよく表す、1つのバインド可能なプロパティを示します。|
|[defaultcollelem](defaultcollelem.md)|Visual Basic コードの最適化に使用します。|
|[displaybind](displaybind.md)|バインド可能としてユーザーに表示される必要があるプロパティを示します。|
|[helpcontext](helpcontext.md)|**ヘルプ**ファイル内のこの要素に関する情報をユーザーが表示できるようにするコンテキスト ID を指定します。|
|[helpfile](helpfile.md)|タイプライブラリの**ヘルプ**ファイルの名前を設定します。|
|[helpstring](helpstring.md)|適用先となる要素を記述するために使用される文字列を指定します。|
|[helpstringcontext](helpstringcontext.md)|.Hlp または .chm ファイルのヘルプトピックの ID を指定します。|
|[helpstringdll](helpstringdll.md)|ドキュメント文字列参照 (ローカライズ) を実行するために使用する DLL の名前を指定します。|
|[hidden](hidden.md)|項目が存在するが、ユーザー指向のブラウザーに表示されないことを示します。|
|[id](id.md)|メンバー関数 (インターフェイスまたはディスパッチインターフェイスのプロパティまたはメソッド) の DISPID を指定します。|
|[immediatebind](immediatebind.md)|データバインドオブジェクトのプロパティに対するすべての変更が、すぐにデータベースに通知されることを示します。|
|[in](in-cpp.md)|呼び出し元プロシージャから呼び出されたプロシージャにパラメーターが渡されることを示します。|
|[local](local-cpp.md)|インターフェイスヘッダーで使用するときに、MIDL コンパイラをヘッダージェネレーターとして使用できるようにします。 個々の関数で使用する場合は、スタブが生成されないローカルプロシージャを指定します。|
|[nonbrowsable](nonbrowsable.md)|インターフェイスメンバーをプロパティブラウザーに表示しないことを示します。|
|[propget](propget.md)|プロパティアクセサー関数を指定します。|
|[propput](propput.md)|プロパティ設定関数を指定します。|
|[propputref](propputref.md)|値ではなく参照を使用するプロパティ設定関数を指定します。|
|[ptr](ptr.md)|ポインターをフルポインターとして指定します。|
|[range](range-cpp.md)|実行時に値が設定される引数またはフィールドに使用できる値の範囲を指定します。|
|[requestedit](requestedit.md)|`OnRequestEdit` 通知がプロパティでサポートされることを示します。|
|[restricted](restricted.md)|モジュール、インターフェイス、またはディスパッチインターフェイスのメンバーを任意に呼び出すことができないことを指定します。|
|[satype](satype.md)|`SAFEARRAY` 構造体のデータ型を指定します。|
|[source](source-cpp.md)|クラスの接続ポイントのコントロールのソースインターフェイスを指定します。 プロパティまたはメソッドでは、`source` 属性は、メンバーがイベントのソースであるオブジェクトまたはバリアントを返すことを示します。|
|[synchronize](synchronize.md)|ターゲットメソッドへのアクセスを同期します。|
|[vararg](vararg.md)|関数が可変個の引数を受け取ることを指定します。|

## <a name="see-also"></a>参照

[使用法別の属性](attributes-by-usage.md)
