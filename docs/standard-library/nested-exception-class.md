---
title: nested_exception クラス
ms.date: 11/04/2016
f1_keywords:
- exception/std::bad_exception
helpviewer_keywords:
- bad_exception class
ms.assetid: 5ae2c4ef-c7ad-4469-8a9e-a773e86bb000
ms.openlocfilehash: a568a8d9a3817883656406d63c3dd948539bb385
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2019
ms.locfileid: "68268524"
---
# <a name="nestedexception-class"></a>nested_exception クラス

このクラスは、多重継承で使用するため、例外を表します。 現在処理されている例外をキャプチャし、後で使用するため保存します。

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

### <a name="op_as"></a> 演算子 =

```cpp
nested_exception& operator=(const nested_exception&) = default;
```

### <a name="nested_ptr"></a> nested_ptr

```cpp
exception_ptr nested_ptr() const;
```

#### <a name="return-value"></a>戻り値

これによってキャプチャされた、格納されている例外`nested_exception`オブジェクト。

### <a name="rethrow_nested"></a> rethrow_nested

```cpp
[[noreturn]] void rethrow_nested() const;
```

#### <a name="remarks"></a>Remarks

場合`nested_ptr()`、関数は null ポインターを返します`std::terminate()`します。 によってキャプチャされた、格納されている例外をスローしますそれ以外の場合、`*this`します。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<exception>

**名前空間:** std

## <a name="see-also"></a>関連項目

[exception クラス](../standard-library/exception-class.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
