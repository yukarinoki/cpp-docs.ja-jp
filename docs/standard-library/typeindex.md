---
description: '詳細情報: &lt; typeindex>&gt;'
title: '&lt;typeindex&gt;'
ms.date: 11/04/2016
f1_keywords:
- <typeindex>
ms.assetid: a9551137-f74b-4f02-af64-ff00214cea1f
ms.openlocfilehash: 0f5aee958aee01bcccc87145087001f093ab6749
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226442"
---
# <a name="lttypeindexgt"></a>&lt;typeindex&gt;

\<typeindex>クラス[type_info](../cpp/type-info-class.md)のオブジェクトのインデックス作成をサポートするクラスと関数を定義するには、標準ヘッダーを含めます。

## <a name="syntax"></a>構文

```cpp
#include <typeindex>
```

## <a name="remarks"></a>解説

インデックス値の分布への [type_index](../standard-library/type-index-class.md) 型の値のマッピングに適した `hash function` は、[hash 構造体](../standard-library/hash-structure.md)で定義します。

`type_index` クラスは、インデックス作成をしやすくするために `type_info` オブジェクトへのポインターをラップするものです。

## <a name="see-also"></a>関連項目

[ヘッダーファイルのリファレンス](../standard-library/cpp-standard-library-header-files.md)\
[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ 標準ライブラリリファレンス](../standard-library/cpp-standard-library-reference.md)
