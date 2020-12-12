---
description: '詳細情報: Stand-Alone 属性'
title: Stand-Alone の属性 (C++ COM)
ms.date: 10/02/2018
helpviewer_keywords:
- standalone attributes
- attributes [C++/CLI], standalone
ms.assetid: 0d72e84e-236c-43b3-ac9a-d9b91fcd6794
ms.openlocfilehash: 39b7356243f9b6ba7c42e907ca0733f59b85961e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329590"
---
# <a name="stand-alone-attributes"></a>スタンドアロン属性

スタンドアロン属性は C++ キーワードでは動作しませんが、コード行に似ています。 スタンドアロンの属性ステートメントでは、行の末尾にセミコロンが必要です。

## <a name="stand-alone-attribute-list"></a>スタンドアロン属性の一覧

|属性|説明|
|---------------|-----------------|
|[cpp_quote](cpp-quote.md)|指定した文字列を、引用符ではなく、生成されたヘッダーファイルに出力します。|
|[ショー](custom-cpp.md)|では、独自の属性を定義できます。|
|[db_command](db-command.md)|OLE DB コマンドを作成します。|
|[emitidl](emitidl.md)|すべての後続の IDL 属性を処理し、生成された .idl ファイルに配置するかどうかを決定します。|
|[idl_module](idl-module.md)|DLL のエントリポイントを指定します。|
|[idl_quote](idl-quote.md)|では、現在のバージョンの Visual C++ でサポートされていない IDL 構造体を使用して、生成された .idl ファイルに渡すことができます。|
|[import](import.md)|メインの .idl ファイルから参照する定義を含む、.idl、odl、または .h の別のファイルを指定します。|
|[importidl](importidl.md)|生成された .idl ファイルに、指定した .idl ファイルを挿入します。|
|[importlib](importlib.md)|既に他のタイプ ライブラリでコンパイル済みの型を、作成中のタイプ ライブラリで使用できるようにします。|
|[用意](include-cpp.md)|生成される .idl ファイルに含める1つ以上のヘッダーファイルを指定します。|
|[includelib](includelib-cpp.md)|生成された .idl ファイルに .idl ファイルまたは .h ファイルを含めます。|
|[library_block](library-block.md)|.Idl ファイルのライブラリブロック内にコンストラクトを配置します。|
|[第](module-cpp.md)|.idl ファイルのライブラリ ブロックを定義します。|
|[no_injected_text](no-injected-text.md)|属性の使用によってコードが挿入されないようにします。|
|[unmanaged](pragma.md)|指定された文字列を、引用符ではなく、生成された .idl ファイルに出力します。|

## <a name="see-also"></a>関連項目

[使用法別の属性](attributes-by-usage.md)
