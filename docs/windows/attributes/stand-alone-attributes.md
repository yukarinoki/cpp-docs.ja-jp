---
title: スタンドアロン属性 (C++ COM)
ms.date: 10/02/2018
helpviewer_keywords:
- standalone attributes
- attributes [C++/CLI], standalone
ms.assetid: 0d72e84e-236c-43b3-ac9a-d9b91fcd6794
ms.openlocfilehash: a7df91bbb1c6929b08d8cd867be9f13ce0c35b91
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166173"
---
# <a name="stand-alone-attributes"></a>スタンドアロン属性

スタンドアロン属性はC++キーワードでは動作しませんが、コード行に似ています。 スタンドアロンの属性ステートメントでは、行の末尾にセミコロンが必要です。

## <a name="stand-alone-attribute-list"></a>スタンドアロン属性の一覧

|Attribute|説明|
|---------------|-----------------|
|[cpp_quote](cpp-quote.md)|指定した文字列を、引用符ではなく、生成されたヘッダーファイルに出力します。|
|[custom](custom-cpp.md)|では、独自の属性を定義できます。|
|[db_command](db-command.md)|OLE DB コマンドを作成します。|
|[emitidl](emitidl.md)|すべての後続の IDL 属性を処理し、生成された .idl ファイルに配置するかどうかを決定します。|
|[idl_module](idl-module.md)|DLL のエントリポイントを指定します。|
|[idl_quote](idl-quote.md)|現在のバージョンのビジュアルC++でサポートされていない idl 構造体を使用して、生成された .idl ファイルに渡すことができます。|
|[import](import.md)|メインの .idl ファイルから参照する定義を含む、.idl、odl、または .h の別のファイルを指定します。|
|[importidl](importidl.md)|生成された .idl ファイルに、指定した .idl ファイルを挿入します。|
|[importlib](importlib.md)|既に他のタイプ ライブラリでコンパイル済みの型を、作成中のタイプ ライブラリで使用できるようにします。|
|[include](include-cpp.md)|生成される .idl ファイルに含める1つ以上のヘッダーファイルを指定します。|
|[includelib](includelib-cpp.md)|生成された .idl ファイルに .idl ファイルまたは .h ファイルを含めます。|
|[library_block](library-block.md)|.Idl ファイルのライブラリブロック内にコンストラクトを配置します。|
|[name](module-cpp.md)|.idl ファイルのライブラリ ブロックを定義します。|
|[no_injected_text](no-injected-text.md)|属性の使用によってコードが挿入されないようにします。|
|[pragma](pragma.md)|指定された文字列を、引用符ではなく、生成された .idl ファイルに出力します。|

## <a name="see-also"></a>参照

[使用法別の属性](attributes-by-usage.md)
