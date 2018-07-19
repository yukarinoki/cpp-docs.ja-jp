---
title: hash 構造体 (C++ 標準ライブラリ) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- thread/std::hash
dev_langs:
- C++
ms.assetid: 4a8bf5bc-4334-4070-936b-98585f8a073b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6f2e9fdbef911a0160ff42925a9c7984f0211069
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33843224"
---
# <a name="hash-structure-c-standard-library"></a>hash 構造体 (C++ 標準ライブラリ)

`Val` によって一意に決定される値を返すメンバー関数を定義します。 メンバー関数は、`thread::id` 型の値をインデックス値の分布にマッピングするために適した[ハッシュ](../standard-library/hash-class.md)関数を定義します。

## <a name="syntax"></a>構文

```cpp
template <>
struct hash<thread::id> :
    public unary_function<thread::id, size_t>
{
    size_t operator()(thread::id Val) const;


};
```

## <a name="requirements"></a>要件

**ヘッダー:** \<スレッド >

**名前空間:** std

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<thread>](../standard-library/thread.md)<br/>
[unary_function 構造体](../standard-library/unary-function-struct.md)<br/>
