---
description: '詳細情報: type_index クラス'
title: type_index クラス
ms.date: 11/04/2016
f1_keywords:
- typeindex/std::type_index
helpviewer_keywords:
- type_index class
ms.assetid: db366119-74cb-43e8-aacf-9679e561fa2f
ms.openlocfilehash: 4e9156420811d2712a5b9331d0ece0e7847103e9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142689"
---
# <a name="type_index-class"></a>type_index クラス

`type_index` クラスは、[type_info クラス](../cpp/type-info-class.md)へのポインターをラップして、このクラスのオブジェクトでインデックスを作成しやすくします。

クラス type_index {public: type_index (const type_info& tinfo); const char * name () const; size_t hash_code () const; bool operator = = (const type_info& right) const; bool operator! = (const type_info& right) const; bool 演算子< (const type_info& right) const; bool operator \<=(const type_info& right) const;
   bool operator> (const type_info& right) const; bool operator>= (const type_info& right) const;};

このコンストラクターは、`ptr` を `&tinfo`に初期化します。

`name` は `ptr->name()` を返します。

`hash_code` は `ptr->hash_code().` を返します。

`operator==` は、`*ptr == right.ptr` を返します。

`operator!=` は、`!(*this == right)` を返します。

`operator<` は `*ptr->before(*right.ptr)` を返します。

`operator<=` は `!(right < *this).` を返します。

`operator>` は、`right < *this` を返します。

`operator>=` は、`!(*this < right)` を返します。

## <a name="see-also"></a>関連項目

[実行時の型情報](../cpp/run-time-type-information.md)\
[\<typeindex>](../standard-library/typeindex.md)
