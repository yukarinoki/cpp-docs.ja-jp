---
description: '詳細情報: &lt; span &gt; 関数'
title: '&lt;スパン &gt; 関数'
ms.date: 05/28/2020
f1_keywords:
- span/std::span::as_bytes
- span/std::as_writable_bytes
helpviewer_keywords:
- std::span [C++], as_writable_bytes
- std::as_bytes [C++]
ms.openlocfilehash: 09d712d6dfffee2aa24e0e8cecca4031a27923f5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97169191"
---
# <a name="ltspangt-functions"></a>&lt;スパン &gt; 関数

ヘッダーには、 \<span> **span** オブジェクトを操作する次の非メンバー関数が含まれています。

| **非メンバー関数** | **説明** |
|-|-|
|[as_bytes](#as_bytes) | スパン内の要素のオブジェクト表現の読み取り専用ビューを取得します。 |
|[as_writable_bytes](#as_writable_bytes) | スパン内の要素のオブジェクト表現の読み取り/書き込みビューを取得します。 |

## <a name="as_bytes"></a>`as_bytes`

スパン内の要素のオブジェクト表現の読み取り専用ビューを取得します。

```cpp
template <class T, size_t Extent>
auto as_bytes(span<T, Extent> s) noexcept;
```

### <a name="parameters"></a>パラメーター

*\T*\
スパン内の要素の型。

*エクステント*\
スパン内の要素の数 (コンパイル時にわかっている場合)。それ以外の場合は、 `dynamic_extent` 要素の数がランタイムまで認識されないことを示します。

*2$s*\
生の表現を取得するスパン。

### <a name="return-value"></a>戻り値

`span<const byte, S>`スパンに格納されている最初の項目への ( `S` は)`{reinterpret_cast<const std::byte*>(s.data()), s.size_bytes()}`

### <a name="example"></a>例

```cpp
#include <span>
#include <iostream>

using namespace std;

void main()
{
    int a[] = { 0,1,2 };
    span <int> mySpan(a);
    auto bytes = std::as_bytes(mySpan);
}
```

## <a name="as_writable_bytes"></a>`as_writable_bytes`

がでない場合は `T` **`const`** 、スパン内の要素の生バイト表現の読み取り/書き込みビューを取得します。

```cpp
template <class T, size_t Extent>
auto as_writable_bytes(span<T, Extent> s) noexcept;
```

### <a name="parameters"></a>パラメーター

*\T*\
スパン内の要素の型。

*エクステント*\
スパン内の要素の数 (コンパイル時にわかっている場合)。それ以外の場合は、 `dynamic_extent` 要素の数がランタイムまで認識されないことを示します。

*2$s*\
生の表現を取得するスパン。

### <a name="return-value"></a>戻り値

`span<byte, S>`スパンに格納されている最初の項目への ( `S` は)`{reinterpret_cast<std::byte*>(s.data()), s.size_bytes()}`

### <a name="example"></a>例

```cpp
#include <span>
#include <iostream>

using namespace std;

void main()
{
    int a[] = { 0,1,2 };
    span <int> mySpan(a);
    auto bytes = as_writable_bytes(mySpan);
}
```

## <a name="see-also"></a>関連項目

[\<span>](span.md)
