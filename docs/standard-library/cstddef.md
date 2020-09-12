---
title: '&lt;cstddef&gt;'
description: Stddef.h> について説明 <します。これにより、C 標準ライブラリヘッダーの外部リンケージを使用して宣言された名前が名前空間で宣言されるようになります `std` 。
ms.date: 9/4/2020
f1_keywords:
- <cstddef>
helpviewer_keywords:
- cstddef header
ms.assetid: be8d1e39-5974-41ee-b41d-eafa6c82ffce
ms.openlocfilehash: 186de0e893c413a25d31d4f1431c280d749e9541
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2020
ms.locfileid: "90040029"
---
# <a name="ltcstddefgt"></a>&lt;cstddef&gt;

C 標準ライブラリヘッダーをインクルード \<stddef.h> し、関連する名前を `std` 名前空間に追加します。 このヘッダーをインクルードすると、C 標準ライブラリヘッダーの外部リンケージを使用して宣言された名前が、名前空間で宣言され `std` ます。

> [!NOTE]
> \<cstddef> に型 **バイト** が含まれていますが、型が含まれていません **`wchar_t`** 。

## <a name="syntax"></a>構文

```cpp
#include <cstddef>
```

## <a name="namespace-and-macros"></a>名前空間とマクロ

```cpp
namespace std {
    using ptrdiff_t = see definition;
    using size_t = see definition;
    using max_align_t = see definition;
    using nullptr_t = decltype(nullptr);
}

#define NULL  // an implementation-defined null pointer constant
#define offsetof(type, member-designator)
```

### <a name="parameters"></a>パラメーター

*ptrdiff_t*\
配列オブジェクトの2つの添字の差を保持できる、実装定義の符号付き整数型。

*size_t*\
任意のオブジェクトのサイズ (バイト単位) を格納するのに十分な大きさの実装定義の符号なし整数型。

*max_align_t*\
すべてのスカラー型のアラインメント要件が少なくとも優れており、すべてのコンテキストでアラインメント要件がサポートされている POD 型。

*nullptr_t*\
式の型のシノニム **`nullptr`** 。 アドレスを **`nullptr`** 取得することはできませんが、左辺値である別の *nullptr_t* オブジェクトのアドレスを取得できます。

## <a name="byte-class"></a>byte クラス

```cpp
enum class byte : unsigned char {};

template <class IntType>
    constexpr byte& operator<<=(byte& b, IntType shift) noexcept;
    constexpr byte operator<<(byte b, IntType shift) noexcept;
    constexpr byte& operator>>=(byte& b, IntType shift) noexcept;
    constexpr byte operator>>(byte b, IntType shift) noexcept;

constexpr byte& operator|=(byte& left, byte right) noexcept;
constexpr byte operator|(byte left, byte right) noexcept;
constexpr byte& operator&=(byte& left, byte right) noexcept;
constexpr byte operator&(byte left, byte right) noexcept;
constexpr byte& operator^=(byte& left, byte right) noexcept;
constexpr byte operator^(byte left, byte right) noexcept;
constexpr byte operator~(byte b) noexcept;

template <class IntType>
    IntType to_integer(byte b) noexcept;
```

## <a name="see-also"></a>参照

[ヘッダーファイルのリファレンス](../standard-library/cpp-standard-library-header-files.md)\
[C++ 標準ライブラリの概要](../standard-library/cpp-standard-library-overview.md)\
[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
