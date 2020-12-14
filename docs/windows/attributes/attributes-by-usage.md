---
description: '詳細情報: 使用法別の属性'
title: 使用法別の属性
ms.custom: index-page
ms.date: 10/02/2018
ms.topic: conceptual
helpviewer_keywords:
- attributes [C++/CLI]
ms.assetid: 8be2de10-b1ff-4ca4-a114-75318408593c
ms.openlocfilehash: 7f199ec1ede4cbaeddd46518f29a4b73edb40547
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247541"
---
# <a name="attributes-by-usage"></a>使用法別の属性

このトピックでは、適用される C++ 言語要素に従って属性を示します。

属性のスコープ内にない要素の前に属性がある場合、属性ブロックはコメントとして扱われます。

|属性|説明|
|---------------|-----------------|
|[モジュール属性](module-attributes.md)|[Module](module-cpp.md)属性に適用されます。|
|[インターフェイス属性](interface-attributes.md)|[__Interface](../../cpp/interface.md) C++ キーワードに適用されます。|
|[クラス属性](class-attributes.md)|C++ のキーワードに適用されます。|
|[メソッド属性](method-attributes.md)|クラス、コクラス、またはインターフェイスのメソッドに適用されます。|
|[パラメーター属性](parameter-attributes.md)|クラスまたはインターフェイスのメソッドのパラメーターに適用されます。|
|[データメンバー属性](data-member-attributes.md)|クラス、コクラス、またはインターフェイスのデータメンバーに適用されます。|
|[Typedef、Enum、Union、および Struct 属性](typedef-enum-union-and-struct-attributes.md)|C++ のキーワードに適用されます。|
|[配列属性](array-attributes.md)|配列またはに適用さ `SAFEARRAY` れます。|
|[スタンドアロン属性](stand-alone-attributes.md)|は、コード行のように動作しますが、C++ のキーワードでは動作しません。 スタンドアロンの属性ステートメントでは、行の末尾にセミコロンが必要です。|
|[カスタム属性](custom-attributes-cpp.md)|ユーザーがメタデータを拡張できるようにします。|

## <a name="module-attributes"></a>モジュール属性

次の属性は、 [module](module-cpp.md) 属性にのみ適用できます。

|属性|説明|
|---------------|-----------------|
|[typelib](helpstringdll.md)|ドキュメント文字列参照 (ローカライズ) を実行するために使用する DLL の名前を指定します。|

## <a name="interface-attributes"></a>インターフェイス属性

次の属性は、 [interface (または __interface)](../../cpp/interface.md) C++ キーワードに適用されます。

|属性|説明|
|---------------|-----------------|
|[async_uuid](async-uuid.md)|COM インターフェイスの同期バージョンと非同期バージョンの両方を定義するように MIDL コンパイラに指示する UUID を指定します。|
|[ショー](custom-cpp.md)|では、独自の属性を定義できます。|
|[dispinterface](dispinterface.md)|ディスパッチ インターフェイスとしてインターフェイスを .idl ファイルに配置します。|
|[×](dual.md)|インターフェイスを .idl ファイルにデュアルインターフェイスとして配置します。|
|[輸出](export.md)|データ構造を .idl ファイルに配置します。|
|[helpcontext](helpcontext.md)|ヘルプファイル内のこの要素に関する情報をユーザーが表示できるようにするコンテキスト ID を指定します。|
|[helpfile](helpfile.md)|タイプライブラリのヘルプファイルの名前を設定します。|
|[helpstring](helpstring.md)|適用先となる要素を記述するために使用される文字列を指定します。|
|[helpstringcontext](helpstringcontext.md)|.Hlp または .chm ファイルのヘルプトピックの ID を指定します。|
|[typelib](helpstringdll.md)|ドキュメント文字列参照 (ローカライズ) を実行するために使用する DLL の名前を指定します。|
|[表示](hidden.md)|項目が存在するが、ユーザー指向のブラウザーに表示されないことを示します。|
|[library_block](library-block.md)|.Idl ファイルのライブラリブロック内にコンストラクトを配置します。|
|[地元の](local-cpp.md)|インターフェイスヘッダーで使用するときに、MIDL コンパイラをヘッダージェネレーターとして使用できるようにします。 個々の関数で使用する場合は、スタブが生成されないローカルプロシージャを指定します。|
|[nonextensible](nonextensible.md)|実装に、 `IDispatch` インターフェイスの説明に示されているプロパティとメソッドのみが含まれ、実行時に追加のメンバーで拡張できないことを指定します。 この属性は、 [デュアル](dual.md) インターフェイスでのみ有効です。|
|[odl](odl.md)|オブジェクト記述言語 (ODL) インターフェイスとしてインターフェイスを識別します。|
|[object](object-cpp.md)|カスタムインターフェイスを識別します。|
|[oleautomation](oleautomation.md)|インターフェイスがオートメーションと互換性があることを示します。|
|[pointer_default](pointer-default.md)|パラメーターリストに表示されるトップレベルのポインターを除く、すべてのポインターの既定のポインター属性を指定します。|
|[ptr](ptr.md)|ポインターをフルポインターとして指定します。|
|[限定](restricted.md)|任意のライブラリのメンバーを呼び出すことができないことを指定します。|
|[uuid](uuid-cpp-attributes.md)|ライブラリの一意の ID を提供します。|

インターフェイスを定義するには、次の規則に従う必要があります。

- 既定の呼び出し規約は [__stdcall](../../cpp/stdcall.md)。

- GUID は、指定しない場合に提供されます。

- オーバーロードされたメソッドは使用できません。

[Uuid](uuid-cpp-attributes.md)属性を指定せず、異なる属性プロジェクトで同じインターフェイス名を使用すると、同じ GUID が生成されます。

## <a name="see-also"></a>関連項目

[COM および .NET 用の C++ の属性](cpp-attributes-com-net.md)<br/>
[グループ別の属性](attributes-by-group.md)<br/>
[属性のアルファベット順リファレンス](attributes-alphabetical-reference.md)
