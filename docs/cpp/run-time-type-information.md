---
title: 実行時の型情報 |Microsoft Docs
ms.custom: index-page
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- RTTI compiler option
- run-time type information
- run time, type checking
- type information, run-time type checking
- run-time checks, type checking
ms.assetid: becbd0e5-0439-4c61-854f-8a74f7160c54
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1244c05b7af94d69394c412a3c67864d6e75c337
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46050880"
---
# <a name="run-time-type-information"></a>ランタイム型情報

実行時型情報 (RTTI: Run-Time Type Information) は、プログラムの実行中にオブジェクトの型を決定するための機能です。 クラス ライブラリの多くのベンダーがこの機能を独自に実装していたことから、RTTI が C++ 言語に追加されましたが、 これによってライブラリの間に非互換性が発生しました。 したがって、実行時型情報を言語レベルでサポートする必要があります。

RTTI についてわかりやすく説明するため、ここでは対象をポインターに限定しています。 ただし、ここで説明する概念は参照にも適用されます。

C++ 言語には、実行時型情報を扱う 3 つの主要要素があります。

- [Dynamic_cast](../cpp/dynamic-cast-operator.md)演算子。

     ポリモーフィック型を変換します。

- [Typeid](../cpp/typeid-operator.md)演算子。

     オブジェクトの正確な型を特定します。

- [Type_info](../cpp/type-info-class.md)クラス。

     によって返される型情報を保持するために使用される、 **typeid**演算子。

## <a name="see-also"></a>関連項目

[キャスト](../cpp/casting.md)