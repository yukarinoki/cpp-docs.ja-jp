---
description: '詳細情報: メソッド属性'
title: メソッド属性 (C++ COM)
ms.date: 10/02/2018
helpviewer_keywords:
- method attributes
- attributes [C++/CLI], reference topics
ms.assetid: b2313352-480d-488b-8c35-6242ffd3a549
ms.openlocfilehash: 29acb1f92b01e85960bc727c9b3e91f9a52732d5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327496"
---
# <a name="method-attributes"></a>メソッド属性

クラス、コクラス、またはインターフェイスのメソッドには、次の属性が適用されます。

|属性|説明|
|---------------|-----------------|
|[bindable](bindable.md)|プロパティがデータ バインディングをサポートすることを示します。|
|[call_as](call-as.md)|リモート処理不可能関数をリモート関数にマップできるようにします。|
|[ショー](custom-cpp.md)|では、独自の属性を定義できます。|
|[db_column](db-column.md)|指定された列を行セットにバインドします。|
|[db_command](db-command.md)|OLE DB コマンドを作成します。|
|[db_param](db-param.md)|指定されたメンバー変数を入力パラメーターまたは出力パラメーターに関連付けて、その変数を区切ります。|
|[db_source](db-source.md)|データソースへの接続を作成します。|
|[db_table](db-table.md)|OLE DB テーブルを開きます。|
|[defaultbind](defaultbind.md)|オブジェクトを最もよく表す、1つのバインド可能なプロパティを示します。|
|[defaultcollelem](defaultcollelem.md)|Visual Basic コードの最適化に使用します。|
|[displaybind](displaybind.md)|バインド可能としてユーザーに表示される必要があるプロパティを示します。|
|[helpcontext](helpcontext.md)|**ヘルプ** ファイル内のこの要素に関する情報をユーザーが表示できるようにするコンテキスト ID を指定します。|
|[helpfile](helpfile.md)|タイプライブラリの **ヘルプ** ファイルの名前を設定します。|
|[helpstring](helpstring.md)|適用先となる要素を記述するために使用される文字列を指定します。|
|[helpstringcontext](helpstringcontext.md)|.Hlp または .chm ファイルのヘルプトピックの ID を指定します。|
|[typelib](helpstringdll.md)|ドキュメント文字列参照 (ローカライズ) を実行するために使用する DLL の名前を指定します。|
|[表示](hidden.md)|項目が存在するが、ユーザー指向のブラウザーに表示されないことを示します。|
|[id](id.md)|メンバー関数 (インターフェイスまたはディスパッチインターフェイスのプロパティまたはメソッド) の DISPID を指定します。|
|[immediatebind](immediatebind.md)|データバインドオブジェクトのプロパティに対するすべての変更が、すぐにデータベースに通知されることを示します。|
|[in](in-cpp.md)|呼び出し元プロシージャから呼び出されたプロシージャにパラメーターが渡されることを示します。|
|[地元の](local-cpp.md)|インターフェイスヘッダーで使用するときに、MIDL コンパイラをヘッダージェネレーターとして使用できるようにします。 個々の関数で使用する場合は、スタブが生成されないローカルプロシージャを指定します。|
|[nonbrowsable](nonbrowsable.md)|インターフェイスメンバーをプロパティブラウザーに表示しないことを示します。|
|[propget](propget.md)|プロパティアクセサー関数を指定します。|
|[propput](propput.md)|プロパティ設定関数を指定します。|
|[propputref](propputref.md)|値ではなく参照を使用するプロパティ設定関数を指定します。|
|[ptr](ptr.md)|ポインターをフルポインターとして指定します。|
|[range](range-cpp.md)|実行時に値が設定される引数またはフィールドに使用できる値の範囲を指定します。|
|[requestedit](requestedit.md)|`OnRequestEdit` 通知がプロパティでサポートされることを示します。|
|[限定](restricted.md)|モジュール、インターフェイス、またはディスパッチインターフェイスのメンバーを任意に呼び出すことができないことを指定します。|
|[satype](satype.md)|構造体のデータ型を指定し `SAFEARRAY` ます。|
|[source](source-cpp.md)|クラスの接続ポイントのコントロールのソースインターフェイスを指定します。 プロパティまたはメソッドでは、 `source` 属性は、メンバーがイベントのソースであるオブジェクトまたはバリアントを返すことを示します。|
|[化](synchronize.md)|ターゲットメソッドへのアクセスを同期します。|
|[vararg](vararg.md)|関数が可変個の引数を受け取ることを指定します。|

## <a name="see-also"></a>関連項目

[使用法別の属性](attributes-by-usage.md)
