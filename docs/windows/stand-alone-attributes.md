---
title: スタンドアロン属性 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- standalone attributes
- attributes [C++], standalone
ms.assetid: 0d72e84e-236c-43b3-ac9a-d9b91fcd6794
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 59846b1ca031cc02c85cb6ace23f96e8c5cc9f37
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33890433"
---
# <a name="stand-alone-attributes"></a>スタンドアロン属性
スタンドアロン属性は C++ キーワードについては動作しませんが、行のコードのようにします。 スタンドアロン属性ステートメントでは、行の終わりにセミコロンが必要です。  
  
|属性|説明|  
|---------------|-----------------|  
|[cpp_quote](../windows/cpp-quote.md)|生成されるヘッダー ファイルに、引用符なしの指定した文字列を出力します。|  
|[custom](../windows/custom-cpp.md)|独自の属性を定義できます。|  
|[db_command](../windows/db-command.md)|OLE DB コマンドを作成します。|  
|[emitidl](../windows/emitidl.md)|すべての後続の IDL 属性が処理して生成された .idl ファイル内に配置するかどうかを判断します。|  
|[idl_module](../windows/idl-module.md)|DLL のエントリ ポイントを指定します。|  
|[idl_quote](../windows/idl-quote.md)|Visual C の現在のバージョンでサポートされていない IDL コンストラクトを使用することができますを生成された .idl ファイルへのパススルーします。|  
|[import](../windows/import.md)|メイン .idl ファイルから参照する定義を含む .idl ファイル、.odl ファイル、または .h の別のファイルを指定します。|  
|[importidl](../windows/importidl.md)|生成された .idl ファイルに指定された .idl ファイルを挿入します。|  
|[importlib](../windows/importlib.md)|既に他のタイプ ライブラリでコンパイル済みの型を、作成中のタイプ ライブラリで使用できるようにします。|  
|[include](../windows/include-cpp.md)|生成された .idl ファイルに含まれる 1 つまたは複数のヘッダー ファイルを指定します。|  
|[includelib](../windows/includelib-cpp.md)|生成された .idl ファイルに含まれる、.idl ファイルまたは .h ファイルが発生します。|  
|[library_block](../windows/library-block.md)|.Idl ファイルのライブラリ ブロックの内部構造を配置します。|  
|[モジュール](../windows/module-cpp.md)|.idl ファイルのライブラリ ブロックを定義します。|  
|[no_injected_text](../windows/no-injected-text.md)|コンパイラがコードの属性を使用した結果として挿入するを防ぎます。|  
|[pragma](../windows/pragma.md)|生成された .idl ファイルに、引用符なしの指定した文字列を出力します。|  
  
## <a name="see-also"></a>関連項目  
 [使用法別の属性](../windows/attributes-by-usage.md)