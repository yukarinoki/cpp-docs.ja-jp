---
title: パラメーター属性 (C++ COM)
ms.date: 10/02/2018
helpviewer_keywords:
- attributes [C++/CLI], parameter attributes
- parameter attributes
ms.assetid: 024c2dd5-49d7-4ced-a17a-c56c1bc485b6
ms.openlocfilehash: 37ddd6ad575417b7ad891a173a77f27ef3823e03
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166550"
---
# <a name="parameter-attributes"></a>パラメーター属性

クラスまたはインターフェイスのメソッドのパラメーターには、次の属性が適用されます。

|Attribute|説明|
|---------------|-----------------|
|[custom](custom-cpp.md)|では、独自の属性を定義できます。|
|[defaultvalue](defaultvalue.md)|型指定された省略可能なパラメーターの既定値を指定できます。|
|[first_is](first-is.md)|転送される最初の配列要素のインデックスを指定します。|
|[iid_is](iid-is.md)|転送される最初の配列要素のインデックスを指定します。|
|[immediatebind](immediatebind.md)|データバインドオブジェクトのプロパティに対するすべての変更が、すぐにデータベースに通知されることを示します。|
|[in](in-cpp.md)|呼び出し元プロシージャから呼び出されたプロシージャにパラメーターが渡されることを示します。|
|[last_is](last-is.md)|転送する最後の配列要素のインデックスを指定します。|
|[lcid](lcid.md)|関数にロケール識別子を渡すことができます。|
|[length_is](length-is.md)|転送する配列要素の数を指定します。|
|[max_is](max-is.md)|有効な配列インデックスの最大値を指定します。|
|[省略可能](optional-cpp.md)|メンバー関数の省略可能なパラメーターを指定します。|
|[out](out-cpp.md)|呼び出されたプロシージャから呼び出したプロシージャ (サーバーからクライアント) に返されるポインター パラメーターを示します。|
|[range](range-cpp.md)|実行時に値が設定される引数またはフィールドに使用できる値の範囲を指定します。|
|[ref](ref-cpp.md)|参照ポインターを識別します。|
|[retval](retval.md)|メンバーの戻り値を受け取るパラメーターを指定します。|
|[satype](satype.md)|`SAFEARRAY` 構造体のデータ型を指定します。|
|[size_is](size-is.md)|サイズポインターに割り当てられたメモリのサイズ、サイズ設定されたポインターへのサイズポインター、および単一または多次元の配列を指定します。|
|[unique](unique-cpp.md)|一意のポインターを指定します。|

## <a name="see-also"></a>参照

[使用法別の属性](attributes-by-usage.md)
