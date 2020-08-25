---
title: nested_exception クラス
ms.date: 11/04/2016
f1_keywords:
- exception/std::nested_exception
helpviewer_keywords:
- nested_exception class
ms.assetid: 5ae2c4ef-c7ad-4469-8a9e-a773e86bb000
ms.openlocfilehash: 4ab48f714e8b4de1a47674f1af8fe25467279f94
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88836440"
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

|名前|説明|
|-|-|
|[operator =](#op_as)|代入演算子。|

### <a name="functions"></a>Functions

|名前|説明|
|-|-|
|[rethrow_nested](#rethrow_nested)|格納されている例外をスローします。|
|[nested_ptr](#nested_ptr)|格納されている例外を返します。|

### <a name="operator"></a><a name="op_as"></a> operator =

```cpp
nested_exception& operator=(const nested_exception&) = default;
```

### <a name="nested_ptr"></a><a name="nested_ptr"></a> nested_ptr

```cpp
exception_ptr nested_ptr() const;
```

#### <a name="return-value"></a>戻り値

このオブジェクトによってキャプチャされた格納された例外 `nested_exception` 。

### <a name="rethrow_nested"></a><a name="rethrow_nested"></a> rethrow_nested

```cpp
[[noreturn]] void rethrow_nested() const;
```

#### <a name="remarks"></a>解説

が `nested_ptr()` null ポインターを返す場合、関数はを呼び出し `std::terminate()` ます。 それ以外の場合は、によってキャプチャされた格納済みの例外をスローし **`*this`** ます。

## <a name="requirements"></a>必要条件

**ヘッダー:**\<exception>

**名前空間:** std

## <a name="see-also"></a>関連項目

[exception クラス](../standard-library/exception-class.md)\
[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
