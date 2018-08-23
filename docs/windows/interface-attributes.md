---
title: インターフェイス属性 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++], reference topics
- interface attributes
ms.assetid: 27fcdfee-abce-4585-8b53-ee31635356e8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8c61aeb0dcf3a9e0e001f89b9872b43b0af092b2
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42593324"
---
# <a name="interface-attributes"></a>インターフェイス属性

次の属性を適用する、[インターフェイス (または _ _interface)](../cpp/interface.md) C++ のキーワード。

|属性|説明|
|---------------|-----------------|
|[async_uuid](../windows/async-uuid.md)|同期および非同期の両方のバージョンの COM インターフェイスを定義する、MIDL コンパイラに指示する UUID を指定します。|
|[custom](../windows/custom-cpp.md)|独自の属性を定義できます。|
|[dispinterface](../windows/dispinterface.md)|ディスパッチ インターフェイスとしてインターフェイスを .idl ファイルに配置します。|
|[dual](../windows/dual.md)|.Idl ファイルにデュアル インターフェイスとしてインターフェイスを配置します。|
|[export](../windows/export.md)|.Idl ファイルに配置するデータ構造をによりします。|
|[helpcontext](../windows/helpcontext.md)|ユーザーがヘルプ ファイル内のこの要素についての情報を表示できるようにコンテキスト ID を指定します。|
|[helpfile](../windows/helpfile.md)|タイプ ライブラリのヘルプ ファイルの名前を設定します。|
|[helpstring](../windows/helpstring.md)|適用先となる要素を記述するために使用される文字列を指定します。|
|[helpstringcontext](../windows/helpstringcontext.md)|.Hlp または .chm ファイルをヘルプ トピックの ID を指定します。|
|[helpstringdll](../windows/helpstringdll.md)|使用してドキュメントの文字列の検索 (ローカライズ) を実行する DLL の名前を指定します。|
|[hidden](../windows/hidden.md)|項目が存在しますが、ユーザー指向ブラウザーで表示する必要がありますされませんを示します。|
|[library_block](../windows/library-block.md)|.Idl ファイルのライブラリ ブロック内で構成要素を配置します。|
|[local](../windows/local-cpp.md)|インターフェイスのヘッダーで使用する場合は、ヘッダー ジェネレーターとして、MIDL コンパイラを使用することができます。 個々 の関数で使用する場合は、スタブが生成されたないローカル プロシージャを指定します。|
|[nonextensible](../windows/nonextensible.md)|指定します、`IDispatch`実装にはプロパティのみが含まれていて、メソッドは、インターフェイスの説明に記載して、実行時にメンバーを追加して拡張することはできません。 この属性でのみ有効です、[デュアル](../windows/dual.md)インターフェイス。|
|[odl](../windows/odl.md)|オブジェクト記述言語 (ODL) インターフェイスとしてインターフェイスを識別します。|
|[object](../windows/object-cpp.md)|カスタム インターフェイスを識別します。|
|[oleautomation](../windows/oleautomation.md)|インターフェイスが Automation と互換性があることを示します。|
|[pointer_default](../windows/pointer-default.md)|パラメーター リストで表示される最上位レベルのポインターを除くすべてのポインターの既定のポインターの属性を指定します。|
|[ptr](../windows/ptr.md)|完全なポインターとしてのポインターを指定します。|
|[restricted](../windows/restricted.md)|ライブラリのメンバーを任意に呼び出すことはできませんを指定します。|
|[uuid](../windows/uuid-cpp-attributes.md)|ライブラリの一意の ID を提供します。|

インターフェイスを定義するため、これらの規則に従う必要があります。

- 既定の呼び出し規約は[_ _stdcall](../cpp/stdcall.md)します。

- いずれかを指定しない場合、GUID が指定されます。

- オーバー ロードされたメソッドは許可されません。

指定しない場合、 [uuid](../windows/uuid-cpp-attributes.md)属性し、同じインターフェイスの名前を使用して、別の属性のプロジェクトで、同じ GUID が生成されます。

## <a name="see-also"></a>関連項目

[使用法別の属性](../windows/attributes-by-usage.md)