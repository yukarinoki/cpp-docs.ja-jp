---
title: _ _unaligned |Microsoft ドキュメント
ms.custom: ''
ms.date: 03/09/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __unaligned_cpp
dev_langs:
- C++
helpviewer_keywords:
- __unaligned keyword [C++]
ms.assetid: 0cd83aad-1840-47e3-ad33-59bfcbe6375b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d73b082b9f41d03eb0b1a8c9fe772351ff4da91f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32420917"
---
# <a name="unaligned"></a>__unaligned

**Microsoft 固有の仕様**です。 `__unaligned` 修飾子を使用してポインターを宣言すると、コンパイラは、ポインターがアラインされていないデータを指していると見なします。 そのため、プラットフォームに適したコードが整列されていない読み取りを処理するが生成され、ポインターの書き込み。

## <a name="remarks"></a>コメント

この修飾子はポインターによってアドレス指定されるデータのアラインメントをについて説明しますポインター自体を配置すると見なされます。

必要性、`__unaligned`キーワードはプラットフォームと環境によって異なります。 データを適切にマークする障害は、パフォーマンスの低下からハードウェアの障害に至るまでの問題になります。 `__unaligned`修飾子が正しくありません x86 プラットフォームです。

アラインメントの詳細については、次のトピックを参照してください。

- [align](../cpp/align-cpp.md)

- [__alignof 演算子](../cpp/alignof-operator.md)

- [pack](../preprocessor/pack.md)

- [/Zp (構造体メンバーの配置)](../build/reference/zp-struct-member-alignment.md)

- [構造体の配置例](../build/examples-of-structure-alignment.md)

## <a name="see-also"></a>関連項目

[キーワード](../cpp/keywords-cpp.md)
