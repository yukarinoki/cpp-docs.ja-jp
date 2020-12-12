---
description: '詳細情報: &lt; cwctype&gt;'
title: '&lt;cwctype&gt;'
ms.date: 11/04/2016
f1_keywords:
- <cwctype>
helpviewer_keywords:
- cwctype header
ms.assetid: 46476f95-b8c3-4ab2-a172-9a1be91124b7
ms.openlocfilehash: 604cffe5acb61a90fc36e7733db01f2f92aa6155
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324615"
---
# <a name="ltcwctypegt"></a>&lt;cwctype&gt;

標準 C ライブラリヘッダーをインクルード \<wctype.h> し、関連する名前を名前空間に追加し `std` ます。

## <a name="syntax"></a>構文

```cpp
#include <cwctype>
```

## <a name="remarks"></a>解説

このヘッダーをインクルードすると、標準 C ライブラリ ヘッダーの外部リンケージで宣言された名前が、`std` 名前空間でも宣言されます。

## <a name="constants"></a>定数

```cpp
namespace std {
    using wint_t = see below ;
    using wctrans_t = see below ;
    using wctype_t = see below ;
}

#define WEOF see below
```

## <a name="functions"></a>関数

```cpp
int iswalnum(wint_t wc);
int iswalpha(wint_t wc);
int iswblank(wint_t wc);
int iswcntrl(wint_t wc);
int iswdigit(wint_t wc);
int iswgraph(wint_t wc);
int iswlower(wint_t wc);
int iswprint(wint_t wc);
int iswpunct(wint_t wc);
int iswspace(wint_t wc);
int iswupper(wint_t wc);
int iswxdigit(wint_t wc);
int iswctype(wint_t wc, wctype_t desc);
wctype_t wctype(const char* property);
wint_t towlower(wint_t wc);
wint_t towupper(wint_t wc);
wint_t towctrans(wint_t wc, wctrans_t desc);
wctrans_t wctrans(const char* property);
```

## <a name="see-also"></a>関連項目

[ヘッダーファイルのリファレンス](../standard-library/cpp-standard-library-header-files.md)\
[C++ 標準ライブラリの概要](../standard-library/cpp-standard-library-overview.md)\
[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
