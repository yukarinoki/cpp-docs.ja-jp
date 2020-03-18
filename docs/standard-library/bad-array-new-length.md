---
title: bad_array_new_length クラス
ms.date: 11/04/2016
f1_keywords:
- new/std::bad_array_new_length
helpviewer_keywords:
- bad_alloc class
ms.assetid: 6429a8e6-5a49-4907-8d56-f4a4ec8131d0
ms.openlocfilehash: c4f4f58f7b28960bbacf695a675fbe4f20a54192
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79443706"
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

## <a name="remarks"></a>コメント

`what` によって返される値は、実装定義の C 文字列です。 このメンバー関数は、いずれも例外をスローしません。

## <a name="requirements"></a>要件

**ヘッダー:** \<新しい >

## <a name="see-also"></a>参照

[例外クラス](../standard-library/exception-class.md)\
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
