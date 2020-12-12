---
description: '詳細情報: bad_array_new_length クラス'
title: bad_array_new_length クラス
ms.date: 11/04/2016
f1_keywords:
- new/std::bad_array_new_length
helpviewer_keywords:
- bad_alloc class
ms.assetid: 6429a8e6-5a49-4907-8d56-f4a4ec8131d0
ms.openlocfilehash: e9de10b6fee215651ac8ff6ce2fce4af55ce6c82
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321641"
---
# <a name="bad_array_new_length-class"></a>bad_array_new_length クラス

クラスは、配列のサイズが0未満であるか、または制限を超えたために割り当て要求が成功しなかったことを示すためにスローされる例外を表します。

## <a name="syntax"></a>構文

```cpp
class bad_array_new_length : public bad_alloc {
    public: bad_array_new_length() noexcept;
    const char* what() const noexcept override;
};
```

## <a name="remarks"></a>解説

によって返される値 `what` は、実装定義の C 文字列です。 このメンバー関数は、いずれも例外をスローしません。

## <a name="requirements"></a>要件

**ヘッダー:**\<new>

## <a name="see-also"></a>関連項目

[exception クラス](../standard-library/exception-class.md)\
[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
