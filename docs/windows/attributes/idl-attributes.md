---
description: IDL 属性に関する詳細情報
title: IDL 属性 (C++ COM)
ms.date: 10/02/2018
helpviewer_keywords:
- attributes [C++/CLI], reference topics
- IDL attributes
- .idl files [C++], attributes
- IDL files [C++], attributes
- .idl files [C++]
ms.assetid: 04c596f4-c97b-4952-8053-316678b1d0b6
ms.openlocfilehash: 1db49b6c68d0dd4e4f4c6c5dcfb148cafc39159d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97275465"
---
# <a name="idl-attributes"></a>IDL 属性

従来、.idl ファイルを保持することは、次のことを意味しました。

- 変更できるようにするには、.idl ファイルの構造と構文について理解しておいてください。

- .Idl ファイルのいくつかの側面を変更できるウィザードに依存します。

これで、Visual C++ IDL 属性を使用してソースコードファイル内から .idl ファイルを変更できます。 多くの場合、Visual C++ の IDL 属性には、MIDL 属性と同じ名前が付けられます。 Visual C++ IDL 属性と MIDL 属性の名前が同じである場合は、Visual C++ 属性をソースコードファイルに配置すると、その名前 MIDL 属性を含む .idl ファイルが生成されます。 ただし、Visual C++ IDL 属性では、MIDL 属性のすべての機能を提供できない場合があります。

[COM 属性](com-attributes.md)で使用しない場合、IDL 属性を使用してインターフェイスを定義できます。 ソースコードをコンパイルするときに、生成された .idl ファイルを定義するために属性が使用されます。 ATL プロジェクトで COM 属性と共に使用すると、などの一部の IDL 属性によって `coclass` コードがプロジェクトに挿入されます。

[Idl_quote](idl-quote.md)では、Visual C++ の現在のバージョンでサポートされていない MIDL コンストラクトを使用できます。 この属性や [importlib](importlib.md) などの他の属性は、現在の Visual Studio C++ プロジェクトで既存の .idl ファイルを使用するの [に役立ちます](includelib-cpp.md) 。

