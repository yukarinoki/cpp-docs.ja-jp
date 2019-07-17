---
title: '&lt;cstddef&gt;'
ms.date: 11/04/2016
f1_keywords:
- <cstddef>
helpviewer_keywords:
- cstddef header
ms.assetid: be8d1e39-5974-41ee-b41d-eafa6c82ffce
ms.openlocfilehash: 15d13a3af35cb41950df8aeba0c86d779e701ddb
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2019
ms.locfileid: "68244445"
---
# <a name="ltcstddefgt"></a>&lt;cstddef&gt;

C 標準ライブラリ ヘッダーをインクルード\<stddef.h > に関連する名前を追加し、`std`名前空間。 外部リンケージを使用して、C 標準ライブラリ ヘッダーで宣言された名前を宣言することにより、このヘッダーを含む、`std`名前空間。

> [!NOTE]
> \<cstddef > 型が含まれて**バイト**型が含まれていないと**wchar_t**します。

## <a name="syntax"></a>構文

```cpp
#include <cstddef>
```

## <a name="namespace-and-macros"></a>Namespace とマクロ

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
実装で定義する符号付き配列オブジェクトに添字が 2 つの違いを保持できる整数型。

*size_t*\
任意のオブジェクトのバイト単位のサイズを格納するのに十分な大きさである符号なし整数の実装で定義された型。

*max_align_t*\
POD 型のアラインメント要件は、少なくとも、すべてのスカラー型の場合と同程度に優れたとのアラインメント要件がすべてのコンテキストでサポートされています。

*nullptr_t*\
型のシノニム、 **nullptr**式。 ただし、 **nullptr**アドレスは取得できません、別のアドレス*nullptr_t*を左辺値であるオブジェクトを取得できます。

## <a name="byte-class"></a>バイト クラス

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

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 標準ライブラリの概要](../standard-library/cpp-standard-library-overview.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
