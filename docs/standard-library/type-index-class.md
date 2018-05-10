---
title: type_index クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- typeindex/std::type_index
dev_langs:
- C++
helpviewer_keywords:
- type_index class
ms.assetid: db366119-74cb-43e8-aacf-9679e561fa2f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e301b8d47c1a054a5b80bff105950d876d90b047
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
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
