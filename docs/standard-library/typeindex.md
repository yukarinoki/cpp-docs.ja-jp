---
title: '&lt;typeindex&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <typeindex>
dev_langs:
- C++
ms.assetid: a9551137-f74b-4f02-af64-ff00214cea1f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 189fb7cd3757a3f71a50badc682b7b4db611b4e0
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33855111"
---
# <a name="lttypeindexgt"></a>&lt;typeindex&gt;

[type_info](../cpp/type-info-class.md) クラスのオブジェクトのインデックス作成をサポートするクラスや関数を定義するには、標準ヘッダー \<typeindex> をインクルードします。

## <a name="syntax"></a>構文

```cpp
#include <typeindex>
```

## <a name="remarks"></a>コメント

インデックス値の分布への [type_index](../standard-library/type-index-class.md) 型の値のマッピングに適した `hash function` は、[hash 構造体](../standard-library/hash-structure.md)で定義します。

`type_index` クラスは、インデックス作成をしやすくするために `type_info` オブジェクトへのポインターをラップするものです。

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)<br/>
