---
title: '&lt;typeindex&gt;'
ms.date: 11/04/2016
f1_keywords:
- <typeindex>
ms.assetid: a9551137-f74b-4f02-af64-ff00214cea1f
ms.openlocfilehash: e22ce63c01185112ed512217156470e6f2948cd5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62278918"
---
# <a name="lttypeindexgt"></a>&lt;typeindex&gt;

[type_info](../cpp/type-info-class.md) クラスのオブジェクトのインデックス作成をサポートするクラスや関数を定義するには、標準ヘッダー \<typeindex> をインクルードします。

## <a name="syntax"></a>構文

```cpp
#include <typeindex>
```

## <a name="remarks"></a>Remarks

インデックス値の分布への [type_index](../standard-library/type-index-class.md) 型の値のマッピングに適した `hash function` は、[hash 構造体](../standard-library/hash-structure.md)で定義します。

`type_index` クラスは、インデックス作成をしやすくするために `type_info` オブジェクトへのポインターをラップするものです。

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)<br/>
