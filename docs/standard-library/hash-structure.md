---
title: hash 構造体
ms.date: 11/04/2016
f1_keywords:
- typeindex/std::hash
ms.assetid: e5a41202-ef3b-45d0-b3a7-4c2dbdc0487a
ms.openlocfilehash: ba05d70692b2f85c1a14f319fb1e92dcadc0ccce
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50582261"
---
# <a name="hash-structure"></a>hash 構造体

テンプレート クラスは `val.hash_code()` を返すようにメソッドを定義します。 メソッドは、ハッシュ関数を定義します。これは [type_index](../standard-library/type-index-class.md) 型の値をインデックス値の分布にマッピングするために使用されます。

## <a name="syntax"></a>構文

```cpp
template <>
struct hash<type_index>
: public unary_function<type_index, size_t>
{ // hashes a typeinfo object
    size_t operator()(type_index val) const;

};
```

## <a name="see-also"></a>関連項目

[\<typeindex>](../standard-library/typeindex.md)<br/>
