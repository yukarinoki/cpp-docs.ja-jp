---
title: 使用法別の属性
ms.custom: index-page
ms.date: 10/02/2018
ms.topic: conceptual
helpviewer_keywords:
- attributes [C++/CLI]
ms.assetid: 8be2de10-b1ff-4ca4-a114-75318408593c
ms.openlocfilehash: dcbed019f8cd08ddbf4ab6b4756a59f7fcbabc4b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81361330"
---
# <a name="attributes-by-usage"></a>使用法別の属性

このトピックでは、適用先の C++ 言語要素に従って属性を一覧表示します。

属性のスコープ内にない要素の前に属性がある場合、属性ブロックはコメントとして扱われます。

|属性|説明|
|---------------|-----------------|
|[モジュール属性](module-attributes.md)|[モジュール](module-cpp.md)属性に適用されます。|
|[インターフェイス属性](interface-attributes.md)|[__interface](../../cpp/interface.md) C++ キーワードに適用されます。|
|[クラス属性](class-attributes.md)|C++ キーワードに適用されます。|
|[メソッド属性](method-attributes.md)|クラス、コクラス、またはインターフェイス内のメソッドに適用されます。|
|[パラメーター属性](parameter-attributes.md)|クラスまたはインターフェイス内のメソッドのパラメーターに適用されます。|
|[データ メンバー属性](data-member-attributes.md)|クラス、コクラス、またはインターフェイスのデータ メンバーに適用されます。|
|[型定義、列挙型、和集合、および構造体の属性](typedef-enum-union-and-struct-attributes.md)|C++ キーワードに適用されます。|
|[配列属性](array-attributes.md)|配列または`SAFEARRAY`s に適用されます。|
|[スタンドアロン属性](stand-alone-attributes.md)|コード行のように動作しますが、C++ キーワードでは動作しません。 スタンドアロン属性ステートメントでは、行の末尾にセミコロンが必要です。|
|[カスタム属性](custom-attributes-cpp.md)|ユーザーがメタデータを拡張できるようにします。|

## <a name="module-attributes"></a>モジュール属性

次の属性は[、モジュール](module-cpp.md)属性にのみ適用できます。

|属性|説明|
|---------------|-----------------|
|[typelib](helpstringdll.md)|ドキュメント文字列の参照 (ローカリゼーション) の実行に使用する DLL の名前を指定します。|

## <a name="interface-attributes"></a>インターフェイス属性

次の属性は[、インターフェイス (または__interface)](../../cpp/interface.md) C++ キーワードに適用されます。

|属性|説明|
|---------------|-----------------|
|[async_uuid](async-uuid.md)|COM インターフェイスの同期バージョンと非同期バージョンの両方を定義するように MIDL コンパイラに指示する UUID を指定します。|
|[カスタム](custom-cpp.md)|独自の属性を定義できます。|
|[ディスパッチ](dispinterface.md)|ディスパッチ インターフェイスとしてインターフェイスを .idl ファイルに配置します。|
|[デュアル](dual.md)|インターフェイスをデュアル インターフェイスとして .idl ファイルに配置します。|
|[エクスポート](export.md)|データ構造を .idl ファイルに配置します。|
|[helpcontext](helpcontext.md)|ユーザーがヘルプ ファイル内のこの要素に関する情報を表示できるようにするコンテキスト ID を指定します。|
|[Helpfile](helpfile.md)|タイプ ライブラリのヘルプ ファイルの名前を設定します。|
|[helpstring](helpstring.md)|適用先となる要素を記述するために使用される文字列を指定します。|
|[helpstringcontext](helpstringcontext.md)|.hlp ファイルまたは .chm ファイル内のヘルプ トピックの ID を指定します。|
|[typelib](helpstringdll.md)|ドキュメント文字列の参照 (ローカリゼーション) の実行に使用する DLL の名前を指定します。|
|[隠さ れた](hidden.md)|アイテムが存在するが、ユーザー指向のブラウザーに表示されないことを示します。|
|[library_block](library-block.md)|.idl ファイルのライブラリ ブロック内にコンストラクトを配置します。|
|[local](local-cpp.md)|インターフェイス ヘッダーで使用する場合に、MIDL コンパイラをヘッダー ジェネレーターとして使用できます。 個々の関数で使用する場合、スタブが生成されていないローカル プロシージャを指定します。|
|[nonextensible](nonextensible.md)|実装に`IDispatch`含まれるプロパティとメソッドがインターフェイスの説明に記載されており、実行時に追加のメンバーと共に拡張できないことを指定します。 この属性は[、デュアル](dual.md)インターフェイスでのみ有効です。|
|[Odl](odl.md)|インターフェイスをオブジェクト記述言語 (ODL) インターフェイスとして識別します。|
|[オブジェクト](object-cpp.md)|カスタム インターフェイスを識別します。|
|[oleautomation](oleautomation.md)|インターフェイスがオートメーションと互換性があることを示します。|
|[pointer_default](pointer-default.md)|パラメーター・リストに表示される最上位ポインターを除くすべてのポインターのデフォルト・ポインター属性を指定します。|
|[Ptr](ptr.md)|ポインターを完全なポインターとして指定します。|
|[制限](restricted.md)|ライブラリのどのメンバーを任意に呼び出すことができないかを指定します。|
|[uuid](uuid-cpp-attributes.md)|ライブラリの一意の ID を提供します。|

インターフェイスを定義するには、次の規則に従う必要があります。

- 既定の呼び出し規約は[__stdcall](../../cpp/stdcall.md)です。

- GUID は、指定しない場合に提供されます。

- オーバーロードされたメソッドは使用できません。

[uuid](uuid-cpp-attributes.md)属性を指定せず、異なる属性プロジェクトで同じインターフェイス名を使用する場合は、同じ GUID が生成されます。

## <a name="see-also"></a>関連項目

[COM および .NET 用の C++ の属性](cpp-attributes-com-net.md)<br/>
[グループ別属性](attributes-by-group.md)<br/>
[属性アルファベット順リファレンス](attributes-alphabetical-reference.md)
