---
title: IDL 属性 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++/CLI], reference topics
- IDL attributes
- .idl files [C++], attributes
- IDL files [C++], attributes
- .idl files [C++]
ms.assetid: 04c596f4-c97b-4952-8053-316678b1d0b6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 13c776faee71b757f9d5ce259a2d5ee88ba29066
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2018
ms.locfileid: "44315374"
---
# <a name="idl-attributes"></a>IDL 属性

これまでは、.idl ファイルの管理のものを持っています。

- 構造とそれを変更できる .idl ファイルの構文を理解します。

- .Idl ファイルの一部の側面を変更することができますが、ウィザードに依存します。

ここで、Visual C の IDL 属性を使用してソース コード ファイル内から .idl ファイルを変更できます。 多くの場合は、Visual C の IDL 属性は、MIDL 属性と同じ名前を付けます。 Visual C の IDL 属性と MIDL 属性の名前が同じで、その設立 MIDL 属性を含む .idl ファイル内、ソース コード ファイル内の Visual C 属性を配置することが発生することを示します。 ただし、Visual C の IDL 属性では、MIDL 属性のすべての機能が提供しない可能性があります。

と共に使用しない場合[COM 属性](../windows/com-attributes.md)、IDL 属性を使用して、インターフェイスを定義できます。 ソース コードをコンパイルすると、属性は、生成された .idl ファイルの定義に使用されます。 ATL プロジェクトで COM 属性と共に使用するといくつかの IDL などの属性、`coclass`プロジェクトに挿入するコードが発生します。

なお[idl_quote](../windows/idl-quote.md) Visual C の現在のバージョンでサポートされていない MIDL コンストラクトを使用することができます。 これと他の属性など[importlib](../windows/importlib.md)と[includelib](../windows/includelib-cpp.md)現在の Visual C プロジェクトで既存の .idl ファイルを使用する際に役立ちます。

