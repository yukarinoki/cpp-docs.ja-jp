---
title: IDL 属性 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++], reference topics
- IDL attributes
- .idl files, attributes
- IDL files, attributes
- .idl files
ms.assetid: 04c596f4-c97b-4952-8053-316678b1d0b6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5c522c039a0471240ba319561485e8cc7f348aaa
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33881550"
---
# <a name="idl-attributes"></a>IDL 属性
従来、.idl ファイルを管理することを意図したをする必要があります。  
  
-   構造とそれを変更できる .idl ファイルの構文を理解します。  
  
-   .Idl ファイルの一部の側面を変更すると、ウィザードに依存します。  
  
 ここで、Visual C の IDL 属性を使用してソース コード ファイル内から .idl ファイルを変更することができます。 多くの場合は、Visual C の IDL 属性は、MIDL 属性と同じ名前を持ちます。 Visual C の IDL 属性と MIDL 属性の名前が同じ場合、ソース コード ファイルに、Visual C 属性を配置する原因になる、設立 MIDL 属性を含む .idl ファイルを意味します。 ただし、Visual C の IDL 属性では、MIDL 属性のすべての機能が提供されません可能性があります。  
  
 と共に使用しない場合[COM 属性](../windows/com-attributes.md)、IDL 属性を使用するインターフェイスを定義できます。 ソース コードのコンパイル時に、属性が生成された .idl ファイルの定義に使用されます。 ATL プロジェクトでの COM 属性と共に使用すると一部の IDL など、属性**コクラス**コードをプロジェクトに組み込まれない可能性があります。  
  
 なお[idl_quote](../windows/idl-quote.md) Visual C の現在のバージョンでサポートされていない MIDL コンストラクトを使用することができます。 これとその他の属性など、 [importlib](../windows/importlib.md)と[includelib](../windows/includelib-cpp.md)現在の Visual C プロジェクトで既存の .idl ファイルを使用するのに役立ちます。  
  
