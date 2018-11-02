---
title: type_index クラス
ms.date: 11/04/2016
f1_keywords:
- typeindex/std::type_index
helpviewer_keywords:
- type_index class
ms.assetid: db366119-74cb-43e8-aacf-9679e561fa2f
ms.openlocfilehash: 8807a041ab1c6ef47a9c3c12dac2688f121f6cfa
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50650492"
---
# <a name="typeindex-class"></a>type_index クラス

`type_index` クラスは、[type_info クラス](../cpp/type-info-class.md)へのポインターをラップして、このクラスのオブジェクトでインデックスを作成しやすくします。

class type_index { public: type_index(const type_info& tinfo); const char *name() const; size_t hash_code() const; bool operator==(const type_info& right) const; bool operator!=(const type_info& right) const; bool operator<(const type_info& right) const; bool operator\<=(const type_info& right) const; bool operator>(const type_info& right) const; bool operator>=(const type_info& right) const; };

このコンストラクターは、`ptr` を `&tinfo`に初期化します。

`name` は、`ptr->name()` を返します。

`hash_code` の場合、`ptr->hash_code().` が返されます。

`operator==` は、`*ptr == right.ptr` を返します。

`operator!=` は、`!(*this == right)` を返します。

`operator<` は、`*ptr->before(*right.ptr)` を返します。

`operator<=` の場合、`!(right < *this).` が返されます。

`operator>` は、`right < *this` を返します。

`operator>=` は、`!(*this < right)` を返します。

## <a name="see-also"></a>関連項目

[ランタイム型情報](../cpp/run-time-type-information.md)<br/>
[\<typeindex>](../standard-library/typeindex.md)<br/>