|属性|説明|
|---------------|-----------------|
|[aggregatable](../windows/aggregatable.md)|別のコントロールでコントロールを集計できることを示します。|
|[appobject](../windows/appobject.md)|EXE の完全なアプリケーションに関連付けられ、関数と、コクラスのプロパティがグローバルに使用できるこのタイプ ライブラリを示しますアプリケーション オブジェクトとしてコクラスを識別します。|
|[async_uuid](../windows/async-uuid.md)|同期および非同期の両方のバージョンの COM インターフェイスを定義する、MIDL コンパイラに指示する UUID を指定します。|
|[bindable](../windows/bindable.md)|プロパティがデータ バインディングをサポートすることを示します。|
|[call_as](../windows/call-as.md)|リモート関数にマップするリモート処理不可能関数を使用できます。|
|[case](../windows/case-cpp.md)|使用される、 [switch_type](../windows/switch-type.md)共用体の属性。|
|[coclass](../windows/coclass.md)|クラスとしてコクラスを .idl ファイルに定義の場所。|
|[control](../windows/control.md)|コントロールに、ユーザー定義型を指定します。|
|[cpp_quote](../windows/cpp-quote.md)|生成されたヘッダー ファイルに、引用符なしの指定した文字列を出力します。|
|[defaultbind](../windows/defaultbind.md)|オブジェクトを最もよく表す単一のバインド可能なプロパティを示します。|
|[defaultcollelem](../windows/defaultcollelem.md)|Visual Basic コードの最適化に使用されます。|
|[defaultvalue](../windows/defaultvalue.md)|型指定された省略可能なパラメーターの既定値を指定をできます。|
|[default](../windows/default-cpp.md)|コクラス内で定義されるカスタムまたはディスパッチ インターフェイスが既定のプログラミング インターフェイスを表すことを示します。|
|[defaultvtable](../windows/defaultvtable.md)|コントロールの既定の vtable インターフェイスとしてインターフェイスを定義します。|
|[dispinterface](../windows/dispinterface.md)|ディスパッチ インターフェイスとしてインターフェイスを .idl ファイルに配置します。|
|[displaybind](../windows/displaybind.md)|バインド可能なユーザーに表示されるプロパティを示します。|
|[dual](../windows/dual.md)|.Idl ファイルにデュアル インターフェイスとしてインターフェイスを配置します。|
|[entry](../windows/entry.md)|DLL 内のエントリ ポイントを識別することによって、モジュールで、エクスポートされた関数または定数を指定します。|
|[first_is](../windows/first-is.md)|転送する最初の配列要素のインデックスを指定します。|
|[helpcontext](../windows/helpcontext.md)|ユーザーがヘルプ ファイル内のこの要素についての情報を表示できるようにコンテキスト ID を指定します。|
|[helpfile](../windows/helpfile.md)|タイプ ライブラリのヘルプ ファイルの名前を設定します。|
|[helpstringcontext](../windows/helpstringcontext.md)|.Hlp または .chm ファイルをヘルプ トピックの ID を指定します。|
|[helpstringdll](../windows/helpstringdll.md)|使用してドキュメントの文字列の検索 (ローカライズ) を実行する DLL の名前を指定します。|
|[helpstring](../windows/helpstring.md)|適用先となる要素を記述するために使用される文字列を指定します。|
|[hidden](../windows/hidden.md)|項目が存在しますが、ユーザー指向ブラウザーで表示する必要がありますされませんを示します。|
|[idl_module](../windows/idl-module.md)|DLL エントリ ポイントを指定します。|
|[idl_quote](../windows/idl-quote.md)|IDL 構造を現在のバージョンの Visual C でサポートされていないまたは属性を使用することができます。|
|[ID](../windows/id.md)|メンバー関数 (プロパティまたはメソッド、インターフェイスまたは dispinterface) のように DISPID を指定します。|
|[iid_is](../windows/iid-is.md)|インターフェイス ポインターによって示される COM インターフェイスの IID を指定します。|
|[immediatebind](../windows/immediatebind.md)|データ バインド オブジェクトのプロパティに対するすべての変更のデータベースに直ちに通知されることを示します。|
|[importlib](../windows/importlib.md)|既に他のタイプ ライブラリでコンパイル済みの型を、作成中のタイプ ライブラリで使用できるようにします。|
|[import](../windows/import.md)|メイン .idl ファイルから参照する定義を含む .idl、.odl ファイル、またはヘッダーの別のファイルを指定します。|
|[include](../windows/include-cpp.md)|生成された .idl ファイルに含まれる 1 つまたは複数のヘッダー ファイルを指定します。|
|[includelib](../windows/includelib-cpp.md)|生成された .idl ファイルに含まれる、.idl ファイルまたは .h ファイル。|
|[in](../windows/in-cpp.md)|呼び出し元のプロシージャから呼び出されたプロシージャに渡されるパラメーターがあることを示します。|
|[last_is](../windows/last-is.md)|転送する最後の配列要素のインデックスを指定します。|
|[lcid](../windows/lcid.md)|ロケール識別子を関数に渡すことができます。|
|[length_is](../windows/length-is.md)|転送する配列要素の数を指定します。|
|[licensed](../windows/licensed.md)|適用するコクラスはライセンスされていることを示しますを使用してインスタンス化する必要があります`IClassFactory2`します。|
|[local](../windows/local-cpp.md)|インターフェイスのヘッダーで使用する場合は、ヘッダー ジェネレーターとして、MIDL コンパイラを使用することができます。 個々 の関数で使用する場合は、スタブが生成されたないローカル プロシージャを指定します。|
|[max_is](../windows/max-is.md)|有効な配列のインデックスの最大値を指定します。|
|[モジュール](../windows/module-cpp.md)|.idl ファイルのライブラリ ブロックを定義します。|
|[ms_union](../windows/ms-union.md)|カプセル化されていない共用体のネットワーク データ表現の整列を制御します。|
|[no_injected_text](../windows/no-injected-text.md)|コンパイラがコードの属性を使用した結果として挿入するを防ぎます。|
|[nonbrowsable](../windows/nonbrowsable.md)|インターフェイス メンバーをプロパティ ブラウザーに表示されないことを示します。|
|[noncreatable](../windows/noncreatable.md)|単独でインスタンス化できないオブジェクトを定義します。|
|[nonextensible](../windows/nonextensible.md)|指定します、`IDispatch`実装にはプロパティのみが含まれていて、メソッドは、インターフェイスの説明に記載して、実行時にメンバーを追加して拡張することはできません。|
|[object](../windows/object-cpp.md)|カスタムのインターフェイスを識別します。カスタム属性と同義です。|
|[odl](../windows/odl.md)|オブジェクト記述言語 (ODL) インターフェイスとしてインターフェイスを識別します。|
|[oleautomation](../windows/oleautomation.md)|インターフェイスが Automation と互換性があることを示します。|
|[省略可能](../windows/optional-cpp.md)|メンバー関数のオプション パラメーターを指定します。|
|[out](../windows/out-cpp.md)|呼び出されたプロシージャから呼び出したプロシージャ (サーバーからクライアント) に返されるポインター パラメーターを示します。|
|[pointer_default](../windows/pointer-default.md)|パラメーター リストで表示される最上位レベルのポインターを除くすべてのポインターの既定のポインターの属性を指定します。|
|[pragma](../windows/pragma.md)|生成された .idl ファイルに、引用符なしの指定した文字列を出力します。|
|[progid](../windows/progid.md)|COM オブジェクトの ProgID を指定します。|
|[propget](../windows/propget.md)|プロパティのアクセサー (get) 関数を指定します。|
|[propputref](../windows/propputref.md)|値の代わりに参照を使用するプロパティ設定関数を指定します。|
|[propput](../windows/propput.md)|プロパティ設定関数を指定します。|
|[ptr](../windows/ptr.md)|完全なポインターとしてのポインターを指定します。|
|[public](../windows/public-cpp-attributes.md)|.Idl ファイル内から参照されていない場合でも、typedef がタイプ ライブラリに送られるようにします。|
|[range](../windows/range-cpp.md)|引数または値を持つが実行時に設定されているフィールドに使用できる値の範囲を指定します。|
|[readonly](../windows/readonly-cpp.md)|変数への代入を禁止します。|
|[ref](../windows/ref-cpp.md)|参照ポインターを識別します。|
|[requestedit](../windows/requestedit.md)|プロパティをサポートしていることを示します、`OnRequestEdit`通知します。|
|[restricted](../windows/restricted.md)|あるライブラリ、またはモジュール、インターフェイス、またはディスパッチ インターフェイスのメンバーを呼び出せないことを指定します。|
|[retval](../windows/retval.md)|メンバーの戻り値を受け取るパラメーターを指定します。|
|[size_is](../windows/size-is.md)|メモリのサイズがサイズのポインターに割り当てられた、サイズのポインター、および 1 次元または多次元配列へのポインターのサイズを指定します。|
|[source](../windows/source-cpp.md)|クラス、プロパティ、またはメソッドのメンバーがイベントの発生元であることを示します。|
|[string](../windows/string-cpp.md)|示します、1 次元**char**、 **wchar_t**、 `byte`、または同等の配列またはそのような配列へのポインターは、文字列として扱う必要があります。|
|[switch_is](../windows/switch-is.md)|式または共用体の判別共用体のメンバーを選択するとして機能する識別子を指定します。|
|[switch_type](../windows/switch-type.md)|共用体の判別式として使用される変数の型を識別します。|
|[transmit_as](../windows/transmit-as.md)|提示された種類、クライアントとサーバー アプリケーションは、次の操作、転送の型との関連付けをコンパイラに指示します。|
|[uidefault](../windows/uidefault.md)|型情報メンバーは、ユーザー インターフェイスに表示する既定のメンバーであることを示します。|
|[unique](../windows/unique-cpp.md)|一意のポインターを指定します。|
|[usesgetlasterror](../windows/usesgetlasterror.md)|その関数を呼び出すときにエラーがある場合、呼び出し元できますし、呼び出しを呼び出し元に通知`GetLastError`エラー コードを取得します。|
|[uuid](../windows/uuid-cpp-attributes.md)|クラスまたはインターフェイスの一意の ID を指定します。|
|[v1_enum](../windows/v1-enum.md)|指定した列挙型は、16 ビットの既定ではなく、32 ビットのエンティティとして送信するよう指示します。|
|[vararg](../windows/vararg.md)|関数が可変個の引数を実行することを指定します。|
|[vi_progid](../windows/vi-progid.md)|ProgID のバージョンに依存しない形式を指定します。|
|[wire_marshal](../windows/wire-marshal.md)|アプリケーションに固有のデータ型ではなく転送されるデータ型を指定します。|

## <a name="see-also"></a>関連項目

[グループ別の属性](../windows/attributes-by-group.md)  
