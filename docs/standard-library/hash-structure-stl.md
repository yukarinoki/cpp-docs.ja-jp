---
description: '詳細情報: hash 構造体 (C++ 標準ライブラリ)'
title: hash 構造体 (C++ 標準ライブラリ) | Microsoft Docs
ms.date: 11/04/2016
f1_keywords:
- thread/std::hash
ms.assetid: 4a8bf5bc-4334-4070-936b-98585f8a073b
ms.openlocfilehash: 095566b6855c837c3ee6049a5cbedfbb087420bb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324069"
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

## <a name="requirements"></a>必要条件

**ヘッダー:**\<thread>

**名前空間:** std

## <a name="see-also"></a>関連項目

[ヘッダーファイルのリファレンス](../standard-library/cpp-standard-library-header-files.md)\
[\<thread>](../standard-library/thread.md)\
[unary_function 構造体](../standard-library/unary-function-struct.md)