|属性|説明|
|---------------|-----------------|
|[aggregatable](aggregatable.md)|コントロールを別のコントロールで集計できることを示します。|
|[appobject](appobject.md)|コクラスをアプリケーションオブジェクトとして識別します。このオブジェクトは、完全な EXE アプリケーションに関連付けられています。また、コクラスの関数とプロパティは、このタイプライブラリでグローバルに使用できることを示します。|
|[async_uuid](async-uuid.md)|COM インターフェイスの同期バージョンと非同期バージョンの両方を定義するように MIDL コンパイラに指示する UUID を指定します。|
|[bindable](bindable.md)|プロパティがデータ バインディングをサポートすることを示します。|
|[call_as](call-as.md)|リモート処理不可能関数をリモート関数にマップできるようにします。|
|[case](case-cpp.md)|共用体の [switch_type](switch-type.md) 属性と共に使用されます。|
|[coclass](coclass.md)|クラス定義をコクラスとして .idl ファイルに配置します。|
|[control](control.md)|ユーザー定義型がコントロールであることを指定します。|
|[cpp_quote](cpp-quote.md)|指定した文字列を、引用符ではなく、生成されたヘッダーファイルに出力します。|
|[defaultbind](defaultbind.md)|オブジェクトを最もよく表す、1つのバインド可能なプロパティを示します。|
|[defaultcollelem](defaultcollelem.md)|Visual Basic コードの最適化に使用します。|
|[既定](defaultvalue.md)|型指定された省略可能なパラメーターの既定値を指定できます。|
|[default](default-cpp.md)|コクラス内で定義されるカスタムまたはディスパッチ インターフェイスが既定のプログラミング インターフェイスを表すことを示します。|
|[defaultvtable](defaultvtable.md)|コントロールの既定の vtable インターフェイスとしてインターフェイスを定義します。|
|[dispinterface](dispinterface.md)|ディスパッチ インターフェイスとしてインターフェイスを .idl ファイルに配置します。|
|[displaybind](displaybind.md)|バインド可能としてユーザーに表示される必要があるプロパティを示します。|
|[×](dual.md)|インターフェイスを .idl ファイルにデュアルインターフェイスとして配置します。|
|[キー](entry.md)|DLL 内のエントリポイントを識別することによって、モジュール内のエクスポートされた関数または定数を指定します。|
|[first_is](first-is.md)|転送される最初の配列要素のインデックスを指定します。|
|[helpcontext](helpcontext.md)|ヘルプファイル内のこの要素に関する情報をユーザーが表示できるようにするコンテキスト ID を指定します。|
|[helpfile](helpfile.md)|タイプライブラリのヘルプファイルの名前を設定します。|
|[helpstringcontext](helpstringcontext.md)|.Hlp または .chm ファイルのヘルプトピックの ID を指定します。|
|[typelib](helpstringdll.md)|ドキュメント文字列参照 (ローカライズ) を実行するために使用する DLL の名前を指定します。|
|[helpstring](helpstring.md)|適用先となる要素を記述するために使用される文字列を指定します。|
|[表示](hidden.md)|項目が存在するが、ユーザー指向のブラウザーに表示されないことを示します。|
|[idl_module](idl-module.md)|DLL のエントリポイントを指定します。|
|[idl_quote](idl-quote.md)|現在のバージョンの Visual C++ でサポートされていない属性または IDL コンストラクトを使用できるようにします。|
|[id](id.md)|メンバー関数 (インターフェイスまたはディスパッチインターフェイスのプロパティまたはメソッド) の DISPID を指定します。|
|[iid_is](iid-is.md)|インターフェイスポインターが指す COM インターフェイスの IID を指定します。|
|[immediatebind](immediatebind.md)|データバインドオブジェクトのプロパティに対するすべての変更が、すぐにデータベースに通知されることを示します。|
|[importlib](importlib.md)|既に他のタイプ ライブラリでコンパイル済みの型を、作成中のタイプ ライブラリで使用できるようにします。|
|[import](import.md)|メインの .idl ファイルから参照する定義が含まれている、別の .idl、odl、またはヘッダーファイルを指定します。|
|[用意](include-cpp.md)|生成される .idl ファイルに含める1つ以上のヘッダーファイルを指定します。|
|[includelib](includelib-cpp.md)|生成された .idl ファイルに .idl ファイルまたは .h ファイルを含めます。|
|[in](in-cpp.md)|呼び出し元プロシージャから呼び出されたプロシージャにパラメーターが渡されることを示します。|
|[last_is](last-is.md)|転送する最後の配列要素のインデックスを指定します。|
|[lcid](lcid.md)|関数にロケール識別子を渡すことができます。|
|[length_is](length-is.md)|転送する配列要素の数を指定します。|
|[ライセンス](licensed.md)|適用されるコクラスがライセンスされ、を使用してインスタンス化される必要があることを示し `IClassFactory2` ます。|
|[地元の](local-cpp.md)|インターフェイスヘッダーで使用するときに、MIDL コンパイラをヘッダージェネレーターとして使用できるようにします。 個々の関数で使用する場合は、スタブが生成されないローカルプロシージャを指定します。|
|[max_is](max-is.md)|有効な配列インデックスの最大値を指定します。|
|[第](module-cpp.md)|.idl ファイルのライブラリ ブロックを定義します。|
|[ms_union](ms-union.md)|カプセル化されていない共用体のネットワークデータ表現の配置を制御します。|
|[no_injected_text](no-injected-text.md)|属性の使用によってコードが挿入されないようにします。|
|[nonbrowsable](nonbrowsable.md)|インターフェイスメンバーをプロパティブラウザーに表示しないことを示します。|
|[noncreatable](noncreatable.md)|単独ではインスタンス化できないオブジェクトを定義します。|
|[nonextensible](nonextensible.md)|実装に、 `IDispatch` インターフェイスの説明に示されているプロパティとメソッドのみが含まれ、実行時に追加のメンバーで拡張できないことを指定します。|
|[object](object-cpp.md)|カスタムインターフェイスを識別します。カスタム属性と同義です。|
|[odl](odl.md)|オブジェクト記述言語 (ODL) インターフェイスとしてインターフェイスを識別します。|
|[oleautomation](oleautomation.md)|インターフェイスがオートメーションと互換性があることを示します。|
|[省略可能](optional-cpp.md)|メンバー関数の省略可能なパラメーターを指定します。|
|[out](out-cpp.md)|呼び出されたプロシージャから呼び出したプロシージャ (サーバーからクライアント) に返されるポインター パラメーターを示します。|
|[pointer_default](pointer-default.md)|パラメーターリストに表示されるトップレベルのポインターを除く、すべてのポインターの既定のポインター属性を指定します。|
|[unmanaged](pragma.md)|指定された文字列を、引用符ではなく、生成された .idl ファイルに出力します。|
|[progid](progid.md)|COM オブジェクトの ProgID を指定します。|
|[propget](propget.md)|プロパティアクセサー (get) 関数を指定します。|
|[propputref](propputref.md)|値ではなく参照を使用するプロパティ設定関数を指定します。|
|[propput](propput.md)|プロパティ設定関数を指定します。|
|[ptr](ptr.md)|ポインターをフルポインターとして指定します。|
|[public](public-cpp-attributes.md)|は、.idl ファイル内から参照されていない場合でも、typedef がタイプライブラリに入ることを保証します。|
|[range](range-cpp.md)|実行時に値が設定される引数またはフィールドに使用できる値の範囲を指定します。|
|[readonly](readonly-cpp.md)|変数への代入を禁止します。|
|[ref](ref-cpp.md)|参照ポインターを識別します。|
|[requestedit](requestedit.md)|`OnRequestEdit` 通知がプロパティでサポートされることを示します。|
|[限定](restricted.md)|ライブラリ、またはモジュール、インターフェイス、またはディスパッチインターフェイスのメンバーを任意に呼び出すことができないことを指定します。|
|[retval](retval.md)|メンバーの戻り値を受け取るパラメーターを指定します。|
|[size_is](size-is.md)|サイズポインターに割り当てられたメモリのサイズ、サイズ設定されたポインターへのサイズポインター、および単一または多次元の配列を指定します。|
|[source](source-cpp.md)|クラス、プロパティ、またはメソッドのメンバーがイベントのソースであることを示します。|
|[string](string-cpp.md)|1次元 **`char`** 、、 **`wchar_t`** `byte` 、または同等の配列、またはこのような配列へのポインターを文字列として扱う必要があることを示します。|
|[switch_is](switch-is.md)|共用体メンバーを選択する union 判別として機能する式または識別子を指定します。|
|[switch_type](switch-type.md)|Union 判別として使用される変数の型を識別します。|
|[transmit_as](transmit-as.md)|クライアントおよびサーバーアプリケーションが操作する提示された型を、送信された型で関連付けるようにコンパイラに指示します。|
|[uidefault](uidefault.md)|型情報メンバーがユーザーインターフェイスに表示される既定のメンバーであることを示します。|
|[unique](unique-cpp.md)|一意のポインターを指定します。|
|[usesgetlasterror](usesgetlasterror.md)|この関数を呼び出したときにエラーが発生した場合に、呼び出し元がを呼び出してエラーコードを取得することを呼び出し元に通知し `GetLastError` ます。|
|[uuid](uuid-cpp-attributes.md)|クラスまたはインターフェイスの一意の ID を指定します。|
|[v1_enum](v1-enum.md)|指定された列挙型を16ビットの既定値ではなく、32ビットのエンティティとして送信するように指示します。|
|[vararg](vararg.md)|関数が可変個の引数を受け取ることを指定します。|
|[vi_progid](vi-progid.md)|バージョンに依存しない ProgID の形式を指定します。|
|[wire_marshal](wire-marshal.md)|アプリケーション固有のデータ型ではなく、転送に使用されるデータ型を指定します。|

## <a name="see-also"></a>関連項目

[グループ別の属性](attributes-by-group.md)
