---
title: メソッドの属性 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- method attributes
- attributes [C++], reference topics
ms.assetid: b2313352-480d-488b-8c35-6242ffd3a549
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9d2efe55058ab2ace7530afee7255b2ba08377b0
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33879823"
---
# <a name="method-attributes"></a>メソッド属性
次の属性は、クラス、コクラス、またはインターフェイスのメソッドに適用されます。  
  
|属性|説明|  
|---------------|-----------------|  
|[bindable](../windows/bindable.md)|プロパティがデータ バインディングをサポートしていることを示します。|  
|[call_as](../windows/call-as.md)|リモート関数にマップするリモート処理不可能関数を有効にします。|  
|[custom](../windows/custom-cpp.md)|独自の属性を定義できます。|  
|[db_column](../windows/db-column.md)|行セットに指定された列をバインドします。|  
|[db_command](../windows/db-command.md)|OLE DB コマンドを作成します。|  
|[db_param](../windows/db-param.md)|入力または出力パラメーターを持つ指定したメンバー変数を関連付けるし、変数を区切ります。|  
|[db_source](../windows/db-source.md)|データ ソースへの接続を作成します。|  
|[db_table](../windows/db-table.md)|OLE DB テーブルを開きます。|  
|[defaultbind](../windows/defaultbind.md)|1 つのバインド可能なプロパティ オブジェクトを最も良く表すものを示します。|  
|[defaultcollelem](../windows/defaultcollelem.md)|Visual Basic コードの最適化に使用されます。|  
|[displaybind](../windows/displaybind.md)|バインド可能なとしてユーザーに表示されるプロパティを示します。|  
|[helpcontext](../windows/helpcontext.md)|コンテキスト ID をユーザーに関する情報を表示、ヘルプ ファイル内のこの要素を指定します。|  
|[helpfile](../windows/helpfile.md)|タイプ ライブラリのヘルプ ファイルの名前を設定します。|  
|[helpstring](../windows/helpstring.md)|適用すると、要素の記述に使用される文字の文字列を指定します。|  
|[helpstringcontext](../windows/helpstringcontext.md)|.Hlp または .chm ファイルには、ヘルプ トピックの ID を指定します。|  
|[helpstringdll](../windows/helpstringdll.md)|ドキュメントの文字列の検索 (ローカリゼーション) の実行に使用する DLL の名前を指定します。|  
|[hidden](../windows/hidden.md)|項目が存在しますが、ユーザー指向ブラウザーで表示する必要がありますされませんを示します。|  
|[ID](../windows/id.md)|メンバー関数 (プロパティまたはメソッド、インターフェイスまたはディスパッチ インターフェイス) の DISPID を指定します。|  
|[immediatebind](../windows/immediatebind.md)|データ バインドされたオブジェクトのプロパティに対するすべての変更のデータベースに直ちに通知されることを示します。|  
|[in](../windows/in-cpp.md)|パラメーターが呼び出し元のプロシージャから呼び出されたプロシージャに渡されることを示します。|  
|[local](../windows/local-cpp.md)|インターフェイスのヘッダーで使用する場合は、ヘッダー ジェネレーターとして MIDL コンパイラを使用できます。 個々 の関数で使用する場合は、対象のスタブが生成されないローカル プロシージャを指定します。|  
|[nonbrowsable](../windows/nonbrowsable.md)|インターフェイス メンバーをプロパティ ブラウザーで表示されないことを示します。|  
|[propget](../windows/propget.md)|プロパティ アクセサー関数を指定します。|  
|[propput](../windows/propput.md)|プロパティ設定関数を指定します。|  
|[propputref](../windows/propputref.md)|値の代わりに参照を使用するプロパティ設定関数を指定します。|  
|[ptr](../windows/ptr.md)|すべてのポインターとしてのポインターを指定します。|  
|[range](../windows/range-cpp.md)|引数または値が設定される実行時にフィールドに使用できる値の範囲を指定します。|  
|[requestedit](../windows/requestedit.md)|プロパティをサポートしていることを示します、 **OnRequestEdit**通知します。|  
|[restricted](../windows/restricted.md)|モジュール、インターフェイス、またはディスパッチ インターフェイスのメンバーを任意に呼び出すことができませんを指定します。|  
|[satype](../windows/satype.md)|データ型を指定します、 **SAFEARRAY**構造体。|  
|[ソース](../windows/source-cpp.md)|クラスのコネクション ポイント用のコントロールのソース インターフェイスを指定します。 プロパティまたはメソッドで、**ソース**属性は、メンバーがオブジェクトまたはイベントのソースであるバリアント型を返すことを示します。|  
|[synchronize](../windows/synchronize.md)|ターゲット メソッドへのアクセスを同期します。|  
|[vararg](../windows/vararg.md)|関数が可変個の引数を実行するように指定します。|  
  
## <a name="see-also"></a>関連項目  
 [使用法別の属性](../windows/attributes-by-usage.md)