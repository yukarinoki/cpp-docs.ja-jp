---
title: スタンドアロン属性 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- standalone attributes
- attributes [C++/CLI], standalone
ms.assetid: 0d72e84e-236c-43b3-ac9a-d9b91fcd6794
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5d395053231f54570e1bf86ba79f6237b89681fc
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2018
ms.locfileid: "44315549"
---
# <a name="stand-alone-attributes"></a>スタンドアロン属性
スタンドアロン属性は C++ キーワードについては動作しませんが、行のコードのようにします。 スタンドアロン属性ステートメントには、行の末尾にセミコロンが必要です。
  
|属性|説明|
|---------------|-----------------|
|[cpp_quote](../windows/cpp-quote.md)|生成されたヘッダー ファイルに、引用符なしの指定した文字列を出力します。|
|[custom](../windows/custom-cpp.md)|独自の属性を定義できます。|
|[db_command](../windows/db-command.md)|OLE DB コマンドを作成します。|
|[emitidl](../windows/emitidl.md)|後続のすべての IDL 属性が処理され、生成された .idl ファイル内に配置するかどうかを判断します。|
|[idl_module](../windows/idl-module.md)|DLL エントリ ポイントを指定します。|
|[idl_quote](../windows/idl-quote.md)|Visual C の現在のバージョンでサポートされていない IDL コンストラクトを使用することができ、生成された .idl ファイルに渡すことがあります。|
|[import](../windows/import.md)|メインの .idl ファイルから参照する定義を含む別の .idl、.odl ファイル、または .h ファイルを指定します。|
|[importidl](../windows/importidl.md)|生成された .idl ファイルに指定された .idl ファイルを挿入します。|
|[importlib](../windows/importlib.md)|既に他のタイプ ライブラリでコンパイル済みの型を、作成中のタイプ ライブラリで使用できるようにします。|
|[include](../windows/include-cpp.md)|生成された .idl ファイルに含まれる 1 つまたは複数のヘッダー ファイルを指定します。|
|[includelib](../windows/includelib-cpp.md)|生成された .idl ファイルに含まれる、.idl ファイルまたは .h ファイル。|
|[library_block](../windows/library-block.md)|.Idl ファイルのライブラリ ブロック内で構成要素を配置します。|
|[モジュール](../windows/module-cpp.md)|.idl ファイルのライブラリ ブロックを定義します。|
|[no_injected_text](../windows/no-injected-text.md)|コンパイラがコードの属性を使用した結果として挿入するを防ぎます。|
|[pragma](../windows/pragma.md)|生成された .idl ファイルに、引用符なしの指定した文字列を出力します。|
  
## <a name="see-also"></a>関連項目
 [使用法別の属性](../windows/attributes-by-usage.md)