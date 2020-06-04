---
title: nested_exception クラス
ms.date: 11/04/2016
f1_keywords:
- exception/std::nested_exception
helpviewer_keywords:
- nested_exception class
ms.assetid: 5ae2c4ef-c7ad-4469-8a9e-a773e86bb000
ms.openlocfilehash: ed58eb6cc074b54ae6801d2b11089af9a79f8c8f
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79441618"
---
# <a name="nested_exception-class"></a>nested_exception クラス

クラスは、多重継承で使用する例外を記述します。 現在処理されている例外をキャプチャし、後で使用できるように格納します。

## <a name="syntax"></a>構文

```cpp
class nested_exception {
    public:
        nested_exception();
        nested_exception(const nested_exception&) = default;
        virtual ~nested_exception() = default; // access functions
};
```

## <a name="members"></a>メンバー

### <a name="operators"></a>演算子

|||
|-|-|
|[operator=](#op_as)||

### <a name="functions"></a>関数

|||
|-|-|
|[rethrow_nested](#rethrow_nested)|格納されている例外をスローします。|
|[nested_ptr](#nested_ptr)|格納されている例外を返します。|

### <a name="op_as"></a>operator =

```cpp
nested_exception& operator=(const nested_exception&) = default;
```

### <a name="nested_ptr"></a>nested_ptr

```cpp
exception_ptr nested_ptr() const;
```

#### <a name="return-value"></a>戻り値

この `nested_exception` オブジェクトによってキャプチャされた、格納されている例外。

### <a name="rethrow_nested"></a>rethrow_nested

```cpp
[[noreturn]] void rethrow_nested() const;
```

#### <a name="remarks"></a>コメント

`nested_ptr()` が null ポインターを返す場合、関数は `std::terminate()`を呼び出します。 それ以外の場合は、`*this`によってキャプチャされた格納済みの例外をスローします。

## <a name="requirements"></a>要件

**ヘッダー:** \<例外 >

**名前空間:** std

## <a name="see-also"></a>参照

[例外クラス](../standard-library/exception-class.md)\
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
