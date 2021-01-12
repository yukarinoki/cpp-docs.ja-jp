---
description: 詳細については、「ctime」を参照してください。 &lt;&gt;
title: '&lt;ctime&gt;'
ms.date: 11/04/2016
f1_keywords:
- <ctime>
helpviewer_keywords:
- ctime header
ms.assetid: c1f7d4a4-4bfe-4e35-92cb-f63dbd3c39a8
ms.openlocfilehash: 3ebf4849f990f7e0ae835fca88a6b38a8ca1838d
ms.sourcegitcommit: 118e4ad82c0f1c9ac120f105d84224e5fe4cef28
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "98126703"
---
# <a name="ltctimegt"></a>&lt;ctime&gt;

標準 C ライブラリヘッダーをインクルード \<time.h> し、関連する名前を名前空間に追加し `std` ます。

## <a name="syntax"></a>構文

```cpp
#include <ctime>
```

## <a name="remarks"></a>解説

このヘッダーをインクルードすると、標準 C ライブラリ ヘッダーの外部リンケージで宣言された名前が、`std` 名前空間でも宣言されます。

## <a name="constants"></a>定数

```cpp
#define NULL
#define CLOCKS_PER_SEC
#define TIME_UTC

namespace std {
    using size_t = see below;
    using clock_t = see below ;
    using time_t = see below ;
}
```

## <a name="structures"></a>構造体

```cpp
struct timespec;
struct tm;
```

## <a name="functions"></a>関数

```cpp
clock_t clock();
double difftime(time_t time1, time_t time0);
time_t mktime(struct tm* timeptr);
time_t time(time_t* timer);
int timespec_get(timespec* ts, int base);
char* asctime(const struct tm* timeptr);
char* ctime(const time_t* timer);
struct tm* gmtime(const time_t* timer);
struct tm* localtime(const time_t* timer);
size_t strftime(char* s, size_t maxsize, const char* format, const struct tm* timeptr);
```

## <a name="see-also"></a>関連項目

[ヘッダーファイルのリファレンス](../standard-library/cpp-standard-library-header-files.md)\
[C++ 標準ライブラリの概要](../standard-library/cpp-standard-library-overview.md)\
[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