|属性|説明|  
|---------------|-----------------|  
|[aggregatable](../windows/aggregatable.md)|別のコントロールでコントロールを集計できることを示します。|  
|[appobject](../windows/appobject.md)|EXE アプリケーションを完全に関連付けられ、関数と、コクラスのプロパティがグローバルに使用できることでこのタイプ ライブラリを示すアプリケーション オブジェクトとしてコクラスを識別します。|  
|[async_uuid](../windows/async-uuid.md)|COM インターフェイスの同期および非同期の両方のバージョンを定義する MIDL コンパイラに指示する UUID を指定します。|  
|[bindable](../windows/bindable.md)|プロパティがデータ バインディングをサポートしていることを示します。|  
|[call_as](../windows/call-as.md)|リモート関数にマップするリモート処理不可能関数を有効にします。|  
|[case](../windows/case-cpp.md)|使用される、 [switch_type](../windows/switch-type.md)共用体の属性です。|  
|[coclass](../windows/coclass.md)|場所クラスはコクラスとして .idl ファイルに定義します。|  
|[control](../windows/control.md)|ユーザー定義型がコントロールであることを指定します。|  
|[cpp_quote](../windows/cpp-quote.md)|生成されるヘッダー ファイルに、引用符なしの指定した文字列を出力します。|  
|[defaultbind](../windows/defaultbind.md)|1 つのバインド可能なプロパティ オブジェクトを最も良く表すものを示します。|  
|[defaultcollelem](../windows/defaultcollelem.md)|Visual Basic コードの最適化に使用されます。|  
|[defaultvalue](../windows/defaultvalue.md)|型指定されたオプションのパラメーターの既定値を指定をできます。|  
|[default](../windows/default-cpp.md)|コクラス内で定義されるカスタムまたはディスパッチ インターフェイスが既定のプログラミング インターフェイスを表すことを示します。|  
|[defaultvtable](../windows/defaultvtable.md)|コントロールの既定の vtable インターフェイスとしてインターフェイスを定義します。|  
|[dispinterface](../windows/dispinterface.md)|ディスパッチ インターフェイスとしてインターフェイスを .idl ファイルに配置します。|  
|[displaybind](../windows/displaybind.md)|バインド可能なとしてユーザーに表示されるプロパティを示します。|  
|[dual](../windows/dual.md)|.Idl ファイル内のインターフェイスをデュアル インターフェイスとして配置します。|  
|[entry](../windows/entry.md)|モジュールで、DLL 内のエントリ ポイントを識別することによって、エクスポートされた関数または定数を指定します。|  
|[first_is](../windows/first-is.md)|転送する最初の配列要素のインデックスを指定します。|  
|[helpcontext](../windows/helpcontext.md)|コンテキスト ID をユーザーに関する情報を表示、ヘルプ ファイル内のこの要素を指定します。|  
|[helpfile](../windows/helpfile.md)|タイプ ライブラリのヘルプ ファイルの名前を設定します。|  
|[helpstringcontext](../windows/helpstringcontext.md)|.Hlp または .chm ファイルには、ヘルプ トピックの ID を指定します。|  
|[helpstringdll](../windows/helpstringdll.md)|ドキュメントの文字列の検索 (ローカリゼーション) の実行に使用する DLL の名前を指定します。|  
|[helpstring](../windows/helpstring.md)|適用すると、要素の記述に使用される文字の文字列を指定します。|  
|[hidden](../windows/hidden.md)|項目が存在しますが、ユーザー指向ブラウザーで表示する必要がありますされませんを示します。|  
|[idl_module](../windows/idl-module.md)|DLL のエントリ ポイントを指定します。|  
|[idl_quote](../windows/idl-quote.md)|属性を使用することができます。 または IDL コンストラクトは、現在のバージョンの Visual C ではサポートされていません。|  
|[ID](../windows/id.md)|メンバー関数 (プロパティまたはメソッド、インターフェイスまたはディスパッチ インターフェイス) の DISPID を指定します。|  
|[iid_is](../windows/iid-is.md)|インターフェイス ポインターによって指さ COM インターフェイスの IID を指定します。|  
|[immediatebind](../windows/immediatebind.md)|データ バインドされたオブジェクトのプロパティに対するすべての変更のデータベースに直ちに通知されることを示します。|  
|[importlib](../windows/importlib.md)|既に他のタイプ ライブラリでコンパイル済みの型を、作成中のタイプ ライブラリで使用できるようにします。|  
|[import](../windows/import.md)|メイン .idl ファイルから参照する定義を含む .idl、.odl ファイル、またはヘッダーの別のファイルを指定します。|  
|[include](../windows/include-cpp.md)|生成された .idl ファイルに含まれる 1 つまたは複数のヘッダー ファイルを指定します。|  
|[includelib](../windows/includelib-cpp.md)|生成された .idl ファイルに含まれる、.idl ファイルまたは .h ファイルが発生します。|  
|[in](../windows/in-cpp.md)|パラメーターが呼び出し元のプロシージャから呼び出されたプロシージャに渡されることを示します。|  
|[last_is](../windows/last-is.md)|転送する最後の配列要素のインデックスを指定します。|  
|[lcid](../windows/lcid.md)|ロケール識別子を関数に渡すことができます。|  
|[length_is](../windows/length-is.md)|転送する配列要素の数を指定します。|  
|[licensed](../windows/licensed.md)|使用してインスタンス化する必要がありますに適用すると、コクラスはライセンスされていることを示します**IClassFactory2**です。|  
|[local](../windows/local-cpp.md)|インターフェイスのヘッダーで使用する場合は、ヘッダー ジェネレーターとして MIDL コンパイラを使用できます。 個々 の関数で使用する場合は、対象のスタブが生成されないローカル プロシージャを指定します。|  
|[max_is](../windows/max-is.md)|有効な配列インデックスの最大値を指定します。|  
|[モジュール](../windows/module-cpp.md)|.idl ファイルのライブラリ ブロックを定義します。|  
|[ms_union](../windows/ms-union.md)|カプセル化されていない共用体のネットワーク データ表現のアラインメントを制御します。|  
|[no_injected_text](../windows/no-injected-text.md)|コンパイラがコードの属性を使用した結果として挿入するを防ぎます。|  
|[nonbrowsable](../windows/nonbrowsable.md)|インターフェイス メンバーをプロパティ ブラウザーで表示されないことを示します。|  
|[noncreatable](../windows/noncreatable.md)|単独でインスタンス化できないオブジェクトを定義します。|  
|[nonextensible](../windows/nonextensible.md)|指定する、`IDispatch`実装にはプロパティのみが含まれます、メソッドのインターフェイスの説明で一覧表示および実行時にメンバーを追加して拡張することはできません。|  
|[object](../windows/object-cpp.md)|カスタムのインターフェイスを識別します。カスタム属性と同義です。|  
|[odl](../windows/odl.md)|オブジェクト記述言語 (ODL) インターフェイスとしてインターフェイスを識別します。|  
|[oleautomation](../windows/oleautomation.md)|インターフェイスに Automation では互換性があることを示します。|  
|[省略可能です](../windows/optional-cpp.md)|メンバー関数のオプション パラメーターを指定します。|  
|[out](../windows/out-cpp.md)|呼び出されたプロシージャから呼び出したプロシージャ (サーバーからクライアント) に返されるポインター パラメーターを示します。|  
|[pointer_default](../windows/pointer-default.md)|パラメーター リストに表示される最上位のポインターを除くすべてのポインターの既定のポインターの属性を指定します。|  
|[pragma](../windows/pragma.md)|生成された .idl ファイルに、引用符なしの指定した文字列を出力します。|  
|[progid](../windows/progid.md)|COM オブジェクトの ProgID を指定します。|  
|[propget](../windows/propget.md)|プロパティ アクセサー (get) 関数を指定します。|  
|[propputref](../windows/propputref.md)|値の代わりに参照を使用するプロパティ設定関数を指定します。|  
|[propput](../windows/propput.md)|プロパティ設定関数を指定します。|  
|[ptr](../windows/ptr.md)|すべてのポインターとしてのポインターを指定します。|  
|[public](../windows/public-cpp-attributes.md)|.Idl ファイル内で参照されていない場合でも、typedef がタイプ ライブラリに送られることを確認します。|  
|[range](../windows/range-cpp.md)|引数または値が設定される実行時にフィールドに使用できる値の範囲を指定します。|  
|[readonly](../windows/readonly-cpp.md)|変数への代入を禁止します。|  
|[ref](../windows/ref-cpp.md)|参照ポインターを識別します。|  
|[requestedit](../windows/requestedit.md)|プロパティをサポートしていることを示します、 **OnRequestEdit**通知します。|  
|[restricted](../windows/restricted.md)|あるライブラリ、またはモジュール、インターフェイス、またはディスパッチ インターフェイスのメンバー呼び出せないことを指定します。|  
|[retval](../windows/retval.md)|メンバーの戻り値を受け取るパラメーターを指定します。|  
|[size_is](../windows/size-is.md)|サイズのポインターに割り当てられた、サイズのポインター、および 1 次元または多次元配列へのポインターのサイズのメモリのサイズを指定します。|  
|[ソース](../windows/source-cpp.md)|クラス、プロパティ、またはメソッドのメンバーは、イベントの発生元であることを示します。|  
|[string](../windows/string-cpp.md)|示します、1 次元`char`、 `wchar_t`、**バイト**、同等の配列またはそのような配列へのポインターは、文字列として扱う必要があるか。|  
|[switch_is](../windows/switch-is.md)|式または共用体の判別共用体のメンバーが選択した役割を果たす識別子を指定します。|  
|[switch_type](../windows/switch-type.md)|共用体の判別変数として使用される変数の型を識別します。|  
|[transmit_as](../windows/transmit-as.md)|クライアントとサーバー アプリケーションは、次の操作、表現の型を転送型に関連付けるようにコンパイラに指示します。|  
|[uidefault](../windows/uidefault.md)|型情報のメンバーがユーザー インターフェイスに表示する既定のメンバーであることを示します。|  
|[unique](../windows/unique-cpp.md)|一意のポインターを指定します。|  
|[usesgetlasterror](../windows/usesgetlasterror.md)|呼び出し元に通知する関数を呼び出すときにエラーがある場合、呼び出し元ことができますし、`GetLastError`エラー コードを取得します。|  
|[uuid](../windows/uuid-cpp-attributes.md)|クラスまたはインターフェイスの一意の ID を指定します。|  
|[v1_enum](../windows/v1-enum.md)|指定した列挙型は、既定の 16 ビットではなく、32 ビットのエンティティとして送信するように指示します。|  
|[vararg](../windows/vararg.md)|関数が可変個の引数を実行するように指定します。|  
|[vi_progid](../windows/vi-progid.md)|ProgID のバージョンに依存しない形式を指定します。|  
|[wire_marshal](../windows/wire-marshal.md)|送信アプリケーションに固有のデータ型の代わりに使用されるデータ型を指定します。|  
  
## <a name="see-also"></a>関連項目  
 [グループ別の属性](../windows/attributes-by-group.md)   
 [属性に関する制限事項](http://msdn.microsoft.com/en-us/6e6c4329-f667-4869-b991-cbe9cb7a8f61)