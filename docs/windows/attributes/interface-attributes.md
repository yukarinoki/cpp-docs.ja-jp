---
title: インターフェイス属性 (C++ COM)
ms.date: 10/02/2018
helpviewer_keywords:
- attributes [C++/CLI], reference topics
- interface attributes
ms.assetid: 27fcdfee-abce-4585-8b53-ee31635356e8
ms.openlocfilehash: 81a88ddfd74f20fa57ef615c988ba9786f41c1ad
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214826"
---
# <a name="interface-attributes"></a>インターフェイス属性

次の属性は、[インターフェイス (または __interface)](../../cpp/interface.md) C++キーワードに適用されます。

|Attribute|説明|
|---------------|-----------------|
|[async_uuid](async-uuid.md)|COM インターフェイスの同期バージョンと非同期バージョンの両方を定義するように MIDL コンパイラに指示する UUID を指定します。|
|[custom](custom-cpp.md)|では、独自の属性を定義できます。|
|[dispinterface](dispinterface.md)|ディスパッチ インターフェイスとしてインターフェイスを .idl ファイルに配置します。|
|[dual](dual.md)|インターフェイスを .idl ファイルにデュアルインターフェイスとして配置します。|
|[export](export.md)|データ構造を .idl ファイルに配置します。|
|[helpcontext](helpcontext.md)|ヘルプファイル内のこの要素に関する情報をユーザーが表示できるようにするコンテキスト ID を指定します。|
|[helpfile](helpfile.md)|タイプライブラリのヘルプファイルの名前を設定します。|
|[helpstring](helpstring.md)|適用先となる要素を記述するために使用される文字列を指定します。|
|[helpstringcontext](helpstringcontext.md)|.Hlp または .chm ファイルのヘルプトピックの ID を指定します。|
|[helpstringdll](helpstringdll.md)|ドキュメント文字列参照 (ローカライズ) を実行するために使用する DLL の名前を指定します。|
|[hidden](hidden.md)|項目が存在するが、ユーザー指向のブラウザーに表示されないことを示します。|
|[library_block](library-block.md)|.Idl ファイルのライブラリブロック内にコンストラクトを配置します。|
|[local](local-cpp.md)|インターフェイスヘッダーで使用するときに、MIDL コンパイラをヘッダージェネレーターとして使用できるようにします。 個々の関数で使用する場合は、スタブが生成されないローカルプロシージャを指定します。|
|[nonextensible](nonextensible.md)|`IDispatch` の実装に、インターフェイスの説明に示されているプロパティとメソッドのみが含まれ、実行時に追加のメンバーで拡張できないことを指定します。 この属性は、[デュアル](dual.md)インターフェイスでのみ有効です。|
|[odl](odl.md)|オブジェクト記述言語 (ODL) インターフェイスとしてインターフェイスを識別します。|
|[object](object-cpp.md)|カスタムインターフェイスを識別します。|
|[oleautomation](oleautomation.md)|インターフェイスがオートメーションと互換性があることを示します。|
|[pointer_default](pointer-default.md)|パラメーターリストに表示されるトップレベルのポインターを除く、すべてのポインターの既定のポインター属性を指定します。|
|[ptr](ptr.md)|ポインターをフルポインターとして指定します。|
|[restricted](restricted.md)|任意のライブラリのメンバーを呼び出すことができないことを指定します。|
|[uuid](uuid-cpp-attributes.md)|ライブラリの一意の ID を提供します。|

インターフェイスを定義するには、次の規則に従う必要があります。

- 既定の呼び出し規約は[__stdcall](../../cpp/stdcall.md)。

- GUID は、指定しない場合に提供されます。

- オーバーロードされたメソッドは使用できません。

[Uuid](uuid-cpp-attributes.md)属性を指定せず、異なる属性プロジェクトで同じインターフェイス名を使用すると、同じ GUID が生成されます。

## <a name="see-also"></a>参照

[使用法別の属性](attributes-by-usage.md)
