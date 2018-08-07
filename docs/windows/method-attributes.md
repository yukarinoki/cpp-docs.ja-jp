---
title: メソッドの属性 |Microsoft Docs
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
ms.openlocfilehash: 1850507b9d00ab717a2602d4e230968f5222f077
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2018
ms.locfileid: "39604282"
---
# <a name="method-attributes"></a>メソッド属性
次の属性は、クラス、コクラスまたはインターフェイスのメソッドに適用されます。  
  
|属性|説明|  
|---------------|-----------------|  
|[bindable](../windows/bindable.md)|プロパティがデータ バインディングをサポートすることを示します。|  
|[call_as](../windows/call-as.md)|リモート関数にマップするリモート処理不可能関数を使用できます。|  
|[custom](../windows/custom-cpp.md)|独自の属性を定義できます。|  
|[db_column](../windows/db-column.md)|行セットに指定された列をバインドします。|  
|[db_command](../windows/db-command.md)|OLE DB コマンドを作成します。|  
|[db_param](../windows/db-param.md)|入力または出力パラメーターを使用して、指定したメンバー変数を関連付けるし、変数を区切ります。|  
|[db_source](../windows/db-source.md)|データ ソースへの接続を作成します。|  
|[db_table](../windows/db-table.md)|OLE DB、テーブルを開きます。|  
|[defaultbind](../windows/defaultbind.md)|オブジェクトを最もよく表す単一のバインド可能なプロパティを示します。|  
|[defaultcollelem](../windows/defaultcollelem.md)|Visual Basic コードの最適化に使用されます。|  
|[displaybind](../windows/displaybind.md)|バインド可能なユーザーに表示されるプロパティを示します。|  
|[helpcontext](../windows/helpcontext.md)|ユーザーがヘルプ ファイル内のこの要素についての情報を表示できるようにコンテキスト ID を指定します。|  
|[helpfile](../windows/helpfile.md)|タイプ ライブラリのヘルプ ファイルの名前を設定します。|  
|[helpstring](../windows/helpstring.md)|適用先となる要素を記述するために使用される文字列を指定します。|  
|[helpstringcontext](../windows/helpstringcontext.md)|.Hlp または .chm ファイルをヘルプ トピックの ID を指定します。|  
|[helpstringdll](../windows/helpstringdll.md)|使用してドキュメントの文字列の検索 (ローカライズ) を実行する DLL の名前を指定します。|  
|[hidden](../windows/hidden.md)|項目が存在しますが、ユーザー指向ブラウザーで表示する必要がありますされませんを示します。|  
|[ID](../windows/id.md)|メンバー関数 (プロパティまたはメソッド、インターフェイスまたは dispinterface) のように DISPID を指定します。|  
|[immediatebind](../windows/immediatebind.md)|データ バインド オブジェクトのプロパティに対するすべての変更のデータベースに直ちに通知されることを示します。|  
|[in](../windows/in-cpp.md)|呼び出し元のプロシージャから呼び出されたプロシージャに渡されるパラメーターがあることを示します。|  
|[local](../windows/local-cpp.md)|インターフェイスのヘッダーで使用する場合は、ヘッダー ジェネレーターとして、MIDL コンパイラを使用することができます。 個々 の関数で使用する場合は、スタブが生成されたないローカル プロシージャを指定します。|  
|[nonbrowsable](../windows/nonbrowsable.md)|インターフェイス メンバーをプロパティ ブラウザーに表示されないことを示します。|  
|[propget](../windows/propget.md)|プロパティのアクセサー関数を指定します。|  
|[propput](../windows/propput.md)|プロパティ設定関数を指定します。|  
|[propputref](../windows/propputref.md)|値の代わりに参照を使用するプロパティ設定関数を指定します。|  
|[ptr](../windows/ptr.md)|完全なポインターとしてのポインターを指定します。|  
|[range](../windows/range-cpp.md)|引数または値を持つが実行時に設定されているフィールドに使用できる値の範囲を指定します。|  
|[requestedit](../windows/requestedit.md)|プロパティをサポートしていることを示します、`OnRequestEdit`通知します。|  
|[restricted](../windows/restricted.md)|モジュール、インターフェイス、またはディスパッチ インターフェイスのメンバーを任意に呼び出すことはできませんを指定します。|  
|[satype](../windows/satype.md)|データ型を指定します、`SAFEARRAY`構造体。|  
|[source](../windows/source-cpp.md)|コネクション ポイントのソース インターフェイスのコントロールのクラスを指定します。 プロパティまたはメソッドで、`source`属性では、オブジェクトまたはイベントのソースをバリアントにメンバーを返すことを示します。|  
|[synchronize](../windows/synchronize.md)|ターゲット メソッドへのアクセスを同期します。|  
|[vararg](../windows/vararg.md)|関数が可変個の引数を実行することを指定します。|  
  
## <a name="see-also"></a>関連項目  
 [使用法別の属性](../windows/attributes-by-usage.md)