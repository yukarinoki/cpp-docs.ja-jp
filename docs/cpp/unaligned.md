---
title: _ _unaligned |Microsoft Docs
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
ms.openlocfilehash: 9593a0b3c6e6980f5be2ce9dcf13e505e94dcace
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46040201"
---
# <a name="unaligned"></a>__unaligned

**Microsoft 固有の仕様**します。 マウス ポインターを宣言する場合、 **_ _unaligned**修飾子は、コンパイラはポインターがアラインされていないデータをアドレスします。 その結果、プラットフォームに適したコードでは、アラインされていない読み取りを処理するためが生成され、ポインターを書き込みます。

## <a name="remarks"></a>Remarks

この修飾子はポインターによってアドレス指定されたデータのアラインメントをについて説明しますポインター自体は、配置すると見なされます。

必要性、 **_ _unaligned**キーワードは、プラットフォームおよび環境によって異なります。 エラー データを適切にマークすると、パフォーマンスの低下からハードウェアの障害に至るまでの問題があります。 **_ _Unaligned**修飾子は無効です、x86 プラットフォーム。

アラインメントの詳細については、次のトピックを参照してください。

- [align](../cpp/align-cpp.md)

- [__alignof 演算子](../cpp/alignof-operator.md)

- [pack](../preprocessor/pack.md)

- [/Zp (構造体メンバーの配置)](../build/reference/zp-struct-member-alignment.md)

- [構造体の配置例](../build/examples-of-structure-alignment.md)

## <a name="see-also"></a>関連項目

[キーワード](../cpp/keywords-cpp.md)